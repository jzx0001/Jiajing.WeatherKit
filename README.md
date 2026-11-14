# Jiajing.WeatherKit · 李佳静（老婆）定制版

> 李佳静（老婆）定制只给老公一人专用的，其他人只能用公共版 iRingo WeatherKit β 模块：零配置、AQI 美标、天气数据透传（修体感温度）

## 两个版本

- **老公专用定制版（v2.1.0「两全版」）**：只给老公一人专用，功能最全——在公共版基础上另有体感温度守卫回填、分钟降水文案兜底。**不提供公开安装。**
- **公共版（v1.0.0「透传版」）**：给其他朋友用的版本——零配置、AQI 美标、天气数据透传修复体感温度，安装地址见下节。两个版本在 Surge 里显示名、分类、文件名、版本号各不相同，不会装混。

## 公共版安装

Surge，模块，HTTPS 解密

**安装路径**：配置 > 模块 > 右上角加号

**模块地址**：

`https://raw.githubusercontent.com/jzx0001/Jiajing.WeatherKit/main/modules/Jiajing.WeatherKit.public.sgmodule`

安装后在模块列表中点「更新」，即可同步本仓库的最新提交。

## 定制内容（两版共有）

- 基于 `iRingo WeatherKit` **dev 版**模块定制（原版见文末链接），定制与维护：李佳静（老婆）
- `[天气] 数据源`：`WeatherKit`（保留 Apple 原始天气数据，不再由彩云替换）
- `[今日空气指数] 数据源`：彩云天气美标指数 `ColorfulCloudsUS`，替换目标仍为中国标准条目——天气 App 显示的即为美标数值与等级
- `[储存] 配置类型`：`Argument`（dev 版默认为 `PersistentStore`，会导致 Surge 里改的参数不生效）
- **参数内置**：全部参数已写死进脚本，模块不再带参数区，Surge 里不会再出现显示不全的参数页
- **天气数据透传**：响应脚本不再处理「当前天气」「逐时预报」「每日预报」三块数据，原样透传 Apple 原始数据——体感温度就是在脚本重组这三块数据时被丢掉的；「空气质量」「未来一小时降水」「天气预警」仍由脚本处理

## 专用版独有（v2.1.0）

- **两全守卫**：对彩云处理后的「当前天气」做字段级守卫回填——彩云缺失的字段（如沿海/海岛网格缺失的体感温度）自动用 Apple 原值补回，两边数据取长补短
- **分钟降水文案兜底**：降水形态在窗口尾沿翻转时，摘要文案按实际降水段重建，不再出现「有柱子没文字」

## 修改记录

见本仓库提交历史：

1. 原版：iRingo WeatherKit β dev 模块（未改动）
2. 参数修正：天气数据源=WeatherKit，AQI 指数=彩云美标，储存=Argument
3. 零配置版：参数全部焊死进脚本，删掉参数区
4. 天气数据透传：修体感温度丢失，AQI/降水/预警不变
5. v2.0.0 两全版（专用版）：字段守卫回填＋分钟降水文案兜底，模块更名为 `Jiajing.Loves.Jianbo.WeatherKit.sgmodule`
6. 双版本并行：公共版 v1.0.0 独立发布（文件 `Jiajing.WeatherKit.public.sgmodule`，脚本自托管于本账号 Gist，与专用版完全解耦）
7. v2.1.0（专用版）：下一小时降水改走和风分钟级预报（经自家 /minutely 代理取数），分钟雨卡转正；其余两全版能力不变

## 原版

- 模块原版（VirgilClyne）：https://gist.githubusercontent.com/VirgilClyne/862db28df04be7523476d10b61b128f2/raw/iRingo.WeatherKit.dev.sgmodule
- 官方项目（NSRingo/WeatherKit）：https://github.com/NSRingo/WeatherKit

## 版本与分支
- `main`：正式线，含专用版与公共版两个模块文件。
- `dev`：试验线，候选版先上 dev 逐项验收，通过后再合并进 main。
- 发行版：v2.1.0「两全版」（专用版现行，分钟雨转正）；v2.0.0「两全版」（历史）；v1.0.0「天气透传版」（历史）；public-v1.0.0「公共版」。
