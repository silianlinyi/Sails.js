## Sails杂七杂八

我们知道，在Sails.js框架中，默认使用的视图引擎是ejs，但`.ejs`后缀的文件在大多数的编辑器中，代码是没有高亮显示的，这样就给我们的开发带来了麻烦，所以我们想办法让文件的后缀修改为.html，这样代码就可以高亮显示了。

查看`C:\Users\***\AppData\Roaming\npm\node_modules\sails\lib\express\index.js`文件，`***`对应电脑用户名，我们可以发现下面的一段代码（#57 ~ 59）：

```
// Set view engine within express to set up res.render()
app.engine(sails.config.views.engine.ext, sails.config.views.engine.fn);
sails.express.app.set('view engine', sails.config.views.engine.ext);
```

这样我们可以修改`\config\views.js`文件

```
engine: {
    ext: 'html',
    fn: require('ejs').__express
},
```
