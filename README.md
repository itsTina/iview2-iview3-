# iview2~iview3升级采坑
 
 
**iview3 中源码使用了es6, 导致打包失败**
需要再babel编译js 时设置
    
     {
      test: /\.js$/,
      include: [
        path.resolve(__dirname, 'js'),
        path.resolve(__dirname, 'node_modules/iview')
      ],
      exclude: [
        path.resolve(__dirname, 'js/lib')
      ],
      loader: 'babel-loader'
    }
     
