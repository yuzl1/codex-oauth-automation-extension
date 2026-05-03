# SMSBower 改动说明

## 变更说明

本次改动主要完善了手机号验证码流程的接码配置与调试能力，重点包括：

1. 将默认接码服务端点从 `hero-sms.com` 调整为 `smsbower.page`
2. 在 sidepanel 增加手动测试接码服务商能力，便于在正式跑流程前验证配置是否可用
3. 补充手机号验证运行态同步，在验证码、当前号码、激活状态等变化时及时回传到 UI
4. 调整相关提示文案与错误识别逻辑，使日志和异常信息能够覆盖 `SMSBower` 场景
5. 更新并补充手机号验证与 sidepanel 配置相关测试

## 主要影响

- 手机号验证流程默认会走新的 SMSBower 接口地址
- sidepanel 中可以直接触发接码测试，减少排查成本
- UI 能更及时展示当前号码、验证码和接码状态变化

## 已验证

已通过以下相关测试：

- `node --test tests/phone-verification-flow.test.js`
- `node --test tests/sidepanel-phone-verification-settings.test.js`

## 备注

当前改动已推送到分支：

- `feat/smsbower-testing-sync`
