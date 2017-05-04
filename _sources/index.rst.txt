.. study-BNN-PYNQ documentation master file, created by
   sphinx-quickstart on Wed May  3 18:34:55 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. source: https://github.com/tkat0/study-BNN-PYNQ

study-BNN-PYNQ
========================================

BNN-PYNQについて調べた内容をまとめます。

BNN-PYNQは、ホビーFPGAボード"PYNQ(ピンク)"で動作するNeuralNetworkのシステムです。

Pythonのアプリケーション層、Cのドライバ、高位合成用の実装まで、ほとんどのコードが公開されているためDeepLearningのアルゴリズムをFPGAで動かすことを学ぶには良い素材です。

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

.. toctree::
   :maxdepth: 1
   :caption: Contents:
   
   faq

資料
---------

* BNN-PYNQ
    * ソースコード: https://github.com/Xilinx/BNN-PYNQ
    * 論文: https://arxiv.org/abs/1612.07119

* PYNQ-Z1
    * プロジェクトページ http://www.pynq.io/
    * ドキュメント: http://pynq.readthedocs.io/en/latest/
    * ソースコード: https://github.com/Xilinx/PYNQ/

Author
------

tkato
    組み込みソフトエンジニアですが、PythonやRubyが好きです。

* Twitter: https://twitter.com/_tkato_
* Blog: http://tkat0.hateblo.jp/


内容に間違いがある場合等、Twitter等で教えて頂けると助かります。

Change log
-----------

* 2017/05/03
    * 新規作成
    * FAQを追加


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
