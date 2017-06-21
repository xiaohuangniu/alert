基于JQuery开发的一套弹窗插件
===============================================

最近在开发一个API协调工具，需要一套可控性跟独特性比较强的弹窗插件，于是就画了一天时间，自己动手写这套东西，再三考量后，还是决定开源出来给大家使用。
-----------------------------------------------


+ 当前版本 - V1.0.0.1

+ 上传日期 - 2017-6-21 10:10:00

+ 作者 - 小黄牛

+ 邮箱 - 1731223728@qq.com     

+ QQ群 - 368405253



## 1、设置颜色配置(放置最顶部可做全局配置使用)

```
$.MaskColor(颜色编码);
现有以下5种颜色配色方案可选：
cyan(青色)
green(绿色)
blue(蓝色)
orange(橙色)
dark(深色))
````


## 2、打开遮罩层

```
$.MaskStart(颜色,不透明度);
颜色默认为 #000
不透明度默认为 0.8
````


## 3、关闭遮罩层

```
$.MaskEnd();
````


##  4、打开可编辑弹窗

```
$.mkter({
    Id         : 'App',         // 唯一ID名，默认为:App
    Title      : '我是头部标题', // 标题内容，默认为:新建项目
    Botton     :' 我是按钮',     // 保存按钮名称，默认为:保存
    Width      : 500,           // 弹窗宽度，默认为:320
    Top        : 200,           // 弹窗距离顶部浮动距离，默认为:50
    MaskColor  : '#000',        // 背景遮罩层颜色
    MaskBright : 0.7,           // 背景遮罩层不透明度
    Form       : [              // 表单内容，具体格式如下，主要支持以下5种类型表单元素
        {
            "type":"hidden",
            "id":"pid",
            "title":"表单提交的修改ID",
            "value":"默认值"
        },
        {
            "type":"text",
            "id":"name",
            "title":"用户名",
            "value":"默认值"
        },
        {
            "type":"password",
            "id":"pwd",
            "title":"密码",
            "value":""
        },
        {
            "type":"textarea",
            "id":"des",
            "title":"描述",
            "value":"默认值"
        },
        {
            "type":"select",
            "id":"name",
            "value":"2",
            "option":[
                {id:"0", title:"未知"},
                {id:"1", title:"男"},
                {id:"2", title:"女"}
            ]
        }
    ],
    Click      : 'AddClick()', // 点击保存按钮的回调方法
});
````


## 5、关闭弹窗

```
$.MaskClick(ID号);
注意，可用于所有弹窗，$.prompt除外
````


## 6、带确认按钮弹窗

```
$.confirm({
    Id          : 'App-alert',                  // 唯一ID号，默认为:App-alert-1
    Title       : '不要反驳，请同意',            // 标题内容，默认为:提示
    Content     : '妈卖批，小黄牛真是帅得一匹~~', // 弹窗内容，默认为:不要反驳，小黄牛帅得一B！
    Out         : '不同意',                     // 取消按钮名称，默认为:取消
    Confirm     : '同意',                       // 确认按钮名称，默认为:确认
    Width       : 500,                          // 弹窗宽度，默认为: 320
    MaskColor   : '#000',                       // 背景遮罩层颜色
    MaskBright  : 0.7,                          // 背景遮罩层不透明度
    OutState    : true,                         // 是否显示取消按钮，默认为true
    Click_O     : 'Alert_O()',                  // 点击取消按钮的回调方法
    Click_C     : 'Alert_C()',                  // 点击确认按钮的回调方法
});
````


## 7、带头部信息的警告弹窗

```
$.alert({
    Id          : 'App-alert-2',                // 唯一ID号，默认为:App-alert-2
    Title       : '不要反驳，请同意',            // 标题内容，默认为:提示
    Content     : '妈卖批，小黄牛真是帅得一匹~~', // 弹窗内容，默认为:不要反驳，小黄牛帅得一B！
    Width       : 500,                          // 弹窗宽度，默认为: 320
    MaskColor   : '#000',                       // 背景遮罩层颜色
    MaskBright  : 0.7,                          // 背景遮罩层不透明度
});
````


## 8、只有文字的提示弹窗

```
$.warning({
    Id          : 'App-alert-3',                // 唯一ID号，默认为:App-alert-3
    Content     : '妈卖批，小黄牛真是帅得一匹~~', // 弹窗内容，默认为:不要反驳，小黄牛帅得一B！
    Width       : 500,                          // 弹窗宽度，默认为:320
    OutTime     : 20000,                        // 自动关闭时间，默认为:1500(S)
    MaskColor   : '#000',                       // 背景遮罩层颜色
    MaskBright  : 0.7,                          // 背景遮罩层不透明度
});
````


## 9、打开加载层

```
$.load({
    Id          : 'App-alert-loading',  // 唯一ID号，默认为:App-alert-loading
    Model       : 'ch',                 // 语言模式，可选ch|en，默认为:ch
    OutState    : false,                // 是否开启自动关闭，默认为:false
    OutTime     : 2000,                 // 自动关闭时间，默认为:2000(S)
    MaskColor   : '#000',               // 背景遮罩层颜色
    MaskBright  : 0.7,                  // 背景遮罩层不透明度
});
````


## 10、关闭加载层

```
$.load({
      OutState : false,  // 是否开启自动关闭，默认为:false
      OutTime  : 2000,   // 自动关闭时间，默认为:2000(S)
});
````


## 11、打开表单验证提示，文字左滑效果

```
$.prompt({
      Id          : 'App-alert-loading',  // 唯一ID号，无默认值
      Content     : '用户名不能为空',      // 提示内容，默认值:不要反驳，小黄牛帅得一B！
      Color       : 'red',                // 文字颜色，默认为:red
      OutState    : true,                 // 是否开启自动关闭，默认为:true
      OutTime     : 2000,                 // 自动关闭时间，默认为:1500(S)
});
注意：
1、使用$.prompt，对应ID的父元素一定要先设置为position: relative;，否则无效
2、对$.mkter的表单验证，插件自动设置了position: relative;并为每一个表单元素生成了规则为【id名-vif】的ID属性，方便可编辑弹窗提示验证
````


## 12、关闭表单验证提示

```
$.promptEnd({
      Id          : 'App-alert-loading',  // 唯一ID号，无默认值
      OutTime     : 2000,                 // 关闭延时，默认为:1500(S)
});
````