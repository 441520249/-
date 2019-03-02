# 目录结构

- pages页面
  - index 页面组件
    - index.wxml .vue组件 template
    - index.wxss .vue组件 style
    - index.js   .vue组件 script
    - index.json （局部JSON文件）组件的一些局部参数
  - logs
- utils封装库
- app.js应用入口文件（应用的生命周期，全局参数等）
- app.json （全局JSON） 项目页面设置（路由，头部底部颜色，上拉刷新，下拉刷新）
- app.wxss（微信样式全局样式）
- project.config.json（微信开发者工具的参数）



# 与vue的区别
bindtap  ==  on-click



#app.json 配置底部与路由
## tabBar
tabBar其实就是配置底部的选项卡，在`app.json`文件的`tabBar`属性里面定义底部的选项卡的详细配置

```javascript
{
  "pages": [
    "pages/index/index",//路由
    "pages/logs/logs",
    "pages/mine/mine",
    "pages/find/find"
  ],
  "window": {
    "backgroundTextStyle": "dark",//下拉刷新等待图标
    "navigationBarBackgroundColor": "#0ff",
    "navigationBarTitleText": "WeChat",
    "navigationBarTextStyle": "black",
    "enablePullDownRefresh":false,//下拉刷新
    "navigationStyle":"custom"//只保留胶囊
  },
  "tabBar": {
    "color": "#f0f",
    "selectedColor": "#666",
    "borderStyle": "black",
    "backgroundColor": "#ddd",
    "position":"bottom",
    "list": [//其中 list 接受一个数组，只能配置最少 2 个、最多 5 个 tab。tab 按数组的顺序排序
      {
        "pagePath": "pages/index/index",
        "text": "首页"
      },
      {
        "pagePath": "pages/logs/logs",
        "text": "分类"
      },
      {
        "pagePath": "pages/mine/mine",
        "text": "我的",
        "iconPath":"images/icon/爱心.png",//图标
        "selectedIconPath":"images/icon/爱心 _实心.png"//选择后的图标
      },
      {
        "pagePath": "pages/find/find",
        "text": "发现"
      }
    ]
  }
}
```

# 局部json不能配置底部和路由