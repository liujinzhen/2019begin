#<center>webpack
## webpack基本概念

### 基本组成
+ 入口(entry)   
	- 用于配置入口文件
+ 输出(output)
	- 用于配置输出的打包目录和文件
+ loader
	- 用于解析.css  .sass .vue .xxx等类型文件

+ 插件(plugins)
	- HtmlWebpackPlugin 自动生成html模板

### 安装
+ 安装

```

	// 全局安装
	npm install --global webpack

	// 在文件夹进行局部安装
	npm  init
	//同时安装 webpack 和  webpack-cli(3.x是没有这个库的)

	// cnpm  是  npm的国内淘宝镜像  cnpm怎么用? 
[cnpm]<https://www.baidu.com/>

	cnpm install webpack webpack-cli --save-dev
	cnpm install webpack webpack --save-dev

	或者
	npm install webpack --save-dev
	npm install webpack-cli --save-dev
	
	

```

+  module 用于配置各种loader
+  rules 用于匹配规则

+ plugin是插件的意思,它可以帮我们自动生成HTML页面
const HtmlWebpackPlugin = require('html-webpack-plugin');

+ 用于清除dist文件夹的多余文件
const CleanWebpackPlugin = require('clean-webpack-plugin');

+ "start": "webpack-dev-server --open"  //这个在config中,是在localhost:8080启动,出现vue的ico;
