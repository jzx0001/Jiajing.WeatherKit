# iRingo WeatherKit β · 缪斯定制版（Surge 模块）

参考 NSRingo/WeatherKit 官方项目的组织方式建立。基于 VirgilClyne 的 iRingo WeatherKit **dev 版**模块定制。原版：
https://gist.githubusercontent.com/VirgilClyne/862db28df04be7523476d10b61b128f2/raw/iRingo.WeatherKit.dev.sgmodule

## 定制内容（详见 modules/iRingo.WeatherKit.fixed.sgmodule 的提交历史）

1. **参数修正**：天气数据源改回 `WeatherKit`（原版默认彩云替换）；今日空气指数改用彩云美标 `ColorfulCloudsUS`；储存方式改 `Argument`（dev 版默认 PersistentStore 会让 Surge 参数修改不生效）。
2. **零配置版**：全部参数焊死进脚本，删掉参数区——Surge 里不再有显示不全的参数页，装上即用。
3. **天气数据透传版**：响应脚本不再处理「当前天气 / 逐时预报 / 每日预报」三块数据（原样透传 Apple 数据），修复体感温度在脚本重组数据时丢失的问题；空气质量、下一小时降水、天气预警仍走脚本处理。

效果：AQI 显示美标指数；体感温度正常显示。

## Surge 安装 / 更新

模块地址（在 Surge 里：配置 → 模块 → ＋ → 粘贴）：
https://raw.githubusercontent.com/jzx0001/iRingo.WeatherKit.fixed/main/modules/iRingo.WeatherKit.fixed.sgmodule

以后缪斯的修改都会以提交形式出现在这里，在 Surge 里点模块「更新」即可同步。
