# my-clash-rules

自用 Clash / mihomo 规则集。

## 目录

| 文件 | behavior | 用途 |
|---|---|---|
| `rules/emby.yaml` | domain | Emby 相关域名 |

## 使用方式

```yaml
rule-providers:
  emby:
    type: http
    behavior: domain
    format: yaml
    url: https://raw.githubusercontent.com/zdyfj0228-cmyk/my-clash-rules/main/rules/emby.yaml
    path: ./rules/emby.yaml
    interval: 86400

rules:
  - RULE-SET,emby,Emby 专业
```

## 格式说明

`behavior: domain` 的 yaml 规则写在 `payload:` 下，每行一个域名：

- `+.example.com` — 等价于 `DOMAIN-SUFFIX`，匹配该域名及其所有子域
- `example.com` — 仅精确匹配该域名

注意缩进必须正确。yaml 解析失败时会静默跳过该行而不报错，更新后请核对 provider 的规则计数。
