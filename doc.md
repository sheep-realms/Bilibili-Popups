# Bilibili Popups 技术文档

## 类
| 名称 | 用途 |
|-----|-----|
| Popups | Popups 主类，负责管理 Popups 的基本属性和行为。 |
| PopupsFactory | Popups 工厂类，负责构建 DOM 结构，处理较为复杂的结构生成。 |
| PopupsSkin | Popups 皮肤类，负责管理样式。 |

### Popups
Popups 主类，负责管理 Popups 的基本属性和行为。

#### 属性
| 名称 | 类型 | 用途 |
|-----|------|-----|
| id | String | Popups 在 DOM 中的 ID。 |
| $sel | String | 通过 JQuery 选择器找到 Popups 需要用到的选择器语句。 |
| state | Number | Popups 的状态。0 代表隐藏，1 代表显示。 |
| timer | Number | 定时器编号。用于处理何时隐藏，何时出现。 |
| disable | Boolean | 是否暂时禁用。 |
| deactivate | Boolean | 是否在当前会话中禁用。 |
| posX | Number | 水平位置。 |
| posY | Number | 垂直位置。 |
| skin | Array<PopupsSkin> | 已获取的皮肤列表。 |
| maxWidth | Number | 最大宽度。防止 Popups 溢出可视区域，由皮肤定义。设为 0 则不做防溢出处理。 |
| maxHeight | Number | 最大高度。防止 Popups 溢出可视区域，由皮肤定义。设为 0 则不做防溢出处理。 |

### PopupsFactory
Popups 工厂类，负责构建 DOM 结构，处理较为复杂的结构生成。

#### 属性
| 名称 | 类型 | 用途 |
|-----|------|-----|
| id | String | Popups 在 DOM 中的 ID。 |
| $sel | String | 通过 JQuery 选择器找到 Popups 需要用到的选择器语句。 |

### PopupsSkin
Popups 皮肤类，负责管理样式。

#### 属性
| 名称 | 类型 | 用途 |
|-----|------|-----|
| name | String | 皮肤名称。 |
| styleSheets | Array<String> | 样式表。直接写入 CSS 样式即可，数组中的字符串会以空格相连接。 |
| maxWidth | Number | Popups 的最大宽度。 |
| maxHeight | Number | Popups 的最大高度。 |
