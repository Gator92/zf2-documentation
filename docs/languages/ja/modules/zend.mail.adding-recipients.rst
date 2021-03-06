.. _zend.mail.adding-recipients:

受信者の追加
======

受信者を追加するには、次のようにします。

- ``addTo()``: メールの "To" ヘッダに受信者を追加します

- ``addCc()``: メールの "Cc" ヘッダに受信者を追加します

- ``addBcc()``: ヘッダに表示されない受信者をメールに追加します

``getRecipients()`` によりあて先一覧を取得します。 ``clearRecipients()``
によりあて先一覧を消去します。

.. note::

   **追加のパラメータ**

   ``addTo()`` および ``addCc()`` では、 2
   番目の引数として、人間が読みやすい形式のあて先を指定することができます。
   その引き数中の２重引用符は単一引用符に、山括弧は角括弧に変更されます。

.. note::

   **選択できる使用法**

   これらのメソッド３つは全て、１回につき一つの代わりに、
   追加する電子メール・アドレスの配列を受け取ることもできます。 ``addTo()`` 及び
   ``addCc()`` の場合、
   それらは、キーが人間が読み取れる受取人の名前である連想配列でありえます。


