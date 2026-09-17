# ThumbGlance Specifications

- 独立数据仓库，主分支 `main`，远端 `origin` 为 `https://github.com/Ethereal49/thumbglance-specifications.git`。
- CSV、README.md 与 LICENSE 位于仓库根目录；使用 CC0 数据许可，保留 UTF-8 BOM、列名、来源链接和核对日期。
- 本机位于 ThumbGlance 项目的 `specifications/`，与 `open-source/` 平级，保留独立 Git 历史，不嵌套到其他公开仓库。
- README.md 定义数据口径：只记录有来源的规格，未说明值保留为未说明，不加入模拟设备尺寸；不要用 `../site/dist/` 或 `../operations/` 的 CSV 自动覆盖。
- 修改数据时同步 README.md 的记录数、核对日期及来源说明，并检查 CSV 可解析、各行列数一致；文档修改运行 `git diff --check`。
- 不提交凭据、个人账号信息或生成产物；普通推送后核对远端 SHA，不强推。
- 独立克隆不依赖本机兄弟目录。GitHub 推送不代表 Hugging Face、Zenodo 或生产站已同步。
