# 阴阳师藏宝阁看号插件

作者：EMIN。

这是一个 Chrome Manifest V3 插件。它从已打开的阴阳师藏宝阁标签页读取商品数据，在独立的插件页面显示账号概览、速度盘点、PVE 预览、式神技能、御魂计算器、阵容计算器和御魂库存。

收藏夹入口目前隐藏，原收藏代码和 `yys-cbg-assistant:favorites:v1` 存储数据保留。插件不保存商品查看历史，也不需要数据库或独立服务。

## 安装

可直接使用项目同级生成的 `yys-cbg-inspector-extension.zip`，解压后在 Chrome `chrome://extensions` 打开开发者模式，点击“加载已解压的扩展程序”，选择解压目录。也可以直接选择本项目目录。

“分析当前账号”只在阴阳师藏宝阁商品详情页的右下角显示，包括站点使用的 `/cgi/mweb/equip/` 地址。点击后，插件会打开分析页并自动读取当前商品，无需再点击“读取当前商品”。也可以在分析页手动粘贴其他商品链接并点击“读取账号”。

商品读取使用当前藏宝阁标签页的登录状态。官方接口若返回风控或暂时不可用，插件会显示读取失败原因；请稍后重试。当前仅接入官服域名。

## 开发

```sh
npm install
npm run typecheck
npm run build
```

`npm run build` 会生成 `workbench/` 页面、`content/inspector.js` 和 `background/inspector.js`。静态式神与御魂资料位于 `public/data/`，随构建复制到插件中；不需要导入 SQL。原版插件已备份在项目同级的 `yys-cbg-assistant-v0.16.9-original-backup.zip`。

分析页面、计算逻辑和静态美术资源来自 `iXinMengChen/yys-cbg-inspector`，遵循其 MIT 许可证，见 `licenses/yys-cbg-inspector-MIT.txt`。
