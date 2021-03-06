.. _zend.feed.findFeeds:

Получение лент из веб-страниц
=============================

Веб-страницы часто содержат теги *<link>*, которые ссылаются на
ленты с соответсвующим данной странице содержимым. *Zend_Feed* дает
возможность извлечь все ленты, на которые ссылается
веб-страница, всего одним вызовом метода:

.. code-block:: php
   :linenos:

   $feedArray = Zend_Feed::findFeeds('http://www.example.com/news.html');


Здесь метод *findFeeds()* возвращает массив объектов лент
*Zend_Feed_Abstract*, на которые ссылались теги *<link>* в коде веб-страницы
*news.html*. В зависимости от типа ленты, каждый элемент массива
``$feedArray`` может быть экземпляром *Zend_Feed_Rss* или *Zend_Feed_Atom*. *Zend_Feed*
будет генерировать исключение *Zend_Feed_Exception* в случае ошибки,
такой, как возврат HTTP-кода 404 или плохо сформированная лента.


