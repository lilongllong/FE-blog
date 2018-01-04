# FE-blog
前端技术学习知识记录，为期两周的短期速记，之后会空闲时间维护
## 1. react-hot-loader
React Hot Loader is a plugin for Webpack that allows instantaneous live refresh without losing state while editing React components.
*热更新而不丢失状态*

### 安装
- npm install --save react-hot-loader
- .babel.rc文件
```
{
    ""
    "plugins": ["react-hot-loader/babel"]
}
```
- webpack.config.js
```
module.exports = {
    devtool: 'source-map', // 代码映射
    entry: {
        'app': [
            'babel-polyfill',
            'react-hot-loader/patch',
            './src/index'
        ],
    }
    /*
        Make sure to set the output.publicPath property to "/" as well. Otherwise hot reloading won't work as expected for nested routes.
    */
    output: {
        path: path.resolve(__dirname, './dist'),
        filename: '[name].js',
        publicPath: '/',
    }
}
```
- index.js
```
// main.js
import React from 'react'
import ReactDOM from 'react-dom'
import { AppContainer } from 'react-hot-loader'
import App from './containers/App'
 
const render = Component => {
  ReactDOM.render(
    <AppContainer>
      <Component />
    </AppContainer>,
    document.getElementById('root'),
  )
}
 
render(App)
 
// Webpack Hot Module Replacement API
/* webpack-dev-server --hot or 'new webpack.HotModuleReplacementPlugin({
  // Options...
})' active module.hot 
*/
if (module.hot) {
  module.hot.accept('./containers/App', () => { render(App) })
}
```
