# Popups
[< 返回 | Bilibili Popups 技术文档](../index.md)

Popups 主类，负责管理 Popups 的基本属性和行为。

## 属性
| 名称 | 类型 | 用途 | 默认值 |
|-----|------|-----|-----|
| id | String | Popups 在 DOM 中的 ID。 | "popups" |
| $sel | String | 通过 JQuery 选择器找到 Popups 需要用到的选择器语句。 | "#" + this.id |
| state | Number | Popups 的状态。0 代表隐藏，1 代表显示。 | 0 |
| used | Boolean | 当前会话中是否使用过 Popups。 | false |
| timer | Number | 定时器编号。用于处理何时隐藏，何时出现。 | 0 |
| disable | Boolean | 是否暂时禁用。 | false |
| deactivate | Boolean | 是否在当前会话中禁用。 | false |
| posX | Number | 水平位置。 | 0 |
| posY | Number | 垂直位置。 | 0 |
| skin | Array\<PopupsSkin\> | 已提交的皮肤列表。 | [] |
| maxWidth | Number | 最大宽度。防止 Popups 溢出可视区域，由皮肤定义。设为 0 则不做防溢出处理。 | 0 |
| maxHeight | Number | 最大高度。防止 Popups 溢出可视区域，由皮肤定义。设为 0 则不做防溢出处理。 | 0 |
| urlAntiTrack | Boolean | 是否启用链接反追踪。启用后，悬浮框内的链接点击行为将被本程序接管，不再由浏览器默认行为处理。部分苛刻条件下可能会被浏览器拦截新页面。 | true |
| data | Object | 用于存放数据。 | {} |
| lang | Object | I18N。 | {} |
| noAntiYposOflow | Array\<String\> | 禁用反 Y 轴溢出的站点。部分网站样式可能会影响 Popups 的 Y 轴定位，禁用此功能可改善这一问题，但浮窗内容可能会溢出可视区域。 | ["live.bilibili.com"] |

构造示例：
```
let pop = new Popups();
```

## getConfig
获取配置。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| name | String | 配置名称。 |  |
目前仅有 “useSkin” 这一项配置。

## setConfig
更改配置。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| name | String | 配置名称。 |  |
| value |  | 配置值。 |  |

## setData
设置数据。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| data | Object | 数据内容。 |  |

## resetView
重置 Popups 内容并设置标题。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| title | String | 标题。 | "missingno" |

## load
初始化，向 DOM 中加入 Popups。

无参数。

同时会执行```resetView()```。

## pushSkin
提交皮肤到皮肤列表中。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| skinObj | PopupsSkin | Popups皮肤。 |  |

## loadSkin
加载已选择的皮肤。此函数只执行一次，重复执行会发生无法预料的后果。

无论如何，此方法都会尝试加载默认皮肤```Default```。

## switchSkin
切换皮肤。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| skinName | String | 皮肤名称。 |  |

## setTitle
设置标题。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| str | String | 标题。 |  |

## setSubtitle
设置副标题。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| str | String | 副标题。注意该值会被解析为 HTML。 |  |

## add
向内容区末尾添加一段 HTML。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| str | String | HTML 代码。 |  |

## move
移动 Popups。注意，若 Popups 设置了最大尺寸，此方法无法将 Popups 移动到可视区域之外。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| left | Number | Popups 左侧到容器左侧的距离。 | this.posX+5 |
| top | Number | Popups 顶部到容器顶部的距离。 | this.posY+5 |

## show
显示 Popups。

## hide
隐藏 Popups。

## setImage
设置 Popups 中的预览图。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| url | String | 图片地址 |  |

## error
加载报错画面。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| title | String | 错误画面标题。 | "出错啦！" |
| message | String | 详细信息。 |  |
| code | String | 错误代码。 | "无" |

## stop
在当前会话中停用 Popups。