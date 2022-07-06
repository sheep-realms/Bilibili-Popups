# PopupsSkin
[< 返回 | Bilibili Popups 技术文档](../index.md)

Popups 皮肤类，负责管理样式。

主类上的```loadSkin```方法无论如何都会尝试加载默认皮肤```Default```，可在此皮肤中写入全局通用样式。

除此以外 Popups 还内置了```Classic```样式和```Vanilla```样式可供用户切换。

## 属性
| 名称 | 类型 | 用途 | 默认值 |
|-----|------|-----|-----|
| name | String | 皮肤名称。 | "Example Popups Skin" |
| styleSheets | Array\<String\> | 样式表。直接写入 CSS 样式即可，数组中的字符串会以空格相连接。 | [] |
| maxWidth | Number | Popups 的最大宽度。 | 0 |
| maxHeight | Number | Popups 的最大高度。 | 0 |

构造示例：
```
let exampleSkin = new PopupsSkin("Example Popups Skin", [
    "#popups {display: block;}",
    "#popups .red {color: red;}"
], 350, 600);
```

## getStyle
获取样式表。

## loadStyle
加载样式。