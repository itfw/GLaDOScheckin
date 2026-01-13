# Checkin

GitHub Actions 实现 [GLaDOS][glados] 自动签到

([GLaDOS][glados] 可用邀请码: `MW4DK-O0RSF-C7AOU-EN1MP`, 双方都有奖励天数)

## 使用说明

1. Fork 这个仓库

1. 登录 [GLaDOS][glados] 获取 Cookie

1. 添加 Cookie 到 Secret `GLADOS`

1. 启用 Actions, 每天北京时间 00:10 自动签到

## 高级功能

1. 如有多个帐号, 可以写为多行 Secret `GLADOS`, 每行写一个 Cookie
https://private-user-images.githubusercontent.com/47891429/422682912-c2de60a4-85d5-4ba7-8a80-d63841511bf4.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjgyNzMxMDAsIm5iZiI6MTc2ODI3MjgwMCwicGF0aCI6Ii80Nzg5MTQyOS80MjI2ODI5MTItYzJkZTYwYTQtODVkNS00YmE3LThhODAtZDYzODQxNTExYmY0LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNjAxMTMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjYwMTEzVDAyNTMyMFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTRhY2RmYWZlOWJmNjA1ODZkZTI5NjBlZDJkNzJlOWNjNTgwNDAxN2NjOTIzNTA0MjJhNjVmMGI0M2ZkZjY5ZDMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.IHJbSDVNhRych04FAVLlk4tMwex0uTmE6LFjo-nNUPM


1. 如需修改时间, 可以修改文件 [run.yml](.github/workflows/run.yml#L7) 中的 `cron` 参数, 格式可参考 [crontab]

1. 如需推送通知, 可配置 Secret `NOTIFY`, 已支持:
    1. [WxPusher][wxpusher]: 格式 `wxpusher:{token}:{uid}`
    1. [PushPlus][pushplus]: 格式 `pushplus:{token}`
    1. Console: 格式 `console:log`, 作为日志输出, 一般用于调试
    1. 如需配置多个, 可以写为多行, 每行写一个

1. 注意: Cookie 以及接口输出数据, 包含帐号敏感信息, 因此不要随意公开

---

[glados]: https://github.com/glados-network/GLaDOS
[crontab]: https://crontab.guru/
[pushplus]: https://www.pushplus.plus/
[wxpusher]: https://wxpusher.zjiecode.com/
