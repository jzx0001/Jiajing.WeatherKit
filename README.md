#  iRingo: 🌤️ WeatherKit β · 李佳静（老婆）定制版

## 简介

- 基于 `iRingo WeatherKit` **dev 版**模块定制（原版见文末链接）
- 修复「体感温度」不显示
- 「空气质量指数」改为美国标准显示
- 零配置：全部参数已内置，安装后无需任何设置
- 定制与维护：李佳静（老婆）

## 定制内容

- `[天气] 数据源`：`WeatherKit`（保留 Apple 原始天气数据，不再由彩云替换）
- `[今日空气指数] 数据源`：彩云天气美标指数 `ColorfulCloudsUS`，替换目标仍为中国标准条目——天气 App 显示的即为美标数值与等级
- `[储存] 配置类型`：`Argument`（dev 版默认为 `PersistentStore`，会导致 Surge 里改的参数不生效）
- **参数内置**：全部参数已写死进脚本，模块不再带参数区，Surge 里不会再出现显示不全的参数页
- **天气数据透传**：响应脚本不再处理「当前天气」「逐时预报」「每日预报」三块数据，原样透传 Apple 原始数据——体感温度就是在脚本重组这三块数据时被丢掉的；「空气质量」「未来一小时降水」「天气预警」仍由脚本处理

## 修改记录

见 `modules/iRingo.WeatherKit.fixed.sgmodule` 的提交历史：

1. 原版：iRingo WeatherKit β dev 模块（未改动）
2. 参数修正：天气数据源=WeatherKit，AQI 指数=彩云美标，储存=Argument
3. 零配置版：参数全部焊死进脚本，删掉参数区
4. 天气数据透传：修体感温度丢失，AQI/降水/预警不变

## 安装链接

Surge，模块，HTTPS 解密

---

**安装路径**

配置 > 模块 > 右上角加号

**模块地址**

`https://raw.githubusercontent.com/jzx0001/Jiajing.WeatherKit/main/modules/Jiajing.Loves.Jianbo.WeatherKit.sgmodule`

安装后在模块列表中点「更新」，即可同步本仓库的最新提交。

## 原版

- 模块原版（VirgilClyne）：https://gist.githubusercontent.com/VirgilClyne/862db28df04be7523476d10b61b128f2/raw/iRingo.WeatherKit.dev.sgmodule
- 官方项目（NSRingo/WeatherKit）：https://github.com/NSRingo/WeatherKit

## 版本与分支
- `main`：正式线，Surge 安装/更新走这条线的 raw 链接。
- `dev`：试验线，候选版先上 dev 逐项验收，通过后再合并进 main。
- 发行版：v1.0.0「天气透传版（首个正式版）」已发布；v2.0.0 预留给「背景＋体感」两全版，验收通过再发。
