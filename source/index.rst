.. study-BNN-PYNQ documentation master file, created by
   sphinx-quickstart on Wed May  3 18:34:55 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. source: https://github.com/tkat0/study-BNN-PYNQ

study-BNN-PYNQ
========================================

BNN-PYNQについて調べた内容をまとめます。

主な読み手として、ハードウェアや高位合成に詳しくない、ソフトウェア側の方を意識しています。

* BNN-PYNQは、ホビーFPGAボード"PYNQ(ピンク)"で動作するNeuralNetworkのシステムです
* DeepLearningのアルゴリズムをFPGAで動かすことを学ぶには良い素材です
    * 論文が公開
    * Pythonのアプリケーション層、Cのドライバ、高位合成用の実装が公開
    * 学習コードの一部が公開

.. SNS連携
.. raw:: html

   <div class="social-buttons">
       <div class="social-button-item">
           <a href="https://twitter.com/share" class="twitter-share-button" data-url="https://tkat0.github.io/doc-BNN-PYNQ/" data-via="_tkato_">Tweet</a> <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+'://platform.twitter.com/widgets.js';fjs.parentNode.insertBefore(js,fjs);}}(document, 'script', 'twitter-wjs');</script>
       </div>
       <div class="social-button-item">
           <a href="http://b.hatena.ne.jp/entry/" class="hatena-bookmark-button" data-hatena-bookmark-layout="basic-counter" title="このエントリーをはてなブックマークに追加"><img src="https://b.st-hatena.com/images/entry-button/button-only@2x.png" alt="このエントリーをはてなブックマークに追加" width="20" height="20" style="border: none;" /></a><script type="text/javascript" src="https://b.st-hatena.com/js/bookmark_button.js" charset="utf-8" async="async"></script>
       </div>
       <div class="social-button-item">
           <a data-pocket-label="pocket" data-pocket-count="horizontal" class="pocket-btn" data-lang="en"></a>
       <script type="text/javascript">!function(d,i){if(!d.getElementById(i)){var j=d.createElement("script");j.id=i;j.src="https://widgets.getpocket.com/v1/j/btn.js?v=1";var w=d.getElementById(i);d.body.appendChild(j);}}(document,"pocket-btn-js");</script>
       </div>
   </div><br>

.. note::
   BNN-PYNQのソースコードは5/2時点で最新のものを使いました。

   https://github.com/Xilinx/BNN-PYNQ/tree/a86e0863418ce4161ed61b69ba89ec1481014362

.. warning::
   現在、勉強を兼ねてこのページを作成している途中です。

   内容の間違い、ご意見等はGitHubのissueやTwitter等で教えて頂けると助かります。

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   faq
   soft-overview
   tree
   hw
   hw-implement
   links

Author
------

tkato
    組み込みソフトエンジニアです。PythonやRubyが好きです。

* Twitter: https://twitter.com/_tkato_
* Blog: http://tkat0.hateblo.jp/
* GitHub: https://github.com/tkat0

Change log
-----------

* 2017/05/11
    * ハードウェア概要、ハードウェア実装を追加
    * ソフトウェアのシーケンスを追加
    * Todo追加
* 2017/05/04
    * ソフトウェア全体像を追加
    * ファイル構成を追加
* 2017/05/03
    * 新規作成(ブログ記事を元に作成)
    * FAQを追加

Todo
-----

今後書く予定の内容

* Binarized Neural Networkの説明
* LFC, CNVの構成、特長
* HW
    * レジスタマップ
    * MVTUのデータフロー詳細
    * FCとConvolutionでMVTUをどう使っているのか
    * MVTUのコンパイル時のパラメータの決め方
* 学習ツールや学習のシーケンス
    * モデルデータのバイナリフォーマット
    * 任意のデータで学習するには
    * 任意のモデルを構築して学習してみる

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

.. raw:: html

   <script>
   (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
   (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
   m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
   })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

   ga('create', 'UA-98471030-1', 'auto');
   ga('send', 'pageview');

   </script>


.. 図は `mermaid.js <http://knsv.github.io/mermaid/>`_ で作成
