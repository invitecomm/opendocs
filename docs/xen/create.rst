#########
XenCenter
#########

============================
Creating MCAT Virtual Server
============================

.. image:: ../images/mcat/xenserver_001.png
    :scale: 50 %
    
* インフラストラクチャ欄 テンプレート> 右クリック > 新規VMウィザード


.. image:: ../images/mcat/xenserver_002.png
    :scale: 50 %
    
.. image:: ../images/mcat/xenserver_003.png
    :scale: 50 %

* テンプレート MCAT 0.2.2.D (最新のスナップショット)を選択したまま 次へ

    
.. image:: ../images/mcat/xenserver_004.png
    :scale: 50 %
    
* 名前 大文字で 説明 いれる

    
.. image:: ../images/mcat/xenserver_005.png
    :scale: 50 %

* インストールメディア なし 次へ

    
.. image:: ../images/mcat/xenserver_006.png
    :scale: 50 %

* ホームサーバー 指定しない
    
.. image:: ../images/mcat/xenserver_007.png
    :scale: 50 %

* CPUとメモリ 2 2S1C 512MB/1024MB 次へ
    
.. image:: ../images/mcat/xenserver_008.png
    :scale: 50 %

* GPU 次へ
    
.. image:: ../images/mcat/xenserver_009.png
    :scale: 50 %

* ストレージ CloudByte ``CB`` 次へ

.. image:: ../images/mcat/xenserver_010.png
    :scale: 50 %
    
.. image:: ../images/mcat/xenserver_011.png
    :scale: 50 %
    
* ネットワーク eth2 を足す VLAN調整 OpenSwan等 次へ

.. image:: ../images/mcat/xenserver_012.png
    :scale: 50 %
    
.. image:: ../images/mcat/xenserver_013.png
    :scale: 50 %
    
.. image:: ../images/mcat/xenserver_014.png
    :scale: 50 %
    
.. image:: ../images/mcat/xenserver_015.png
    :scale: 50 %
    
自動的に起動しない（チェックボックスをオフにする）
*あなたが調整したい場合はオプションです。*
    
.. image:: ../images/mcat/xenserver_016.png
    :scale: 50 %
    
* 完了 作成

* サーチして、右クリック VMのコピー 名前変更 コピーモードを完全コピーを選択しクラウドバイトに コピー
