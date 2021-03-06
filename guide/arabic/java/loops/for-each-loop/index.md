---
title: For Each Loop
localeTitle: لكل حلقة
---
# لكل حلقة

كما دعا إلى تعزيز `for` حلقة، فإنه هو وسيلة مفيدة للغاية وبسيطة لتكرار عبر كل عنصر في مجموعة، مجموعة أو أي كائن التي تطبق `Iterable` اجهة.

 `for (object : iterable) 
 { 
    // Statements 
 } 
` 

تتم قراءة الحلقة كـ "لكل عنصر في `iterable` (يمكن أن يكون صفيفًا أو قابل للتحصيل وما إلى ذلك)". يجب أن يتطابق نوع `object` مع نوع عنصر `iterable` .

 `int[] number_list = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}; 
 
 for (int numbers : number_list) 
 { 
    System.out.print(numbers + " "); 
    // Iterated 10 times, numbers 0,1,2...9 
 } 
` 

انتاج:

 `    0 1 2 3 4 5 6 7 8 9 
` 

: صاروخ: [تشغيل التعليمات البرمجية](https://repl.it/CJYs/0)

وبمقارنة هذا مع التقليدية `for` حلقات:

 `int[] number_list = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}; 
 
 for(int i=0;i < number_list.length;i++) 
 { 
  System.out.print(number_list[i]+" "); 
      // Iterated 10 times, numbers 0,1,2...9 
 
 } 
` 

انتاج:

 `    0 1 2 3 4 5 6 7 8 9 
` 

: صاروخ: [تشغيل التعليمات البرمجية](https://repl.it/NJfG/0)

كلا القطع المذكورة أعلاه من مقتطفات الشفرة تقوم بنفس العمل ، ولكن من الواضح أن كل حلقة تقدم مزايا في جعل التكرار من خلال عناصر مجموعة (صفيف ، في حالتنا) أسهل.

مع الحلقات المحسّنة ، لم نعد بحاجة إلى الإشارة إلى نقاط البداية والنهاية للحلقة ، وبالتالي تقليل أخطاء OutofBounds. تتم إزالة الحاجة إلى عدادات الحلقة والفهرسة اليدوية ، وتحسين قراءة التعليمات البرمجية.

من المهم ملاحظة أن إجراء تغييرات على متغير المتكرّرة لتعزيز الحلقات داخل الحلقة لا يؤدي إلى تغييرات في عناصر المجموعة الأصلية.

يمكن أيضًا استخدام المحسن للحلقات مع المصفوفات متعددة الأبعاد أو مجموعات جافا الأخرى. ويرد مثال على استخدامه مع صفائف متعددة الطوابق أدناه:

 `int number_list_new[][]={  {  0,  1, 2}, 
                  {  3, 4, 5}, 
                  { 6, 7, 8} }; 
 
 // Because 2d arrays are implemented as "arrays of arrays",the first iteration variable iterates 
 // through 3 such arrays(that is, the 3 rows of testarr[][]) 
 for(int i[] : number_list_new) 
 { 
  for(int j : i){ 
    System.out.print(j+" "); 
  } 
 } 
` 

انتاج:

 `0 1 2 3 4 5 6 7 8 
` 

: صاروخ: [تشغيل التعليمات البرمجية](https://repl.it/NJhP/0)

في المقتطفات البرمجية الواردة أعلاه ، `number_list` عبارة عن مصفوفة. إذا كنت لا تعرف ما هو هذا ، فلا تقلق بشأنه. المصفوفة هي كائن حاوية يحمل عددًا ثابتًا من القيم من نوع واحد ، ولكن أكثر على هذا لاحقًا.