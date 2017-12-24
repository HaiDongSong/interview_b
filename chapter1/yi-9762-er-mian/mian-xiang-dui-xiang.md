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







