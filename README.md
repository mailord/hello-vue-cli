#hello-vue-cli
## 介绍
hello-vue-cli是基于vue-cli 2创建的项目脚手架，用于webpack 3源码调试。基于vue-cli 2创建项目脚手架hello-vue-cli的详细步骤参考文档“从源码看webpack3.0打包流程.md”的第1.3节。

## 项目构建
你需要安装Node.js。笔者安装的版本是v16.20.2。然后在终端运行以下命令进行项目构建。
``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

##webpack 3源码调试

webpack 3源码调试参考文档“从源码看webpack3.0打包流程.md”的第3节。在webpack源码中打好断点，然后运行`npm run build`即可开始调试。

在调试过程中，对hello-vue-cli项目进行了以下修改：

- 为了简化webpack 3源码调试，调试前将配置文件./build/webpack.prod.conf.js中的部分插件注释掉了。注释掉的插件有UglifyJsPlugin、ExtractTextPlugin、OptimizeCSSPlugin和HtmlWebpackPlugin。

- 创建dist_bak文件夹，用于存储不同wepback配置时生成的发布物文件，方便进行对比。dist_bak的子文件夹的含义如下所示。

  ./dist： 注释掉UglifyJsPlugin、ExtractTextPlugin、OptimizeCSSPlugin和HtmlWebpackPlugin生成的发布物文件;

  ./dist_bak/c_none: 项目原配置（未注释插件）生成的发布物文件；

  ./dist_bak/c_UEO: 注释掉UglifyJsPlugin、ExtractTextPlugin、OptimizeCSSPlugin后生成的发布物文件；

  ./dist_bak/c_U: 注释掉UglifyJsPlugin生成的发布物文件；

​        
