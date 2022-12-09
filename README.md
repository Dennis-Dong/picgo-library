# picgo-library
基于Typora的上传图片插件picgo-core搭建的图床

# 搭建方法
[https://picgo.github.io/PicGo-Core-Doc/zh/guide/config.html](https://picgo.github.io/PicGo-Core-Doc/zh/guide/config.html)

# 安装操作说明
## 1. 添加 github token
> 右上角-->Settings-->Developer settings-->Personal access tokens-->Tokens(classic)-->Generate new token-->Generate new token (classic)

- 权限要求全选
- Select scopes
  - [x] repo 
  - [x] repo:status 
  - [x] repo_deployment 
  - [x] public_repo 
  - [x] repo:invite 
  - [x] security_events 

## 2. 下载 picgo-code
> 在typora编辑器-->文件-->偏好设置-->图像-->上传服务-->选择 `Picgo-Code (command line)`-->下载或更新
> 
> 下载路径在 `C:\Users\Dennis\AppData\Roaming\Typora\picgo\win64`

## 3. 初始化图床
在`picgo`安装路径打开cmd
```
PS C:\Users\Dennis\AppData\Roaming\Typora\picgo\win64> .\picgo.exe use
? Use an uploader github
? Use a transformer path
? Use plugins (Press <space> to select, <a> to toggle all, <i> to invert selection)
[PicGo SUCCESS]: Configure config successfully!
```

成功后会在`C:\Users\Dennis`下生成`.picgo`文件夹

## 4.配置图床
```
PS C:\Users\Dennis\AppData\Roaming\Typora\picgo\win64> .\picgo.exe set uploader
? Choose a(n) uploader github
? repo: 用户名/仓库名，Dennis-Dong/picgo-library
? branch: 分支名称，默认master
? token: 自己的token
? path: 自定义路径，填写images/则会在仓库生成一个文件夹
? customUrl: 默认为空即可，自定义域名，注意要加 http://或者 https://
[PicGo SUCCESS]: Configure config successfully!
```

最后生成的配置如下
```JSON
{
  "picBed": {
    "current": "github",
    "uploader": "github",
    "transformer": "path",
    "github": {
      "repo": "Dennis-Dong/picgo-library",
      "branch": "master",
      "token": "自己的token",
      "path": "自定义路径，填写images/则会在仓库生成一个文件夹",
      "customUrl": "默认为空即可，自定义域名，注意要加 http://或者 https://"
    }
  },
  "picgoPlugins": {}
}
```
## 5.测试配置结果
在第2步中点击`验证图片上传选项`，若提示成功即可

# 添加/更换图床
操作上面3，4步骤

