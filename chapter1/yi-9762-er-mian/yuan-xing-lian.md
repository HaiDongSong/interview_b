![](/assets/import56.png)![](/assets/import57.png)

![](/assets/import58.png)![](/assets/impor59t.png)

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

![](/assets/import59.png)instanceof判断该实例的构造函数时不严谨，只要是整个原型链上的构造函数都会返回true

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



