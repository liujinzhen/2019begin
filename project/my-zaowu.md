# <center>vue-cli

1. 搭建脚手架在黑窗口 输入vue create my-zaowu
2. 移动端需要写

```

	<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">

+ 安装依赖

```shell

    npm install lib-flexible –-save
    npm install postcss-pxtorem --save-dev

```

+ 添加meta

```html

    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">

```

3. 在main.js文件引入lib-flexible 作用是:根据当前的手机分辨率,重置HTML的font-size,用于配合rem 
	
	import  'lib-flexible'

4. 在postcss.config.js 配置文字大小,代码如下:

```javascript

	module.exports = {
  	plugins: {
      autoprefixer: {},
      "postcss-pxtorem": {
        "rootValue": 37.5, // 设计稿宽度的1/10,（JSON文件中不加注释，此行注释及下行注释均删除）
        "propList":["*"] // 需要做转化处理的属性，如`hight`、`width`、`margin`等，`*`表示全部
     		}
   		}
	}

```

5. assets为静态问件,在这里建style文件夹,放个reset.css文件,这个文件内容是去掉默认样式,具体内容百度可见.并且在main.js中引入这个文件
	
	import  '@/assets/style/reset.css'

6. 


