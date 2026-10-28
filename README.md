# my-clash-rules

自用 Clash / mihomo 规则集。

## 目录

| 文件 | behavior | 用途 |
|---|---|---|
| `rules/emby.txt` | domain | Emby 相关域名 |

## 使用方式

```yaml
rule-providers:
  emby:
    type: http
    behavior: domain
    format: text
    url: https://raw.githubusercontent.com/kris-2-call/my-clash-rules/main/rules/emby.txt
    path: ./rules/emby.txt
    interval: 86400

rules:
  - RULE-SET,emby,DE Aiyun
```

## 格式说明

`behavior: domain` 的 text 规则每行一个域名：

- `+.example.com` — 等价于 `DOMAIN-SUFFIX`，匹配该域名及其所有子域
- `example.com` — 仅精确匹配该域名
