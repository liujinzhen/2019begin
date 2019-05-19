##vue-cli

###在node_mudule文件中添加axios文件方法: 在黑窗口打开输入npm install axios --save;
###同理方法引入bootstrap和jQuery,
###但是他们引入到vue的文件时,方法不同,
####例:axios 是 import axios from 'axios',
####例:import 'bootstrap/dist/css/bootstrap.min.css'
####例:import 'bootstrap/dist/js/bootstrap.min.js'
####jquery不同于他们,它不能这样引入,而是需要webpack来配置,例:
	// 这里的配置 都是webpack的配置 因为vue-cli3集成了默认的常用的webpack配置,所以很多时候
	// 我们不需要手动配置
	// 但是某些情况下我们需要修改部分配置 需要添加vue.config.js来覆盖默认的webpack配置
	const webpack = require('webpack');
	module.exports = {
  		configureWebpack: {
    		plugins: [
      	new webpack.ProvidePlugin({
		  	'$': 'jquery',
		 	'jQuery': 'jquery',
		})
    	]
  		}
		}
####注: 配置完之后需要重新启动服务器