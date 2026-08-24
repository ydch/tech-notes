# Tailscale SSH

开启 Tailscale SSH 后，其他机器登录这台机器时，只需要使用用户名和 IP，无需密码。

## 在目标机器上开启

```bash
sudo tailscale up --ssh
```

## 配置 Tailscale 控制台

随后进入 Tailscale 控制台，依次打开：

**Access controls → Policies → Tailscale SSH → Edit**

将 **Check mode** 设置为 `off`。

> 设置为 `on` 时，每次连接都需要先登录一次，并在控制台中完成授权。

控制台配置入口：[Tailscale SSH](https://console.tailscale.com/admin/acls/visual/tailscale-ssh/0/edit)

## Shadowrocket 注意事项

在 [science/shadowrocket/shadowrocket-tailscale.md](../science/shadowrocket/shadowrocket-tailscale.md) 中也提到过 Shadowrocket 使用 Tailscale 的情况。

需要注意的是，使用 auth key 创建的节点不要设置标签，否则如果目标机器没有标签，Tailscale SSH 将无法连接。
