# 金数据SDK

本插件旨在快速在其他小程序中集成金数据表单

## Tips
* 目前支持「单行文字」「多行文字」「单项选择」「多项选择」「数字」「手机」「日期」「评分」「地理位置」「上传文件」字段显示和提交
* 表单中含有其他字段将会显示「不支持」
* 表单中不支持的其他字段含有校验规则将会导致提交数据失败

## 接入方式 
1. 在app.json配置插件信息

```
app.json
{
  xxx...
  "plugins": {
    "gdPlugin": {
      "version": "0.2.0",
      "provider": "wx34b0738d0eef5f78"
    }
  }
}
```

2. 创建一个page，成功创建后的page页面文件应该是这样子

```
gd-component.js
gd-component.json
gd-copmonent.wxml
gd-component.wxss
```

3. 在gd-component.json引入gd-form组件

```
gd-component.json
{
  "usingComponents": {
    "gd-form": "plugin://gdPlugin/gd-form"
  }
}
```

4. 使用gd-form组件，传入表单token

```
gd-component.wxml
<gd-form token="{{token}}" userinfo="{{userinfo}}" openid="{{openid}}" bind:submit="submit"></gd-form>
```

#### gd-form 属性
| 参数 | 类型 | 说明 | 必填 | 默认值 |
| --- | ---| ----| --- | ----|
| token| String | 表单token值 | true | null
| userinfo | Object | 微信用户公开信息 | false | null
| openid | String | 微信用户openid | false | null
#### gd-form 事件
| 名称 | 描述 | 返回值|
| --- | --- | ---|
| submit | 提交事件 | 'success' &#124; errors |
