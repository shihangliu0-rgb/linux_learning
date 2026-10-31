# 03 SSH 连接远程开发

> 目标：在 Windows 上通过 SSH 直接操作板卡，配合 VS Code 做远程开发。
> 前提：板卡已联网，见 [02 连接网络](02连接网络.md)。
> 状态：**待补充**，下面先列提纲，操作完按实际结果填。

## 待记录

- [ ] 板卡默认用户名、密码；如何改密码（`passwd`）
- [ ] Windows 上首次连接：`ssh 用户名@板卡IP`，确认指纹
- [ ] 配置免密登录（`ssh-keygen` 生成密钥 + 拷贝公钥到板卡）
- [ ] VS Code 远程连接（Remote - SSH 插件）
- [ ] 常用排错：
  - `Connection refused` —— sshd 没起，或端口不对
  - `Permission denied` —— 用户名/密码错误
  - 主机密钥变更（重烧系统后会出现）

## 命令速查

```bash
ssh 用户名@板卡IP          # 远程登录
scp 本地文件 用户名@IP:/路径   # 传文件
```

## 备注

板卡重新烧录后 SSH 指纹会变，Windows 侧需要清掉旧的 known_hosts 记录：

```powershell
ssh-keygen -R 板卡IP
```
