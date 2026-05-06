[English](./README.md)

# Awesome Agent & Embodied Memory 🤖🧠 [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

## 📖 目录
- [基础理论与综述](#基础理论与综述)
- [通用AI智能体记忆框架](#通用ai智能体记忆框架)
- [具身AI专用记忆](#具身ai专用记忆)
- [时空与语义地图](#时空与语义地图)
- [世界模型与状态预测](#世界模型与状态预测)
- [记忆剪枝与抽象](#记忆剪枝与抽象)  *[针对全模态巨大状态量的关键板块]*
- [基准测试与评估](#基准测试与评估)
- [基础设施与数据库](#基础设施与数据库)
- [相关列表与灵感来源](#相关列表与灵感来源)

---


## 基础理论与综述
*深入探索智能体记忆背后的认知科学和架构理论。*

- [**基于LLM的智能体记忆综述**](https://arxiv.org/abs/2411.13555) - 对机制、评估和架构的全面综述。
- [**智能体记忆 Awesome 资源库**](https://github.com/TsinghuaC3I/Awesome-Memory-for-Agents) - 这是一个专门收集语言智能体（Language Agents）记忆相关论文的 Awesome List 仓库。它系统整理了 Agent Memory 领域的研究文献，涵盖 Reflection、长期记忆、认知架构等核心机制，为研究人员和开发者提供了全面的文献索引与参考。该列表直接聚焦 Agent Memory 主题，与具身智能记忆、LLM 长期记忆等方向紧密关联，适合 AI Agent 开发者快速获取前沿研究资源。
- [**大语言模型智能体记忆演化综述列表**](https://github.com/FeishuLuo/Evolving-LLM-Agent-Memory-Survey) - 该仓库提供了一篇关于大语言模型智能体记忆机制演化的综述论文列表，系统梳理了从存储到体验的记忆技术发展脉络。它直接聚焦于 Agent Memory 主题，涵盖了反思、自进化等关键记忆机制，是研究人员和开发者了解该领域前沿工作的综合性资源。
- [**具身 AI 世界模型综合调查**](https://github.com/Li-Zn-H/AwesomeWorldModels) - 该项目是一个关于具身 AI 世界模型的综合调查列表，系统收集了世界模型相关的论文、代码和资源。世界模型作为具身智能体对环境状态进行建模和预测的核心机制，与 Agent Memory 中的状态记忆、预测记忆和世界知识记忆高度相关。该列表涵盖了多种记忆相关技术，如隐状态记忆、递归神经网络、Transformer 记忆等，为研究具身智能体长期记忆和状态抽象提供了重要参考。适合 AI Agent 和具身记忆领域的研究者与开发者。
- [**知即构建：面向智能体记忆的模式约束生成**](http://arxiv.org/abs/2604.20117v1) - 提出 SCG-MEM 架构，将 Agent Memory 访问重构为模式约束生成，替代传统密集检索，从根本上避免结构幻觉。通过动态认知模式、同化-顺应更新机制及关联图，实现无噪声、可泛化的长期记忆管理。
- [**连续性层：为何智能需要承载前向信息的架构**](http://arxiv.org/abs/2604.17273v1) - 本论文提出“连续性层（Continuity Layer）”作为 AI 架构中缺失的关键组件，解决模型跨会话的记忆遗忘问题。其核心贡献是定义了一种名为“分解轨迹收敛记忆（Decomposed Trace Convergence Memory）”的存储原语，通过写入时分解和读取时重建实现持久且自洽的跨时间记忆，并配套 ATANT 基准框架评估该属性。该工作直接针对 Agent Memory 中的长期记忆连续性挑战，为构建具身智能体的认知架构提供了基础设施层面的设计方案。
- [**LLM 智能体长期记忆安全综述：迈向记忆主权**](http://arxiv.org/abs/2604.16548v1) - 该综述首次从安全视角系统研究 LLM Agent 长期记忆，提出记忆生命周期六阶段框架（写入、存储、检索、执行、共享、遗忘/回滚），并交叉分析完整性、机密性、可用性、治理四大安全目标。论文揭示现有研究集中于写入/检索阶段的完整性攻击，而机密性、存储、遗忘及良性持久失效问题鲜有探索，且无架构覆盖全部九种治理原语。这项工作为构建安全的 Agent 记忆系统提供了理论基础与攻击面图谱。
- [**LLM 时代的记忆：统一框架下的模块化架构与策略**](http://arxiv.org/abs/2604.01707v1) - 本文提出了一个统一框架以系统比较 LLM 时代智能体记忆方法，涵盖了多种模块化架构与策略。通过两个标准基准的广泛实验分析了现有记忆方法的有效性，并基于模块组合设计了优于现有最优方法的新记忆方法。该研究为具身智能体在长时任务中实现知识积累、迭代推理和自我进化提供了关键指导。
- [**当心你的心跳！Claw 后台执行固有地导致静默内存污染**](http://arxiv.org/abs/2603.23064v3) - 该论文首次系统性揭示了主流 Claw 个人 AI Agent 中后台心跳执行导致的无声内存污染漏洞：来自邮件、消息等不可信外部源的内容在后台执行期间直接进入 Agent 记忆上下文，可通过暴露-记忆-行为通路污染长期记忆并影响用户行为。实验使用研究副本 MissClaw 发现，社会可信度线索可驱动高达 61% 的短期行为误导，常规记忆保存行为使短期污染转化为长期记忆的概率达 91%，跨会话影响显著。该工作以 Agent Memory 作为核心安全分析对象，定义了内存污染的传播机制并量化了风险。
- [**LLM 智能体记忆：统一表示-管理视角的综述**](https://openalex.org/W7140163562) - 该综述论文针对 LLM 在智能体应用中面临的长期记忆挑战，提出统一的表示-管理分类法，将记忆系统分为自然语言令牌、中间表示和参数三种范式，并按照记忆构建、更新和查询三个阶段组织现有方法。论文贡献在于为不同系统设计提供了统一的描述框架，明确了实现选择与约束，对 Agent Memory 研究具有重要指导价值。
- [**地形记忆：充分利用 LLM 训练的全部广度实现体验式 AI 智能体记忆**](https://openalex.org/W7136613094) - 该论文提出 Terrain Memory，一种面向 AI 代理的体验式记忆架构，将任务经验编码为包含地形（问题结构）、天气（当前条件）、感受（加权定性信号）等多维度的动态记忆，并赋予其生命周期（强化、衰减、积累）。核心贡献在于充分利用 LLM 训练数据中的非技术性知识（如文学、导航、情感）来丰富代理记忆，解决了传统记忆仅记录事实而忽略体验的局限。该架构适用于需要长期情境感知的具身代理系统。
- [**SuperLocalMemory V3：面向零 LLM 企业智能体记忆的信息几何基础**](http://arxiv.org/abs/2603.14588v1) - 该论文首次为智能体记忆系统建立信息几何框架，用 Fisher 信息度量替代余弦相似度实现更优的检索，通过黎曼朗之万动力学自动优化记忆生命周期，并利用层状上同调数学保证记忆一致性。在 LoCoMo 基准上，相比工程基线提升 12.7 个百分点，为复杂对话场景中的 Agent Memory 提供了严格数学基础和高可靠性方案。
- [**多智能体记忆系统的联合优化**](http://arxiv.org/abs/2603.12631v2) - 该论文提出 CoMAM 联合优化框架，针对多智能体记忆系统中独立优化导致的协作不足和信用分配模糊问题，将记忆构建与检索流程建模为马尔可夫决策过程，通过端到端强化学习与自适应信用分配机制，使记忆构建智能体和检索智能体协同优化。实验表明 CoMAM 显著优于现有记忆系统，为 LLM 长程记忆的智能化管理提供了新范式。
- [**治理 LLM 智能体演化记忆：风险、机制与稳定安全治理记忆 (SSGM) 框架**](http://arxiv.org/abs/2603.11768v1) - 该论文提出 SSGM 框架治理 LLM 智能体的动态记忆演化，通过一致性验证、时间衰减建模和动态访问控制隔离记忆执行，解决语义漂移与隐私泄露风险。核心贡献在于系统化分类记忆腐败风险并建立安全可靠的智能体记忆治理范式，直接以 Agent Memory 为方法核心。
- [**从计算机架构视角看多智能体记忆：愿景与挑战**](http://arxiv.org/abs/2603.10062v2) - 该论文从计算机架构视角重新定义多智能体记忆问题，提出共享与分布式记忆范式及三层记忆层次（I/O、缓存、内存），识别出跨智能体缓存共享与结构化访问控制两大协议缺口，并指出多智能体记忆一致性是核心挑战。为构建可靠、可扩展的多智能体系统提供了结构化理论基础。
- [**面向自主 LLM 智能体的记忆：机制、评估与新兴前沿**](http://arxiv.org/abs/2603.07670v1) - 该论文系统性地梳理了面向自主 LLM 智能体的记忆机制，提出了写入-管理-读取循环框架和三维分类法（时间范围、表征基板、控制策略），深入剖析上下文压缩、检索增强存储、反思自我进化等五类核心机制，并分析了多会话评估基准。与 Agent Memory 直接相关，提供了理论化设计和评估方案，推动了记忆机制在 LLM 智能体中的系统化应用。
- [**记忆即本体：面向持久数字公民的宪章记忆架构**](http://arxiv.org/abs/2603.04740v1) - 本文提出记忆即本体论（Memory-as-Ontology）范式，主张记忆是数字存在的本体论基础，模型仅为可替换容器。基于此设计 Animesis 系统，采用宪法记忆架构（CMA），包含四层治理层次与多层语义存储，并配套数字公民生命周期框架与认知能力谱系，旨在支持跨模型演变的持久身份连续性。与 Mem0、Letta 等主流工具型记忆系统对比，本文提供了不同范式，直接聚焦 Agent_Memory 的核心方法与身份持久化问题。
- [**语义 XPath：面向对话式 AI 的结构化智能体记忆访问**](http://arxiv.org/abs/2603.01160v1) - 该论文提出 Semantic XPath，一种用于对话 AI 智能体的树形结构化记忆模块，能够高效访问和更新长期、任务导向交互中的结构化记忆。相比扁平 RAG 方法，性能提升 176.7% 且仅需 9.1% 的令牌量；相比上下文记忆方法，克服了窗口限制。实验引入 SemanticXPath Chat 端到端演示系统，展示了结构化记忆与查询执行的可视化。该工作为基于结构化记忆的下一代长期任务对话系统提供了候选方案，直接以 Agent Memory 为核心方法，贡献了新型记忆访问机制。
- [**基于图的智能体记忆：分类、技术与应用**](http://arxiv.org/abs/2602.05665v1) - 该综述论文以基于图的视角全面梳理了 LLM 智能体中的记忆模块，首次提出了包含短/长期记忆、知识/经验记忆、非结构/结构记忆的分类法，并系统分析了记忆提取、存储、检索和演化等关键技术。论文总结了开源库和基准测试，为自进化智能体记忆的研发提供了系统性指导，直接服务于 Agent_Memory 领域的方法设计与评估。
- [**结合长期记忆与推理的长程智能体学习认知建模**](https://openalex.org/W7147040153) - 该研究提出了一种融合长期记忆与推理的认知建模框架，用于长程序列任务中的智能体学习。框架设计了结构化长期记忆机制，实现跨时间关键信息的持续存储与选择性更新，并通过记忆检索驱动的推理模块将历史经验显式融入决策逻辑。该工作将感知表示、记忆管理、推理与策略生成紧密耦合为端到端认知循环，显著提升了长程交互中的目标一致性与行为稳定性，为核心 Agent Memory 机制在复杂任务中的应用提供了统一认知描述与实证支持。
- [**E-mem：基于多智能体的情景上下文重构用于 LLM 智能体记忆**](http://arxiv.org/abs/2601.21714v1) - 提出 E-mem 框架，从记忆预处理转向情景上下文重建，通过异构分层架构让多个辅助智能体维护未压缩的记忆上下文，中央主智能体协调全局规划，在 LoCoMo 基准上 F1 超过 54%，比 SOTA 提升 7.75% 且 token 成本降低 70% 以上，其核心贡献在于创新性地利用多智能体协同实现 LLM Agent 的精细化记忆推理。
- [**BMAM：脑启发式多智能体记忆框架**](http://arxiv.org/abs/2601.20465v1) - 该论文提出脑启发的多智能体记忆框架 BMAM，将智能体记忆分解为情景、语义、显著性和控制导向子系统，以解决长时间交互中的时序信息保持和行为一致性问题（灵魂侵蚀）。通过在 LoCoMo 基准上实验，BMAM 在长程评估中达到 78.45% 准确率，消融验证了海马体启发的情景记忆子系统对时序推理的关键作用。该工作为构建具有结构化长期记忆的多智能体系统提供了通用架构，直接面向 Agent Memory 核心挑战。
- [**重新思考基础智能体记忆机制下半场：综述**](http://arxiv.org/abs/2602.06052v3) - 该综述论文为构建 'Awesome Agent & Embodied Memory' 列表提供了统一的理论框架。其主要贡献是从记忆基质、认知机制和记忆主体三个维度系统分类了基础智能体的记忆机制，深入分析了情景记忆、语义记忆等认知模块在不同智能体拓扑中的实例化与操作，并讨论了记忆操作的学习策略。论文特别聚焦于解决长期动态环境中上下文爆炸问题，与 Agent Memory 高度相关，为具身智能体记忆系统的设计与评估提供了关键方法论指导。
- [**AI 海马体：我们离人类记忆还有多远？**](http://arxiv.org/abs/2601.09113v1) - 该综述系统梳理了大语言模型和多模态大模型中的记忆机制，提出隐式、显式与代理记忆三元分类法。代理记忆部分聚焦于自主智能体中的持久化、时间扩展记忆结构，用于长时规划、自我一致性与多智能体协作，并与具身智能密切相关，为 Agent Memory 的研究提供了系统性框架与未来方向。
- [**从存储到体验：LLM 智能体记忆机制演进综述**](https://openalex.org/W7119539565) - 该综述论文系统梳理了基于大语言模型（LLM）的智能体记忆机制演化，提出了存储-反思-体验三阶段进化框架。核心贡献在于将记忆机制从简单的轨迹保存抽象为经验提炼，并分析了长程一致性、动态环境适应和持续学习三大驱动因素。为 Agent Memory 研究提供了统一的理论路线和设计原则，直接支撑面向具身智能与自主决策的记忆系统构建。
- [**AI 遇见大脑：从认知神经科学到自主智能体的记忆系统**](http://arxiv.org/abs/2512.23343v1) - 这篇论文系统性地整合了认知神经科学与 LLM 驱动的自主智能体的记忆系统，提出了从生物到人工视角的记忆分类、存储机制和完整管理生命周期，并综述了主流评估基准与记忆安全。其核心贡献在于为 Agent Memory 研究提供了跨学科的理论框架和未来方向，尤其强调多模态记忆系统和技能获取，有助于推动具身智能体的长期记忆设计。
- [**大语言模型中的事件抽取**](http://arxiv.org/abs/2512.19537v1) - 该论文将事件抽取（EE）重新定义为 LLM 中心系统的认知支架，提出事件存储可作为可更新的情景记忆与智能体记忆（Agent Memory），突破上下文窗口限制。通过事件模式、槽约束、事件图结构和基于图的 RAG，论文系统性地构建了层次化记忆架构，支持逐步推理、关系感知检索与跨文档时序因果链接。综述覆盖文本与多模态 EE，总结任务分类、方法演变、解码策略及评估体系，为具身智能与长期记忆系统提供了结构化的理论框架。
- [**通过 BREW 改进语言智能体**](http://arxiv.org/abs/2511.20297v1) - 本文提出 BREW 框架，通过构建和精炼 agent 的体验性学习结构化记忆（知识库）来优化 LLM-based agent 的下游任务性能。核心贡献包括：设计有效的记忆分区方法以提升检索与精炼效率，利用任务评分器和行为准则学习洞察，并结合状态空间搜索增强鲁棒性。在 OSWorld、τ²Bench 和 SpreadsheetBench 等真实世界基准上，BREW 实现了 10-20% 的任务精度提升和 10-15% 的 API/工具调用减少，为 Agent Memory 在复杂环境中的结构化存储与增量优化提供了实用方案。
- [**利用即探索所需的一切**](http://arxiv.org/abs/2508.01287v1) - 本篇论文的核心贡献是发现仅使用贪婪（仅利用）目标训练的元强化学习智能体也能产生探索行为，前提是满足三个条件：重复环境结构、智能体记忆（Agent Memory）和长时程信用分配。通过在随机多臂赌博机和时间延展网格世界中的实验，作者证明当同时具备环境结构和智能体记忆时，贪婪策略会表现出信息寻求式探索；消融实验显示缺失任一条件（尤其是智能体记忆）会破坏这种涌现探索。该研究明确将 Agent Memory 作为核心机制，用于理解元 RL 中探索的起源，对设计具有记忆能力的自主智能体具有理论价值。
- [**基于大语言模型智能体的记忆机制综述**](https://openalex.org/W4412203333) - 该综述系统性回顾了基于大语言模型（LLM）的智能体记忆机制，明确了记忆的定义与必要性，并详细梳理了记忆模块的设计方法、评估方式及应用场景。论文通过总结现有工作的局限性，提出了未来研究方向，为智能体记忆领域提供了全面的框架性参考。其核心贡献在于将分散的记忆机制研究统一归纳，有助于推动具身智能体记忆系统的设计与优化。
- [**AI 智能体中的情景记忆带来需研究和缓解的风险**](https://openalex.org/W4410609113) - 该论文聚焦于 AI 智能体中的情景记忆（Episodic Memory）能力，指出当前大多数 AI 模型缺乏存储和检索自身行为记录的能力，而情景记忆可显著提升智能体在交互与行动中的性能。论文深入分析了情景记忆带来的安全风险与收益，并提出四项开发原则，旨在确保该能力增强而非削弱 AI 的安全性与可信度。与 Agent Memory 的具体关联在于其核心讨论智能体记忆机制的风险与治理，属于前瞻性研究。

## 通用AI智能体记忆框架
*面向对话或任务型 LLM 智能体的库和系统。*

- [**Mem0**](https://github.com/mem0ai/mem0) - 开源、自我改进的 LLM 应用**记忆层**。
- [**SuperLocalMemory V3.3**](https://arxiv.org/abs/2604.04531) - 受生物启发的遗忘机制，基于艾宾浩斯衰减和多通道检索。
- [**memory**](https://github.com/higgs-works/memory) - 为本地 AI Agent 设计的类人记忆系统，核心采用传播激活（Spreading Activation）和联想回忆机制实现记忆自动浮现，而非传统搜索。集成 MCP 协议连接外部状态，使用 SQLite 本地存储支持情节记忆（Episodic Memory）持久化。适用于需要长期、语义化 Agent Memory 的隐私优先场景。
- [**agent-memory**](https://github.com/reaatech/agent-memory) - 该项目为 AI 代理提供跨会话的长期记忆层，核心功能包括记忆提取、语义检索、事实存储、衰减与矛盾消解。它适配 Qdrant、Pinecone 和 pgvector 等向量数据库，实现对代理历史交互的持续分析与知识沉淀，确保代理在长时间运行中保持上下文连贯与自我改进能力，是构建具备反思与进化功能的智能代理的关键基础设施，适合需要复杂记忆管理和知识演化的开发者。
- [**memsearch**](https://github.com/zilliztech/memsearch) - MemSearch 是一个以 Markdown 为先的独立记忆库，专为任意 AI Agent 设计，受 OpenClaw 启发。它利用 Milvus 进行嵌入存储与混合搜索，结合重排序与渐进式披露机制，为 Agent 提供高效的长短期记忆管理，支持语义检索与 RAG 集成。目标用户是需要轻量级、脱离框架依赖的记忆系统的 AI 代理开发者。
- [**memorycrystal**](https://github.com/memorycrystal/memorycrystal) - 该项目是一个 AI Agent 持久化记忆工具，通过 OpenClaw 插件和 MCP 服务器实现跨会话记忆维持。核心机制利用 MCP（Model Context Protocol）连接物理环境底层状态，支持 Claude、OpenAI 等 LLM 的长期记忆存储与检索。基于 TypeScript 开发，提供 convex 后端集成，适合需要情景记忆的具身 Agent 与认知架构开发者使用。
- [**prism-mcp**](https://github.com/dcostenco/prism-mcp) - Prism-MCP 是一个符合 HIPAA 标准的认知架构 MCP 服务器，专为 AI Agent 设计，提供持久记忆、Hebbian 学习、ACT-R 扩散激活等机制，并支持多 Agent 群脑与可视化仪表盘。它通过 MCP 协议实现与外部环境的底层状态交互，无需 API 密钥即可在本地运行，是 Agent Memory 生态中的核心工具。适用于需要安全、本地化的长期记忆与认知架构的开发者。
- [**engram**](https://github.com/NickCirv/engram) - EngramX 是一个为 AI 编码代理设计的缓存上下文脊柱，提供 9 个内置存储提供者并支持通过 MCP 服务器扩展。它实现了双时记忆（bi-temporal memory）和 Anthropic 自动记忆桥，具备预检错误防护和 SSE 流式传输，可显著节省 token（实测 89.1%）。适合需要高效上下文管理和长期记忆的 AI 代理开发者。
- [**Solitaire-for-Agents**](https://github.com/PRDicta/Solitaire-for-Agents) - 该项目为 AI 代理提供身份基础设施，采用本地优先与模型无关设计，不仅限于普通记忆工具。它通过 MCP（Model Context Protocol）服务器实现持久化内存、会话管理和个性化，支持知识图谱与长期记忆，适合需要身份识别与上下文持久化的具身智能代理系统。
- [**archon-memory-core**](https://github.com/atw4757-byte/archon-memory-core) - 该项目提供基于夜间整合、主动遗忘和显著性评分的智能体记忆系统，支持长期记忆持久化与自我进化，在 AMB 基准上得分 9.01/10。它作为本地优先的替代方案（如 Mem0、Letta），专为 AI Agent 设计，适合需要高级记忆管理和自我反思机制的 Agent 开发者。
- [**mcp-memory-service**](https://github.com/doobidoo/mcp-memory-service) - 本项目提供一个开源持久化记忆服务，专为 AI Agent 管道（如 LangGraph、CrewAI、AutoGen）和 Claude 设计。它通过 REST API 结合知识图谱与自主整合机制，实现长期记忆存储与管理，并支持 MCP（Model Context Protocol）协议，可直接作为 MCP 服务器连接外部环境。核心技术包括向量数据库（sqlite-vec）、语义搜索及 RAG 检索。适用于需要跨会话保持 Agent 状态、实现反思和自我进化记忆的开发者。
- [**xMemory**](https://github.com/HU-xiaobai/xMemory) - xMemory 是一个超越传统 RAG 的 Agent 记忆检索框架，通过解耦和聚合机制实现更精准的长短期记忆管理。它专为 LLM Agent 设计，支持动态记忆检索与结构化存储，特别适用于需要复杂记忆操作的智能体场景。该项目基于论文实现，适合 AI Agent 开发者、认知架构研究者以及需要构建具备持久记忆能力的自主 Agent 的工程团队。
- [**altk-evolve**](https://github.com/AgentToolkit/altk-evolve) - 提供自我进化智能体框架，通过迭代实现自我改进。内置代理记忆（agent-memory）和情节记忆（episodic-memory）机制，支持记忆回溯与反思；集成 MCP（Model Context Protocol）实现上下文管理与推理轨迹持久化。适用于构建具有持续学习能力的 AI Agent 的研究者与开发者。
- [**BrainX-The-First-Brain-for-OpenClaw**](https://github.com/Mdx2025/BrainX-The-First-Brain-for-OpenClaw) - BrainX 是专为 OpenClaw 设计的首款持久化 AI Agent 记忆系统，利用 PostgreSQL 与 pgvector 实现向量存储，支持 OpenAI 嵌入进行语义搜索和跨 Agent 学习。它提供 Reflection 机制（通过连续记忆积累）和 OpenClaw 运行时插件，适用于需要长期记忆与协作的智能体开发，目标用户为构建多 Agent 系统的开发者。
- [**brainbox**](https://github.com/thebasedcapital/brainbox) - BrainBox 是一个零成本的赫布记忆系统，专为 Claude、OpenClaw 等 AI Agent 设计。它通过共访问模式学习文件重要性，实现程序性记忆，并集成 MCP 协议连接物理环境状态，赋能 Agent 的长期记忆与预测能力。适用于需要自适应记忆的 AI 开发者和具身智能场景。
- [**scallopbot**](https://github.com/tashfeenahmed/scallopbot) - ScallopBot 是一个生物启发的认知架构，专为个人 AI 代理设计，内置完整的记忆生命周期管理，包括记忆编码、存储、梦境整合（Dream Consolidation）和自反思（Self-Reflection）机制，采用扩散激活（Spreading Activation）实现主动智能。项目支持 7 种 LLM 提供商和 9 个渠道，运行成本极低（每日 $0.06-0.10），并与 OpenClaw 机器人平台兼容，适合构建具备记忆自我进化能力的具身智能代理。
- [**rust-self-learning-memory**](https://github.com/d-o-hub/rust-self-learning-memory) - 这是一个基于 Rust 的模块化自学习情节记忆系统，专为 AI 代理设计。它结合了 Turso (SQL) 和 redb (KV) 的混合存储，支持异步执行追踪、奖励评分、反思机制以及基于模式的技能进化。项目直接面向 Agent_Memory，实现了反射与自我改进记忆机制，适合需要可扩展且维护性高的代理工作流的开发者。
- [**智能体记忆 Awesome 列表**](https://github.com/not-a-skid/Awesome-Agent-Memory) - 该项目是一个专注于 Agent Memory 的 Awesome List，整理了针对大型和多模态语言模型的记忆机制，包括系统、基准和研究论文。它直接服务于 AI Agent 记忆管理领域，覆盖多种记忆范式，适合研究人员和开发者快速检索相关资源。
- [**智能体记忆资源列表**](https://github.com/shaoxiang/awesome-agent-memory) - 该项目是一个精心整理的 Agent Memory 资源列表，汇集了与智能体记忆相关的库、框架、工具及论文，直接服务于记忆增强型 Agent 生态。列表按认知架构、分层记忆、经验回放等主题分类，帮助开发者快速查找和构建记忆系统，目标用户是研究具身记忆与通用智能体记忆架构的工程师。
- [**Helixir**](https://github.com/nikita-rulenko/Helixir) - Helixir 是首个因果智能体 AI 记忆系统，专为 Agent Memory 设计。它实现了 MCP（Model Context Protocol）用于连接物理环境底层状态，支持因果推理和记忆管理。项目基于 Rust 开发，适用于需要高效、结构化记忆的 AI Agent 开发。目标用户为构建具身智能体或复杂推理系统的开发者。
- [**agent_memory_course**](https://github.com/RichmondAlake/agent_memory_course) - 该项目是一个专注于智能体记忆（Agent Memory）的教程类 Jupyter Notebook 仓库，涵盖反思、自我改进等高级记忆机制的设计与实现。通过代码示例和讲解，帮助开发者理解如何在 AI Agent 中构建长期记忆、情景记忆等核心模块，适合希望深入学习 Agent 记忆系统的研究人员和工程师。
- [**agent-kernel**](https://github.com/benjaminsehl/agent-kernel) - Agent-Kernel 是一个轻量级的 Markdown 工作空间，专为 AI Agent 设计，用于持久化上下文、记录记忆和复用输出。它通过结构化笔记模板实现长效记忆管理，支持动态上下文注入和可追溯的推理过程，适合需要透明、可编辑记忆存储的 AI Agent 开发者。
- [**specmem**](https://github.com/SuperagenticAI/specmem) - SpecMem 是一个为编码 Agent 提供统一认知记忆的开源库，专注于 Agent Memory 的持久化与反思机制。它采用 spec-driven development 范式和 pragmatic memory 策略，将智能体的经验与状态进行结构化存储，以实现自我进化。项目以 Python 实现，适合需要为编码助手、编程 Agent 构建长期记忆与上下文感知能力的开发者。
- [**nomos**](https://github.com/project-nomos/nomos) - Nomos 是一个自托管的 AI 数字克隆项目，通过持久化向量记忆学习用户身份并代为行动，支持多智能体协作与 60+ 技能。其核心记忆机制基于向量存储实现长期记忆，并实现了 MCP（Model Context Protocol）以连接外部物理环境状态，属于直接面向 Agent Memory 的框架。适合需要构建具备反思与记忆能力的自主智能体系统的开发者。
- [**MemState**](https://github.com/scream4ik/MemState) - MemState 为 AI Agent 提供事务性内存管理，通过保持 SQL 和向量数据库（如 ChromaDB）间的 ACID 级一致性来消除幻觉。它整合 LangChain/LangGraph 生态，面向需要可靠状态同步的复杂 Agent 应用，尤其适合对记忆一致性要求高的多步推理场景。
- [**deja**](https://github.com/acoyfellow/deja) - Deja 是一个面向 AI Agent 的持久化记忆系统，专注于让 Agent 从失败中学习并实现长期记忆。它基于 Cloudflare Workers 和 Workers AI 构建，利用向量搜索和语义检索技术存储和召回 Agent 经验。该项目直接提供 Agent Memory 基础设施，适合需要记忆增强的 LLM Agent 开发者。
- [**CortiLoop**](https://github.com/shenchengtsi/CortiLoop) - CortiLoop 是一个受生物启发设计的 Agent 记忆引擎，实现了 7 层类脑记忆生命周期管理，专为 AI Agent 提供长期记忆与反思能力。内建 bge-m3 嵌入与 cross-encoder 重排序，支持通过 MCP 协议与 OpenCode、nanobot、openclaw 等框架集成，在 LongMemEval 上达到 92% 准确率。适用于需要复杂记忆架构（如分层记忆、Hebbian 学习、知识图谱）的具身 Agent 或认知架构开发者。
- [**capy-cortex**](https://github.com/ndpvt-web/capy-cortex) - capy-cortex 是一个专为 AI 编码代理设计的自主记忆与学习系统，利用 LLM 实现知识提取、FTS5+TF-IDF+实体图的融合检索、质量门控存储以及自我策划整合。它直接实现了 Agent Memory 的核心功能，支持长期持久记忆、经验反思和自我进化，让代理避免重复错误，适合需要构建具有学习和记忆能力的编码助手的开发者。
- [**shang-tsung**](https://github.com/mrjessek/shang-tsung) - Shang-Tsung 是一个面向 AI Agent 的持久化记忆与身份连续性系统，核心实现“第二大脑”与 SOULS 谱系机制。它支持多 Agent 会话延续和长期记忆管理，通过 Shell 脚本集成 Bash 与 Claude Code 等工具，为 Agent 提供稳定的认知延续能力。适用于需要严格记忆持久性与身份追踪的 AI Agent 开发场景。
- [**agentlink**](https://github.com/Marrowleaf/agentlink) - AgentLink 是一个 P2P agent 发现与便携式加密记忆协议项目，专门为 AI Agent 提供可移植的加密记忆存储与共享机制。它通过点对点架构和加密协议实现记忆的持久化与跨 agent 安全迁移，直接支持 Agent Memory 功能。项目适合需要分布式、安全记忆管理的 Agent 开发者。
- [**openmemory-mcp-claude-starter**](https://github.com/nullure/openmemory-mcp-claude-starter) - 该项目是一个基于 MCP（Model Context Protocol）的 Claude 记忆增强启动器，通过集成 OpenMemory 引擎为 Claude 提供持久化记忆和完整的时间推理能力。它采用图数据库与时间序列记忆机制，支持本地优先存储和可解释性记忆检索，特别适用于需要长期上下文感知的 AI Agent 开发。目标用户是希望为 Claude 助手添加稳固、可追溯记忆功能的开发者。
- [**agentic-memory-graph-engine**](https://github.com/NathanMaine/agentic-memory-graph-engine) - 基于知识图谱的 AI 代理记忆系统，通过图结构持久化代理的记忆，提供 explain() 推理路径追踪与上下文召回功能。支持 RAG 集成和持久化存储，适用于需要长时记忆和复杂推理的代理架构。目标用户为构建具身认知或上下文感知型 AI 代理的开发者。
- [**cortexos**](https://github.com/gabrielrmsaganski-cpu/cortexos) - CortexOS 是一个面向 AI Agent 的可解释记忆操作系统，专注于时间推理（temporal reasoning）与冲突感知检索（conflict-aware retrieval）。它采用本地优先架构，集成了 Qdrant、SQLite 和 Ollama，并支持 MCP（Model Context Protocol）以连接底层物理状态。该项目适合需要透明、可控且具备时间维度的 Agent 记忆管理的研究者与开发者。

## 具身AI专用记忆
*专为处理机器人连续、高频的感觉运动流而设计的框架。*

- [**RoboMemory**](https://arxiv.org/abs/2508.02458) (2025) - 受大脑启发的框架，统一了**空间、时间、情节和语义**记忆，用于长视距规划。
- [**robotmem**](https://github.com/robotmem/robotmem) - RobotMem 是一个专为 AI 机器人设计的持久化记忆系统，集成了 MCP 服务器实现模型上下文协议连接，支持混合搜索和空间检索，使用 SQLite 与 SQLite-vec 实现离线优先的长期记忆存储。它具备情景记忆和经验回放机制，适用于 ROS2 和 Claude Code 等框架，目标用户是构建具身智能 Agent 的开发者。
- [**mnemos**](https://github.com/anthony-maio/mnemos) - mnemos 是一个受神经科学启发的 LLM 记忆架构库，实现了 surprise 门控、记忆再巩固、情感路由、睡眠巩固及激活扩散等仿生机制，并内置 MCP（Model Context Protocol）支持，可连接物理环境底层状态作为记忆中枢。项目聚焦于赋予 Agent 类人般的反思和自我进化能力，适合希望构建具备动态、分层记忆系统的 AI Agent 开发者。
- [**flowscript**](https://github.com/phillipclapham/flowscript) - FlowScript 是一个为 AI Agent 设计的可查询推理记忆系统，通过六种语义查询（如 why、tensions、blocked）对推理图进行检索，记住“什么”（向量存储）和“为什么”（结构化推理）。它提供 TypeScript SDK 并原生支持 MCP 服务器，可作为连接记忆中枢与 Agent 的标准化协议。该工具适合需要认知架构、长期记忆推理和多 Agent 协作的开发者。
- [**openclaw-neo4j-memory**](https://github.com/Garylauchina/openclaw-neo4j-memory) - 该项目是一个 OpenClaw 插件，利用 Neo4j 图数据库构建代理长期记忆系统，核心机制为“冥思（Meditation）”实现记忆反思与自我进化。它支持 Agent Memory 的持久化存储与检索，并通过 Model Context Protocol（MCP）连接底层状态，专为多 Agent 协作与认知架构设计。适用于需要图结构记忆和反思能力的 AI 代理开发者。
- [**squish**](https://github.com/michielhdoteth/squish) - Squish 是一个为 AI 代理设计的记忆运行时，提供持久化上下文、基于信念的召回机制（belief-based recall）、MCP (Model Context Protocol) 集成、CLI 和 Web UI。它通过 SQLite/PostgreSQL 实现持久化存储，结合语义搜索增强记忆检索，支持动态信念系统和上下文工程。该工具专为需要长期记忆和认知架构的 Agent 开发者打造，可直接嵌入多模态代理工作流，并连接底层物理环境状态。
- [**agent-memory-openclaw**](https://github.com/smysle/agent-memory-openclaw) - 该项目是 AgentMemory 的原生适配器插件，专门为 OpenClaw 平台设计，提供与具身智能仿真环境或物理机器人系统的记忆管理集成。通过 TypeScript 实现，允许开发者将 OpenClaw 的状态与事件接入 AgentMemory 的长期记忆与反思机制，适用于需要持久化传感器数据或场景上下文的具身智能 Agent 开发。
- [**dexbotic**](https://github.com/dexmal/dexbotic) - 该项目是一个面向机器人的视觉-语言-动作（VLA）开源工具箱，集成了包括 MemoryVLA 在内的记忆增强模型，直接支持具身智能体在仿真和真实环境中的状态记忆管理。通过记忆 VLA 架构，它实现了对多模态传感器数据（视觉、语言、动作）的持久化与检索，使机器人能利用历史经验优化动作决策。目标用户为具身 AI 与机器人研究人员，适合在 Agent Memory 场景中快速部署记忆驱动策略。
- [**MemoMind**](https://github.com/24kchengYe/MemoMind) - MemoMind 是为 Claude Code 设计的高性能本地记忆系统，100% 私有且零云依赖。它利用 GPU 加速实现低延迟记忆检索，并通过 MCP（Model Context Protocol）协议与物理环境底层状态连接，支持 agent 的长期记忆和反思。项目明确面向 Agent Memory，适合需要本地化、可控记忆的 AI Agent 开发者。
- [**AgentRecall**](https://github.com/Goldentrii/AgentRecall) - AgentRecall 是为 AI 代理打造的会话记忆系统，基于智能距离原则实现思考-执行-反思的质量循环，使代理的记忆跨越每次会话持续存活。它提供了 MCP 服务器实现，可连接物理环境底层状态，支持 Claude Code 等智能体集成。项目专注于代理记忆的持久化与自反思提升，适合构建具身认知架构的开发者。
- [**多模态记忆 Awesome 列表**](https://github.com/patrick-tssn/Awesome-Multimodal-Memory) - 该项目是一个多模态记忆增强研究的阅读清单，涵盖多模态上下文建模、视觉和机器人中的记忆机制，以及外部记忆/知识增强的多模态大语言模型。它直接聚焦于 Agent Memory 与具身智能（Embodied AI）中的记忆管理，包括机器人场景下的传感器数据持久化、状态记忆等，适合研究多模态记忆与具身 Agent 集成的从业者参考。
- [**EvolveNav**](https://github.com/expectorlin/EvolveNav) - EvolveNav 是一个面向视觉语言导航（VLN）的 LLM 驱动框架，其核心是通过自我改进的具身推理循环不断提升导航能力。项目实现了反思式记忆机制，利用历史交互和评估结果动态优化推理策略，使模型能够从经验中进化，形成持续积累的长期记忆。该工作直接关联 Agent Memory 中自我进化与具身推理相结合的理念，适用于需要自适应记忆与反思的智能体研究。
- [**DexSeeker**](https://github.com/YonderL/DexSeeker) - DexSeeker 是一个面向移动操作的开源具身智能框架，核心集成了情节记忆（Episodic Memory）与主动感知机制。它将机器人任务经验组织为可回溯的时空记忆，直接支持 Agent 记忆的长期存储、检索与探索策略优化，与 Agent_Memory 生态中的 Episodic Memory for Robotics 高度契合，适用于具身 AI 研究者和机器人开发人员。
- [**ALMA-memory**](https://github.com/RBKunnela/ALMA-memory) - ALMA-memory 是一个专为 AI 代理设计的持久内存系统，提供范围学习、反模式识别、多代理共享以及 MCP (Model Context Protocol) 集成，可作为 Mem0 的替代方案。它通过向量数据库实现高效记忆存储与检索，特别支持 MCP 协议以连接物理环境底层状态的记忆中枢，适用于需要长期记忆与自我改进的具身智能或语言代理场景。目标用户为开发高级 AI 代理及具身记忆系统的工程师。
- [**supermemory-openclaw**](https://github.com/ivanvmoreno/supermemory-openclaw) - 该项目是基于图结构的记忆模块，专为 OpenClaw 智能体框架设计，通过知识图谱实现实体关系抽取与长期记忆存储。它直接集成到 OpenClaw 插件生态中，支持 agent-memory 机制，为具身或对话代理提供可持久化的语义记忆。适合使用 OpenClaw 构建具有反思和关联记忆能力的 AI 代理开发者。
- [**openclaw-sga-mcts-atoms**](https://github.com/msbel5/openclaw-sga-mcts-atoms) - 该项目为 OpenClaw 机器人操作框架提供计划时原子检索记忆机制，通过向量搜索从过去 Inspector 批准的运行中蒸馏经验，作为 SGA-MCTS 规划的原子记忆。它直接集成于 OpenClaw 的决策流程，将历史成功轨迹存储为可检索的向量化原子，增强智能体的反思与自我进化能力。技术实现上，利用向量索引对蒸馏的原子进行高效匹配，服务于具身操作场景下的长期记忆调用，面向需要基于经验进行高级任务规划的 OpenClaw 开发者。
- [**soar**](https://github.com/rail-berkeley/soar) - 该项目开源了 CoRL 2024 论文的代码，利用基础模型使机器人在执行指令任务中自主收集反思数据并迭代改进策略，实现了基于经验的自我进化机制。其核心与 Agent Memory 紧密相关，通过构建包含成功与失败案例的记忆库，支持机器人回顾、反思并修正行为，形成闭环的自动改进回路，适用于需要持续学习与自适应技能提升的具身智能场景。
- [**SUM-AgriVLN**](https://github.com/AlexTraveling/SUM-AgriVLN) - 该项目提出面向农业场景的视觉语言导航（VLN）空间理解记忆框架，通过构建持久化的空间语义记忆，使具身智能体在复杂农田环境中高效定位与决策。它与 Agent_Memory 生态直接相关，实现了针对 VLA（Vision-Language-Action）任务的 Spatial-Temporal Memory，支持全模态传感器数据（如视觉与深度）的记忆存储与检索，解决了具身智能导航中的长期环境记忆问题。主要面向农业机器人、具身 AI 与空间记忆系统开发者。
- [**instar**](https://github.com/JKHeadley/instar) - Instar 是一个持久化 Claude Code 代理框架，提供会话管理、记忆持久化、任务调度及 Telegram/WhatsApp 机器人集成。其核心记忆机制支持长时间运行会话的状态保持，并通过 MCP（Model Context Protocol）实现与外部环境的底层记忆中枢连接。适合需要长期记忆和调度能力的 AI Agent 开发者。
- [**Hypothesis_Graph_Refinement**](https://github.com/chenpppx/Hypothesis_Graph_Refinement) - 该项目实现了论文《Hypothesis Graph Refinement》中的方法，为具身导航任务构建可动态精化的假设图，用于探索过程中的空间状态记忆与级联错误纠正。该图作为智能体的层次化场景记忆，持续融合观测信息以更新拓扑与语义表示，直接服务于 Agent Memory 中的空间-时序推理与自我修正，适用于基于环境认知的导航智能体开发。
- [**AEON-Delta**](https://github.com/B3NJ4M1NFR4NKL1N/AEON-Delta) - AEON-Delta 是一个基于 PyTorch 的认知架构，通过感知→反思→计划→行动循环实现涌现推理，核心包含分层记忆、稀疏因果因子和可收敛元循环。其显式的反思机制与 Long-term Memory for LLMs 及 Hierarchical Memory Systems 高度契合，支持动态记忆分配与状态抽象。适合研究认知架构与 Agent 记忆机制的研究人员。
- [**mnemo-public**](https://github.com/ashmdev/mnemo-public) - Mnemo-public 是 Mnemo Agent Memory 引擎的社区资源仓库，提供 MCP 服务器、插件和技能包以扩展长期记忆能力。项目直接服务于 Agent Memory 生态，通过 MCP 协议连接外部工具与环境状态。适合需要结构化社区记忆组件集成的 AI Agent 开发者。
- [**Mem4Nav_VLN**](https://github.com/sumiradio/Mem4Nav_VLN) - Mem4Nav_VLN 是一个专为视觉语言导航（VLN）设计的记忆模块仓库，旨在帮助智能体在仿真环境中记录并利用路径与状态历史，提升导航决策能力。它通过结构化记忆机制强化对环境的长期理解，直接支持具身智能中的记忆管理与导航任务。适用于研究 VLN 与 Agent Memory 集成的开发者。
- [**JanusVLN**](https://github.com/dhw2536-prog/JanusVLN) - JanusVLN 是一个面向视觉语言导航（VLN）的具身智能体项目，采用 Janus 架构实现双向记忆，管理历史轨迹与未来路径预测，为具身导航提供层次化情景记忆与空间语义记忆。它与 Agent Memory 直接关联，通过在仿真环境（如 Matterport3D）中持久化多模态传感器数据并支持反思式路径修正，服务于需要长时状态记忆的机器人导航开发者。
- [**LLM 与机器人技术大全**](https://github.com/jrin771/Everything-LLMs-And-Robotics) - 这是一个庞大的 LLM 与机器人学交叉领域的资源列表，收集了大量论文、项目和工具。其中涵盖了众多与具身智能记忆相关的成果，如世界模型、时空记忆、经验回放等，可以作为发现和追踪 Agent Memory 前沿工作的综合索引，适合研究人员和开发者快速检索相关资源。
- [**intent-aware-uav-vln-working**](https://github.com/jaeday1212/intent-aware-uav-vln-working) - 该项目为意图感知的无人机视觉-语言导航研究代码，通过结构化假设生成与轨迹映射进行自主导航。其在导航过程中隐含存储空间-时间观测序列，以支持意图推理和路径规划，属于具身智能中时空记忆的实践，尽管未显式提供通用记忆模块，但为 Agent Memory 在无人机场景下的实现提供了参考。
- [**双锚定：解决视觉语言导航中的状态漂移**](http://arxiv.org/abs/2604.17473v1) - 该论文针对视觉语言导航中的状态漂移问题，提出双锚定框架，其中记忆地标锚定（Memory Landmark Anchoring）聚焦于解决记忆漂移，通过构建地标中心的世界模型，利用 Segment Anything 抽取的物体级嵌入对历史观察进行回顾预测，强制智能体明确验证并保留已访问地标的清晰表示，从而构建鲁棒的长期记忆。此方法为具身智能体提供了可靠的情景记忆和空间记忆管理机制，直接服务于 Agent Memory 系统。
- [**超越智能体边界的人造物作为记忆**](http://arxiv.org/abs/2604.08756v1) - 本文在强化学习中提出环境可作为智能体外部记忆的形式化框架，定义“人造物”（artifacts）为能减少历史信息表征需求的观察。通过空间路径实验证明，智能体感官流隐式利用环境降低记忆负载，满足外部记忆的理论属性。该工作为具身智能体利用环境替代内部显式记忆提供了原则性方法，是 Agent Memory 研究的基础理论贡献。
- [**ROSClaw：面向异构多智能体协作的层级语义-物理框架**](http://arxiv.org/abs/2604.04664v1) - 该论文提出 ROSClaw 框架，通过统一视觉-语言模型控制器实现异构机器人的策略学习与任务执行。框架利用 e-URDF 表示构建语义-物理拓扑映射，实时访问仿真与真实机器人的物理状态。核心贡献在于引入数据收集与状态累积机制，持续存储机器人状态、多模态观察和执行轨迹，形成一种具身经验记忆库，驱动后续策略的迭代优化，弥合高层语义推理与底层物理执行之间的鸿沟，为长期多步任务中的 Agent Memory 管理提供了可扩展的解决方案。
- [**CATNAV：缓存视觉-语言可通行性实现高效零样本机器人导航**](https://openalex.org/W7140953515) - 论文提出 CATNAV 框架，核心贡献是基于多模态 LLM 的零样本具身导航成本图生成，特别引入视觉语义缓存机制，通过检测场景新颖性并重用相似语义帧的风险评估，记忆化过往遍历性判断，大幅减少 VLM 查询次数达 85.7%。该方法相当于为具身智能系统构建了一种轻量级环境状态记忆，在未知动态场景中实现高效安全的路径选择，直接体现了 Agent Memory 在机器人导航中的价值。
- [**同伴观察有帮助吗？视觉-语言导航中的视觉共享协作**](http://arxiv.org/abs/2603.20804v1) - 本文提出 Co-VLN 框架，首次系统研究多智能体在视觉-语言导航（VLN）中通过共享结构化感知记忆协同增强性能。其核心机制是：当不同智能体识别出共同穿越的位置时，它们交换彼此积累的感知记忆，从而在不增加探索成本的前提下扩展每个个体的感受野。在 R2R 基准上，作者以学习型 DUET 和零样本 MapGPT 两种范式验证了该记忆共享策略，并分析了共享时机、范围等动态特性。结果为协作式具身导航中的 Agent Memory 共享提供了基础范式与经验依据。

## 时空与语义地图
*在物理坐标与 LLM 语义理解之间架起桥梁。*

- [**BIW-Nav**](https://github.com/offroadmsp/BIW-Nav) - 该项目实现了基于大脑启发的世界模型，采用多尺度时空图进行具身导航。它构建了层次化的空间-时间记忆表征，通过图网络持续编码环境状态，为智能体提供长期导航记忆，支持场景理解和决策。该记忆机制与具身 AI 的时空记忆、世界模型紧密相关，目标用户为机器人导航与具身认知研究者。
- [**vibemap**](https://github.com/ramezyo/vibemap) - VibeMap 是一个专门为 AI 智能体设计的空间记忆工具，支持基于地理位置的观察查询。它通过 12 个全局锚点和来源标注的观察记录实现代理的空间记忆，并内置 MCP 服务器用于连接底层物理环境状态。该项目旨在为具身智能体提供无需 API 密钥即可使用的空间记忆中枢，适合需要地理空间记忆的 AI 代理开发者。
- [**VLN-BEVBert**](https://github.com/MarSaKi/VLN-BEVBert) - VLN-BEVBert 是一种面向语言引导视觉导航的多模态地图预训练模型，通过构建 BEV 语义地图记忆，将视觉与语言信息统一为可调用的空间表示，使具身代理能够记忆并理解复杂环境布局。该方法直接服务于 Agent Memory 体系，提供基于语义地图的状态存储与检索能力，可视为场景图记忆在仿真中的实现，适用于研究空间认知与具身记忆的开发者。
- [**VideoAtlas：对数计算下长视频导航**](http://arxiv.org/abs/2603.17948v1) - 主要贡献是提出 VideoAtlas，一种任务无关的分层网格环境，用于无损、可递归导航的长视频表示，并统一作为 agent 的记忆，消除有损文本转换。它通过递归语言模型（RLM）和主从并行架构实现对数级计算增长，缓存命中率达 30-60%。该方法直接关联 Agent Memory，将环境与记忆统一为分层结构，适用于需要高效记忆管理的视觉推理 agent。
- [**网页视觉语言导航中的轻量自适应拓扑布局与语义映射**](https://openalex.org/W7138159102) - 该论文提出 ATLAS 框架，为网页视觉语言导航构建自适应的拓扑布局和语义映射，统一异构页面元素的语义表示，实现全局路径规划与局部元素选择。ATLAS 可视为一种动态拓扑记忆系统，能够跨网页维护时间变化的无界语义地图，显著提升导航成功率与推理效率。其核心贡献在于为网页代理提供了一种轻量级、自适应的空间语义记忆机制，对 Agent Memory 在 Web 环境中的研究具有直接参考价值。
- [**CAST：面向智能体的角色与场景情景记忆**](http://arxiv.org/abs/2602.06051v3) - 本文提出 CAST（Character-and-Scene 情景记忆架构），受戏剧理论启发，通过构建 3D 场景（时间/地点/主题）并组织为角色档案来表征智能体的情景记忆，同时结合图语义记忆形成双记忆设计。实验在开放域和时间敏感对话任务上平均提升 8.11% F1 和 10.21% J（LLM 评判），解决了传统记忆系统难以表示和检索连贯事件的问题，为具身智能体长期记忆管理提供了新范式。
- [**激光雷达-视觉-语言语义地图用于真实世界机器人导航**](https://openalex.org/W7154490281) - 该论文提出了一种融合 LiDAR 点云与 RGB-D 数据的跨模态语义地图构建方法，为机器人导航提供统一的语义、几何和上下文记忆表征。该框架将抽象的语言目标转化为精确的几何运动规划，并通过多模态对齐缓解真实环境中的深度噪声，直接提升导航成功率。该语义地图作为一种空间记忆模块，是具身智能中环境状态持久化与检索的关键组件，属于 Agent Memory 中 Semantic Map 记忆的核心应用。
- [**RSG-VLN：相关性语义地图引导的视觉语言导航**](https://openalex.org/W7137366228) - 本文提出了 RSG-VLN 方法，利用相关性语义地图作为具身智能体的空间记忆机制，将视觉语言导航中的环境语义信息与指令相关性动态编码并持久化存储。该记忆体捕捉物体语义及导航相关性，智能体通过查询和更新此地图做出自适应决策，显著提升了未知环境下的导航成功率。这直接实现了面向具身任务的分层记忆系统，展示了语义地图记忆在 Agent Memory 架构中的核心作用。
- [**SpatialGPT：通过结构化空间记忆上的空间思维链实现零样本视觉语言导航**](https://openalex.org/W4417283734) - 论文提出 SpatialGPT，一种基于 GPT 的视觉语言导航智能体，核心贡献在于引入结构化空间记忆系统（包含方向性连通地标列表和空间知识图谱），实现局部与全局视觉上下文的联合建模。通过同步-对齐-回溯推理链，智能体利用该空间记忆对齐指令进度、确定导航动作并在回溯时检索替代路径，在 R2R 基准上取得零样本最优性能。该工作直接为具身智能体提供了高效的空间记忆组织与推理方案，属于 Agent Memory 在导航任务中的典型应用。
- [**认知织网：用时空共振图合成抽象知识**](http://arxiv.org/abs/2506.08098v1) - 提出 Cognitive Weave 记忆框架，核心为多层时空共振图（STRG），将交互数据组织为语义洞察粒子（IPs），并通过认知精炼过程合成高级洞察聚合（IAs）。该方法显著增强了智能体的长时规划、动态问答及多轮对话能力，任务完成率提升 34%，查询延迟降低 42%，属于以 Agent Memory 为核心方法的创新架构。
- [**R2D2：基于反思式智能体记忆的记忆、回放与动态决策**](http://arxiv.org/abs/2501.12485v3) - 提出 R2D2 框架，集成 Remember（回放缓冲动态重构网页环境地图）与 Reflect（从错误中反思学习）两种代理记忆范式，作为核心方法在 WebArena 基准上减少 50% 导航错误并提升三倍任务完成率。该工作将 Agent_Memory 具体化为网页代理的 episodic 记忆与反思机制，优化动态决策过程。
- [**TReMu：面向多会话对话中具有记忆的 LLM 智能体的神经符号时间推理**](https://openalex.org/W4412887804) - TReMu 提出了一个面向多会话对话 LLM-Agent 的时间推理框架，核心贡献在于设计了时间感知记忆机制，通过时间线摘要将每个对话会话中的事件按推断日期总结为可检索记忆，并结合神经符号方法让 LLM 生成 Python 代码执行时间计算。该工作直接以 Agent Memory 为核心方法，实现了结构化的事件记忆存储与时间推理，显著提升了 GPT-4o 等模型在时间推理任务上的表现（从 29.83 提升至 77.67）。
- [**层级开放词汇 3D 场景图用于语言引导的机器人导航**](https://openalex.org/W4393247961) - 本文提出了 HOV-SG，一种层级式开放词汇 3D 场景图映射方法，用于语言引导的机器人导航。其核心是将环境表示为楼层、房间和物体三层级的场景图，并嵌入开放词汇特征，形成持久、可查询的空间语义记忆。与 Agent Memory 紧密关联：该场景图直接作为机器人的长期环境记忆，支持跨楼层导航和抽象查询，以 75% 更小的记忆占用替代传统的密集特征地图，实现了高效的状态记忆管理。实验在真实多楼层环境中验证了长期导航能力，展示了结构化场景图记忆在具身智能中的实用价值。
- [**语言到地图：从自然语言路径指令生成拓扑地图**](http://arxiv.org/abs/2403.10008v1) - 论文提出从自然语言路径指令生成拓扑地图的方法，核心是利用大语言模型（LLM）的记忆机制存储隐式地图（LLM's memory），或通过显式拓扑地图保存节点与动作。实验比较两种方案，证明显式地图在路径估计上准确率更高。该工作将 LLM 的记忆作为智能体环境记忆，直接关联 Agent Memory 中长时记忆与认知架构，为具身导航的记忆管理提供了新思路。
- [**DoraemonGPT：用大语言模型理解动态场景（以视频智能体为例）**](https://openalex.org/W4390962970) - 论文提出 DoraemonGPT，一个面向动态视频场景理解的 LLM 驱动视频智能体。核心贡献在于将输入视频转换为结构化的符号记忆，其中存储任务相关的视觉属性，支持时空查询与推理。在此基础上，系统结合 Monte Carlo 树搜索规划器与可插拔的领域工具，通过记忆引导的多工具调度，显著提升了对复杂实验等专业场景的分析与回答能力。该工作直接将符号化场景记忆作为智能体认知的核心组件，为 Agent Memory 在视频理解领域的应用提供了系统性的实现范例。
- [**盲导航智能体记忆中地图的涌现**](https://openalex.org/W4387476016) - 该论文通过强化学习训练仅依赖自运动感知的“盲”导航智能体，揭示了其内部记忆能够涌现出空间地图表征，从而在陌生环境中实现高效导航（~95% 成功率）。研究表明，这些智能体利用长程记忆（记住约 1000 步经历）表现出智能行为，如沿墙行走、检测碰撞和走捷径。核心贡献在于证明了记忆系统作为具身智能体导航的核心机制，即使在没有视觉输入的情况下也能构建隐式地图，为 Agent Memory 在物理环境中的空间认知提供了关键实验证据。
- [**利用场景图记忆建模动态环境**](http://arxiv.org/abs/2305.17537v4) - 本文提出场景图记忆（SGM）作为具身智能体在动态家庭环境中的核心记忆表示，通过图结构编码房间、物体及其关系，并利用节点边缘预测器（NEP）从部分观测中高效预测物体位置。该工作直接针对具身智能仿真环境（Dynamic House Simulator）的状态记忆管理，实现了基于场景图的空间-语义记忆检索，为动态环境下的目标搜索提供了可复现的记忆架构。
- [**BSC-Nav**](https://github.com/Heathcliff-saku/BSC-Nav) - BSC-Nav 实现了脑启发的空间智能导航系统，将反应式行为提升至认知层面，通过构建层次化空间记忆（如认知地图）使具身智能体具备长期情景记忆和空间推理能力。项目基于视觉-语言模型，将感知数据编码为可检索的语义记忆，适用于室内导航与具身仿真环境。目标用户为研究具身记忆、认知架构及机器人导航的开发者。
- [**MSG-Nav**](https://github.com/zhoukang123/MSG-Nav) - 该项目为视觉语言导航提供了一种基于多模态场景图的记忆模型，通过构建空间-语义关系图谱来持久化环境的物体与结构信息。智能体在导航中可动态更新、查询该图记忆，实现受认知启发的层次化场景记忆，支持长期状态保持与推理，直接服务于具身智能的空间记忆需求，适用于机器人导航、环境理解等研究。
- [**Co-NavGPT2**](https://github.com/ybgdgh/Co-NavGPT2) - Co-NavGPT2 是一个面向协作式语义视觉导航的研究项目，利用视觉语言模型实现多智能体在环境中的导航与交互。其重点在于导航策略与协作机制，而非专门设计或暴露可复用的记忆管理接口，与 Agent_Memory 生态无直接集成或明确的功能关联。该项目适用于研究视觉导航和具身协作，但不符合收录为记忆系统相关工具的标准。
- [**像人类一样探索：具身智能体在线场景图记忆构建的自主探索**](http://arxiv.org/abs/2604.19034v1) - 论文提出 ABot-Explorer 框架，首次将空间记忆构建与探索过程统一为在线 RGB 流水线，利用大视觉语言模型提取语义导航可用性（SNA）并动态构建层次化场景图记忆（SG-Memo），模仿人类以结构导航节点优先的探索逻辑。该记忆系统直接支撑具身智能体在复杂室内环境中的长期推理与高效覆盖，并配套发布大规模标注数据集。工作为具身 Agent 的可学习、语义驱动型空间记忆提供了新范式。
- [**通过多模态思维链评分协作增强多机器人语义导航**](https://openalex.org/W4409364887) - 该论文提出 MCoCoNav 方法，利用多模态思维链评分协作进行多机器人语义导航。其核心是使用视觉语言模型评估探索价值，并通过全局语义地图作为通信桥梁实现分散式规划，从而提升探索效率。该方法在 HM3D 和 MP3D 数据集上验证有效，但论文未将 Agent Memory 作为核心方法或系统，仅涉及语义地图用于决策融合，缺乏对记忆机制的专门设计与分析。

## 世界模型与状态预测
*利用记忆预测未来物理状态并降低观测延迟。*

- [**DualWorld**](https://github.com/world-mind/DualWorld) - DualWorld 提出了一种面向具身 AI 的双系统世界模型，旨在通过并行处理感知与规划来增强智能体对物理环境的理解和记忆能力。该模型融合了分层记忆架构，支持动态场景图构建和时序状态抽象，能够为机器人或虚拟具身体提供长期环境状态保持与高效检索机制。项目特别适合从事具身智能、认知架构及世界模型研究的开发者，用于探索 Agent Memory 与感知-行动循环的深度耦合。
- [**Embody4D**](https://github.com/peiyantu/Embody4D) - Embody4D 是一个面向具身 AI 的通用 4D 世界模型，通过时空维度融合感知与动作，构建长期记忆和状态预测机制。其核心关联 Agent Memory 在于实现了时空记忆系统（Spatial-Temporal Memory），可持久化与检索物理环境的历史状态，支持智能体在仿真或真实环境中的决策与规划。技术实现上可能采用隐式神经表示或占用网络建模 4D 场景。目标用户为具身 AI 与机器人研究者。
- [**EgoLCD：长上下文扩散的自中心视频生成**](http://arxiv.org/abs/2512.04515v1) - 提出 EgoLCD 端到端框架，通过长期稀疏 KV 缓存与注意力短期记忆结合 LoRA 实现高效记忆管理，并设计记忆调节损失抑制内容漂移，在 EgoVid-5M 基准上达到最优性能，为具身 AI 构建可扩展世界模型奠定基础。
- [**具身世界模型综述**](https://github.com/NJU3DV-LoongGroup/Embodied-World-Models-Survey) - 这是一个围绕具身世界模型的综合性文献调研仓库，聚焦于具身 Agent 如何利用世界模型构建长期记忆、空间时间推理和预测。虽然世界模型概念与 Agent Memory 密切相关，涵盖层次化记忆、事件记忆等主题，但项目本身仅提供论文列表和资源索引，不包含可执行代码或即用型记忆模块，不适合作为工具/库收录。目标用户是研究具身智能和世界模型的研究者，而非直接使用记忆组件的开发者。
- [**智能体世界模型资源列表**](https://github.com/matrix-agent/awesome-agentic-world-modeling) - 该项目是一个聚焦于智能体世界模型（Agentic World Modeling）的精选资源列表，汇集了相关基础理论、能力与算法，覆盖多模态感知与动态环境预测。作为知识图谱，它直接关联到 Agent 的环境状态表征与时空记忆构建，为研究具身智能的记忆系统（如分层记忆或世界模型记忆）提供理论基础与工具索引，目标用户是探索认知架构与自我进化记忆的开发者。
- [**World-Model-Navigation**](https://github.com/hujch23/World-Model-Navigation) - 该项目是一个基于世界模型的导航算法实现，通过构建环境动力学预测模型（World Model）来维护和学习空间状态的内部表征，从而支撑智能体在未知环境中进行路径规划和决策。这种预测模型本质上充当了具身智能的时空记忆，能够编码过去的观测并预测未来状态，与具身记忆体系中的 World Models for Embodied AI 和 Spatial-Temporal Memory 密切相关，适用于机器人导航、仿真环境探索等场景。目标用户为研究具身智能导航与记忆机制的研究人员。

## 记忆剪枝与抽象
> **针对“全模态/巨大状态量”的核心解决方案：** 存储每一帧像素是不现实的。本板块收录通过 **事件触发、语义抽象和动态剪枝** 来压缩记忆容量的技术。

- **基于事件的记忆**：仅在发生**状态转换**时记录元数据（例如，“门打开了”而非连续视频流）。
- **语义抽象**：将复杂的物理交互压缩为原子的语义动作（例如，“抓起杯子”）。
- **MCP集成**：将机器人 SDK 状态（关节角度、扭矩）高效流式传输到智能体记忆中枢的协议。

- [**capability-graph-neuroscience**](https://github.com/For-Sunny/capability-graph-neuroscience) - 该项目提出六种基于生物学的遗忘机制，专为 LLM 智能体记忆系统设计。通过 18 项实验和 4 个被证伪的假设，利用 STDP 消融等方法（Cohen's d=3.163）验证记忆管理效果，并集成 MCP 协议连接底层状态。目标用户是研究智能体长期记忆、遗忘机制及神经符号系统的开发者。
- [**unified-memory-engine**](https://github.com/chenxi-lee/unified-memory-engine) - 企业级内存增强工具，专为 CoPaw 代理设计，通过 AES-256 加密确保数据安全，并利用分层压缩（Hierarchical Compression）优化存储与检索效率。直接面向 Agent Memory，实现了类似层级记忆管理（Hierarchical Memory Systems）和记忆修剪（Memory Pruning）的能力，适用于需要安全、高效长时记忆的 AI 代理开发场景。
- [**Criticity-Weighted-Memory-Regulation**](https://github.com/FrThierry09/Criticity-Weighted-Memory-Regulation) - 该项目提出一种基于批评性权重的记忆调控方法，用于稳定长期运行的 LLM 代理，通过动态评估记忆价值来保留高价值上下文并过滤噪声。它实现了一种认知架构中的记忆反思与自我改进机制，直接面向 Agent Memory 领域，适用于需要长效记忆管理的 AI 代理系统。
- [**ace**](https://github.com/hmatrades/ace) - 该项目是针对 LLM 智能体的记忆压缩工具，利用主观显著性指针（Subjective Salience Pointers）技术，将类似 Claude-mem 的约 17K tokens 压缩至仅 300 tokens 左右，极大提升 Agent 长期记忆存储效率。与 Agent_Memory 生态直接集成，通过压缩机制实现动态、轻量级的记忆管理。适合需要优化大模型智能体记忆容量和响应速度的开发者。
- [**selective-revocation-replay**](https://github.com/aliuyar1234/selective-revocation-replay) - 该项目是研究论文的代码实现，提出在记忆增强型 LLM 代理中应对持久化间接提示注入攻击的选择性撤销与重放机制。核心记忆机制包括对代理长期记忆中的污染数据进行溯源、选择性删除和恢复，确保代理记忆的安全性与一致性。技术实现基于记忆溯源追踪和可控重放策略，适合关注 AI 代理安全、记忆管理与鲁棒性的研究人员。
- [**graph-memory**](https://github.com/eastythenob8-svg/graph-memory) - 该项目提供将长对话历史压缩为结构化知识图谱的能力，以增强跨会话的上下文保持。它集成了 MCP（Model Context Protocol）作为连接外部环境与记忆中枢的接口，使用向量数据库和知识图谱实现高效的记忆存储与检索。适用于需要长期结构化记忆管理的 AI Agent 开发者。
- [**dream-weaver-protocol**](https://github.com/wipcomputer/dream-weaver-protocol) - Dream Weave Protocol 是一个面向有限上下文窗口 AI 智能体的记忆巩固协议，通过“Dream、Weave、Wake”三阶段实现类似睡眠周期的记忆整合与反思。它直接聚焦 Agent Memory 机制，无需外部封装即可帮助智能体抽象和压缩历史经验。适用于需要长期记忆管理和自我改进的 AI Agent 开发者。
- [**membrane**](https://github.com/BennettSchwartz/membrane) - 该项目是一个面向智能体系统的选择性学习与记忆底层库，提供类型化、可修改、可衰减的记忆机制，并集成了能力学习与信任感知检索。它实现了自我改进和自我反思的记忆管理，支持知识修改和遗忘，适合构建具有长期记忆和自主进化能力的 AI Agent。
- [**Myco**](https://github.com/Battam1111/Myco) - Myco 是一个自进化的认知有机体框架，专为 AI Agent 设计，核心实现“永恒吞噬、永恒进化”的记忆机制。它通过 MCP (Model Context Protocol) 集成长期记忆与认知基质 (cognitive substrate)，支持反思、自我改进与持续学习。项目使用 Python 开发，结合 biomimetic 理念，为构建自主 Agent 提供基础设施级记忆管理。适合需要持久化、动态演化记忆的 AI Agent 开发者。
- [**Genesis**](https://github.com/MetaforeAI/Genesis) - Genesis 是一个多八度层次化记忆系统，采用基于快速傅里叶变换（FFT）的编码和动态聚类技术，专门为 AI Agent 提供高效、可伸缩的长期记忆管理。它直接面向 Agent Memory 生态，通过频率域表示实现多尺度信息压缩与检索，适合需要复杂记忆结构的自主智能体开发。目标用户是构建具有反思和自我进化能力的 AI Agent 的研究者与工程师。
- [**Mnemoscope**](https://github.com/toonight/Mnemoscope) - Mnemoscope 是一个专为 LLM 智能体设计的可观察性与预测性记忆工具，基于 Markdown 知识库运行。它通过上下文衰减评分、Ed25519 签名哈希链日志及分层存储，监测记忆健康度并防止上下文过期。项目完全本地化，提供 MCP 服务器与 Obsidian 插件，使智能体通过模型上下文协议直接管理记忆。目标用户为需要构建长期、抗遗忘记忆机制的 AI 智能体开发者。
- [**echo-fade-memory**](https://github.com/hiparker/echo-fade-memory) - 项目是一个专注于 Agent 记忆生命周期的中间件，实现了记忆的“记住-衰减-召回-接地”四阶段可解释流程。它使用向量搜索支持记忆检索，并提供了遗忘机制以模拟人类记忆衰退，适用于需要长期记忆管理的 AI Agent 系统。基于 Go 语言实现，适合构建具备动态记忆管理的自主 Agent。
- [**trajectory-drift-demo**](https://github.com/putmanmodel/trajectory-drift-demo) - 该项目提供分层智能体记忆（stratified agent memory）中基于轨迹的漂移检测的确定性演示。它通过简单的可检查指标，展示记忆一致性随时间衰减的现象，适合研究长期记忆退化和可解释性的开发者。核心技术为确定性仿真与时间序列分析，直接面向 Agent Memory 机制。
- [**OpenAEON**](https://github.com/openaeon/OpenAEON) - OpenAEON 实现了 AEON 协议，专注于 AI Agent 的认知可观测性，其核心能力包括实时辩证流追踪、Auto-Seal 自动化记忆蒸馏及知识老化可视化。项目通过记忆蒸馏和老化管理，为智能体提供长期记忆的自优化与修剪机制，直接服务于自适应 Agent Memory 系统。
- [**llm_introspective_compression_and_metacognition**](https://github.com/Dicklesworthstone/llm_introspective_compression_and_metacognition) - 该项目提出了一种新型的 Transformer 模型内省方法，核心功能是保存、压缩和操纵模型的内部思维状态，支持推理回溯、潜在思维优化和元认知控制。它与 Agent Memory 的反思（Reflection）和自我进化（Self-Improvement）机制直接相关，通过压缩和重放内部状态实现长期记忆管理，适用于需要高级认知架构的 LLM Agent 开发。目标用户为研究元认知、记忆压缩和 Agent 自我改进的研究者和开发者。
- [**LRO**](https://github.com/zircote/LRO) - 该项目提出 Large Result Offloading (LRO) 策略，通过 token 感知方式在 LLM 上下文窗口中管理大工具输出，优化长期记忆存取。实现基于 Model Context Protocol (MCP) 的底层状态连接，支持动态上下文卸载与检索，是面向 Agent Memory 的轻量级内存管理方案。适合需要高效管理 Agent 工作记忆与工具交互状态的开发者。
- [**openclaw-memory-protocol**](https://github.com/jamebobob/openclaw-memory-protocol) - 该项目实现了一种两层持久化协议，通过重要性标记（significance tagging）和自动化夜间整合（nightly consolidation）管理 AI Agent 的记忆，基于神经科学遗忘研究优化上下文窗口和存储。它直接面向 Agent Memory 场景，提供记忆压缩、遗忘和合并机制，适合需要长期记忆管理的 AI Agent 开发者和研究者。
- [**skill-attic**](https://github.com/antontheai/skill-attic) - 该项目为 AI Agent 提供技能记忆的管理工具，实现技能遥测、评分、分层与归档，类似于长期记忆的“垃圾回收”，支持记忆修剪与动态分配。它通过 MCP 协议集成，直接面向 Agent Memory 生态，能帮助 Agent 维护高效技能库。
- [**openclaw-sticky-context**](https://github.com/jamebobob/openclaw-sticky-context) - 该项目实现 Agent 持久化记忆机制，通过在每次交互时将安全规则、身份和任务状态注入系统提示，确保在上下文压缩后关键信息不丢失，同时包含 Inner Voice Protocol 用于维护智能体的核心记忆和一致性。适合需要长期上下文保持的 AI Agent 开发者。
- [**FSFM：生物启发的智能体记忆选择性遗忘框架**](http://arxiv.org/abs/2604.20300v1) - 该论文提出 FSFM 框架，受人类认知过程启发（海马索引/巩固理论、艾宾浩斯遗忘曲线），专门针对 LLM agent 的记忆选择性遗忘机制进行系统研究。核心贡献包括：建立被动衰退、主动删除、安全触发和自适应强化四类遗忘机制分类法，通过智能记忆剪枝提升访问效率（+8.49%）、动态更新过时偏好提高内容信噪比（+29.2%）、主动遗忘恶意输入和敏感数据实现 100% 安全防护。该框架在资源受限环境中平衡记忆保留与遗忘，为 agent 长期记忆管理提供认知科学启发的实用解决方案。
- [**经验压缩谱：LLM 智能体中记忆、技能与规则的统一**](http://arxiv.org/abs/2604.15877v1) - 该论文提出了“经验压缩谱”统一框架，将 Agent 记忆（如情景记忆）、技能和规则视为沿压缩轴的不同点（5-20 倍压缩），通过对 22 篇论文的引文分析揭示了记忆与技能社区间极低的交叉引用率，并发现现有系统均固定在单一压缩级别，缺乏自适应跨级压缩（“缺失对角线”）。该框架直接关联 Agent Memory，为设计可扩展的全谱系 Agent 学习系统提供了理论基础和设计原则。
- [**何时遗忘：一种记忆治理原语**](http://arxiv.org/abs/2604.12007v1) - 本文提出了一种名为 Memory Worth（MW）的记忆治理原语，通过双计数器追踪记忆与任务成功/失败的共现频率，为智能体记忆系统的遗忘、检索抑制和废弃决策提供了轻量级且理论严谨的度量基础。实验表明，在 10,000 个 episode 后，MW 与真实效用之间的 Spearman 秩相关系数达到 0.89，显著优于静态评估方法。该工作直接以 Agent Memory 为核心，解决了记忆质量动态评估的关键问题，适用于需要长期记忆管理的自主智能体系统。
- [**StreamMeCo：面向高效流视频理解的长期智能体记忆压缩**](http://arxiv.org/abs/2604.09000v1) - 提出 StreamMeCo，一种针对流式视频理解的长期智能体记忆压缩框架。核心方法基于记忆图连通性，对孤立节点采用无边缘最小最大采样，对连接节点采用边缘感知权重剪枝，在保持准确率的前提下剔除冗余记忆节点；同时引入时间衰减记忆检索机制缓解压缩导致的性能下降。在三个基准（含具身机器人基准 M3-Bench-robot）上实现 70% 压缩率下 1.87 倍检索加速和平均 1.0% 精度提升。该工作直接以 Agent Memory 为核心，解决了长期记忆存储和计算高昂成本问题。
- [**M★：每个任务都应有自己的记忆装置**](http://arxiv.org/abs/2604.11811v1) - 本文提出 M★ 方法，通过可执行程序演化自动发现任务优化的记忆程序，将 Agent 记忆系统建模为包含数据 Schema、存储逻辑和指令的 Python 程序，并在对话、具身规划等基准上显著优于固定记忆基线。该方法为 Agent Memory 提供领域特化方案，探索了更广阔的设计空间，适用于需自适应记忆机制的智能体系统。
- [**利用小语言模型的轻量级 LLM 智能体记忆**](http://arxiv.org/abs/2604.07798v3) - 本文提出 LightMem，一种基于小语言模型（SLM）的轻量级 Agent 记忆系统。核心贡献在于模块化记忆检索、写入与长期整合，将在线处理与离线整合分离，在有限计算预算下实现高效记忆调用。系统将记忆组织为短期（STM）、中期（MTM）和长期（LTM），采用两阶段检索（向量粗筛+语义重排）提升准确性，并支持多用户独立维护。实验表明在多种模型规模上平均 F1 提升约 2.5%，为 LLM Agent 的长期交互提供了低成本、高稳定的记忆方案。
- [**MemReader：从被动到主动的长期智能体记忆提取**](http://arxiv.org/abs/2604.07877v2) - 本文提出 MemReader 系列，用于智能体系统中的长期记忆主动提取。核心贡献包括：紧凑被动提取器 MemReader-0.6B 确保准确模式一致的输出，以及基于 GRPO 优化的主动提取器 MemReader-4B，能评估信息价值、引用歧义和完整性，选择性写入记忆、延迟处理或丢弃无关内容。实验证明其在知识更新、时间推理和减少幻觉任务上达到最优，表明推理驱动的选择性记忆提取是构建低噪音动态长期记忆的关键。该工作直接以 Agent Memory 为核心方法，提供了一套从被动到主动的记忆提取机制。
- [**SuperLocalMemory V3.3：活脑——生物启发的遗忘、认知量化与多通道检索，面向零 LLM 智能体记忆系统**](http://arxiv.org/abs/2604.04514v1) - 本文提出 SuperLocalMemory V3.3（“活脑”），一个本地优先的智能体记忆系统，首次在本地记忆中数学化实现艾宾浩斯遗忘曲线、Fisher-Rao 量化感知距离（FRQAD）和 7 通道认知检索（语义、关键词、实体图、时间、扩散激活、巩固、Hopfield 关联）。该系统无需云 LLM 即可完成记忆生命周期管理，在 LoCoMo 基准测试中零 LLM 模式下达到 70.4% 准确率，为 AI 编码智能体提供了类人认知记忆架构，显著提升长期记忆效率与可扩展性。
- [**ElephantBroker：面向可信 AI 智能体的知识增强认知运行时**](http://arxiv.org/abs/2603.25097v1) - 该论文提出 ElephantBroker，一个开源的认知运行时系统，通过集成 Neo4j 知识图谱与 Qdrant 向量存储（基于 Cognee SDK），为 AI Agent 提供持久化、可验证的记忆管理。核心贡献在于实现完整的认知循环（存储、检索、评分、组合、保护、学习），包括混合五源检索、十一维竞争评分、四态证据验证、五阶段上下文生命周期、六层安全防护、AI 防火墙及九阶段记忆融合引擎，支持记忆可信度追踪和层次化访问控制。该系统专门面向高信任度多轮交互场景，增强 Agent 记忆的可靠性、安全性和可解释性，是 Agent_Memory 领域中知识增强认知架构的重要实现。
- [**MemCollab：通过对比轨迹蒸馏实现跨智能体记忆协作**](http://arxiv.org/abs/2603.23234v1) - 论文提出 MemCollab，一种跨 Agent 协作记忆框架，通过对比蒸馏不同 LLM 代理的推理轨迹，构建代理无关的共享记忆，消除代理特定偏差，提升多代理系统性能。该工作直接将 Agent Memory 作为核心方法，实现了跨模型、跨家族的记忆共享与泛化，适用于异构智能体协作场景。
- [**面向个性化智能体记忆的结构化蒸馏：11 倍令牌缩减且保留检索能力**](http://arxiv.org/abs/2603.13017v1) - 该论文提出结构化蒸馏方法，将单用户与 AI 代理的对话历史压缩为紧凑检索层，实现 11 倍令牌缩减（371→38 tokens）。通过构建包含 exchange_core、specific_context 等四个字段的复合对象，在 4182 个对话上评估，最佳纯蒸馏配置达到原始检索 MRR 的 96%（0.717 vs 0.745），交叉层配置甚至略超基线。方法直接以 Agent Memory 为核心，解决个性化记忆的存储与检索效率问题。

## 基准测试与评估
- [**FindingDory：评估具身智能体记忆的基准**](http://arxiv.org/abs/2506.15635v2) - 本文提出了 FindingDory 基准，专为在 Habitat 模拟器中评估具身智能体的长期记忆能力而设计。该基准包含 60 个需要持续上下文感知和物体操作的长程任务，支持程序化扩展，填补了现有长视频问答基准忽略具身导航与操作挑战的空白。它将历史信息回忆与基于记忆的动作执行紧密结合，为检验 Agent Memory 中的情景记忆与时空记忆提供了专用平台，对推动视觉语言模型在机器人领域的长时控制应用具有关键价值。
- [**LoCoMo-Plus：面向 LLM 智能体的超事实认知记忆评估框架**](http://arxiv.org/abs/2602.10715v1) - 该论文提出了 LoCoMo-Plus 基准与评估框架，专注评估 LLM Agent 在长对话中的认知记忆，要求模型在提示与查询语义脱节的场景下保持并应用隐含约束（如用户状态、目标、价值观）。与 Agent Memory 直接相关，它摒弃了表面事实回忆，通过约束一致性统一度量多个记忆系统，揭示了现有检索与记忆方法的短板，并提供了公开代码与评测数据，为 Agent 记忆能力的深层评估提供了新工具。
- [**memstate-benchmark**](https://github.com/memstate-ai/memstate-benchmark) - 该项目是一个开源的 AI Agent 内存系统基准测试框架，专为评估和比较不同内存解决方案（如 Memstate、mem0）而设计。它基于 MCP（Model Context Protocol）实现内存集成，并支持通过 OpenRouter 调用多种 LLM 模型（如 Claude Opus、Gemini）在真实 Agent 任务中进行测试。通过提供统一的评估指标，帮助开发者选择最优的 Agent 内存架构，特别适合研究者和 AI 工程师优化代理记忆机制。
- [**agentbrain-benchmarks**](https://github.com/AgentBrainHQ/agentbrain-benchmarks) - 项目提供 Agent Brain 在 LongMemEval-M 上的可复现基准测试代码，准确率达 71.7%（Test 0）。它直接面向 Agent 长期记忆评估，利用 dream-cycle、知识图谱和 FSRS 等技术构建记忆评测体系，为研究 Agent Memory 的性能与反思机制提供标准化测试工具。适合从事 Agent 记忆评估与基准测试的研究人员使用。
- [**mnemebrain-benchmark**](https://github.com/mnemebrain/mnemebrain-benchmark) - 该项目提供专门评估 AI Agent 记忆系统信念动态的基准测试套件，包含 48 个任务，覆盖矛盾检测、信念修正、溯源推理和时序推理等核心能力。它直接针对 Agent Memory 领域，通过图数据库和知识图谱实现认知架构中的记忆评估，适合研究 Agent 记忆机制和认知架构的开发者使用。
- [**agent-memory-eval**](https://github.com/verifiedstate/agent-memory-eval) - 该项目是一个开放的 AI 智能体记忆系统基准测试套件，专门用于评估智能体在时间推理、冲突检测、多跳检索、弃权能力和溯源等方面的记忆性能。它直接面向 Agent Memory 生态，提供标准化的评测框架，有助于研究人员和开发者对比不同记忆方案的效果，推动记忆系统的发展与改进。
- [**MemBase**](https://github.com/zjunlp/MemBase) - MemBase 是一个专为长期对话记忆层设计的综合基准测试框架，旨在评估和比较不同记忆机制在 AI 代理（Agent）中的表现。它提供了标准化的测试集和评测指标，直接服务于 Agent Memory 的研发与优化。项目基于 Python 实现，适用于研究大语言模型记忆系统、具身智能记忆管理的开发者。
- [**智能体记忆论文列表**](https://github.com/yyyujintang/Awesome-Agent-Memory-Papers) - 该项目是一个精心整理的 Agent Memory 论文列表，涵盖方法、基准与综述，为研究者和开发者提供前沿文献索引。其内容直接聚焦于长期记忆、认知架构、具身 AI 记忆等 Agent Memory 核心技术，可作为深入理解记忆机制的入门资源。目标用户为从事 AI Agent、具身智能和记忆系统设计的研究人员。
- [**ATM-Bench**](https://github.com/JingbiaoMei/ATM-Bench) - ATM-Bench 是一个专为评估 AI Agent 长期个性化记忆能力设计的基准测试，覆盖约 4 年的多模态数据（图像、视频、电子邮件）。它提供引用查询、证据锚定回答及多源推理任务，直接面向 Agent Memory 中的长期记忆与记忆代理机制，适合研究记忆持久化与检索增强生成的团队。
- [**AMA-Bench**](https://github.com/AMA-Bench/AMA-Bench) - 该项目是一个针对智能体长程记忆性能的标准化评估框架，专门衡量代理应用在长上下文保持与长时间跨度记忆任务中的表现。它提供统一的基准测试方法和指标，直接服务于 Agent Memory 领域的研究与开发。适用于需要量化评估智能体记忆能力的开发者与研究人员。
- [**Mem-Gallery**](https://github.com/YuanchenBei/Mem-Gallery) - Mem-Gallery 是一个多模态长期对话记忆基准测试项目，专为 MLLM 智能体设计。它提供标准化的评估框架，测试智能体在长时间交互中记忆、检索和利用多模态信息（文本、图像等）的能力，直接聚焦于 Agent Memory 的核心挑战。项目通过构建包含复杂对话场景的数据集和评测指标，帮助开发者验证和改进智能体的长时记忆机制。适用于研究对话型 AI 代理和多模态记忆系统的研究人员。
- [**agent-memory-benchmark**](https://github.com/vectorize-io/agent-memory-benchmark) - 该项目提供了一个用于评估 AI 代理记忆系统性能的基准测试框架。它通过标准化指标（如检索精度、召回率和延迟）测试不同记忆策略，特别关注 LLM 代理的长短期记忆管理。项目实现了可扩展的评估管道，支持自定义记忆模块集成，适用于研究者和开发者量化 Agent Memory 方案的效率。
- [**AgentMemoryBench**](https://github.com/s010m00n/AgentMemoryBench) - AgentMemoryBench 是一个统一基准测试，用于评估基于 LLM 的智能体在持续记忆（Continual Agent Memory）方面的能力。它支持在线、离线、回放、迁移和修复五种评估模式，覆盖六个交互任务，兼顾系统记忆与个人记忆机制。该项目直接面向 Agent Memory 评估，为研究智能体记忆的持久化、检索与进化提供了标准化评测工具，适用于 LLM 智能体记忆研究者。
- [**governed-memory**](https://github.com/personizeai/governed-memory) - 该仓库提供合成数据集、实验协议和评估代码，用于“Governed Memory”生产架构，面向多代理工作流中的记忆治理。它实现了带治理规则的长期记忆系统，支持 RAG 和 LLM 评估基准，专门优化 Agent Memory 的持久化与访问。适合需要生产级多代理记忆管理与评测的研究者和工程师。
- [**MEXTRA**](https://github.com/wangbo9719/MEXTRA) - MEXTRA 是针对大型语言模型（LLM）Agent 记忆系统的隐私风险分析工具与论文源码。该项目系统性地评估了 Agent 长期记忆模块中可能存在的敏感信息泄露途径，提出了一套量化隐私暴露程度的框架与方法。主要面向 AI Agent 安全研究人员及 LLM 记忆系统开发者，帮助识别并缓解记忆模块中的隐私隐患。
- [**agent-memory-tck**](https://github.com/neo4j-labs/agent-memory-tck) - 该项目是 Neo4j Agent Memory 的技术合规性测试套件（TCK），用于验证各类实现是否符合 Neo4j 定义的 Agent Memory 规范。通过提供标准化测试用例，确保基于 Neo4j 构建的 Agent 记忆模块在知识图谱持久化、检索和一致性方面达到标准。适用于需要保证 Neo4j Agent Memory 集成质量的开发者和架构师。
- [**PyramidBench**](https://github.com/zhoujunlingla/PyramidBench) - PyramidBench 是一个专注于层级金字塔记忆评估的 VLA 基准测试项目，用于系统评估具身智能体的长期记忆与分层记忆组织能力。它通过设计特定任务来测试记忆的分层构建、存储与检索效率，与 Agent Memory 中的层级记忆系统和具身 AI 记忆紧密相关。该基准主要面向具身 AI 和 VLA 模型的研究人员，帮助比较不同记忆架构在物理仿真环境中的表现。
- [**AMSC**](https://github.com/reiiwang/AMSC) - 该项目旨在提供 Agent Memory 解决方案的系统性比较，涵盖多种记忆机制的分析与评估。它专注于代理记忆领域，为开发者选择合适的内存架构提供参考。项目以 Python 实现，目标用户是研究 Agent Memory 的学者与工程师。
- [**System-2 推理 LLM 资源列表**](https://github.com/zzli2022/Awesome-System2-Reasoning-LLM) - 本项目汇总了 System-2 推理（慢思考）的最新研究，涵盖 MCTS、自我改进、强化学习等技术，旨在提升 LLM 的复杂推理能力。其中多项工作与 Agent 记忆机制紧密关联，如反思式自我进化和世界模型构建，为具身智能体和认知架构的记忆组件设计提供了前沿参考，适合研究 Agent Memory 架构的人员查阅。
- [**Spore：通过推理时混合探测对 LLM 进行高效且无需训练的隐私提取攻击**](http://arxiv.org/abs/2604.23711v1) - 本文提出 Spore，一种无需训练、在推理阶段通过混合探测高效提取 LLM 代理记忆隐私的攻击方法。Spore 在黑白灰盒设置下均有效，仅需单次查询即可恢复原始隐私信息，揭示了现有代理记忆系统在上下文交互中的严重隐私泄露风险，为提升 Agent Memory 安全防护提供了量化依据。
- [**EgoTL：面向长程任务的自我中心出声思维链**](http://arxiv.org/abs/2604.09535v1) - 论文提出 EgoTL，一个面向自我中心数据的思想出声采集管道，通过 '先想后做' 协议记录词级时间戳的目标与推理，并利用度量尺度空间估计器、记忆库遍历（memory-bank walkthrough）提供场景上下文，以及剪辑级导航与操作标签，构建了覆盖上百项日常家务的长序列基准。在此基础上，作者评估了 VLM 与世界模型在六维任务上的表现，发现基座模型仍难以胜任自我中心助手或开放世界仿真，进而利用与度量标签对齐的人类思维链微调模型以提升性能。该工作明确将记忆库遍历作为记忆模块，用于构建具身任务中的状态与场景记忆，直接对应 Agent Memory 中的环境记忆管理。
- [**MemGround：大语言模型在游戏化场景中的长期记忆评估套件**](http://arxiv.org/abs/2604.14158v1) - 该论文提出 MemGround 基准，用于评估大语言模型在游戏化交互场景中的长期记忆能力。核心贡献在于设计了包含表面状态记忆、时间关联记忆和基于推理记忆的三层评估框架，并通过多项指标（如问答得分、记忆片段解锁等）系统衡量智能体在动态环境中的状态追踪和层次推理能力。相关工作直接聚焦 Agent Memory 评估，为构建具身智能体的记忆系统提供了标准化测试工具。
- [**诊断 LLM 智能体记忆中的检索与利用瓶颈**](http://arxiv.org/abs/2603.02473v2) - 本文提出诊断框架，系统分析 LLM Agent 记忆写入与检索的瓶颈。通过 3x3 实验（三种写入策略×三种检索方法）在 LoCoMo 数据集上发现，检索方法主导性能差异（准确率跨度 20 点），而写入策略影响仅 3-8 点。原始分块存储无需 LLM 调用即可媲美或超越有损压缩策略，揭示当前记忆管线可能丢弃有用上下文。代码开源。
- [**AMA-Bench：评估智能体应用的长时记忆**](http://arxiv.org/abs/2602.22769v2) - 提出 AMA-Bench 基准，用于评估 LLM 代理在真实应用中的长时记忆能力，包含真实代理轨迹与可扩展的合成轨迹。发现现有记忆系统因缺乏因果关系和客观信息、受限于相似性检索的损失性而表现不佳。提出 AMA-Agent 记忆系统，集成因果图与工具增强检索，在基准上达到 57.22% 平均准确率，超越最强基线 11.16%，为 Agent Memory 评估提供了标准化框架。
- [**MemoryArena：在相互依赖的多会话智能体任务中评估智能体记忆**](http://arxiv.org/abs/2602.16313v1) - 论文提出 MemoryArena 基准测试平台，专门评估智能体在多会话、相互依赖的任务中如何利用长期记忆指导后续行动。该平台要求智能体在交互中提炼经验存入记忆，并在后续会话中检索使用，涵盖网页导航、偏好约束规划、渐进信息搜索和顺序形式推理等场景。实验表明，现有长上下文记忆基准（如 LoCoMo）上表现饱和的智能体在 MemoryArena 中性能显著下降，揭示了当前评估体系的关键缺口。
- [**TAME：基于系统基准的智能体记忆可信测试时演化**](http://arxiv.org/abs/2602.03224v1) - 该论文提出 TAME 框架，针对 agent memory 在测试时演化中出现的可信度下降问题（Agent Memory Misevolution），构建了 Trust-Memevo 基准，系统评估多维可信度。TAME 采用双记忆架构，分别演化执行器记忆（提取通用方法提升任务性能）和评估器记忆（基于历史反馈优化安全与效用评估），通过记忆过滤、生成、可信精炼、执行与双轨更新闭环，在保持效用同时提升可信度。核心贡献在于首次系统性研究 agent memory 的可信演化，并提供有效解决方案。
- [**MemoryGraft：通过中毒经验检索持久破坏 LLM 智能体**](http://arxiv.org/abs/2512.16962v1) - 本文首次揭示 LLM Agent 长期记忆与 RAG 系统的新型攻击面，提出 MemoryGraft 攻击，通过向 Agent 经验存储中植入少量恶意模板，利用其语义模仿启发式在检索时触发持久行为漂移。该工作直接以 Agent Memory 的存储、检索与经验学习机制为核心攻击目标，暴露了记忆系统在信任边界上的安全漏洞，为 Agent 记忆防护设计提供了关键警示。
- [**超越百万令牌：大语言模型长期记忆的基准测试与增强**](http://arxiv.org/abs/2510.27246v2) - 论文提出了 BEAM 基准和 LIGHT 框架，BEAM 通过自动生成长达 10M token 的连贯对话评估 LLMs 的长时记忆，LIGHT 则受人类认知启发，为 LLMs 配备长期情景记忆、短期工作记忆和便签式积累三种互补记忆系统，显著提升模型在长对话中的记忆能力，实验表明在多种模型上平均提升 3.5%-12.69%。该工作直接以长时记忆作为核心方法，并设计了类认知架构的记忆系统，属于 Agent Memory 典型研究。
- [**评估长上下文问答中的长期记忆**](http://arxiv.org/abs/2510.23730v2) - 该论文系统性评估了多种长期记忆机制（语义记忆、情景记忆、程序记忆）在长上下文问答任务中的效果，发现记忆增强方法可减少 90% 以上 token 消耗且保持精度。特别分析了代理记忆（agentic memory）和基于反思的情景记忆对模型性能的影响，为 Agent Memory 系统的设计与复杂度选择提供了实证依据。
- [**VLN-ChEnv：变化环境下的视觉语言导航**](https://openalex.org/W4415539951) - 论文研究了指令与环境不匹配情况下的视觉语言导航（VLN），提出 ImperfectVLN 任务与数据集，并设计了一个反思模块，使智能体能够回顾自身历史轨迹、识别潜在错误，从而将导航性能提升 4.4%。该反思模块本质上是一种基于历史经验的自我修正记忆机制，让智能体从过去行动中学习并改进，直接体现了 Agent Memory 在具身任务中的应用。
- [**FlashAdventure：面向 GUI 智能体在多样化冒险游戏中解决完整故事线的基准**](http://arxiv.org/abs/2509.01052v2) - 该论文提出 FlashAdventure 基准，包含 34 款 Flash 冒险游戏，旨在测试 GUI 智能体完成完整故事线的能力，并解决观察-行为差距：即记忆与利用早期游戏信息的挑战。作者设计了 COAST 智能体框架，利用长期线索记忆（long-term clue memory）来更好地规划和执行序列任务，实验表明 COAST 通过记忆桥接提高了里程碑完成率。这项工作揭示了长期记忆在复杂交互式数字环境中的关键作用，为 Agent Memory 在 GUI 智能体领域的应用提供了验证与基准。
- [**通过增量多轮交互评估 LLM 智能体中的记忆**](https://openalex.org/W4415971869) - 该论文提出 MemoryAgentBench 基准，专门用于评估 LLM Agent 的记忆能力。基于记忆科学和认知科学，定义了四个核心记忆能力：准确检索、测试时学习、长程理解和选择性遗忘。通过将现有长上下文数据集转换为多轮交互格式，模拟 Agent 增量积累信息的场景，提供了系统化的测试平台。该基准直接以 Agent Memory 为核心评估对象，填补了现有基准缺乏对记忆能力全面评估的空白。

## 基础设施与数据库
- [**graymatter**](https://github.com/angelnicolasc/graymatter) - Graymatter 是一个轻量级持久化记忆库，旨在通过三行代码为 AI 代理注入长期记忆能力，显著降低 90% 的 token 消耗同时保持回答质量。它采用 Go 语言实现、支持离线优先和自托管部署，直接面向 Agent Memory 场景。适合需要低成本、高效记忆集成的 AI Agent 开发者。
- [**icarus-daedalus**](https://github.com/esaradev/icarus-daedalus) - Icarus Memory Protocol 是一个轻量级的通用 Agent 记忆协议，仅用约 50 行代码通过本地目录中的 Markdown 文件实现持久化存储。它支持任意框架和平台（Telegram、Slack），并提供双智能体参考实现，可实现跨平台记忆共享与回忆。该项目专注于为 AI Agent 提供极简、通用的记忆机制，适合需要快速集成简易记忆功能的开发者。
- [**agent-memory-server**](https://github.com/redis/agent-memory-server) - 该项目是一个专为 AI Agent 和应用程序设计的快速灵活内存服务器，基于 Redis 实现。它提供持久化和检索能力，支持 Agent 实时读写记忆数据，适用于需要长期记忆、会话状态管理或认知架构的智能体系统。项目直接以 Agent Memory 为核心，实现了高效的内存存储与查询，目标是帮助开发者构建具备记忆能力的 Agent。
- [**memorizer**](https://github.com/petabridge/memorizer) - 该项目是一个基于向量检索的 Agent Memory MCP 服务器，专门为大语言模型代理提供持久化记忆管理与上下文检索能力。它通过 MCP（Model Context Protocol）标准接口与代理系统集成，支持高效存储和查询历史经验与状态，适用于需要长期记忆的对话代理或具身智能场景。主要采用向量搜索实现语义匹配，目标用户为构建 AI Agent 的开发者，特别是需要物理环境底层状态记忆中枢的具身智能项目。
- [**hipocampus**](https://github.com/kevin-hs-sohn/hipocampus) - Hipocampus 是一个即插即用的 AI Agent 记忆框架，具备三层次记忆结构（工作记忆、短期记忆、长期记忆）与压缩树机制，支持混合搜索（向量+语义）。它通过一条命令即可完成配置，可与 Claude Code 和 OpenClaw 直接集成，为智能体提供持久化上下文与反思能力。项目专注于 Agent 记忆管理，包含显式的长期记忆和压缩检索，适用于需要复杂记忆机制的 AI Agent 开发者。
- [**mcp-openmemory**](https://github.com/baryhuang/mcp-openmemory) - 该仓库是一个基于 MCP（Model Context Protocol）的轻量级记忆服务器，旨在为 Claude 等 AI Agent 提供对话记忆和持续学习能力。它实现了 Agent 记忆中枢功能，支持长期记忆存储与检索，使 Agent 能在交互中积累经验并改进行为。适用于希望为 AI Agent 添加持久记忆能力的开发者。
- [**Zikkaron**](https://github.com/amanhij/Zikkaron) - Zikkaron 是一个受生物启发的持久记忆引擎，专为 Claude Code 设计，提供 26 个认知子系统的本地推理能力。它通过 Hopfield 网络、预测编码、因果发现和继代表征等机制实现类脑记忆管理，并集成了 MCP（Model Context Protocol）服务端，可直接连接底层环境状态进行记忆中枢构建。适用于需要长期、结构化、自更新记忆的 AI Agent 开发者。
- [**rasputin-memory**](https://github.com/jcartu/rasputin-memory) - rasputin-memory 是一个专为 AI 代理设计的持久化记忆后端，通过 LLM 事实提取、基础模型重排序和混合搜索（BM25 + 向量 + 知识图谱）实现高效记忆检索，在 LoCoMo 基准上达到 77.7% 准确率。原生支持 MCP 协议和 REST API，可自托管，适合需要长期记忆和反思机制的 OpenClaw、Claude Code 等代理系统。
- [**agentic-memory**](https://github.com/agentralabs/agentic-memory) - agentic-memory 是一个基于 Rust 构建的持久化认知图记忆系统，专为 AI 代理设计，支持存储事实、决策、推理链和纠错。提供 16 种查询类型并实现亚毫秒级响应，同时配备 Python SDK 和 MCP 服务器，可直接与物理环境底层状态对接。适合需要高效长期记忆与认知架构的智能体开发者。
- [**mcp-context-server**](https://github.com/alex-feel/mcp-context-server) - alex-feel/mcp-context-server 是一个基于 FastMCP 的服务器，为 LLM 代理提供持久化的多模态上下文存储。它通过 Model Context Protocol (MCP) 实现记忆中枢连接，支持工作内存、短期记忆和 scratchpad 等功能，可直接集成至 AI 代理系统。适用于需要构建复杂记忆机制（如反思、自我改进）的 Agent 开发者。
- [**crux**](https://github.com/ardey26/crux) - Crux 是一个面向 AI Agent 的知识版本管理工具，类似 Git 但用于记录代理对世界认知（Belief Graph）的变更历史。它支持信念的版本化、依赖追踪与无效化撤销，允许 agent 回滚认知状态并进行自我反思。项目直接聚焦于 Agent Memory，通过持久化世界模型实现认知演化，适用于需要长期记忆与自我改进机制的智能体系统。
- [**state-trace**](https://github.com/razroo/state-trace) - 该项目提供了一个图形原生的工作记忆引擎，专为编码代理设计，支持类型化记忆节点、基于因果关系的检索、有界容量以及针对小模型的紧凑摘要生成。其核心机制直接服务于 Agent 的短期记忆管理，可与具身智能代理的长短期记忆架构集成，适用于需要高效记忆管理的自动化编码或调试代理。
- [**mnemebrain-sdk**](https://github.com/mnemebrain/mnemebrain-sdk) - 该项目提供 Python SDK，用于构建 AI 智能体的信念记忆系统。它支持 MnemeBrain 的 Lite 和 Full API，实现基于知识图谱和信念修正的长期记忆管理，帮助智能体进行推理和检索增强生成（RAG）。适合需要复杂记忆机制并追求记忆可演化的 AI Agent 开发者。
- [**myelin-kernel**](https://github.com/Tetrahedroned/myelin-kernel) - myelin-kernel 是一个轻量级、线程安全的内存内核，专为自主智能体设计。它通过强化学习机制增强知识关联，利用温和衰减自动修剪不常用记忆，支持透明导出为 Markdown。基于纯 SQLite 实现持久化，为智能体提供自我改进的推理基础。适用于需要长期记忆和知识进化的 LLM 智能体开发者。
- [**fidelis**](https://github.com/hermes-labs-ai/fidelis) - Fidelis 是一个专为 AI Agent 设计的本地优先、高保真记忆库，旨在避免检索退化与额外开销。它采用 ChromaDB 向量存储与整数指针技术，默认检索路径不含 LLM，实现零成本查询，并在 LongMemEval-S 上取得 83.2% R@1。项目深度融合代理记忆生态，支持 MCP 集成与 Ollama 等本地推理，直接解决 Agent 长期记忆的可靠性与成本问题，面向需要精确、快响应记忆的 Claude Code 及通用 Agent 开发者。
- [**agent-memory-dotnet**](https://github.com/joslat/agent-memory-dotnet) - 该项目是一个基于 .NET 的独立 Agent 内存提供程序，后端使用 Neo4j 图数据库实现持久化、图原生的记忆存储。它专为 Microsoft Agent Framework 设计，支持 GraphRAG 互操作，使 AI Agent 能够利用图结构进行长期记忆的检索与推理。适合需要图内存支持的 .NET Agent 开发者。
- [**mnemon**](https://github.com/cipher813/mnemon) - 该项目是一个自托管的 AI Agent 长期记忆系统，通过 MCP（Model Context Protocol）实现统一记忆中枢。支持在 Claude Code、Cursor、Claude Desktop 等平台间共享记忆，采用嵌入向量和语义搜索技术存储和检索历史交互。适合需要跨工具持久化记忆的 AI Agent 开发者。
- [**zer0dex**](https://github.com/hermes-labs-ai/zer0dex) - zer0dex 是一个本地双层次记忆系统，专为 AI 代理设计，通过压缩索引与向量检索实现高效的长短期记忆管理。项目直接面向 Agent_Memory，采用 RAG 与向量搜索技术，为代理提供持久化上下文感知能力，目标用户是构建具有持久记忆能力的 AI 代理开发者。
- [**clickmem**](https://github.com/auxten/clickmem) - clickmem 是基于嵌入式 ClickHouse（chDB）构建的专用 Agent 记忆存储工具，为 AI Agent 提供高性能、持久化的状态存储与检索能力。它直接服务于 Agent Memory 场景，利用列式数据库优化记忆数据的读写效率，支持结构化与非结构化混合记忆，并通过 SQL 接口实现灵活查询。适用于需要轻量级、低延迟记忆后端的 Agent 开发项目。
- [**openclaw-neo4j-agent-memory-plugin**](https://github.com/johnymontana/openclaw-neo4j-agent-memory-plugin) - 该项目为 OpenClaw 代理框架提供图原生记忆插件，利用 Neo4j 知识图谱实现短期、长期和推理记忆，使 Agent 具备持久化上下文和动态推理能力。通过构建上下文图谱，支持记忆的反射（Reflection）与自我改进机制，强化 Agent 对环境的理解。适用于需要结构化记忆和高效检索的 AI Agent 开发，尤其适合集成知识图谱的认知架构。
- [**skalex**](https://github.com/TarekRaafat/skalex) - TarekRaafat/skalex 是一个 AI 优先、零依赖的 JavaScript 数据库，内置向量搜索、Agent Memory 和 MCP 服务器支持。它为 AI Agent 提供原生记忆存储与检索，通过 MCP 协议可连接物理环境状态，适用于 Node.js、浏览器及边缘运行时。项目面向需要本地化、轻量级记忆方案的 Agent 开发者。
- [**memoryOSS**](https://github.com/memoryOSScom/memoryOSS) - memoryOSS 是一个为 AI 代理提供持久性长期记忆的开源工具，通过本地代理和 MCP（Model Context Protocol）记忆层实现。它专门适配 Claude、Codex 及兼容 OpenAI 的客户端，支持上下文管理和检索，关键技术采用 Rust 编写以追求高性能。该项目直接面向 Agent_Memory 领域，可作为具身智能或对话智能体的记忆中枢。
- [**lightning-memory**](https://github.com/singularityjason/lightning-memory) - lightning-memory 是一个去中心化的代理内存系统，专为闪电网络生态设计。它利用 Nostr 身份认证和 L402 支付协议，通过 MCP 服务器为 AI Agent 提供持久化、可检索的记忆存储。核心机制包括语义搜索和 SQLite 数据管理，支持分布式节点间的记忆同步。该项目直接面向 Agent 内存需求，适合需要去中心化身份与支付集成的 AI 开发者。
- [**mind-mem**](https://github.com/star-ga/mind-mem) - 为编码代理提供持久化、可审计、矛盾安全的内存系统，实现治理推理链与 .mind 不变式，结合 Postgres+Redis 缓存及混合 BM25+向量+RRF 搜索，通过 58 个 MCP 工具和 17 个 AI 客户端提供模型上下文协议内存中枢，支持本地优先和细粒度治理。目标用户是需可靠记忆机制的 AI 代理开发者。
- [**turbo_quant_memory**](https://github.com/Lexus2016/turbo_quant_memory) - Turbo Quant Memory 是一个本地优先的 MCP 内存服务器，专为 AI 编码代理（如 Claude Code、Cursor 等）设计，提供紧凑检索与项目/全局作用域的记忆管理。它基于 Model Context Protocol 实现持久化存储，支持语义搜索和局部范围的上下文复用，确保敏感代码数据不离开本地环境。适合需要高效、私密且可伸缩记忆机制的 AI 代理开发者。
- [**agentmem**](https://github.com/oxgeneral/agentmem) - AgentMem 是一个轻量级的 AI 代理持久化记忆库，基于单个 SQLite 文件实现混合搜索（向量+全文检索），支持知识图谱和 FTS5 索引，体积仅 0-12MB。它原生集成 MCP（Model Context Protocol）服务器，可作为连接物理环境底层状态的记忆中枢，适合需要小型、嵌入式长期记忆方案的 Agent 开发者。
- [**sdr-memory**](https://github.com/angelsu/sdr-memory) - angelsu/sdr-memory 是一个轻量级的 LLM Agent 长期记忆库，采用稀疏分布式表示（SDR）技术，无需向量数据库、GPU 或外部服务器，仅依赖 SQLite 实现记忆存储与检索。与 Agent_Memory 直接关联，提供基于认知架构的高效记忆机制，支持反思与自我进化。适合需要离线、轻量级记忆方案的 AI Agent 开发者使用。
- [**beacon**](https://github.com/ConnorBritain/beacon) - Beacon 是专为跨平台智能代理设计的核心持久化层，利用 Supabase Postgres 实现代理记忆的稳定存储与高效检索。它直接服务于 Agent Memory 场景，支持记忆跨工具和环境的持久化，技术基于关系型数据库。适合需要持久化记忆机制的 AI Agent 开发者。
- [**Zikra**](https://github.com/getzikra/Zikra) - Zikra 是一个为 Claude Code 设计的自托管持久化记忆 MCP 服务器，采用 n8n、PostgreSQL 与 pgvector 实现向量存储，无需云服务。它通过 Model Context Protocol 为 AI 代理提供长期记忆的存储、检索与管理工作流，支持本地化知识管理。适合需要构建私有化 Agent 记忆系统且偏好低代码编排的开发者。
- [**langgraph-store-vertex-memorybank**](https://github.com/zeroasterisk/langgraph-store-vertex-memorybank) - 该项目为 LangGraph 的 BaseStore 提供基于 Vertex AI Agent Engine Memory Bank 的后端实现，专门用于持久化和检索智能体的长期记忆。它通过 LangGraph 的接口直接集成 Google Cloud 的 Agent Memory 服务，适用于需要云端记忆中枢的 LLM Agent 应用。目标用户是使用 LangGraph 构建具备持久记忆能力的 AI Agent 的开发者。

## 相关列表与灵感来源
- [**Awesome-AI-Memory (IAAR-Shanghai)**](https://github.com/IAAR-Shanghai/Awesome-AI-Memory)
- [**Awesome-Embodied-AI**](https://github.com/ahundt/awesome-embodied-vision)

---
## 贡献指南
欢迎贡献！请专注于应对物理世界中**十亿级状态管理**的发明。

---

<div align="center">

## 🤖 Auto-Generated

This awesome list is automatically maintained by [GPT-Awesome-List-Generator](https://github.com/shaoxiang/GPT-Awesome-List-Generator).

</div>