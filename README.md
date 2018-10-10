# iview2~iview3升级采坑
 
 
- **iview3 中源码使用了es6, 导致打包失败**
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
     
- **iview3 验证中对类型进行了判断，默认为string，所以如果字段类型初始值为number，就会验证失败**
    { required: true, message: '面额不能为空', trigger: 'blur', pattern: /\S/ }
