# GROMACS Interactive

一个中文交互式 Codex Skill，用于准备分子动力学体系、运行 GROMACS、排查错误和分析轨迹。MolPilot 桌面程序有独立的安装包。

## 安装

将本仓库克隆或解压到 Codex 的用户 Skill 目录，目录名使用 `gromacs-interactive`。目录内应直接包含 `SKILL.md`。Windows 默认位置为 `%USERPROFILE%\.codex\skills\gromacs-interactive`。

```powershell
git clone https://github.com/fanyutai/gromacs-interactive.git "$env:USERPROFILE\.codex\skills\gromacs-interactive"
```

在 Codex 中指定 `$gromacs-interactive` 和当前 MD 项目路径，再选择所需步骤。已经安装同名 Skill 时，可以先克隆到另一个目录检查版本。

## 工作流

- 体系检查、力场和水模型选择、拓扑维护、溶剂与离子、最小化、平衡、生产模拟和检查点续跑。
- PBC 处理、RMSD、Rg、RMSF、氢键、盐桥、FEL、最低自由能构象、通道、口袋、DSSP 和 DCCM。
- CSV 到原生 Origin 的绘图和工程回读。RMSD、Rg、RMSF 各有参考图样，支持普通折线和 WT/MUT 均值 ± 样本 SD 对照。

按模块配置 GROMACS、Python、Bash、gnuplot、VMD、PyMOL、fpocket 或 Windows Origin。先阅读 [Skill 入口](SKILL.md) 和 [项目目录规则](references/project-layout.md)。

## 测试

```powershell
python -m unittest discover -s tests
```

测试覆盖输入校验、数据转换及绘图配置。各科学程序的原生运行按对应模块单独核验。随包参考图和用户提供的原脚本保存在 `assets/`，输出目录由项目决定。

