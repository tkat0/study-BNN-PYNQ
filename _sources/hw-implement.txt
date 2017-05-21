
ハードウェア実装
===============

実装の特長
---------

* 静的、固定長な実装
    * 定数（constや定数のテンプレート）を使い、関数内のループなど全て固定サイズ
        * 高位合成のテクニック
        * Vivado 2017.1では可変ループ最適化が対応したらしいので、このような工夫をしなくても最適化される？？
* テンプレートによる汎用化
    * 各レイヤーに特化した、静的な関数を効率よく実装する仕組み
    * MVTUの関数定義は1箇所だが、テンプレートの変数を変えることでコンパイル時に静的な関数を複数生成できる
* pragmaによる最適化
    * ループの並列化や、C/C++上の配列をFPGAのどのリソースにあてるかなど指定
    * （使われているpragmaと説明をあとでまとめる）
* Hardware Library
    * BNNのアクセラレータの共通部品は、Hardware Libraryとして独立している
    * LFC, CNVともに、Hardware Libraryを使ってモデルを記述する（高位合成ターゲットとなるTop関数だけ記述）
    * ファイルは、 ``bnn/src/hls`` 以下


.. * 任意精度型
..     * 任意精度型で、SIMD幅bitの型を定義して演算している
.. I   * 1bit型の8要素配列か、8bit型の1変数、の違い？実装上の扱いやすさ？

Hardware Library概要
--------------------

Hardware Libraryのファイル名と、その簡単な説明。

* ファイルは、 ``bnn/src/hls`` 以下

* streamtools.h
    * streamのBit幅変換APIなど
* dma.h
    * メモリ上の配列データとAXI4-Streamの相互変換API
* matrixvector.h
    * MVTUの実装
* fclayer.h
    * Fully Connectedレイヤー
    * 行列演算そのものはMVTUがおこなう
    * MVTUの入出力を前後のレイヤーに合わせてbit幅変換する
* convlayer.h
    * Convolution Layerの実装
    * slidingwindow.hで入力ストリームを変換し、MVTUへ入力する
* maxpool.h
    * MAX Poolingの実装
    * 入力を内部バッファにためて、そこでMax値を計算
    * 二値の最大値は、OR演算で得られる(0,1どちらかあれば1が最大なので)
* slidingwindow.h
    * Convolutionを行列積で計算する（=MVTUで扱う）ために、入力画像を変換する
