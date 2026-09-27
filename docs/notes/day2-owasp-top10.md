# Day 2｜OWASP Top 10 逐个拆解

一句话结论：Web 漏洞的学习重点不是背名称，而是能说明入口、危害、最小验证和修复方法。

## 1. OWASP Top 10 快速表

| 风险 | 一句话原理 | 最小验证思路 | 防护 |
|---|---|---|---|
| Broken Access Control | 用户能访问无权限资源 | 修改对象 ID | 服务端鉴权、默认拒绝 |
| Cryptographic Failures | 敏感数据未正确加密 | 检查明文传输 | TLS、密钥管理 |
| Injection | 用户输入被当成命令执行 | 输入构造符 | 参数化查询、输入校验 |
| Insecure Design | 设计阶段缺少安全控制 | 绕过业务流程 | 威胁建模、限流 |
| Security Misconfiguration | 默认配置或权限过宽 | 检查目录和默认账号 | 基线加固 |
| Vulnerable Components | 依赖版本存在已知漏洞 | 扫描组件版本 | SCA、升级 |
| Authentication Failures | 认证机制可绕过 | 弱密码、会话固定 | MFA、会话轮换 |
| Integrity Failures | 更新或反序列化不可信 | 篡改对象 | 签名校验 |
| Logging Failures | 缺少日志和监控 | 检查关键事件记录 | 集中审计 |
| SSRF | 服务端被诱导访问内部资源 | 提交可控 URL | 白名单、网络隔离 |

## 2. 最小复现示例

### SQL 注入

只在本地 DVWA 或授权靶场使用：

```sql
1' OR '1'='1
```

防护重点：

```python
cursor.execute("SELECT * FROM users WHERE id = ?", (user_id,))
```

### 反射型 XSS

输入：

```html
<script>alert('xss')</script>
```

防护重点：

- 输出编码；
- 禁止把不可信输入插入 HTML；
- 使用 CSP 降低利用影响。

## 3. 可复制检查清单

- [ ] 能讲清漏洞输入点；
- [ ] 能说明攻击者目标；
- [ ] 能给出安全修复代码；
- [ ] 能说明日志中会出现什么痕迹。

## 4. 与告警分诊 POC 的关系

POC 中的 WAF 告警对应 SQL 注入尝试，钓鱼 URL 告警对应社会工程攻击。Day 5 会继续解释 IOC 命中后如何判断风险。

