# Cloudflare 中国大陆 IP 列表/ Cloudflare China Mainland IP List

用于Shadowrocket/Clash 分流与规则匹配的自动更新 Cloudflare 中国大陆 IP 列表。
Auto-updated Cloudflare China Mainland IP list for use in Shadowrocket/Clash routing and rule matching.

---

## How to Use Shadowrocket & Clash / 在 Shadowrocket 与 Clash 中使用

### File Link / 文件链接

- **Raw File Link / Raw 原始链接:**  
  `https://raw.githubusercontent.com/Aaakul/cf-cn-ip-list/main/Clash/cf_cn_ip.txt`
- **CDN Proxy Link / 加速代理链接:**  
  `https://cdn.jsdelivr.net/gh/Aaakul/cf-cn-ip-list/main/Clash/cf_cn_ip.txt`

---

### Using in Shadowrocket (小火箭)

Shadowrocket supports importing rule sets via URL or converting them into rule files.

Shadowrocket 支持通过远程 URL 导入规则集，或将其挂载到配置文件中。

1. Open **Shadowrocket** -> Go to **Config** (配置).
2. Tap the active config (`default.conf` or your active profile) -> Select **Edit Config** (编辑配置) or **Add Rule** (添加规则).
3. Select **Rule Type**: `RULE-SET`
4. Enter the Raw URL:
   `https://raw.githubusercontent.com/Aaakul/cf-cn-ip-list/main/Clash/cf_cn_ip.txt`
5. Select the desired Policy (e.g., `DIRECT` or `PROXY`).
6. Save and update the configuration.

---

### Using in Clash

```yaml
# 1. Define the Rule Provider / 定义规则提供者
rule-providers:
  cf_cn_ip:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Aaakul/cf-cn-ip-list/main/Clash/cf_cn_ip.txt"
    path: ./rules/cf_cn_ip.yaml
    interval: 86400

# 2. Reference in Rules / 在规则区域引用
rules:
  - RULE-SET,cf_cn_ip,DIRECT
  # - RULE-SET,cf_cn_ip,PROXY
```
