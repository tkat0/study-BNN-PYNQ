ソフトウェア全体像
==================

BNN-PYNQのソフトウェアの構成を図にしてみました。

.. image:: ../image/software-overview.png
   :scale: 50%
   :align: center

* 青色の箱が、モデル毎に実装するモジュール
    * ソースは、 `bnn/src/network <https://github.com/Xilinx/BNN-PYNQ/tree/master/bnn/src/network>`_
* 緑色の箱は、FINN libraryと呼ばれており、モデルによらず共通
    * ソースは、 `bnn/src/library <https://github.com/Xilinx/BNN-PYNQ/tree/master/bnn/src/library>`_
    * hostは、上位からの呼び出しに対してSW/HWビルドの差異を吸収する
        * ビルド時の定数マクロで、関数を切り替えている
        * SWビルドのときは、高位合成対象のCの関数を直接呼ぶ
        * HWビルドのときは、driverを介してアクセラレータを制御する
    * driverは、アクセラレータ用のメモリ管理やレジスタ制御を行う
    * hlsは、高位合成時にインクルードされる共通ライブラリ

.. commented
   シーケンス
   ==========
   
   LFCで単一画像を推論する場合のシーケンスは以下のようになっています。

