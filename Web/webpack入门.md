# 安装webpack到项目 
>npm i -D webpack webpack-cli (npm i -D 是npm install --save-dev的简写，是指安装模块并保存到package.json的devDependencies) 

正式使用webpack前的准备:  

在终端中创建一个package.json文件夹: 
>npm init 或  
>npm init -y(默认所有信息)  
输入这个命令后，终端会问你一系列诸如项目名称，项目描述，作者等信息，不过不用担心，如果你不准备在npm中发布你的模块，这些问题的答案都不重要，回车默认即可。  
在根目录下创建两个文件夹：app文件夹,public文件夹;app文件夹用来存放原始数据和我们将写的JavaScript模块，并在app文件夹下创建Greeter.js和main.js文件，public文件夹用来存放之后供浏览器读取的文件,并在public文件夹下创建index.html文件;  
在index.html文件中写入最基础的html代码，它在这里目的在于引入打包后的js文件（这里我们先把之后打包后的js文件命名为bundle.js，之后我们还会详细讲述）。  
<!-- index.html -->  
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Webpack Sample Project</title>
  </head>
  <body>
    <div id='root'>
    </div>
    <script src="bundle.js"></script>
  </body>
</html>
在Greeter.js中定义一个返回包含问候信息的html元素的函数,并依据CommonJS规范导出这个函数为一个模块：  

// Greeter.js  
module.exports = function() {  
  var greet = document.createElement('div');  
  greet.textContent = "Hello World!";  
  return greet;  
};  
main.js文件中我们写入下述代码，用以把Greeter模块返回的节点插入页面。  
  
//main.js   
const greeter = require('./Greeter.js');    
document.querySelector("#root").appendChild(greeter());  
正式使用webpack  
在终端输入:webpack app/main.js -o public/bundle.js  
结果如下:  
在这里插入图片描述  
打开index.html可以看到webpack同时编译了Greeter.js和main.js.  

通过配置文件来使用webpack  
首先我来说明下webpack的几个核心概念:  
  
Entry:入口，webpack执行构建的第一步将从Entry开始，可抽象成输入;  
Module:模块，在webpack里一切皆模块，一个模块对应一个文件。webpack会从配置的Entry开始递归找出所有依赖的模块;  
Chunk:代码块，一个chunk由多个模块组合而成，用于代码合并与分割；  
Loader:模块转换器，用于将模块的原内容按照需求转换成新内容;  
Plugin:扩展插件，在webpack构建流程中的特定时机注入扩展逻辑，来改变构建结果或者做我们想要的事情;  
Output:输出结果，在webpack经过一系列处理并得出最终想要的代码后输出结果；  
webpack工作流程:  
webpack在启动后会从Entry里配置的Module开始，递归解析Entry依赖的所有Module。每找到一个Module，就会根据配置的Loader去找出对应的转换规则，对Module进行转换后，再解析出当前Module依赖的Module。这些模块会以Entry为单位进行分组，一个Entry及其所有依赖的Module被分到一个组也就是一个Chunk。最后，webpack会将所有的Chunk转换成文件输出。在整个流程中，webpack会在恰当的时机执行Plugin里面定义的逻辑。  
  
在根目录下新建一个名为webpack.config.js的文件，目前的配置主要涉及到的内容是入口文件路径和打包后文件的存放路径。  
webpack.config.js  
  
module.exports = {  
  entry:  __dirname + "/app/main.js",//已多次提及的唯一入口文件  
  output: {  
    path: __dirname + "/public",//打包后的文件存放的地方  
    filename: "bundle.js"//打包后输出文件的文件名  
  }  
}  
注：“__dirname”是node.js中的一个全局变量，它指向当前执行脚本所在的目录。  
  
有了这个配置之后，再打包文件，只需在终端里运行webpack,这条命令会自动引用webpack.config.js文件中的配置选项.  
  
npm可以引导任务执行，对npm进行配置后可以在命令行中使用简单的npm start命令来替代上面略微繁琐的命令。在package.json中对scripts对象进行相关设置即可，设置方法如下。  
  
{  
  "name": "webpackPractice",  
  "version": "1.0.0",  
  "description": "",  
  "main": "index.js",  
  "dependencies": {  
    "webpack": "^4.31.0",  
    "webpack-cli": "^3.3.2"  
  },  
  "devDependencies": {},  
  "scripts": {  
    "test": "echo \"Error: no test specified\" && exit 1",   
    "start": "webpack"  
  },  
  "keywords": [],  
  "author": "",  
  "license": "ISC"  
}  

使用mode  
提供模式配置选项告诉webpack相应地使用其内置优化。  
Possible values for mode are: none, development or production(default).  
在这里插入图片描述在webpack中使用:  
  
module.exports = {  
  mode: 'production'  
};  
使用source-map-loader  
开发总是离不开调试，方便的调试能极大的提高开发效率，不过有时候通过打包后的文件，你是不容易找到出错了的地方，对应的你写的代码的位置的，source-map-loader就是来帮我们解决这个问题的  
安装：npm i -D source-map-loader (npm i -D 是npm install --save-dev的简写，是指安装模块并保存到package.json的devDependencies)  
使用：  
  
module.exports = {  
    mode: 'production',    
    entry: __dirname + '/app/main.js',  //唯一的入口文件  
    output: {  
        path: __dirname + '/public', //打包后的文件存放的地方  
        filename: 'bundle.js' //打包后输出文件的文件名  
    },  
    module: {  
        rules:[  
            {  
                test:/\.js$/,  
                use: ["source-map-loader"],  
                enforce:'pre'  
            }  
        ]  
    }  
}  
使用devserver  
让浏览器监听你的代码的修改，并自动刷新显示修改后的结果，其实Webpack提供一个可选的本地开发服务器，这个本地服务器基于node.js构建，可以实现你想要的这些功能，不过它是一个单独的组件，在webpack中进行配置之前需要单独安装它作为项目依赖。  
安装：npm i webpack-dev-server -D  
使用：  
引入path:const path = require(“path”);  
  
var path = require("path");  
module.exports = {  
    mode: 'production',  
    entry: __dirname + '/app/main.js',  //唯一的入口文件  
    output: {  
        path: __dirname + '/public', //打包后的文件存放的地方  
        filename: 'bundle.js' //打包后输出文件的文件名  
    },  
    devServer: {  
        contentBase:path.join(__dirname,'public'), //设置在那个目录下提供本地服务器  
        compress:true, //是否启用gzip压缩  
        port:9000,   //端口  
        open:true,  //自动打开页面  
    },  
    module: {  
        rules:[  
            {  
                test:/\.js$/,  
                use: ["source-map-loader"],  
                enforce:'pre'  
            }  
        ]  
    }  
}  
修改package.json中的配置  
  
"scripts": {  
    "test": "echo \"Error: no test specified\" && exit 1",  
    "start": "webpack",  
    "server": "webpack-dev-server"  
  },  
在终端输入npm run server  
  
修改Greeter.js中的greet.textContent中的内容，页面会自动刷新.  
  
Loaders  
Loader可以看作是具有文件转换功能的翻译员，配置里面的module.rules数组配置了一组规则，告诉webpack在遇到那些文件时使用哪些loader去加载和转换.  
  
Babel  
Babel其实是一个编译JavaScript的平台，它可以编译代码帮你达到以下目的：  
  
让你能使用最新的JavaScript代码（ES6，ES7…），而不用管新标准是否被当前使用的浏览器完全支持；
让你能使用基于JavaScript进行了拓展的语言，比如React的JSX；  
安装：npm install -D babel-loader @babel/core @babel/preset-env @babel/preset-react react react-dom  

配置webpack  
  
var path = require("path");  
module.exports = {  
    mode: 'production',  
    entry: __dirname + '/app/main.js',  //唯一的入口文件  
    output: {  
        path: __dirname + '/public', //打包后的文件存放的地方  
        filename: 'bundle.js' //打包后输出文件的文件名  
    },  
    devServer: {  
        contentBase:path.join(__dirname,'public'), //设置在那个目录下提供本地服务器  
        compress:true, //是否启用gzip压缩  
        port:9000,   //端口  
        open:true,  //自动打开页面  
    },  
    module: {  
        rules:[  
            {  
                test:/\.js$/,  
                use: ["source-map-loader"],  
                enforce:'pre'  
            },  
            {  
                test: /\.jsx|\.js$/,  
                exclude: /(node_modules)/,  
                use: {  
                  loader: 'babel-loader',  
                  options: {  
                    presets: ["@babel/react","@babel/env"]  
                  }  
                }  
            }  
        ]  
    }  
}  
成功显示：  
在这里插入图片描述  
css  
webpack在遇到以.css结尾的文件时，先使用css-loader读取css文件,再由style-loader将css的内容注入JavaScript里,执行顺序由后向前。  
安装：npm install --save-dev style-loader css-loader  
配置webpack  
  
{  
      test:/\.css$/,  
      use:['style-loader','css-loader']  
}  
再app目录下创建Greeter.css文件  
Greeter.css  
  
.body{  
    color:red;  
}  
修改Greeter.js  
  
// Greeter.js  
import React, {Component} from 'react'; 
import style from "./Greeter.css";  
  
  
class Greeter extends Component{  
  render() {  
    return (  
      <div className = {style.body}>  
        Hello World!  
      </div>  
    );  
  }  
}  
  
export default Greeter  
  
修改main.js  
import React from 'react';  
  
import {render} from 'react-dom';  
  
import Greeter from './Greeter.js';  
import style from "./Greeter.css";  
render(<Greeter/>, document.getElementById('root'));  
再终端运行npm run server，Hello World字体颜色变成红色了  