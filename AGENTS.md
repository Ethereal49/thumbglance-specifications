# 规格数据开发规范

位于 ThumbGlance 工作区时继承 `../AGENTS.md`；独立克隆时不依赖本机兄弟目录。

## 数据与来源
- CSV、README.md、LICENSE 位于仓库根目录；保留 CC0 许可、UTF-8 BOM、既有换行、列名、来源链接及核对日期。
- README.md 定义数据口径：仅记录有官方来源支持的规格；未说明的值保持未说明，不补充模拟尺寸或设备测量推断。
- 修改规格前重新核对对应官方来源；仅在实际完成核对后更新日期，不把历史快照表述为当前平台保证。
- 不用 `../site/dist/` 或 `../operations/` 的 CSV 自动覆盖数据；生产 banner CSV 中的模拟尺寸不属于本数据集。
- 数据变更同步 README.md 的记录数、来源、验证方式及限制；变更列名或数据配置时同时检查 README.md 中的数据集配置。

## 验证
- 文档变更运行 `git diff --check`；CSV 变更检查 BOM、解析结果、各行列数及 README.md 记录数，并逐项对照来源。
- 在仓库根目录执行最小结构检查：
```sh
python3 - <<'PYCSV'
import csv
from pathlib import Path
for path in Path('.').glob('*.csv'):
    assert path.read_bytes().startswith(b'\xef\xbb\xbf'), path
    with path.open(encoding='utf-8-sig', newline='') as stream:
        rows = list(csv.reader(stream))
    assert len(rows) > 1 and all(len(row) == len(rows[0]) for row in rows), path
    print(path.name, len(rows) - 1, 'records')
PYCSV
```
- 结构校验不能替代来源核对；未完成来源复核不得声称数据已更新验证。

## 仓库与发布
- `main`，`origin`: `https://github.com/Ethereal49/thumbglance-specifications.git`。
- 本机目录为 `specifications/`，与 `open-source/` 平级，保留独立 Git 历史，不嵌套到其他公开仓库。
- 不提交凭据、个人账号信息或生成产物；提交前检查暂存差异，普通推送后核对远端 SHA，不强推。
- GitHub、Hugging Face、Zenodo 与生产站分别发布、分别验证；一个平台成功不表示其他平台已同步。
