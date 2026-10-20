# 天天货运记账 · 更新发布仓库

这个仓库**只放安装包和版本信息**，用于 App 的应用内更新检测。源码在私有仓库 `tiantian-jizhang`。

## 访问地址

- 下载页：https://jz.ffoo.top/
- 版本信息：https://jz.ffoo.top/version.json
- 安装包：https://jz.ffoo.top/app.apk

托管在腾讯 EdgeOne Pages：推送 `main` 分支后自动重新部署，约 1 分钟生效。

## 发新版（三步）

1. 把新 APK 覆盖到 `app.apk`
2. 改 `version.json`：
   - `version`：版本号，必须比上一版大（App 靠它判断要不要弹窗）
   - `versionCode`：整数，每次 +1
   - `size`：安装包大小，随便写个近似值，只用于页面展示
   - `notes`：更新说明，一行一条
   - `force`：`true` 表示强制更新，用户点「稍后」也躲不过
   - `history`：历史版本列表，页面底部展示
3. `git add -A && git commit -m "release 1.0.5" && git push`

推送后 EdgeOne 会自动重新部署，1 分钟左右生效，用户打开 App 就会收到提示。

## 注意

- 安装包必须用同一份签名密钥（`tiantian-jizhang/android/keystore/tiantian.jks`）打包，否则老用户覆盖安装会失败
- 这个仓库是公开的，不要往这里放任何源码或密钥
