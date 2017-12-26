![](/assets/import138.png)

![](/assets/import143.png)

![](/assets/import146.png)

![](/assets/import145.png)![](/assets/import140.png)![](/assets/import141.png)![](/assets/import147.png)![](/assets/import149.png)![](/assets/import150.png)原型链继承的实例：

```js
function Elem (id) {
    this.elem = document.getElementById(id);
}

Elem.prototype.html = function (val) {
    var elem = this.elem;    
    if(val)
    {
        elem.innerHTML = val;
        return this;
    }else{
        return innerHTML;
    }
}

Elem.prototype.on = function (type, fn) {
    var elem = this.elem;
    elem.addEventListener(type,fn);
}

var div1 = new Elem('main');

div1.html('<p>hello js</p>');
div1.on('click',function () {
    alert('cledked');
});


```



