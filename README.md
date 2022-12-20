# unzip-oss-nas 帮助文档

<p align="center" class="flex justify-center">
    <a href="https://www.serverless-devs.com" class="ml-1">
    <img src="http://editor.devsapp.cn/icon?package=start-unzip-oss&type=packageType">
  </a>
  <a href="http://www.devsapp.cn/details.html?name=start-unzip-oss" class="ml-1">
    <img src="http://editor.devsapp.cn/icon?package=unzip-oss-nas&type=packageVersion">
  </a>
  <a href="http://www.devsapp.cn/details.html?name=unzip-oss-nas" class="ml-1">
    <img src="http://editor.devsapp.cn/icon?package=unzip-oss-nas&type=packageDownload">
  </a>
</p>

<description>

> ***快速部署自动解压上传到OSS指定前缀目录的zip文件的应用到阿里云函数计算,主要用于单文件超10G以上的大文件***
</description>

<table>
</table>

<codepre id="codepre">

</codepre>

<deploy>

## 部署 & 体验

<appcenter>



- 通过 [Serverless Devs Cli](https://www.serverless-devs.com/serverless-devs/install) 进行部署：
    - [安装 Serverless Devs Cli 开发者工具](https://www.serverless-devs.com/serverless-devs/install) ，并进行[授权信息配置](https://www.serverless-devs.com/fc/config) ；
    - 初始化项目：`s init unzip-oss-nas -d unzip-oss-nas`   
    - 进入项目，并进行项目部署：`cd unzip-oss-nas && s deploy -y`

</deploy>

<appdetail id="flushContent">


通过给函数创建 OSS 触发器， 用户只需要给对应的 OSS 指定前缀目录上传 zip 文件， 就会自动触发解压函数执行， 解压函数会把解压后的文件和文件夹转存回 OSS

**方案**
将上传oss的文件拉取到函数计算挂载的nas中进行解压上传。函数默认使用的配置较高。

通过 Serverless Devs 开发者工具，您只需要几步，就可以体验 Serverless 架构，带来的降本提效的技术红利。

**声明**
此模板只是一个临时性的解决方案，费用及效率都不如start-oss-zip模板，如果使用start-oss-zip模板有如下报错的话可以尝试使用此模板。
	
	"errorMessage": "{'status': -2, 'x-oss-request-id': '', 'details': 'RequestError: [Errno 32] Broken pipe'}",
    "errorType": "RequestError",
    "stackTrace": [
        [
            "File \"/code/index.py\"",
            "line 48",
            "in wrapper",
            "ret = func(*args, **kwargs)"
        ],
        [
            "File \"/code/index.py\"",
            "line 135",
            "in handler",
            "bucket.put_object(newKey + name, file_obj)"
        ],
        [
            "File \"/var/fc/lang/python3/lib/python3.6/site-packages/oss2/api.py\"",
            "line 518",
            "in put_object",
            "resp = self.__do_object('PUT', key, data=data, headers=headers)"
        ],

</appdetail>

<devgroup>

## 开发者社区

您如果有关于错误的反馈或者未来的期待，您可以在 [Serverless Devs repo Issues](https://github.com/serverless-devs/serverless-devs/issues) 中进行反馈和交流。如果您想要加入我们的讨论组或者了解 FC 组件的最新动态，您可以通过以下渠道进行：

<p align="center">

| <img src="https://serverless-article-picture.oss-cn-hangzhou.aliyuncs.com/1635407298906_20211028074819117230.png" width="130px" > | <img src="https://serverless-article-picture.oss-cn-hangzhou.aliyuncs.com/1635407044136_20211028074404326599.png" width="130px" > | <img src="https://serverless-article-picture.oss-cn-hangzhou.aliyuncs.com/1635407252200_20211028074732517533.png" width="130px" > |
|--- | --- | --- |
| <center>微信公众号：\`serverless\`</center> | <center>微信小助手：\`xiaojiangwh\`</center> | <center>钉钉交流群：\`33947367\`</center> | 

</p>

</devgroup>
