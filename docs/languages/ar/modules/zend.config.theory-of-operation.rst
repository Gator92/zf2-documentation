.. _zend.config.theory_of_operation:

نظرية العمل
===========

يتم تمرير بيانات الأعدادات إلى *Zend_Config* على شكل associative array و التى
من الممكن ان تكون متعددة الأبعاد, و من أجل دعم تنظيم البيانات من
الشكل العام إلى المحدد, تم توفير adapter classes أو "classes توفيقية"
وظيفتها توفيق البيانات المقرؤة من مصادر حفظ البيانات المتعددة
و تحويلها إلى associative array من أجل *Zend_Config*, و يمكن للمبرمج أن يوفر
هذه المصفوفة "array" مباشرة إلى *Zend_Config* بدون استخدام adapter class, و هذا
من الممكن ان يحدث فى بعض الحالات الخاصة.

يطبق *Zend_Config* كل من الـ interfaces المسمى *Countable* و *Iterator* ليوفر وسائل
سهلة للوصل إلى البيانات, حيث سيمكنك إستخدام دالة الـ PHP المسمى
`()count`_ أو إستخدام `foreach`_ على كائنات *Zend_Config*.

السلوك الطبيعى لـ *Zend_Config* يسمح بالقرائة فقط للبيانات , و عملية
تعديل لأحد قيم البيانات المحفوظة به مثل (*$config->database->host =
'example.com'*) يتسبب فى إلقاء exception , و يمكن تغيير هذا السلوك من خلال
الـ constuctor و ذلك للسماح بتعديل قيم البيانات.

   .. note::

      **لاحظ أن**

      تسمح *Zend_Config* بعمل تغييرات فى بيانات الـ configuration التى تم
      تحميلها الى الذاكرة , و لكنها لا توفر امكانية حفظ هذه
      البيانات فى اى من وسائط حفظ البيانات , الأدوات التى تقوم
      بإنشاء و تعديل بيانات الـ configuration و حفظها فى وسائط حفظ
      بيانات هى خارج نطاق Zend_Config , لكن يوجد العديد من الحلول مفتوحة
      المصدر لإنشاء و تعديل بيانات الـ configuration و حفظها فى وسائط
      حفظ بيانات مختلفة و يمكنك الأستعانة بأى منها.



الـ adapter classes يرثون من *Zend_Config* حيث أنهم فقط يعدلون على كيفية
أدائه.

عائلة *Zend_Config* توفر أمكانية أن تكون البيانات مرتبة فى أقسام
بيانات. و من الممكن أن يتم تحميل الـ adapter objects مع تحديد قسم
بيانات واحد, أو أكثر من قسم , أو كل الأقسام (إن لم يتم تحديد قسم).

توفر الـ adapter classes فى *Zend_Config* امكانية الوراثة الأحادية بين أقسام
البيانات , حيث يمكن أن يرث قسم بيانات من قسم بيانات أخر. هذا تم
توفيره للتقليل من الحاجة لتكرار بيانات الأعدادات فى الأقسام
لأسباب متعددة, و القسم الذى يرث من الممكن أن يغير القيم
الموروثة من القسم الأب, و الذى من الممكن أن يكون ورث من قسم جد
(أب الأب) و هكذا , لكن الوراثة المتعددة (مثل القسم C يرث مباشرة من
الأقسام A و B ) غير مدعومة.



.. _`()count`: http://php.net/count
.. _`foreach`: http://php.net/foreach
