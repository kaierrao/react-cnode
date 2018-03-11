# 项目实战二：Webpack + React全栈工程架构项目实战精讲
## 一、工程架构：
### 1、webapp 架构简介
工程架构：解放生产力、围绕解决方案搭建环境、保证项目质量
- 解放生产力：源代码处理；自动打包自动更新页面显示；自动处理图片依赖，保证开发和正式环境的统一
- 围绕解决方案搭建环境：不同的前段框架需要不同的运行架构；预期可能出现的问题并规避；
- 保证项目质量：code lint; 不同环境排除差异；git commit预处理

项目架构：技术选型、数据解决方案、整体代码风格

### 2、web开发常用网络优化
优化方案：合并资源文件，减少HTTP请求；压缩资源文件较少请求大小；合理利用缓存机制

### 3、webpack 的基础配置
```javascript
const path=require('path');

module.exports={
    entry:{
        app:path.join(__dirname,'../client/app.js')//打包入口文件
    },
    output: {
        filename: "[name].[hash].js",//打包输出文件名：[name]表示入口文件名
        path: path.join(__dirname,'../dist'),//文件输出位置
        publicPath: "",//前缀区分资源
    }
};
```
运行的时候，可以配置package.js
```json
  "scripts": {
    "build": "webpack --config build/webpack.config.js"
  },
```