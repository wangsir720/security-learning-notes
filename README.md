# 安全学习笔记：从基础概念到告警分诊 POC

这是一套面向安全售前、SOC 初级分析和安全应用开发学习者的实践笔记。

笔记采用“教程优先”的写法，不记录每天做了什么，而是让另一个刚入门的人能够照着复现、验证和理解。

## 学习主题

1. 企业安全设备部署地图
2. OWASP Top 10 原理、最小复现和防护
3. 等保 2.0 从合规条文到采购清单
4. DVWA 本地靶场：SQL 注入、XSS、文件上传
5. 威胁情报如何从一条 IOC 变成处置决策
6. MITRE ATT&CK 入门与告警映射
7. 售前视角：把安全技术讲成业务价值

## 目录

```text
docs/
  notes/
    day1-security-device-map.md
    day2-owasp-top10.md
    day3-dengbao-2.0.md
    day4-lab-reproduction.md
    day5-threat-intel-in-practice.md
    day6-mitre-attack-mapping.md
    day7-presales-value-translation.md
  KNOWN_ISSUES.md
lab/
  docker-compose.yml
assets/
  screenshots/
```

## 与安全告警分诊 POC 的关系

这套笔记不是孤立学习资料，而是用于解释并支撑另一个项目：

[security-alert-triage-poc](https://github.com/wangsir720/security-alert-triage-poc)

- Day 1 说明告警进入 SOC 后的位置；
- Day 2 说明 Web 漏洞告警的来源；
- Day 3 解释合规与日志留痕；
- Day 4 提供本地漏洞复现证据；
- Day 5 解释 IOC 富化和风险评分；
- Day 6 解释 MITRE ATT&CK 映射；
- Day 7 解释如何将技术指标翻译成业务价值。

## 使用方式

每篇笔记都包含：

- 背景和核心结论；
- 图表、表格或命令；
- 可复制的检查清单；
- 常见坑；
- 与告警分诊 POC 的关联。

## 安全边界

- 所有靶场实验只在本地或授权的隔离环境中运行；
- 不包含真实客户、真实资产、真实漏洞利用目标和生产数据；
- 不提供对公网目标进行攻击的步骤；
- 示例 IP 使用 RFC 5737 文档保留地址，域名使用 `.example`。

## 参考方法

- OWASP Top 10
- MITRE ATT&CK
- NIST 网络安全框架
- 等保 2.0 公开资料
- Wazuh、Suricata、DVWA 官方文档

