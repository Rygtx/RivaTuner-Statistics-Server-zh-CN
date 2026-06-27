# RivaTuner Statistics Server 简体中文语言包

本项目为 RivaTuner Statistics Server (RTSS) 的简体中文本地化语言包，基于 RTMUI 本地化引擎 v1.2 规范实现，采用翻译数据库方式进行界面与帮助文本的本地化。

## 适配软件版本

| 项目 | 说明 |
|---|---|
| 适配软件 | RivaTuner Statistics Server |
| 兼容版本 | **7.3.x 系列**（含 7.3.7 及以上） |
| 本地化规范 | RTMUI Localization Reference v1.2 |
| 语言代码 | CHN |
| 代码页 | 936 (GBK) |
| 文本编码 | GBK / CP936 |
| 行结束符 | CRLF |

> 翻译内容覆盖 7.3.x 引入的特性，包括 NVIDIA Reflex 延迟标记与休眠模式、1% / 0.1% 最低帧率百分位计算、编码器服务器、帧时间历史等。后续 RTSS 小版本更新若未改动源文本，本语言包可继续兼容。

## 安装方法

1. 将本项目根目录下的 `Localization\CHN\` 整个文件夹复制到 RTSS 安装目录下的 `Localization\` 子文件夹中（若该文件夹不存在则新建）。
2. 启动 RTSS，进入 **设置 → 用户界面** 选项卡。
3. 在 **语言** 下拉列表中选择 **简体中文**。
4. 点击 **确定** 后重启 RTSS，界面与帮助提示即切换为简体中文。

## 目录结构

```
.
├── README.md                           # 本说明文件
├── .gitignore                          # Git 忽略规则
├── SDK/
│   └── Doc/
│       └── Localization reference.md   # RTMUI 本地化规范文档
└── Localization/
    └── CHN/                            # 简体中文语言包根目录
        ├── Description                 # 语言包描述（语言名、图标、代码页）
        ├── zhcn.ico                    # 语言图标
        ├── Help/                       # 上下文帮助文件（87 个）
        │   ├── BUTTON_*                # 按钮提示
        │   ├── PLACEHOLDER_*           # 占位符提示
        │   ├── SLIDER_*                # 滑块提示
        │   ├── TEXT_*                  # 文本提示
        │   └── Properties/
        │       ├── General/            # 常规属性提示（31 个）
        │       └── User interface/     # 用户界面属性提示（7 个）
        └── Translation/                # 翻译数据库（23 个文件）
            ├── RTSS.exe/               # 主程序翻译
            │   ├── StringTable         # 字符串表
            │   ├── Dialogs             # 对话框
            │   └── Menus               # 菜单
            ├── SaveMedia.dll/          # 媒体保存模块
            │   ├── Internal
            │   └── Dialogs
            ├── Plugins/
            │   ├── Client/
            │   │   ├── HotkeyHandler.dll/   # 热键处理插件
            │   │   │   ├── Internal
            │   │   │   └── Dialogs
            │   │   └── OverlayEditor.dll/  # 叠加层编辑器插件
            │   │       ├── Internal
            │   │       ├── Dialogs
            │   │       ├── Menus
            │   │       └── StringTable
            │   ├── NVENC.dll/           # NVIDIA NVENC 编码器
            │   ├── QSV.dll/             # Intel Quick Sync Video 编码器
            │   ├── VCE.dll/             # AMD VCE 编码器
            │   └── VCEAMF.dll/          # AMD VCE AMF 编码器
            └── Localization/           # 其他语言名称翻译
                ├── BUL/Description      # 保加利亚语
                ├── CHN/Description      # 简体中文（自描述）
                ├── DUT/Description      # 荷兰语
                ├── FR/Description       # 法语
                ├── GER/Description      # 德语
                ├── ITA/Description      # 意大利语
                ├── KOR/Description      # 韩语
                ├── POL/Description      # 波兰语
                ├── PTBR/Description     # 葡萄牙语（巴西）
                ├── RUS/Description      # 俄语
                ├── SPA/Description      # 西班牙语
                └── UKR/Description      # 乌克兰语
```

## 文件统计

| 类别 | 数量 |
|---|---|
| Description 描述文件 | 1 |
| 帮助文件 (Help) | 87 |
| 翻译数据库文件 (Translation) | 31 |
| 图标文件 | 1 |
| **合计** | **120** |

> 翻译数据库共包含约 600 条 `#src/#dst/#end` 翻译条目，覆盖 RTSS 主程序、媒体保存模块、热键处理与叠加层编辑器插件以及四款视频编码器插件。

## 翻译规范

本语言包严格遵循 `SDK\Doc\Localization reference.md` 中规定的翻译规范：

- **翻译方式**：逐字手动翻译，未使用机器翻译
- **格式说明符**：完整保留 `%s`、`%d`、`%PRODUCTNAME%`、`%I64u`、`%d%%`、`\n`、`\t` 等占位符的原始顺序与位置
- **特殊 Token**：保留 `#dlu -100`（重置缓存按钮宽度调整）与 `#hst Menu`（叠加层编辑器菜单专用翻译）
- **术语统一**：核心术语在主程序、插件与帮助文件中保持一致（如 framerate → 帧率、frametime → 帧时间、overlay → 叠加层、benchmark → 基准测试、profile → 配置文件、On-Screen Display → 屏显等）
- **编码格式**：所有文本文件采用 GBK (CP936) 编码，CRLF 行结束符

## 版本更新

当 RTSS 发布新版本时，可通过 RTMUI 内置的语言包对比功能检测变更：

1. 在 RTSS 高级属性中选择 **简体中文** 作为当前语言
2. 在 RTSS 安装根目录执行命令：`RTSS.exe /CL RUS`
3. 程序将生成 `.\Localization\LocalizationDifferences.log` 报告文件
4. 根据报告中的以下章节进行更新：
   - `Searching for changed translated files` — 需要修改的文件
   - `Searching for RUS pack translated files missing in CHN pack` — 需要新增的文件
   - `Searching for CHN pack translated files missing in RUS pack` — 需要移除的废弃文件
   - `Searching for RUS pack translation database entries missing in CHN pack` — 需要新增的翻译条目
   - `Searching for CHN pack translation database entries missing in RUS pack` — 需要移除的废弃条目

> 俄语语言包 (RUS) 作为官方随附的样本语言包始终保持最新，可作为对比基准。

## 许可说明

本语言包为社区贡献的非官方本地化作品，仅用于 RTSS 界面翻译。RivaTuner Statistics Server 及其所有商标归原版权所有者所有。
