![](/assets/import56.png)![](/assets/import57.png)

![](/assets/import58.png)![](/assets/impor59t.png)

##### 创建对象的四种方法：

```js
<script>
        var o1 = {name: 'o1'};
        var o2 = new Object({name:'o2'});
        var M = function (name) {this.name=name};
        var o3 = new M('o3');
        var P = {name:'o4'};
        var o4 = Object.create(P);
    </script>
```

---

![](/assets/import59.png)instanceof判断该实例的构造函数时不严谨，只要是整个原型链上的构造函数都会返回true

console结果：

```js
o3 instanceof Object
true
o3 instanceof M
true
o3.__proto__===M.prototype
true
M.prototype.__proto__===Object.prototype
true
o3.__proto__.constructor===M
true
o3.__proto__.constructor===Object
false
```

---

### ![](/assets/import60.png)

### new运算符的js的模拟实现

```js
var new2 = function(func){
            var o = Object.create(func.prototype);
            var k = func.call(o);
            if(typeof k == 'Object' )
            {
                return k
            }
            else{
                return o
            }
        };
```

console结果

```js
o6 = new2(M)
M {name: undefined}
o6 instanceof M
true
o6.__proto__.constructor===M
true
M.prototype
{constructor: ƒ}
M.prototype.walk = function(){console.log('walk')}
ƒ (){console.log('walk')}
o6.walk
ƒ (){console.log('walk')}
o6.walk()
VM1174:1 walk
undefined
o3.walk()
VM1174:1 walk
undefined
```

---



