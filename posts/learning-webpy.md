<!-- 
.. title: learning web.py
.. slug: learning-webpy
.. date: 2015-02-05 03:49:39 UTC
.. tags: web.py
.. category: 
.. link: 
.. description: 
.. type: text
-->

## web.py学习笔记
由于后台的几个需求，需要给测试同学构造gm指令以方便测试，思来想去还是搭建个快速的webserver来方便测试同学，django太庞大，tornado不大熟悉，别人介绍了下[web.py](http://webpy.org/)，而且也不需要安装一大堆的第三方依赖库(原谅楼主有时候在服务器上不喜欢装第三方库的臭毛病吧)，甚至把web.py打包后都不需要额外安装任何东西。简单看了下web.py的文档，感觉还是入手还是比较容易。

工程文档目录结构：

```
main
    |---- conf (工程配置文件)
    |---- static (js，图片等)
    |---- template (html文件)
    |---- web (web.py的库文件)
    |---- config.py (目录，密码等配置)
    |---- index.py (路由文件)
```

接着就可以开始coding，在web.py中需要指定url路由,当url请求中包含相应关键字时则跳转到相应的class中进行处理。
```python
urls = (
    '/favicon.ico',"Ico",
    '/about', "About",
    '/list_(.*)', "Script",
    '/bin_upload(.*)', "Upload",
    '/changetime(.*)', "ChangeTime",
    '/(.*)','Index',
)

render = web.template.render('template/')
```

以下以about跳转为例：
``` python
class Upload:
    def POST(self, *args, **kw):
        # save a file to disk
        x = web.input(file={})
        #print "bintag, filename:", x.bintag, x.file.filename
        if x.bintag == "" or x.file.filename == "":
            return "<script type=\"text/javascript\">alert(\"参数输入不正确，请检查参数!\"); \
                parent.location.href= parent.location.href;</script>"
```

**list_resconv.html**
```html
 <form id="upload" action="bin_upload" method="POST" enctype="multipart/form-data" target="ifm">
                    <fieldset>
                        <legend>bin上传路径:</legend>
                        
                        <div>
                            <div class="form-group">
                                <label for="tag" class="col-sm-2 control-label">bin档目录名:</label>
                                <input type="text" id="bintag" name="bintag">
                            </div>
                            <div class="form-group">  
                                <label for="name" class="col-sm-2 control-label">bin文件:</label>
                                <input type="file" id="fileselect" name="file" title="choose a file" onchange="this.form.submit();">
                                <!--<p class="help-block">要上传的bin文件.</p>-->
                            </div>
                            
                            <!--<div id="filedrag">or drop the file here</div>-->

                        </div>
                    </fieldset>
</form>
```
当POST请求跳转到bin_upload时，则跳转到Upload进行相应的处理，Upload中处理接收的参数，进行后台逻辑处理。如果需要将处理后的数据返回前台，通常使用render来处理返回的数据`render.htmlfilename(parms)`的方式。

