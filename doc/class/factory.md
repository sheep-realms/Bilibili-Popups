# PopupsFactory
[< 返回 | Bilibili Popups 技术文档](../index.md)

Popups 工厂类，负责构建 DOM 结构，处理较为复杂的结构生成。

## 属性
| 名称 | 类型 | 用途 |
|-----|------|-----|
| id | String | Popups 在 DOM 中的 ID。 |
| $sel | String | 通过 JQuery 选择器找到 Popups 需要用到的选择器语句。

## url
生成URL地址。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| subdomain | String | 子域名。 | "www" |
| path | String | 地址。 | "" |

## link
生成链接DOM。
| 参数名称 | 类型 | 说明 | 默认值 |
|-----|------|-----|-----|
| url | String | URL地址。 | "" |
| text | String | 链接显示文本。 | "" |
| strClass | String | 链接的 class。 | "" |

示例：
```
link("httt://www.example.com/", "示例链接")
```

<details>
<summary>返回：</summary>

```
<a target="_blank" class="" href="httt://www.example.com/" data-url="httt://www.example.com/">示例链接</a>
```

</details>