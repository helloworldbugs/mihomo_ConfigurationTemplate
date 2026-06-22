# mihomo_ConfigurationTemplate

# 说明

基于 mihomo 官方配置模板修改，在重要字段添加了中文注释便于理解与学习。参考了多位大佬的配置，增加了一些优化项。

## 四份配置文件的区别

| 配置文件 | 说明 | 特点 |
|---|---|---|
| 本地GeoData.yaml | 本地数据库解析，适合网络不好的环境。每24小时更新一次数据库，即使更新失败也不影响使用。稳定性好，但数据库文件大、格式老旧、解析速度一般，官方已不推荐 | 速度：⭐⭐⭐ 稳定：⭐⭐⭐⭐⭐ |
| 在线rule-set.yaml | 在线 MRS 规则库解析域名和 IP。每次启动缓存到本地，MRS 文件小、解析快。适合网络良好的环境，速度最快 | 速度：⭐⭐⭐⭐⭐ 稳定：⭐⭐ |
| 在线mrsDomain+本地mmdbIP混合解析.yaml | 在线 MRS 域名库 + 本地 mmdb IP 库混合解析，平衡速度和稳定 | 速度：⭐⭐⭐⭐ 稳定：⭐⭐⭐⭐ |
| Tproxy.yaml | TPROXY 透明代理模式，Linux 下性能最优的代理方案。使用 iptables 自动引流，适合路由器/软路由/网关环境 | 速度：⭐⭐⭐⭐⭐ 稳定：⭐⭐⭐⭐⭐ |

## 最近更新

- **fakeip-filter** 全部改为在线 MRS 规则库（`DustinWin/ruleset_geodata`），不再手动维护域名白名单
- **sniffer.skip-domain** 复用 `private_domain` 规则库，局域网/内部域名自动跳过嗅探
- **NTP 时间同步** 全部配置添加，保持系统时间准确
- **keep-alive-idle** 连接空闲超时设置
- **Tproxy.yaml** 按统一结构重排，补充完整注释和 `iptables` 自动路由

## 使用说明

1. 在 [mihomo 官网](https://github.com/MetaCubeX/mihomo) 下载所需平台的可执行内核文件
2. 选择一份配置模板，重命名为 `config.yaml`，与内核文件放在同一目录
3. 编辑 `config.yaml`，在 `proxy-providers` 段填入你的订阅链接
4. 命令行执行 `mihomo -d .` 启动（Windows 为例）
5. 访问 [后台管理面板](http://localhost:9090/ui) 进行可视化管理

> Windows 隐藏命令行窗口启动：可用 vbs 脚本或 winsw 注册为系统服务。
