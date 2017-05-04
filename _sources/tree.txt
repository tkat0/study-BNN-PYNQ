ファイル構成
============

リポジトリのファイル構成について。

リポジトリに対して ``tree`` を実行した結果に対してコメントしました（一部ファイルの省略あり）。

概要は、 `README <https://github.com/Xilinx/BNN-PYNQ#repo-organization>`_ にも記載があります。

.. code-block:: none

   .
   ├── CONTRIBUTING.md
   ├── LICENSE
   ├── MANIFEST.in
   ├── README.md
   ├── bnn
   │   ├── __init__.py
   │   ├── bitstreams アクセラレータのビットストリーム（ビルド済み）
   │   │   ├── cnv-pynq-pynq.bit
   │   │   ├── cnv-pynq-pynq.tcl
   │   │   ├── lfc-pynq-pynq.bit
   │   │   └── lfc-pynq-pynq.tcl
   │   ├── bnn.py  PythonのAPI
   │   ├── libraries アクセラレータのドライバ（ビルド済みライブラリ）
   │   │   ├── python_hw-cnv-pynq.so
   │   │   ├── python_hw-lfc-pynq.so
   │   │   ├── python_sw-cnv-pynq.so
   │   │   └── python_sw-lfc-pynq.so
   │   ├── params 学習済みモデルのパラメータ（BNN-PYNQ用のバイナリに変換済み）
   │   │   ├── cifar10
   │   │   ├── mnist
   │   │   ├── road-signs
   │   │   └── streetview
   │   └── src
   │       ├── library モデル共通のライブラリ
   │       │   ├── README.md
   │       │   ├── driver アクセラレータ用の低レベルドライバ（レジスタ制御）
   │       │   │   ├── donutdriver.hpp
   │       │   │   ├── platform-xlnk.cpp
   │       │   │   ├── platform.hpp
   │       │   │   └── xlnkdriver.hpp
   │       │   ├── hls 高位合成されるライブラリ
   │       │   │   ├── bnn-library.h
   │       │   │   ├── convlayer.h
   │       │   │   ├── dma.h
   │       │   │   ├── fclayer.h
   │       │   │   ├── matrixvector.h
   │       │   │   ├── maxpool.h
   │       │   │   ├── slidingwindow.h
   │       │   │   └── streamtools.h
   │       │   ├── host アクセラレータ用の高レベルドライバ（上位に対して、CPU版/HW版の差異をここで吸収）
   │       │   │   ├── foldedmv-offload.cpp
   │       │   │   ├── foldedmv-offload.h
   │       │   │   └── rawhls-offload.cpp
   │       │   └── script Vivado用のプロジェクト生成Tcl、ボード情報
   │       │       ├── PYNQ-Z1_C.xdc
   │       │       ├── make-vivado-proj.tcl
   │       │       └── pynq_revC.tcl
   │       ├── network 各モデルの実装
   │       │   ├── README.md
   │       │   ├── cnv-pynq
   │       │   │   ├── README.md
   │       │   │   ├── hw
   │       │   │   │   ├── config.h
   │       │   │   │   └── top.cpp  高位合成するTop関数の定義
   │       │   │   └── sw
   │       │   │       └── main_python.cpp Pythonに対するAPI
   │       │   ├── hls-syn.tcl 
   │       │   ├── lfc-pynq
   │       │   │   ├── README.md
   │       │   │   ├── hw
   │       │   │   │   ├── config.h
   │       │   │   │   └── top.cpp
   │       │   │   └── sw
   │       │   │       └── main_python.cpp
   │       │   ├── make-hw.sh Vivado HLSとVivadoをバッチ起動して、Cコードからビットストリームを生成する
   │       │   └── make-sw.sh g++でCのドライバ郡をビルドする（CPU版かHW版か切り替えれられる）
   │       └── training 学習スクリプト（PC用）
   │           ├── LICENSE
   │           ├── README.md
   │           ├── binary_net.py Theano用のBinaryレイヤーの定義
   │           ├── cifar10-gen-binary-weights.py Theanoの学習済みモデルをBNN-PYNQ用のバイナリに変換するスクリプト
   │           ├── cifar10.py cifar10の学習スクリプト
   │           ├── cnv.py CNVのモデル定義
   │           ├── finnthesizer.py 
   │           ├── lfc.py LFCのモデル定義
   │           ├── mnist-gen-binary-weights.py
   │           └── mnist.py
   ├── notebooks Jupyter Notebookのアプリケーション例
   │   ├── BNN-from-webcam.ipynb
   │   ├── Cifar10.ipynb
   │   ├── Road-Signs-Batch.ipynb
   │   ├── SVHN-cffi.ipynb
   │   ├── SVHN.ipynb
   ├── setup.py
   └── tests BNN-PYNQの簡単なテストコード
       ├── Test_image
       └── test.py
   
   26 directories, 915 files

