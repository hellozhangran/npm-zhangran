#npm测试发布

##创建
创建自己的npm比较简单：
```
mkdir npm-zhangran
cd npm-zhangran
//参数设置，几点比较重要
//1. name参数，要唯一的，在npmjs.org不重复
//2. main参数，require时，加载的文件，一般写index.js，比如这个例子中require('npm-zhangran');会加载node_modules/npm-zhangran/index.js文件
//3.版本号1.0.0 主版本.此版本.修bug版本。每次发布，这个版本号不能重复，否则发布失败
npm init
touch index.js //随便写几行简单代码
npm adduser//如果没有注册过，如果这一步，天要求填写相关信息
npm login //按要求填入name：zhangran，password：131*11，email：hello@gmail.com
npm publish //发布

```

##其他
1. `npm login` 已经注册了npm账号，直接执行`npm login`根据提示登录
2. `npm owner ls` 列出当前npm包的维护人员
3. 配置属性`main` `bin`。其中bin指定可执行文件的位置，
如果包是**全局安装**的，直接运行则会默认用node执行该bin文件。
如：npm-zhangran 相当于node ./bin/ran
注：在ran文件的第一行默认加#!/usr/bin/env node

```
{
  "name": "npm-zhangran",
  "version": "1.0.3",
  "description": "lala",
  "main": "main.js",//使用require('npm-zhangran')引用
  "bin":"./bin/ran",//全局安装后，命令行运行npm-zhangran时用
  "scripts": {
    "test": "node"
  },
  "keywords": [
    "install"
  ],
  "author": "zhangran",
  "license": "ISC"
}

```





**参考：**
>http://javascript.ruanyifeng.com/nodejs/module.html#toc2
http://www.infoq.com/cn/articles/nodejs-module-mechanism
http://my.oschina.net/ubuntuvim/blog/540494
http://my.oschina.net/ubuntuvim/blog/540494