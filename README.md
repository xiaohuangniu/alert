基于JQuery开发的一套弹窗插件
===============================================

最近在开发一个API协调工具，需要一套可控性跟独特性比较强的弹窗插件，于是就画了一天时间，自己动手写这套东西，再三考量后，还是决定开源出来给大家使用。
-----------------------------------------------


+ 当前版本 - V1.0.0.2

+ 上传日期 - 2017-6-21 10:10:00

+ 作者 - 小黄牛

+ 邮箱 - 1731223728@qq.com     

+ QQ群 - 368405253


有兴趣维护交流的朋友，可以加群一起学习哈~~(^.^)
-----------------------------------------------


### 最新版本说明

1、$.mkter弹窗新增一个more类型分支，用于往下添加无限组合表单元素

2、参数一览

```
{
    "type": "more", // 类型
    'id'  : "key",  // name的根节点名
    'dui' : true,   // 是否开启单行确认回调
    'dui_click': 'DuiClick(ajax_more)', // 单行确认回调函数，方法名可自定义，但内部的ajax_more变量名必须固定
    "option":[// 表单元素
        {id:"mo_title", title:"标题",value:"默认值"},
        {id:"mo_num", title:"数量",value:""},
    ],
    "value":[// 默认填充行数
        {mo_title:"测试-1",mo_num:"3"},
        {mo_title:"测试-2",mo_num:"4"},
        {mo_title:"测试-3",mo_num:"5"},
    ]
}
````