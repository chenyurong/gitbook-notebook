输出为静态网站
====

你有两种方式输出一个静态网站：

**本地预览时自动生成**

当你在自己的电脑上编辑好图书之后，你可以使用Gitbook的命令行进行本地预览：

```bash
$ gitbook serve ./图书目录
```

这里会启动一个端口为`4000`用于预览的服务器：

```bash
$ gitbook serve .
Press CTRL+C to quit ...

Starting build ...
Successfuly built !

Starting server ...
Serving book on http://localhost:4000
```

你可以你的浏览器中打开这个网址：<http://localhost:4000>：

![](../img/yl.png)

这里你会发现，你在你的图书项目的目录中多了一个名为`_book`的文件目录，而这个目录中的文件，即是生成的静态网站内容。

**使用build参数生成到指定目录**

与直接预览生成的静态网站文件不一样的是，使用这个命令，你可以将内容输入到你所想要的目录中去：

```bash
$ mkdir /tmp/gitbook
$ gitbook build --output=/tmp/gitbook
Starting build ...
Successfuly built !
$ ls /tmp/gitbook/
LICENSE           howtouse          manifest.appcache search_index.json
book              img              output
gitbook           index.html        publish
```

无论哪种方式，你都可以将这个文件打包，然后把你的书发给你的朋友们了！

## 帮助

如果你在运行 `gitbook serve .` 命令时报了这个错误：

```
Live reload server started on port: 35729
Press CTRL+C to quit ...

/usr/local/lib/node_modules/gitbook-cli/node_modules/_npm@5.1.0@npm/node_modules/graceful-fs/polyfills.js:287
      if (cb) cb.apply(this, arguments)
                 ^

TypeError: cb.apply is not a function
    at /usr/local/lib/node_modules/gitbook-cli/node_modules/_npm@5.1.0@npm/node_modules/graceful-fs/polyfills.js:287:18
```

这其实是一个依赖的问题，你可以尝试安装旧的 gitbook-cli 版本。

```
npm install gitbook-cli@2.1.2 --global
```
