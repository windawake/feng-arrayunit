# 把数组转化成拥有数组特性的对象

	composer require feng/arrayunit dev-master

案例代码

```php
require 'vendor/autoload.php';
 //数组转为对象[数组]集合类
 $arr = [
     'lesson'  => [
         'one' => 'english',
         'two' => 'chinese',
     ],
     'teacher' => [
         'one'   => 'zhang',
         'two'   => 'chen',
         'three' => 'huang',
     ],
 ];

 $std = new Feng\Arrayunit\Collection($arr);
 var_dump($std->lesson->one);
 var_dump($std->teacher->toArray());
 //新增属性赋值
 $std->lesson->three = 'math';
 var_dump($std->lesson->four);
 var_dump($std['lesson']);
 //混合对象和数组
 var_dump($std->lesson['one']);
 //测试循环
 foreach ($std as $item) {
     var_dump(count($item));
     var_dump($item->toArray());
     var_dump($item->one);
     var_dump($item->three);
 }
```
