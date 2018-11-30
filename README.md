# bdParse

#### 项目介绍
百度小程序富文本解析工具bdParse，改造自wxparse，支持html转换成百度小程序富文本节点。


#### 安装教程

1. 下载整个全部文件，放到你的小程序根目录下
2. 在小程序页面的js种直接引入代码:`var bdParse = require('../../bdParse/bdParse.js')`;
   对应css中引入`@import "../../bdParse/bdParse.css"`;
3. 在需要的字段使用baparse，代码：（注意：article和content不要重复）
   ` that.setData({
          content:bdParse.bdParse('article', 'html', content, that, 5),
    })`
4. swan页面引入模板，`<import src="../../bdParse/bdParse.swan" />`
  然后在需要显示富文本的地方调用：`<template is="bdParse" data="{{ {bdParseData:article.nodes} }}" />` (注意：data调用改为和wxParse一致写法，注意是三个大括号，原先的直接写{{article}}不再支持，请注意修改)

#### 使用说明

1. swan调用模板的data="{{ {bdParseData:article.nodes} }}"和setData中的article保持一致。
2. 调用bdparse组件的时候，组件已经把富文本内容赋值（即setData）给了article；{{ {bdParseData:article.nodes} }} 这种写法的意思是：把article.nodes的内容赋值给bdParseData,bdParse.swan中调用的是bdParseData。

#### 其他说明

1. bdParse是在wxParse的基础上改造的，只是把wxParse替换换成了bdParse，包含js，swan, css
2. wxml修改后缀改成swan，并且修改了全部模板传值的调用方式，符合百度小程序的使用。
3. 修复了其他百度小程序的专有组件，比如s-for，s-if,s-elif,s-for-index等等
4. 修复其他问题，比如去掉`<template name="wxParseImg">`重复的mode以及去掉data-from，给所有的s-for-index添加idx（好像不能为空）。
5. 其他修改，不再赘述
6. 因为直接批量替换内容，基本文章可以满足使用，其他没有做过多测试，欢迎大家反馈bug


#### 参与贡献

 * 开发者：腾石建站
 * 官网:http://www.tengcee.com
 * bdParse.swan改造自wxParse.wxml
 * wxParse的原作者github地址: https://github.com/icindy/wxParse

#### 码农不易，多多支持

如果你觉得bdParse帮你解决了问题，请不要忘了打赏，你的支持是我们最大的动力。

![输入图片说明](https://images.gitee.com/uploads/images/2018/1005/135406_e0d03cd0_1544331.png "支付二维码.png")