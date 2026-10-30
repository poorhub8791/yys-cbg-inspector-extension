# 阴阳师藏宝阁看号插件

这是一个 Chrome Manifest V3 插件。它从已打开的阴阳师藏宝阁标签页读取商品数据，在独立的插件页面显示账号概览、速度盘点、PVE 预览、式神技能、御魂计算器、阵容计算器和御魂库存。

收藏夹入口目前隐藏，原收藏代码和 `yys-cbg-assistant:favorites:v1` 存储数据保留。插件不保存商品查看历史，也不需要数据库或独立服务。

## 安装

1. 在本仓库页面点击 **Code → Download ZIP**，或[直接下载 main 分支 ZIP](https://github.com/poorhub8791/yys-cbg-inspector-extension/archive/refs/heads/main.zip)。
2. 将 ZIP 解压到一个固定目录。安装后请保留该目录，浏览器需要从中加载插件文件。
3. 在 Chrome 地址栏输入 `chrome://extensions`，打开右上角的“开发者模式”。
4. 点击“加载已解压的扩展程序”，选择解压后包含 `manifest.json` 的 `yys-cbg-inspector-extension-main` 目录。
5. 确认扩展列表中出现“阴阳师藏宝阁账号分析”，即安装完成。

仓库已包含可直接加载的插件文件，无需安装 Node.js、运行构建命令或配置数据库。

## 使用

1. 打开[阴阳师藏宝阁](https://yys.cbg.163.com/)，按需登录后进入商品详情页。安装插件前已打开的页面需先刷新。
2. 点击商品详情页右下角的“分析当前账号”，插件会打开分析页并自动读取当前商品。
3. 在分析页查看账号概览、速度盘点、PVE 预览、式神技能、御魂计算器、阵容计算器和御魂库存。也可以手动粘贴其他商品链接，点击“读取账号”进行分析。

“分析当前账号”入口只在阴阳师藏宝阁商品详情页显示，支持站点使用的 `/cgi/mweb/equip/` 地址。

商品读取使用当前藏宝阁标签页的登录状态。官方接口若返回风控或暂时不可用，插件会显示读取失败原因；请稍后重试。当前仅接入官服域名。

## 更新

重新下载最新的仓库 ZIP，解压后用其中的文件替换原安装目录的内容，再到 `chrome://extensions` 点击本插件的重新加载按钮，并刷新藏宝阁页面。已打开的分析页请关闭后重新打开。

## 仓库内容

当前仓库存放已构建的插件文件，不包含完整的开发源码或 npm 构建配置。`manifest.json` 是插件配置，`background/` 和 `content/` 分别包含后台脚本与页面脚本，`workbench/` 包含分析页面及静态资料。

## 参考项目与致谢

本项目参考了以下两个项目，感谢原作者的工作：

- [liyikradlee/yys-cbg-assistant-releases](https://github.com/liyikradlee/yys-cbg-assistant-releases)
- [iXinMengChen/yys-cbg-inspector](https://github.com/iXinMengChen/yys-cbg-inspector)

其中，分析页面、计算逻辑和静态美术资源来自 `iXinMengChen/yys-cbg-inspector`，遵循其 MIT 许可证，见 `licenses/yys-cbg-inspector-MIT.txt`。
