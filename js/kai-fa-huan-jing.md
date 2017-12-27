![](/assets/import227.png)![](/assets/import228.png)![](/assets/import230.png)![](/assets/import231.png)![](/assets/import233.png)![](/assets/import234.png)![](/assets/import235.png)webpack构建工具：

cnpm init

cnpm install webpack --save-dev

cnpm install jquery --save

编辑webpack.config.js:

```js
var path = require('path')
var webpack = require('webpack')

module.exports = {
    context: path.resolve(__dirname, './src'),
    entry: {
        app: './app.js'
    },
    output: {
        path: path.resolve(__dirname, './dist'),
        filename: 'bundle.js'
    }
}
```



