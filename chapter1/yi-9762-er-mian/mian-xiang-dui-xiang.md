![](/assets/import61.png)

```js
<script>
        //类的声明
        var Animal = function () {
            this.name="Parent";
        };

        class Animal2 {
            constructor () {
                this.name="Animal2";
            }
        };
        console.log(new Animal(), new Animal2);

        //类的继承 //借助构造函数实现继承
        function Parent () {
            this.name = 'Parent';
        };

        function Child () {
            Parent.call(this);
            this.type = "type";
            this.play = [1,2,3];
        }
        Parent.prototype.say = function(){

        };
        //console.log(new Child().say());//出错，缺点：继承了一部分
        var s1 = new Child();
        var s2 = new Child();
        s1.play.push(4);
        console.log(s1.play,s2.play);

        //原型链原理继承    //借助原型链实现继承
        function Parent2 () {
            this.name = 'Parent2';
            this.arr = [2,3,4]
        };
        Parent2.prototype.sayhello = function () { };
        Parent2.fuck = 'fuck';
        Parent2.fuck1 = function(){};
        function Child2 () {
            this.type = 'type2';
        }

        Child2.prototype = new Parent2();
        // console.log(new Child2().sayhello());

         var s3 = new Child2();
            var s4 = new Child2();
            s3.arr.push(4);
            console.log(s3.arr, s4.arr);
            
            
         // 组合方式继承

        function Parent4() {
            this.name = 'Parent4';
            this.play = [1, 2, 3];
        };

        function Child4() {
            Parent4.call(this);
            this.type = 'type';
        };
        Child4.prototype = new Parent4();

        s5 = new Child4();
        s6 = new Child4();
        s5.play.push(5);
        console.log(s5.play, s6.play);
        //确点： 构造函数Parent4执行了两次，没必要

        //组合方式优化1
        function Parent5() {
            this.name = 'Parent5';
            this.play = [1, 2, 3];
        }

        function Child5() {
            Parent5.call(this);
            this.type = 'type';
        }
        Child5.prototype = Parent5.prototype;
        s7 = new Child5();
        s8 = new Child5();
        s7.play.push(4);
        console.log(s7.play, s8.play);
        console.log(s7.__proto__);
        console.log(s7.__proto__.constructor); //Parent5
        console.log(s7 instanceof Child5, s7 instanceof Parent5);
        console.log(s7.constructor === s7.__proto__.constructor); //true
        //缺点：通过原型链查找实例的构造函数时，只能找到父类，找不到子类


        //组合方式优化2  最完美方案
        function Parent6() {
            this.name = 'Parent6';
        }

        function Child6() {
            Parent6.call(this);
            this.type = 'type';
        }

        Child6.prototype = new Object(Parent6.prototype);
        Child6.prototype.constructor = Child6;

        var s9 = new Child6();
        console.log(s9);
        console.log(s9.constructor);
        console.log(s9.__proto__);
        console.log(s9.__proto__.constructor);

        console.log(s9.constructor);
        console.log(s9.__proto__.constructor);

    </script>
```

用Parent.call\(this\)的方法继承缺点：

* 不完全继承

让子类的prototype属性赋值为构造函数的实例，Child2.prototype = new Parent2\(\);   方法继承的缺点：

```js
var s3 = new Child2();
            var s4 = new Child2();
            s3.arr.push(4);
            console.log(s3.arr, s4.arr);
```

* 在父类（构造函数）中添加的数据，所有子类都会继承



