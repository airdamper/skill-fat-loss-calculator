# 💪 减脂增肌计算器 — 通用 Agent 技能包

> 一个为 AI Agent（如 Obsidian Copilot、ChatGPT、Claude 等）设计的标准化技能包。  
> 根据用户的体重、体脂率、目标（减脂/增肌/维持）和活动水平，**自动计算每日宏量营养素摄入目标**，并可生成**一周训练计划模板**。

---

## ✨ 功能特点

- **精准计算**：基于《减脂增肌技能手册》制定，蛋白质、碳水、脂肪三步到位  
- **体脂适配**：可选体脂率参数，支持瘦体重优先计算  
- **训练模板**：内置减脂期和增肌期周计划，涵盖力量、有氧、HIIT、主动恢复  
- **即装即用**：支持作为 Obsidian 笔记、Agent System Prompt 或 API 端点部署  
- **开源共享**：MIT 许可证，欢迎 Fork、PR 和个性化修改

---

## 📦 安装方式

### 🅰 作为 Obsidian 笔记（推荐）

1. 将 `obsidian-note.md` 内容复制到你的 Obsidian vault 中，新建笔记，命名为 `技能-减脂增肌计算器`
2. （可选）在 Obsidian Copilot 的 **Custom Prompt** 中加入以下触发规则：

当用户提到“减脂”、“增肌”、“营养素”、“训练计划”等关键词时，请优先搜索并遵循笔记 技能-减脂增肌计算器 中的逻辑执行。


3. 现在直接对 AI 说“70kg，减脂”，即可自动调用技能。

### 🅱 作为通用 System Prompt

1. 打开你的 Agent（ChatGPT、Claude、Gemini 等）
2. 在设置中找到 System Prompt / Custom Instructions 区域
3. 将 `agent-prompt.md` 的全部内容粘贴进去
4. 保存即可。

### 🅲 通过 URL 远程加载（适合支持 URL 访问的 Agent）

在对话开始时发送：

请阅读 https://raw.githubusercontent.com/airdamper/skill-fat-loss-calculator/main/obsidian-note.md 的内容，并按技能逻辑执行。我的参数是：体重70kg，减脂。


> 部分 Agent 不支持直接读取 raw 文件，请以方式 A 或 B 为主。

---

## 🧠 使用方法

### 触发指令示例

| 场景 | 示例指令 |
| :--- | :--- |
| 计算营养素 | “帮我算一下减脂期的营养素，体重75kg，体脂18%” |
| 生成训练计划 | “我70kg，想增肌，给个一周训练计划” |
| 简算 | “计算蛋白质和碳水，目标是维持，体重80kg” |
| 详细咨询 | “使用减脂增肌计算器，体重65kg，减脂，中等活动水平” |

### 输出示例（以 70kg 减脂为例）

| 营养素 | 每日摄入目标 | 备注 |
| :--- | :--- | :--- |
| 蛋白质 | 140g | 2.0g/kg，分3-4餐 |
| 碳水 | 140g | 2.0g/kg，练前练后为主 |
| 脂肪 | 45g | 约0.64g/kg，天然来源 |
| 估算总热量 | ≈1565 kcal | 仅供参考 |

---

## 🗂️ 仓库目录结构

```
skill-fat-loss-calculator/
├── README.md # 本文件
├── skill.json # 技能元数据（供未来自动安装工具解析）
├── agent-prompt.md # 纯文本 System Prompt 版本（可直接粘贴）
├── obsidian-note.md # Obsidian 笔记版本（含前置元数据、触发词、计算逻辑）
└── LICENSE # MIT 许可证
```


### 文件说明

| 文件 | 适用场景 |
| :--- | :--- |
| `agent-prompt.md` | 粘贴到 AI 的 System Prompt |
| `obsidian-note.md` | 粘贴到 Obsidian vault 作为笔记 |
| `skill.json` | 元数据描述，供自动化脚本或未来插件读取 |
| `README.md` | 项目说明（本文件） |

---

## 🔧 自定义指南

1. **修改系数**：如果你有自己的营养师建议，可以调整 `agent-prompt.md` 中的蛋白质系数（如减脂期改用 2.0→2.2）
2. **替换训练模板**：在 `obsidian-note.md` 第三步中替换你自己的周计划
3. **增加参数**：在 `skill.json` 的 `inputParameters` 中添加新字段（如“腰部受伤史”），并在推理逻辑中处理

---

## 🤝 贡献与反馈

欢迎通过 Issue 和 Pull Request 参与改进：

- 报告计算错误或不合理设定
- 提交新语言版本（英文 / 日文 / 韩文）
- 添加更多训练模板（如家庭徒手版、健身房版）
- 贡献安装脚本或自动化工具

---

## 📄 许可证

本项目采用 **MIT 许可证** — 你可以自由使用、修改、分发，甚至用于商业项目，只需保留原始版权声明。

---

## 🙏 致谢

- 本技能基于《减脂增肌技能手册》知识体系构建
- 感谢 [Obsidian Copilot](https://github.com/obsidian-copilot) 社区提供的启发

---

**⭐ 如果这个技能对你有帮助，请给仓库点个 Star！**