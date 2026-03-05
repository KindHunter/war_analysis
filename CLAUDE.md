# CLAUDE.md — war_analysis

## Repository Overview

战争分析项目（War Analysis）—— 用于分析武装冲突的态势演变，预测战争走向，并评估其对金融市场和宏观经济的影响。

## Project Structure

```
war_analysis/
├── CLAUDE.md              # AI assistant guidance (this file)
├── data/
│   ├── raw/               # 原始数据（冲突事件、市场行情、经济指标）
│   ├── processed/         # 清洗后的结构化数据
│   └── external/          # 第三方数据集快照
├── src/
│   ├── data_collection/   # 数据采集与API对接
│   ├── preprocessing/     # 数据清洗、对齐、特征工程
│   ├── conflict/          # 冲突态势分析与预测模型
│   ├── market_impact/     # 金融市场冲击评估（事件研究法等）
│   ├── macro_economy/     # 宏观经济传导机制分析
│   └── utils/             # 通用工具函数
├── notebooks/             # Jupyter 探索性分析
├── reports/               # 分析报告输出
├── tests/                 # 单元测试与集成测试
├── config/                # 配置文件（API密钥模板、参数等）
├── requirements.txt       # Python 依赖
└── README.md              # 项目说明
```

## Tech Stack

- **Language**: Python 3.10+
- **Data Processing**: pandas, numpy, geopandas
- **Modeling**: scikit-learn, statsmodels, pytorch (深度学习模型)
- **Visualization**: matplotlib, plotly, folium (地理可视化)
- **Data Storage**: SQLite / Parquet files (本地), PostgreSQL (可选)
- **Interactive**: Jupyter Notebook (探索), Streamlit (展示)
- **Testing**: pytest

## Data Sources

| 类别 | 来源 | 说明 |
|------|------|------|
| 冲突事件 | ACLED, UCDP/PRIO, GDELT | 武装冲突事件数据库 |
| 金融市场 | Yahoo Finance, FRED | 股指、大宗商品、汇率、债券 |
| 宏观经济 | IMF, World Bank, 各国央行 | GDP、通胀、贸易、财政 |
| 地缘政治 | 联合国决议、制裁数据库 | 政策与制裁变动 |
| 舆情情绪 | 新闻API, GDELT Tone | 市场恐慌、舆论情绪 |

## Analysis Modules

### 1. 冲突态势分析 (`src/conflict/`)
- 冲突事件时间序列分析
- 冲突强度与扩散预测
- 参与方实力对比与博弈建模
- 历史冲突模式匹配

### 2. 金融市场冲击 (`src/market_impact/`)
- 事件研究法 (Event Study) — 冲突事件对资产价格的短期冲击
- 波动率分析 — VIX、隐含波动率与冲突关联
- 大宗商品传导 — 能源、粮食、金属价格响应
- 资本流动 — 避险资产轮动、新兴市场资金外流

### 3. 宏观经济影响 (`src/macro_economy/`)
- 供应链中断评估
- 通胀传导路径
- 贸易格局重塑
- 战后重建经济效应

## Development Workflow

### Branching

- 默认分支用于稳定、已审查的代码
- 功能分支命名: `feature/<description>` 或 `claude/<session-id>`

### Commits

- 使用清晰描述性的提交信息
- 每次提交聚焦于单一逻辑变更

### Running Tests

```bash
pytest tests/
```

### Code Style

- 遵循 PEP 8
- 使用类型注解 (type hints)
- 模块和函数需包含 docstring

## Conventions for AI Assistants

- 修改前先阅读现有代码，理解上下文
- 不引入不必要的依赖
- 遵循已有的编码风格
- 变更聚焦于当前任务，避免过度工程
- **禁止提交 API 密钥、凭证或敏感数据** — 使用环境变量或 config 模板
- data/raw/ 和 data/external/ 中的大文件应加入 .gitignore
- 分析结论需注明数据来源和时间范围
- 金融预测相关输出应包含风险声明
