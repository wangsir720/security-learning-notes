# Day 6｜MITRE ATT&CK 入门与映射实践

一句话结论：ATT&CK 让告警从孤立日志变成可讨论的攻击行为链。

## 1. 三层结构

- Tactics：攻击者想达到什么目标；
- Techniques：攻击者用什么方法；
- Sub-techniques：方法的具体变体。

## 2. 常见告警映射

| 场景 | Technique |
|---|---|
| 钓鱼链接点击 | T1566 Phishing |
| C2 外联 | T1071 Application Layer Protocol |
| 凭据转储 | T1003 OS Credential Dumping |
| 网络扫描 | T1046 Network Service Discovery |
| 勒索加密 | T1486 Data Encrypted for Impact |
| 暴力破解 | T1110 Brute Force |

## 3. 映射步骤

1. 识别告警行为；
2. 判断攻击战术；
3. 选择技术编号；
4. 记录置信度和证据；
5. 把映射写回报告。

## 4. 与告警分诊 POC 的关系

`src/alert_triage/mitre.py` 会根据情报标签映射技术编号，最终写入 JSON 和 Markdown 报告。

