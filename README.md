# Cloudflare 中国网络 IP 列表 / Cloudflare China Mainland Network IP List

自动更新的 Cloudflare 中国网络（京东云合作网络）IP 列表。

Automatically updated Cloudflare China Mainland Network (JD Cloud) IP list

数据来源：

Source:

https://api.cloudflare.com/client/v4/ips?networks=jdcloud

---

## CIDR 列表 / CIDR List

适用于 Clash / Mihomo（`behavior: ipcidr`）

For Clash / Mihomo (`behavior: ipcidr`)

## Clash / Mihomo

```yaml
rule-providers:
  cf_china_network:
    type: http
    behavior: ipcidr
    format: text
    path: ./rules/cf_cn_ip.txt
    url: https://raw.githubusercontent.com/Aaakul/cf-cn-ip-list/main/List/cf_cn_ip.txt
    interval: 86400

rules:
  - RULE-SET,cf_china_network,DIRECT
```

## Classical 规则集 / Classical Rule Set ((`behavior: classical`))

Shadowrocket / Surge

```ini
RULE-SET,https://raw.githubusercontent.com/Aaakul/cf-cn-ip-list/main/Clash/cf_cn_ip.txt,DIRECT
```

## 更新频率 / Update Schedule

通过 GitHub Actions 每日自动更新。

Updated automatically every day via GitHub Actions.
