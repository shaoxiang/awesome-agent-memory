[English](./README.md)

# Awesome Agent & Embodied Memory 🤖🧠

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 一个精心整理的**记忆框架、认知架构和状态管理技术**合集，专为自主AI智能体和具身智能设计。
> *重点关注**大规模、多模态、实时物理世界数据**的管理。*

## 📖 Contents
- [基础理论与综述](#基础理论与综述)
- [通用AI智能体记忆框架](#通用ai智能体记忆框架)
- [具身AI专用记忆](#具身ai专用记忆)
- [时空与语义地图](#时空与语义地图)
- [世界模型与状态预测](#世界模型与状态预测)
- [记忆剪枝与抽象](#记忆剪枝与抽象)  *[针对全模态巨大状态量的关键板块]*
- [基准与评估](#基准与评估)
- [基础设施与数据库](#基础设施与数据库)
- [相关列表与灵感来源](#相关列表与灵感来源)

---



## 基础理论与综述
*深入探索智能体记忆背后的认知科学和架构理论。*

- [**A Survey on Memory for LLM-based Agents**](https://arxiv.org/abs/2411.13555) - 一篇综合性的综述，涵盖了基于LLM的智能体记忆机制、评估方法和架构设计。
- [**memory**](https://github.com/higgs-works/memory) - 为本地AI Agent设计的类人记忆系统，核心采用传播激活(Spreading Activation)和联想回忆机制实现记忆自动浮现，而非传统搜索。集成MCP协议连接外部状态，使用SQLite本地存储支持情节记忆(Episodic Memory)持久化。适用于需要长期、语义化Agent Memory的隐私优先场景。
- **The Missing Knowledge Layer in Cognitive Architectures for AI Agents** *(arXiv, 2026)* - 提出了一个四层分解模型：知识层、记忆层、智慧层、智能层。
- [**agent-memory**](https://github.com/reaatech/agent-memory) - 该项目为AI代理提供跨会话的长期记忆层，核心功能包括记忆提取、语义检索、事实存储、衰减与矛盾消解。它适配Qdrant、Pinecone和pgvector等向量数据库，实现对代理历史交互的持续分析与知识沉淀，确保代理在长时间运行中保持上下文连贯与自我改进能力，是构建具备反思与进化功能的智能代理的关键基础设施，适合需要复杂记忆管理和知识演化的开发者。


- [**memsearch**](https://github.com/zilliztech/memsearch) - MemSearch 是一个以 Markdown 为先的独立记忆库，专为任意 AI Agent 设计，受 OpenClaw 启发。它利用 Milvus 进行嵌入存储与混合搜索，结合重排序与渐进式披露机制，为 Agent 提供高效的长短期记忆管理，支持语义检索与 RAG 集成。目标用户是需要轻量级、脱离框架依赖的记忆系统的 AI 代理开发者。
- [**memorycrystal**](https://github.com/memorycrystal/memorycrystal) - 该项目是一个AI Agent持久化记忆工具，通过OpenClaw插件和MCP服务器实现跨会话记忆维持。核心机制利用MCP（Model Context Protocol）连接物理环境底层状态，支持Claude、OpenAI等LLM的长期记忆存储与检索。基于TypeScript开发，提供convex后端集成，适合需要情景记忆的具身Agent与认知架构开发者使用。
- [**engram**](https://github.com/NickCirv/engram) - EngramX 是一个为 AI 编码代理设计的缓存上下文脊柱，提供9个内置存储提供者并支持通过MCP服务器扩展。它实现了双时记忆（bi-temporal memory）和Anthropic自动记忆桥，具备预检错误防护和SSE流式传输，可显著节省token（实测89.1%）。适合需要高效上下文管理和长期记忆的AI代理开发者。
- [**Solitaire-for-Agents**](https://github.com/PRDicta/Solitaire-for-Agents) - 该项目为AI代理提供身份基础设施，采用本地优先与模型无关设计，不仅限于普通记忆工具。它通过MCP（Model Context Protocol）服务器实现持久化内存、会话管理和个性化，支持知识图谱与长期记忆，适合需要身份识别与上下文持久化的具身智能代理系统。
- [**archon-memory-core**](https://github.com/atw4757-byte/archon-memory-core) - 该项目提供基于夜间整合、主动遗忘和显著性评分的智能体记忆系统，支持长期记忆持久化与自我进化，在AMB基准上得分9.01/10。它作为本地优先的替代方案（如Mem0、Letta），专为AI Agent设计，适合需要高级记忆管理和自我反思机制的Agent开发者。
- [**mcp-memory-service**](https://github.com/doobidoo/mcp-memory-service) - 本项目提供一个开源持久化记忆服务，专为AI Agent管道（如LangGraph、CrewAI、AutoGen）和Claude设计。它通过REST API结合知识图谱与自主整合机制，实现长期记忆存储与管理，并支持MCP（Model Context Protocol）协议，可直接作为MCP服务器连接外部环境。核心技术包括向量数据库（sqlite-vec）、语义搜索及RAG检索。适用于需要跨会话保持Agent状态、实现反思和自我进化记忆的开发者。
- [**hipocampus**](https://github.com/kevin-hs-sohn/hipocampus) - Hipocampus 是一个即插即用的 AI Agent 记忆框架，具备三层次记忆结构（工作记忆、短期记忆、长期记忆）与压缩树机制，支持混合搜索（向量+语义）。它通过一条命令即可完成配置，可与 Claude Code 和 OpenClaw 直接集成，为智能体提供持久化上下文与反思能力。项目专注于 Agent 记忆管理，包含显式的长期记忆和压缩检索，适用于需要复杂记忆机制的 AI Agent 开发者。
- [**xMemory**](https://github.com/HU-xiaobai/xMemory) - xMemory是一个超越传统RAG的Agent记忆检索框架，通过解耦和聚合机制实现更精准的长短期记忆管理。它专为LLM Agent设计，支持动态记忆检索与结构化存储，特别适用于需要复杂记忆操作的智能体场景。该项目基于论文实现，适合AI Agent开发者、认知架构研究者以及需要构建具备持久记忆能力的自主Agent的工程团队。
- [**altk-evolve**](https://github.com/AgentToolkit/altk-evolve) - 提供自我进化智能体框架，通过迭代实现自我改进。内置代理记忆（agent-memory）和情节记忆（episodic-memory）机制，支持记忆回溯与反思；集成 MCP（Model Context Protocol）实现上下文管理与推理轨迹持久化。适用于构建具有持续学习能力的 AI Agent 的研究者与开发者。
- [**BrainX-The-First-Brain-for-OpenClaw**](https://github.com/Mdx2025/BrainX-The-First-Brain-for-OpenClaw) - BrainX是专为OpenClaw设计的首款持久化AI Agent记忆系统，利用PostgreSQL与pgvector实现向量存储，支持OpenAI嵌入进行语义搜索和跨Agent学习。它提供Reflection机制（通过连续记忆积累）和OpenClaw运行时插件，适用于需要长期记忆与协作的智能体开发，目标用户为构建多Agent系统的开发者。
- [**rasputin-memory**](https://github.com/jcartu/rasputin-memory) - rasputin-memory 是一个专为 AI 代理设计的持久化记忆后端，通过 LLM 事实提取、基础模型重排序和混合搜索（BM25 + 向量 + 知识图谱）实现高效记忆检索，在 LoCoMo 基准上达到 77.7% 准确率。原生支持 MCP 协议和 REST API，可自托管，适合需要长期记忆和反思机制的 OpenClaw、Claude Code 等代理系统。
- [**mnemos**](https://github.com/anthony-maio/mnemos) - mnemos 是一个受神经科学启发的 LLM 记忆架构库，实现了 surprise 门控、记忆再巩固、情感路由、睡眠巩固及激活扩散等仿生机制，并内置 MCP（Model Context Protocol）支持，可连接物理环境底层状态作为记忆中枢。项目聚焦于赋予 Agent 类人般的反思和自我进化能力，适合希望构建具备动态、分层记忆系统的 AI Agent 开发者。
- [**brainbox**](https://github.com/thebasedcapital/brainbox) - BrainBox 是一个零成本的赫布记忆系统，专为 Claude、OpenClaw 等 AI Agent 设计。它通过共访问模式学习文件重要性，实现程序性记忆，并集成 MCP 协议连接物理环境状态，赋能 Agent 的长期记忆与预测能力。适用于需要自适应记忆的 AI 开发者和具身智能场景。
- [**agentic-memory**](https://github.com/agentralabs/agentic-memory) - agentic-memory 是一个基于 Rust 构建的持久化认知图记忆系统，专为 AI 代理设计，支持存储事实、决策、推理链和纠错。提供 16 种查询类型并实现亚毫秒级响应，同时配备 Python SDK 和 MCP 服务器，可直接与物理环境底层状态对接。适合需要高效长期记忆与认知架构的智能体开发者。
- [**scallopbot**](https://github.com/tashfeenahmed/scallopbot) - ScallopBot 是一个生物启发的认知架构，专为个人AI代理设计，内置完整的记忆生命周期管理，包括记忆编码、存储、梦境整合（Dream Consolidation）和自反思（Self-Reflection）机制，采用扩散激活（Spreading Activation）实现主动智能。项目支持7种LLM提供商和9个渠道，运行成本极低（每日$0.06-0.10），并与OpenClaw机器人平台兼容，适合构建具备记忆自我进化能力的具身智能代理。
- [**rust-self-learning-memory**](https://github.com/d-o-hub/rust-self-learning-memory) - 这是一个基于Rust的模块化自学习情节记忆系统，专为AI代理设计。它结合了Turso(SQL)和redb(KV)的混合存储，支持异步执行追踪、奖励评分、反思机制以及基于模式的技能进化。项目直接面向Agent_Memory，实现了反射与自我改进记忆机制，适合需要可扩展且维护性高的代理工作流的开发者。
- [**mcp-context-server**](https://github.com/alex-feel/mcp-context-server) - alex-feel/mcp-context-server 是一个基于 FastMCP 的服务器，为 LLM 代理提供持久化的多模态上下文存储。它通过 Model Context Protocol (MCP) 实现记忆中枢连接，支持工作内存、短期记忆和 scratchpad 等功能，可直接集成至 AI 代理系统。适用于需要构建复杂记忆机制（如反思、自我改进）的 Agent 开发者。
- [**Awesome-Agent-Memory**](https://github.com/not-a-skid/Awesome-Agent-Memory) - 该项目是一个专注于Agent Memory的Awesome List，整理了针对大型和多模态语言模型的记忆机制，包括系统、基准和研究论文。它直接服务于AI Agent记忆管理领域，覆盖多种记忆范式，适合研究人员和开发者快速检索相关资源。
- [**state-trace**](https://github.com/razroo/state-trace) - 该项目提供了一个图形原生的工作记忆引擎，专为编码代理设计，支持类型化记忆节点、基于因果关系的检索、有界容量以及针对小模型的紧凑摘要生成。其核心机制直接服务于Agent的短期记忆管理，可与具身智能代理的长短期记忆架构集成，适用于需要高效记忆管理的自动化编码或调试代理。
- [**myelin-kernel**](https://github.com/Tetrahedroned/myelin-kernel) - myelin-kernel 是一个轻量级、线程安全的内存内核，专为自主智能体设计。它通过强化学习机制增强知识关联，利用温和衰减自动修剪不常用记忆，支持透明导出为Markdown。基于纯SQLite实现持久化，为智能体提供自我改进的推理基础。适用于需要长期记忆和知识进化的LLM智能体开发者。
- [**fidelis**](https://github.com/hermes-labs-ai/fidelis) - Fidelis 是一个专为 AI Agent 设计的本地优先、高保真记忆库，旨在避免检索退化与额外开销。它采用 ChromaDB 向量存储与整数指针技术，默认检索路径不含 LLM，实现零成本查询，并在 LongMemEval-S 上取得 83.2% R@1。项目深度融合代理记忆生态，支持 MCP 集成与 Ollama 等本地推理，直接解决 Agent 长期记忆的可靠性与成本问题，面向需要精确、快响应记忆的 Claude Code 及通用 Agent 开发者。
- [**agent-memory-dotnet**](https://github.com/joslat/agent-memory-dotnet) - 该项目是一个基于.NET的独立Agent内存提供程序，后端使用Neo4j图数据库实现持久化、图原生的记忆存储。它专为Microsoft Agent Framework设计，支持GraphRAG互操作，使AI Agent能够利用图结构进行长期记忆的检索与推理。适合需要图内存支持的.NET Agent开发者。
- [**mnemon**](https://github.com/cipher813/mnemon) - 该项目是一个自托管的AI Agent长期记忆系统，通过MCP（Model Context Protocol）实现统一记忆中枢。支持在Claude Code、Cursor、Claude Desktop等平台间共享记忆，采用嵌入向量和语义搜索技术存储和检索历史交互。适合需要跨工具持久化记忆的AI Agent开发者。
- [**Helixir**](https://github.com/nikita-rulenko/Helixir) - Helixir 是首个因果智能体AI记忆系统，专为Agent Memory设计。它实现了MCP（Model Context Protocol）用于连接物理环境底层状态，支持因果推理和记忆管理。项目基于Rust开发，适用于需要高效、结构化记忆的AI Agent开发。目标用户为构建具身智能体或复杂推理系统的开发者。
- [**agent_memory_course**](https://github.com/RichmondAlake/agent_memory_course) - 该项目是一个专注于智能体记忆（Agent Memory）的教程类Jupyter Notebook仓库，涵盖反思、自我改进等高级记忆机制的设计与实现。通过代码示例和讲解，帮助开发者理解如何在AI Agent中构建长期记忆、情景记忆等核心模块，适合希望深入学习Agent记忆系统的研究人员和工程师。
- [**zer0dex**](https://github.com/hermes-labs-ai/zer0dex) - zer0dex 是一个本地双层次记忆系统，专为AI代理设计，通过压缩索引与向量检索实现高效的长短期记忆管理。项目直接面向Agent_Memory，采用RAG与向量搜索技术，为代理提供持久化上下文感知能力，目标用户是构建具有持久记忆能力的AI代理开发者。
- [**clickmem**](https://github.com/auxten/clickmem) - clickmem 是基于嵌入式 ClickHouse（chDB）构建的专用 Agent 记忆存储工具，为 AI Agent 提供高性能、持久化的状态存储与检索能力。它直接服务于 Agent Memory 场景，利用列式数据库优化记忆数据的读写效率，支持结构化与非结构化混合记忆，并通过 SQL 接口实现灵活查询。适用于需要轻量级、低延迟记忆后端的 Agent 开发项目。
- [**openclaw-neo4j-agent-memory-plugin**](https://github.com/johnymontana/openclaw-neo4j-agent-memory-plugin) - 该项目为OpenClaw代理框架提供图原生记忆插件，利用Neo4j知识图谱实现短期、长期和推理记忆，使Agent具备持久化上下文和动态推理能力。通过构建上下文图谱，支持记忆的反射（Reflection）与自我改进机制，强化Agent对环境的理解。适用于需要结构化记忆和高效检索的AI Agent开发，尤其适合集成知识图谱的认知架构。
- [**agent-kernel**](https://github.com/benjaminsehl/agent-kernel) - Agent-Kernel 是一个轻量级的 Markdown 工作空间，专为 AI Agent 设计，用于持久化上下文、记录记忆和复用输出。它通过结构化笔记模板实现长效记忆管理，支持动态上下文注入和可追溯的推理过程，适合需要透明、可编辑记忆存储的 AI Agent 开发者。
- [**specmem**](https://github.com/SuperagenticAI/specmem) - SpecMem 是一个为编码 Agent 提供统一认知记忆的开源库，专注于 Agent Memory 的持久化与反思机制。它采用 spec-driven development 范式和 pragmatic memory 策略，将智能体的经验与状态进行结构化存储，以实现自我进化。项目以 Python 实现，适合需要为编码助手、编程 Agent 构建长期记忆与上下文感知能力的开发者。
## 通用AI智能体记忆框架
*用于对话型或任务导向型LLM智能体的库和系统。*

- [**Mem0**](https://github.com/mem0ai/mem0) - 开源、自我改进的**记忆层**，适用于LLM应用程序。
- [**SuperLocalMemory V3.3**](https://arxiv.org/abs/2604.04531) - 通过艾宾浩斯遗忘曲线和多通道检索实现的仿生遗忘机制。
- [**memory**](https://github.com/higgs-works/memory) - 为本地AI Agent设计的类人记忆系统，核心采用传播激活(Spreading Activation)和联想回忆机制实现记忆自动浮现，而非传统搜索。集成MCP协议连接外部状态，使用SQLite本地存储支持情节记忆(Episodic Memory)持久化。适用于需要长期、语义化Agent Memory的隐私优先场景。


- [**prism-mcp**](https://github.com/dcostenco/prism-mcp) - Prism-MCP 是一个符合HIPAA标准的认知架构MCP服务器，专为AI Agent设计，提供持久记忆、Hebbian学习、ACT-R扩散激活等机制，并支持多Agent群脑与可视化仪表盘。它通过MCP协议实现与外部环境的底层状态交互，无需API密钥即可在本地运行，是Agent Memory生态中的核心工具。适用于需要安全、本地化的长期记忆与认知架构的开发者。
- [**Zikkaron**](https://github.com/amanhij/Zikkaron) - Zikkaron 是一个受生物启发的持久记忆引擎，专为 Claude Code 设计，提供 26 个认知子系统的本地推理能力。它通过 Hopfield 网络、预测编码、因果发现和继代表征等机制实现类脑记忆管理，并集成了 MCP（Model Context Protocol）服务端，可直接连接底层环境状态进行记忆中枢构建。适用于需要长期、结构化、自更新记忆的 AI Agent 开发者。
- [**robotmem**](https://github.com/robotmem/robotmem) - RobotMem 是一个专为AI机器人设计的持久化记忆系统，集成了MCP服务器实现模型上下文协议连接，支持混合搜索和空间检索，使用SQLite与SQLite-vec实现离线优先的长期记忆存储。它具备情景记忆和经验回放机制，适用于ROS2和Claude Code等框架，目标用户是构建具身智能Agent的开发者。
- [**flowscript**](https://github.com/phillipclapham/flowscript) - FlowScript 是一个为 AI Agent 设计的可查询推理记忆系统，通过六种语义查询（如 why、tensions、blocked）对推理图进行检索，记住“什么”（向量存储）和“为什么”（结构化推理）。它提供 TypeScript SDK 并原生支持 MCP 服务器，可作为连接记忆中枢与 Agent 的标准化协议。该工具适合需要认知架构、长期记忆推理和多 Agent 协作的开发者。
- [**capability-graph-neuroscience**](https://github.com/For-Sunny/capability-graph-neuroscience) - 该项目提出六种基于生物学的遗忘机制，专为LLM智能体记忆系统设计。通过18项实验和4个被证伪的假设，利用STDP消融等方法（Cohen's d=3.163）验证记忆管理效果，并集成MCP协议连接底层状态。目标用户是研究智能体长期记忆、遗忘机制及神经符号系统的开发者。
- [**openclaw-neo4j-memory**](https://github.com/Garylauchina/openclaw-neo4j-memory) - 该项目是一个OpenClaw插件，利用Neo4j图数据库构建代理长期记忆系统，核心机制为“冥思（Meditation）”实现记忆反思与自我进化。它支持Agent Memory的持久化存储与检索，并通过Model Context Protocol（MCP）连接底层状态，专为多Agent协作与认知架构设计。适用于需要图结构记忆和反思能力的AI代理开发者。
- [**squish**](https://github.com/michielhdoteth/squish) - Squish 是一个为 AI 代理设计的记忆运行时，提供持久化上下文、基于信念的召回机制（belief-based recall）、MCP (Model Context Protocol) 集成、CLI 和 Web UI。它通过 SQLite/PostgreSQL 实现持久化存储，结合语义搜索增强记忆检索，支持动态信念系统和上下文工程。该工具专为需要长期记忆和认知架构的 Agent 开发者打造，可直接嵌入多模态代理工作流，并连接底层物理环境状态。
- [**cortexos**](https://github.com/gabrielrmsaganski-cpu/cortexos) - CortexOS 是一个面向 AI Agent 的可解释记忆操作系统，专注于时间推理（temporal reasoning）与冲突感知检索（conflict-aware retrieval）。它采用本地优先架构，集成了 Qdrant、SQLite 和 Ollama，并支持 MCP（Model Context Protocol）以连接底层物理状态。该项目适合需要透明、可控且具备时间维度的 Agent 记忆管理的研究者与开发者。
- [**agent-memory-openclaw**](https://github.com/smysle/agent-memory-openclaw) - 该项目是 AgentMemory 的原生适配器插件，专门为 OpenClaw 平台设计，提供与具身智能仿真环境或物理机器人系统的记忆管理集成。通过 TypeScript 实现，允许开发者将 OpenClaw 的状态与事件接入 AgentMemory 的长期记忆与反思机制，适用于需要持久化传感器数据或场景上下文的具身智能 Agent 开发。
- [**AgentMemorySystem**](https://github.com/FluffyAIcode/AgentMemorySystem) - 该项目名为 AgentMemorySystem，旨在融合记忆处理系统与感知记忆系统，为 AI Agent 提供统一的内存管理框架。它明确面向 Agent Memory 领域，专注于记忆机制的整合与实现，可能涉及长期与短期记忆、感知数据的编码与检索。尽管目前处于早期开发阶段（0 Star），但其主题与 Agent Memory 生态高度相关。适用于希望构建具备反思和自我进化能力的智能体的开发者。
- [**mnem**](https://github.com/Uranid/mnem) - Uranid/mnem 是一款面向 AI Agent 的版本化、可合并记忆系统，专为管理长期与短期记忆而设计。它采用混合 GraphRAG 检索，结合知识图谱与向量搜索，支持通过 MCP 协议或直接嵌入 Rust/Python 应用进行交互。系统实现了记忆的版本控制，允许在多次推理间追溯和合并记忆状态，适用于需要持续学习与反思的 Agent、具身智能体及本地优先的场景。
- [**LightAgent**](https://github.com/wanxingai/LightAgent) - LightAgent 是一个轻量级的多智能体协作框架，核心实现包括记忆管理、工具集成和树形思维推理。它直接集成了 MCP/SSE 协议，可通过 Model Context Protocol 连接外部物理环境或底层状态，实现具身智能场景下的长期记忆与状态同步。支持 OpenAI/DeepSeek/Qwen 等主流大语言模型，并提供自学习机制，适合需要 Agent Memory 和物理环境交互的开发者使用。
- [**MemoMind**](https://github.com/24kchengYe/MemoMind) - MemoMind 是为 Claude Code 设计的高性能本地记忆系统，100% 私有且零云依赖。它利用 GPU 加速实现低延迟记忆检索，并通过 MCP（Model Context Protocol） 协议与物理环境底层状态连接，支持 agent 的长期记忆和反思。项目明确面向 Agent Memory，适合需要本地化、可控记忆的 AI Agent 开发者。
- [**AEON-Delta**](https://github.com/B3NJ4M1NFR4NKL1N/AEON-Delta) - AEON-Delta是一个基于PyTorch的认知架构，通过感知→反思→计划→行动循环实现涌现推理，核心包含分层记忆、稀疏因果因子和可收敛元循环。其显式的反思机制与Long-term Memory for LLMs及Hierarchical Memory Systems高度契合，支持动态记忆分配与状态抽象。适合研究认知架构与Agent记忆机制的研究人员。
- [**memstate-mcp**](https://github.com/memstate-ai/memstate-mcp) - Memstate MCP 是一个基于 Model Context Protocol (MCP) 的记忆管理服务，提供标准化的长期记忆持久化与检索接口，专为 AI agents 设计。它支持 agent-memory、ai-memory 等特性，可与 Claude、Cline、Cursor 等工具集成，利用 TypeScript 实现。该项目直接服务于 Agent Memory 场景，适合需要结构化记忆管理的智能体开发者。
- [**mnemo-public**](https://github.com/ashmdev/mnemo-public) - Mnemo-public 是 Mnemo Agent Memory 引擎的社区资源仓库，提供 MCP 服务器、插件和技能包以扩展长期记忆能力。项目直接服务于 Agent Memory 生态，通过 MCP 协议连接外部工具与环境状态。适合需要结构化社区记忆组件集成的 AI Agent 开发者。
- [**Mem4Nav_VLN**](https://github.com/sumiradio/Mem4Nav_VLN) - Mem4Nav_VLN 是一个专为视觉语言导航（VLN）设计的记忆模块仓库，旨在帮助智能体在仿真环境中记录并利用路径与状态历史，提升导航决策能力。它通过结构化记忆机制强化对环境的长期理解，直接支持具身智能中的记忆管理与导航任务。适用于研究 VLN 与 Agent Memory 集成的开发者。
- [**cortex**](https://github.com/jessekemp1/cortex) - Cortex 是一个为 LLM 驱动的智能体提供持久化智能层的工具，实现跨会话的记忆复合。它通过 MCP（Model Context Protocol）服务器连接智能体与底层状态，支持持久上下文存储，旨在解决智能体的会话失忆问题。适用于需要长期记忆、多会话知识积累的 AI Agent 开发者。
- [**syke**](https://github.com/saxenauts/syke) - Syke 是一个专注于智能体动态身份与代理记忆的开源项目。它通过 MCP (Model Context Protocol) 为 AI 提供持久化上下文管理，支持跨对话保留用户身份与信息。该项目可集成到 Agent 开发栈中，适用于需要长期记忆和个性化交互的 AI 应用。对 Agent_Memory 有直接实现，包含 MCP 协议适配。
- [**bookend-skill**](https://github.com/rockywuest/bookend-skill) - 该项目为Clawdbot/Moltbot机器人平台提供结构化记忆系统，具备会话持久化与上下文管理能力，聚焦于Agent Memory中session-persistence与state-management的轻量级实现，目标用户为机器人开发者和记忆系统研究者。
- [**StreamMeCo: Long-Term Agent Memory Compression for Efficient Streaming Video Understanding**](http://arxiv.org/abs/2604.09000v1) - 提出StreamMeCo，一种针对流式视频理解的长期智能体记忆压缩框架。核心方法基于记忆图连通性，对孤立节点采用无边缘最小最大采样，对连接节点采用边缘感知权重剪枝，在保持准确率的前提下剔除冗余记忆节点；同时引入时间衰减记忆检索机制缓解压缩导致的性能下降。在三个基准（含具身机器人基准M3-Bench-robot）上实现70%压缩率下1.87倍检索加速和平均1.0%精度提升。该工作直接以Agent Memory为核心，解决了长期记忆存储和计算高昂成本问题。
- [**Artifacts as Memory Beyond the Agent Boundary**](http://arxiv.org/abs/2604.08756v1) - 本文在强化学习中提出环境可作为智能体外部记忆的形式化框架，定义“人造物”（artifacts）为能减少历史信息表征需求的观察。通过空间路径实验证明，智能体感官流隐式利用环境降低记忆负载，满足外部记忆的理论属性。该工作为具身智能体利用环境替代内部显式记忆提供了原则性方法，是Agent Memory研究的基础理论贡献。
- [**HiMemVLN: Enhancing Reliability of Open-Source Zero-Shot Vision-and-Language Navigation with Hierarchical Memory System**](http://arxiv.org/abs/2603.14807v1) - 本文提出HiMemVLN，通过引入分层记忆系统（Hierarchical Memory System）解决开放源码零样本视觉语言导航中的“导航遗忘”问题。该系统包括视觉感知召回和长期定位模块，显著提升多模态大模型的导航可靠性。在模拟和真实环境中，HiMemVLN性能达到开放源码最佳方法的两倍，直接体现Agent Memory在具身导航中的核心作用。
- [**Continuous Reorganization and Performance Preservation of Agent Memory Structure Under Distributed Change Environments**](https://openalex.org/W7134922009) - 提出Distribution-Aware Continuous Memory Reorganization (DAMCR)算法，针对分布式变化环境中Agent记忆结构重组时存在的触发滞后、性能波动及内存管理失衡问题，构建了“分布感知-动态重组-性能反馈”闭环架构。通过改进KL散度实现分布变化感知，基于多维度值评估进行自适应记忆单元管理，并引入缓冲机制与性能反馈保证重组平稳性。在CIFAR-100和自建导航数据集上验证，平均决策准确率92.3%，重组延迟低至12.7ms，性能波动降低73.1%，内存利用率提升23.9%，为具身智能体在动态环境中的长期记忆维护提供了高效稳定的重组方案。
- [**Grounding Agent Memory in Contextual Intent**](http://arxiv.org/abs/2601.10702v1) - 提出 STITCH（结构化意图跟踪在上下文中）记忆系统，通过为每个轨迹步骤构建包含潜在目标、动作类型和实体类型的上下文意图索引，解决长程目标导向交互中记忆检索的上下文不匹配问题。STITCH 基于当前步骤的意图过滤历史片段，显著降低检索噪声。在提出的 CAME-Bench 基准和 LongMemEval 上，STITCH 以 35.6% 的优势超越最强基线，验证了意图感知记忆对增强长程推理鲁棒性的有效性。
- [**RoboOS-NeXT: A Unified Memory-based Framework for Lifelong, Scalable, and Robust Multi-Robot Collaboration**](http://arxiv.org/abs/2510.26536v1) - 该论文提出RoboOS-NeXT框架，核心贡献是设计了Spatio-Temporal-Embodiment Memory（STEM）统一记忆表示，整合空间场景几何、时序事件历史和机器人本体特征。在脑-小脑架构中，全局规划模型通过检索和更新STEM实现动态任务分配与故障恢复，低层控制器执行动作。实验覆盖餐厅、超市等复杂协作场景，验证了终身适应和可扩展性。该框架为多机器人系统提供了具身记忆中枢，显著提升协作鲁棒性。
- [**Memory Augmented Multi-agent Reinforcement Learning for Cooperative Environment**](https://openalex.org/W4407914197) - 本文提出了一种记忆增强的多智能体强化学习方法，通过在智能体中引入外部记忆模块来存储历史经验与决策轨迹，从而提升合作环境下的协调与信用分配能力。该方法将记忆机制作为核心组件，支持智能体在长期交互中回溯有用信息，有效改善了多智能体系统的协同效率。与Agent_Memory的具体关联在于，该论文明确以记忆增强作为核心方法，直接应用于多智能体强化学习领域。
- [**KARMA: Augmenting Embodied AI Agents with Long-and-short Term Memory Systems**](https://openalex.org/W4403796455) - 本文提出KARMA记忆系统，将长期记忆（3D场景图）与短期记忆（动态对象状态）融合，增强具身AI智能体在长序列任务中的规划能力。该系统通过记忆增强提示优化大语言模型，实验在AI2-THOR仿真中成功率提升1.3-2.3倍，效率提升3.4-62.7倍，且具备即插即用能力，可部署于真实机器人平台。该工作以Agent Memory为核心架构，解决了长期与短期记忆协同问题，属于具身智能记忆领域的系统创新。
- [**RAP: Retrieval-Augmented Planning with Contextual Memory for Multimodal LLM Agents**](https://openalex.org/W4391631574) - 提出RAP（检索增强规划）框架，通过动态检索和融合上下文记忆（contextual memory）来增强多模态LLM agents的规划能力。该框架在文本和具身多模态环境（如机器人、游戏）中均达到SOTA，核心机制是利用过去经验优化当前决策，直接体现Agent Memory的检索与利用。
- [**SMEMO: Social Memory for Trajectory Forecasting**](https://openalex.org/W4391092980) - 该论文提出SMEMO模型，核心贡献是设计了一个端到端可训练的工作记忆模块，作为每个智能体动态信息的持久化外部存储。该记忆支持连续写入、更新和召回操作，能够显式建模多智能体间的社交交互与因果影响，在多个轨迹预测数据集上达到最优性能。其工作记忆机制直接服务于Agent Memory，为智能体轨迹预测提供了可解释的动态记忆架构。
## 具身AI专用记忆
*专为处理机器人连续、高频的感知运动流而设计的框架。*

- [**RoboMemory**](https://arxiv.org/abs/2508.02458) (2025) - 受大脑启发的框架，统一了**空间、时间、情景和语义**记忆，用于长周期规划。
- [**Addressing hallucinations in generative AI agents using observability and dual memory knowledge graphs**](https://openalex.org/W7128375030) - 该论文提出通过可观测性与双记忆知识图谱解决生成式AI代理的幻觉问题。核心贡献是构建一个结合短期和长期记忆的图结构记忆系统，利用可观测性数据实时修正代理输出，减少事实错误。该方法直接针对Agent Memory中的记忆存储与检索机制，适用于需要可靠记忆的自主智能体场景。
- **ReMEmbR** *(RSS, 2025)* - 在机器人导航中，对长周期时空记忆进行推理。
- **Experience-Hub**


- [**loci-db**](https://github.com/zd87pl/loci-db) - Loci-DB 是一个专为物理世界设计的 4D 时空向量数据库，通过 Hilbert 曲线分桶与时间分片实现高效存储和检索。它采用“预测-检索”策略与新颖性检测机制，支持对物体历史位置的记忆而非仅当前视野，适用于具身 AI 机器人的长期空间-时间记忆管理。该项目直接服务于需要持久化传感器数据并支持世界模型推理的 Agent 记忆系统。
- [**vibemap**](https://github.com/ramezyo/vibemap) - VibeMap是一个专门为AI智能体设计的空间记忆工具，支持基于地理位置的观察查询。它通过12个全局锚点和来源标注的观察记录实现代理的空间记忆，并内置MCP服务器用于连接底层物理环境状态。该项目旨在为具身智能体提供无需API密钥即可使用的空间记忆中枢，适合需要地理空间记忆的AI代理开发者。
- [**Temporal**](https://github.com/DomLynch/Temporal) - DomLynch/Temporal 是一个精简的时序知识图谱库，基于 Graphiti 核心逻辑，使用 SQLite 替代 Neo4j，代码仅 2800 行。它专为 AI Agent 的长期记忆与事件管理设计，支持通过时序图结构存储和检索代理交互历史，适合需要轻量级记忆持久化的 LLM 或智能体应用。面向构建具备时间感知能力的智能体开发者。
- [**dreamgraph**](https://github.com/mmethodz/dreamgraph) - DreamGraph 是一个基于图结构的认知层项目，通过 MCP（Model Context Protocol）构建并持久化知识图谱，实现代理的长期记忆和推理能力。其核心机制包括因果推断、时序推理和文档生成，可作为 AI Agent 的记忆中枢。适用于需要持续知识积累、验证和自主决策的智能代理开发者。
- [**Associative Memory Fields: Zero-Infrastructure Spreading Activation for LLM Multi-Agent Systems**](https://openalex.org/W7150189181) - 该论文提出关联记忆场（Associative Memory Fields），一种零基础设施的扩散激活方法，专门用于LLM多智能体系统的记忆检索与关联。核心机制是在每个记忆条目中添加3-5个自由关联词，通过类似神经网络的文本文件结构（神经元=条目，突触=关联词）实现隐式连接和激活传播，无需嵌入或GPU。实验表明，在12个探针查询上，该方法将准确率从50%提升至100%。此工作直接针对Agent Memory的持久化文本记忆检索难题，提供了轻量级、可扩展的解决方案，适用于多智能体协作场景中的记忆管理与关联推理。
- [**Rashomon Memory: Towards Argumentation-Driven Retrieval for Multi-Perspective Agent Memory**](http://arxiv.org/abs/2604.03588v2) - 该论文提出Rashomon Memory架构，为多目标AI代理设计了一种基于论证驱动的检索机制。核心贡献在于允许多个目标条件代理并行编码经验，各自维护独立的ontology和知识图谱，在查询时通过Dung的论证语义进行协商和批判，从而处理同一事件的不同解释冲突。该架构将攻击图作为解释，支持选择、组合和冲突暴露三种检索模式，使决策者能直接看到潜在的阐释冲突。这对开发具有多视角记忆和反思能力的具身智能代理系统具有重要价值。
- [**VideoAtlas: Navigating Long-Form Video in Logarithmic Compute**](http://arxiv.org/abs/2603.17948v1) - 主要贡献是提出VideoAtlas，一种任务无关的分层网格环境，用于无损、可递归导航的长视频表示，并统一作为agent的记忆，消除有损文本转换。它通过递归语言模型（RLM）和主从并行架构实现对数级计算增长，缓存命中率达30-60%。该方法直接关联Agent Memory，将环境与记忆统一为分层结构，适用于需要高效记忆管理的视觉推理agent。
- [**WAT: Online Video Understanding Needs Watching Before Thinking**](http://arxiv.org/abs/2603.13412v1) - 提出 WAT（Watching Before Thinking）两阶段框架，用于在线视频推理，核心是层级记忆系统：短期记忆（STM）缓冲近期帧，固定容量长期记忆（LTM）通过冗余感知驱逐策略维护历史摘要，并在思考阶段由上下文感知检索机制结合查询与STM从LTM获取相关帧。该框架直接以层级记忆系统作为核心方法，配合WAT-85K数据集支持实时感知、回溯与预测任务，在StreamingBench等基准上达到SOTA。与Agent_Memory的关联在于其明确设计了智能体在线推理所需的记忆分层、存储与检索机制，可视为面向视频智能体的记忆架构。
- [**CAST: Character-and-Scene Episodic Memory for Agents**](http://arxiv.org/abs/2602.06051v3) - 本文提出 CAST（Character-and-Scene 情景记忆架构），受戏剧理论启发，通过构建 3D 场景（时间/地点/主题）并组织为角色档案来表征智能体的情景记忆，同时结合图语义记忆形成双记忆设计。实验在开放域和时间敏感对话任务上平均提升 8.11% F1 和 10.21% J（LLM评判），解决了传统记忆系统难以表示和检索连贯事件的问题，为具身智能体长期记忆管理提供了新范式。
- [**Membox: Weaving Topic Continuity into Long-Range Memory for LLM Agents**](http://arxiv.org/abs/2601.03785v2) - 提出了一种名为Membox的层次化记忆架构，专门用于LLM Agent，以解决对话中话题连续性的丢失问题。核心机制包括Topic Loom模块，通过滑动窗口实时监控对话，将同主题连续轮次分组为“记忆盒”，并由Trace Weaver在盒之间构建事件时间线，实现宏观话题的跨间断恢复。在LoCoMo基准上，时间推理F1提升达68%，且仅需更少的上下文令牌。该工作为Agent Memory提供了认知启发的高效连续性建模方法。
- [**Cognitive Weave: Synthesizing Abstracted Knowledge with a Spatio-Temporal Resonance Graph**](http://arxiv.org/abs/2506.08098v1) - 提出Cognitive Weave记忆框架，核心为多层时空共振图（STRG），将交互数据组织为语义洞察粒子（IPs），并通过认知精炼过程合成高级洞察聚合（IAs）。该方法显著增强了智能体的长时规划、动态问答及多轮对话能力，任务完成率提升34%，查询延迟降低42%，属于以Agent Memory为核心方法的创新架构。
- [**R2D2: Remembering, Replaying and Dynamic Decision Making with a Reflective Agentic Memory**](http://arxiv.org/abs/2501.12485v3) - 提出R2D2框架，集成Remember（回放缓冲动态重构网页环境地图）与Reflect（从错误中反思学习）两种代理记忆范式，作为核心方法在WebArena基准上减少50%导航错误并提升三倍任务完成率。该工作将Agent_Memory具体化为网页代理的 episodic 记忆与反思机制，优化动态决策过程。
- [**TReMu: Towards Neuro-Symbolic Temporal Reasoning for LLM-Agents with Memory in Multi-Session Dialogues**](https://openalex.org/W4412887804) - TReMu 提出了一个面向多会话对话LLM-Agent的时间推理框架，核心贡献在于设计了时间感知记忆机制，通过时间线摘要将每个对话会话中的事件按推断日期总结为可检索记忆，并结合神经符号方法让LLM生成Python代码执行时间计算。该工作直接以Agent Memory为核心方法，实现了结构化的事件记忆存储与时间推理，显著提升了GPT-4o等模型在时间推理任务上的表现（从29.83提升至77.67）。
- [**Learning Hierarchical Interactive Multi-Object Search for Mobile Manipulation**](http://arxiv.org/abs/2307.06125v3) - 本文提出HIMOS分层强化学习方法，核心围绕语义地图记忆（Semantic Map Memory）设计高层动作空间，用于移动操作机器人在未知环境中进行交互式多目标搜索。通过维护和利用环境地图记忆，机器人能够组合探索、导航和操作技能，实现零样本迁移。该方法直接以具身智能体记忆作为决策基础，属于Agent Memory核心方法。
- [**Emergence of Maps in the Memories of Blind Navigation Agents**](https://openalex.org/W4387476016) - 该论文通过强化学习训练仅依赖自运动感知的“盲”导航智能体，揭示了其内部记忆能够涌现出空间地图表征，从而在陌生环境中实现高效导航（~95%成功率）。研究表明，这些智能体利用长程记忆（记住约1000步经历）表现出智能行为，如沿墙行走、检测碰撞和走捷径。核心贡献在于证明了记忆系统作为具身智能体导航的核心机制，即使在没有视觉输入的情况下也能构建隐式地图，为Agent Memory在物理环境中的空间认知提供了关键实验证据。
- [**Modeling Dynamic Environments with Scene Graph Memory**](http://arxiv.org/abs/2305.17537v4) - 本文提出场景图记忆（SGM）作为具身智能体在动态家庭环境中的核心记忆表示，通过图结构编码房间、物体及其关系，并利用节点边缘预测器（NEP）从部分观测中高效预测物体位置。该工作直接针对具身智能仿真环境（Dynamic House Simulator）的状态记忆管理，实现了基于场景图的空间-语义记忆检索，为动态环境下的目标搜索提供了可复现的记忆架构。
- [**Interactive Machine Comprehension with Dynamic Knowledge Graphs**](http://arxiv.org/abs/2109.00077v1) - 论文提出将动态知识图作为交互式机器阅读理解中智能体的记忆机制，通过四类文本图表示动态构建和更新，结合图编码与强化学习，在iSQuAD数据集上取得显著性能提升。该工作直接以Agent Memory为核心方法，为基于图结构的智能体记忆管理提供了新范式。
## 时空与语义地图
*弥合物理坐标与LLM语义理解之间的差距。*

- **3DLLM-Mem** *(arXiv, 2025)* - 具有增量式3D场景理解能力的长周期时空记忆。
- [**Embody4D**](https://github.com/peiyantu/Embody4D) - Embody4D 是一个面向具身AI的通用4D世界模型，通过时空维度融合感知与动作，构建长期记忆和状态预测机制。其核心关联 Agent Memory 在于实现了时空记忆系统（Spatial-Temporal Memory），可持久化与检索物理环境的历史状态，支持智能体在仿真或真实环境中的决策与规划。技术实现上可能采用隐式神经表示或占用网络建模4D场景。目标用户为具身AI与机器人研究者。


- [**crux**](https://github.com/ardey26/crux) - Crux 是一个面向 AI Agent 的知识版本管理工具，类似 Git 但用于记录代理对世界认知（Belief Graph）的变更历史。它支持信念的版本化、依赖追踪与无效化撤销，允许 agent 回滚认知状态并进行自我反思。项目直接聚焦于 Agent Memory，通过持久化世界模型实现认知演化，适用于需要长期记忆与自我改进机制的智能体系统。
- [**mnemebrain-sdk**](https://github.com/mnemebrain/mnemebrain-sdk) - 该项目提供 Python SDK，用于构建 AI 智能体的信念记忆系统。它支持 MnemeBrain 的 Lite 和 Full API，实现基于知识图谱和信念修正的长期记忆管理，帮助智能体进行推理和检索增强生成（RAG）。适合需要复杂记忆机制并追求记忆可演化的 AI Agent 开发者。
- [**DualWorld**](https://github.com/world-mind/DualWorld) - DualWorld 提出了一种面向具身 AI 的双系统世界模型，旨在通过并行处理感知与规划来增强智能体对物理环境的理解和记忆能力。该模型融合了分层记忆架构，支持动态场景图构建和时序状态抽象，能够为机器人或虚拟具身体提供长期环境状态保持与高效检索机制。项目特别适合从事具身智能、认知架构及世界模型研究的开发者，用于探索 Agent Memory 与感知-行动循环的深度耦合。
- [**AwesomeWorldModels**](https://github.com/Li-Zn-H/AwesomeWorldModels) - 该项目是一个关于具身AI世界模型的综合调查列表，系统收集了世界模型相关的论文、代码和资源。世界模型作为具身智能体对环境状态进行建模和预测的核心机制，与Agent Memory中的状态记忆、预测记忆和世界知识记忆高度相关。该列表涵盖了多种记忆相关技术，如隐状态记忆、递归神经网络、Transformer记忆等，为研究具身智能体长期记忆和状态抽象提供了重要参考。适合AI Agent和具身记忆领域的研究者与开发者。
- [**TERRAIN MEMORY: LEVERAGING THE FULL BREADTH OF LLM TRAINING FOR EXPERIENTIAL AI AGENT MEMORY**](https://openalex.org/W7136613094) - 该论文提出 Terrain Memory，一种面向 AI 代理的体验式记忆架构，将任务经验编码为包含地形（问题结构）、天气（当前条件）、感受（加权定性信号）等多维度的动态记忆，并赋予其生命周期（强化、衰减、积累）。核心贡献在于充分利用 LLM 训练数据中的非技术性知识（如文学、导航、情感）来丰富代理记忆，解决了传统记忆仅记录事实而忽略体验的局限。该架构适用于需要长期情境感知的具身代理系统。
- [**EgoLCD: Egocentric Video Generation with Long Context Diffusion**](http://arxiv.org/abs/2512.04515v1) - 提出EgoLCD端到端框架，通过长期稀疏KV缓存与注意力短期记忆结合LoRA实现高效记忆管理，并设计记忆调节损失抑制内容漂移，在EgoVid-5M基准上达到最优性能，为具身AI构建可扩展世界模型奠定基础。
## 世界模型与状态预测
*利用记忆来预测未来的物理状态，并减少观测延迟。*

- **VLA-Memory-Repo**


- [**deer**](https://github.com/chrismichaelps/deer) - DEER (Dynamic Efficient External Recall) 是一个为大型语言模型提供无限上下文记忆的C++工具库，采用KVTC/TurboQuant压缩技术实现高效的内存管理。它通过外部存储和压缩机制扩展LLM的记忆容量，直接服务于Agent Memory中的长期记忆需求，适用于需要持久化对话历史或知识流的AI Agent开发者。
- [**Criticity-Weighted-Memory-Regulation**](https://github.com/FrThierry09/Criticity-Weighted-Memory-Regulation) - 该项目提出一种基于批评性权重的记忆调控方法，用于稳定长期运行的LLM代理，通过动态评估记忆价值来保留高价值上下文并过滤噪声。它实现了一种认知架构中的记忆反思与自我改进机制，直接面向Agent Memory领域，适用于需要长效记忆管理的AI代理系统。
- [**ace**](https://github.com/hmatrades/ace) - 该项目是针对LLM智能体的记忆压缩工具，利用主观显著性指针（Subjective Salience Pointers）技术，将类似Claude-mem的约17K tokens压缩至仅300 tokens左右，极大提升Agent长期记忆存储效率。与Agent_Memory生态直接集成，通过压缩机制实现动态、轻量级的记忆管理。适合需要优化大模型智能体记忆容量和响应速度的开发者。
- [**selective-revocation-replay**](https://github.com/aliuyar1234/selective-revocation-replay) - 该项目是研究论文的代码实现，提出在记忆增强型LLM代理中应对持久化间接提示注入攻击的选择性撤销与重放机制。核心记忆机制包括对代理长期记忆中的污染数据进行溯源、选择性删除和恢复，确保代理记忆的安全性与一致性。技术实现基于记忆溯源追踪和可控重放策略，适合关注AI代理安全、记忆管理与鲁棒性的研究人员。
- [**graph-memory**](https://github.com/eastythenob8-svg/graph-memory) - 该项目提供将长对话历史压缩为结构化知识图谱的能力，以增强跨会话的上下文保持。它集成了MCP（Model Context Protocol）作为连接外部环境与记忆中枢的接口，使用向量数据库和知识图谱实现高效的记忆存储与检索。适用于需要长期结构化记忆管理的AI Agent开发者。
- [**dream-weaver-protocol**](https://github.com/wipcomputer/dream-weaver-protocol) - Dream Weave Protocol 是一个面向有限上下文窗口 AI 智能体的记忆巩固协议，通过“Dream、Weave、Wake”三阶段实现类似睡眠周期的记忆整合与反思。它直接聚焦 Agent Memory 机制，无需外部封装即可帮助智能体抽象和压缩历史经验。适用于需要长期记忆管理和自我改进的 AI Agent 开发者。
- [**mneme**](https://github.com/bilay314/mneme) - mneme 为 AI 编码代理提供三层持久化记忆系统，支持长期知识、任务进度和执行上下文的保留。该项目直接面向 Agent Memory 生态，通过分层数据结构实现高效存储与检索，适合需要跨会话保持记忆的 LLM 驱动代理开发者。
- [**membrane**](https://github.com/BennettSchwartz/membrane) - 该项目是一个面向智能体系统的选择性学习与记忆底层库，提供类型化、可修改、可衰减的记忆机制，并集成了能力学习与信任感知检索。它实现了自我改进和自我反思的记忆管理，支持知识修改和遗忘，适合构建具有长期记忆和自主进化能力的AI Agent。
- [**Myco**](https://github.com/Battam1111/Myco) - Myco 是一个自进化的认知有机体框架，专为 AI Agent 设计，核心实现“永恒吞噬、永恒进化”的记忆机制。它通过 MCP (Model Context Protocol) 集成长期记忆与认知基质 (cognitive substrate)，支持反思、自我改进与持续学习。项目使用 Python 开发，结合 biomimetic 理念，为构建自主 Agent 提供基础设施级记忆管理。适合需要持久化、动态演化记忆的 AI Agent 开发者。
- [**Genesis**](https://github.com/MetaforeAI/Genesis) - Genesis 是一个多八度层次化记忆系统，采用基于快速傅里叶变换（FFT）的编码和动态聚类技术，专门为 AI Agent 提供高效、可伸缩的长期记忆管理。它直接面向 Agent Memory 生态，通过频率域表示实现多尺度信息压缩与检索，适合需要复杂记忆结构的自主智能体开发。目标用户是构建具有反思和自我进化能力的 AI Agent 的研究者与工程师。
- [**Mnemoscope**](https://github.com/toonight/Mnemoscope) - Mnemoscope 是一个专为 LLM 智能体设计的可观察性与预测性记忆工具，基于 Markdown 知识库运行。它通过上下文衰减评分、Ed25519 签名哈希链日志及分层存储，监测记忆健康度并防止上下文过期。项目完全本地化，提供 MCP 服务器与 Obsidian 插件，使智能体通过模型上下文协议直接管理记忆。目标用户为需要构建长期、抗遗忘记忆机制的 AI 智能体开发者。
- [**echo-fade-memory**](https://github.com/hiparker/echo-fade-memory) - 项目是一个专注于Agent记忆生命周期的中间件，实现了记忆的“记住-衰减-召回-接地”四阶段可解释流程。它使用向量搜索支持记忆检索，并提供了遗忘机制以模拟人类记忆衰退，适用于需要长期记忆管理的AI Agent系统。基于Go语言实现，适合构建具备动态记忆管理的自主Agent。
- [**Theorex**](https://github.com/LORD-ZYTHOZ/Theorex) - Theorex 是面向多智能体系统的 AI 原生记忆库，通过概念图谱（Concept Web）实现动态记忆管理，支持衰减（Decay）、提升（Promotion）和引导注入（Boot Injection）机制。它专为多智能体协作场景设计，提供长效记忆持久化与智能检索能力，适合需要复杂记忆分层与自适应进化的 Agent 架构开发者。
- [**mnemebrain-lite**](https://github.com/mnemebrain/mnemebrain-lite) - 该项目为AI智能体提供核心信念层，采用结构化信念替代传统文本记忆，支持矛盾检测、信念修正与可解释推理。其显式针对Agent Memory设计，通过知识图谱实现动态记忆管理，可作为RAG的替代方案。适合需要高级记忆推理的LLM代理开发者。
- [**memory-bank-paper-implementation**](https://github.com/karthiknadar1204/memory-bank-paper-implementation) - 该项目实现了MemoryBank论文中的长期记忆机制，为LLM代理提供基于艾宾浩斯遗忘曲线的分层摘要、动态用户画像和语义检索功能，属于专门的Agent Memory工具库，可供AI Agent开发者集成长期记忆能力。
- [**trajectory-drift-demo**](https://github.com/putmanmodel/trajectory-drift-demo) - 该项目提供分层智能体记忆（stratified agent memory）中基于轨迹的漂移检测的确定性演示。它通过简单的可检查指标，展示记忆一致性随时间衰减的现象，适合研究长期记忆退化和可解释性的开发者。核心技术为确定性仿真与时间序列分析，直接面向Agent Memory机制。
- [**llm_introspective_compression_and_metacognition**](https://github.com/Dicklesworthstone/llm_introspective_compression_and_metacognition) - 该项目提出了一种新型的Transformer模型内省方法，核心功能是保存、压缩和操纵模型的内部思维状态，支持推理回溯、潜在思维优化和元认知控制。它与Agent Memory的反思（Reflection）和自我进化（Self-Improvement）机制直接相关，通过压缩和重放内部状态实现长期记忆管理，适用于需要高级认知架构的LLM Agent开发。目标用户为研究元认知、记忆压缩和Agent自我改进的研究者和开发者。
- [**tdr-vector-decay**](https://github.com/Praxis-Collective/tdr-vector-decay) - 该项目提供基于时间衰减的向量数据库检索原生评分方法，无需后检索调整。核心机制通过超维计算（Hyperdimensional Computing）实现时序衰减，专为Agent Memory场景设计，支持Milvus等向量数据库，适用于需要长期记忆时效性管理的AI Agent系统。目标用户为构建具备时间感知记忆的agent开发者。
- [**LRO**](https://github.com/zircote/LRO) - 该项目提出Large Result Offloading (LRO)策略，通过token感知方式在LLM上下文窗口中管理大工具输出，优化长期记忆存取。实现基于Model Context Protocol (MCP)的底层状态连接，支持动态上下文卸载与检索，是面向Agent Memory的轻量级内存管理方案。适合需要高效管理Agent工作记忆与工具交互状态的开发者。
- [**openclaw-memory-protocol**](https://github.com/jamebobob/openclaw-memory-protocol) - 该项目实现了一种两层持久化协议，通过重要性标记（significance tagging）和自动化夜间整合（nightly consolidation）管理AI Agent的记忆，基于神经科学遗忘研究优化上下文窗口和存储。它直接面向Agent Memory场景，提供记忆压缩、遗忘和合并机制，适合需要长期记忆管理的AI Agent开发者和研究者。
- [**agent-os**](https://github.com/ddomixi4-spec/agent-os) - Agent-OS 是一个自托管的 AI 代理框架，核心特色是采用高效的分层记忆系统（Hierarchical Memory System），能从交互中学习并降低 82% 的 token 消耗。项目内置 MCP（Model Context Protocol）支持，可用于连接物理环境底层状态，实现具身智能记忆中枢。适合需要长期记忆管理与 token 优化的 AI Agent 开发者。
- [**skill-attic**](https://github.com/antontheai/skill-attic) - 该项目为AI Agent提供技能记忆的管理工具，实现技能遥测、评分、分层与归档，类似于长期记忆的“垃圾回收”，支持记忆修剪与动态分配。它通过MCP协议集成，直接面向Agent Memory生态，能帮助Agent维护高效技能库。
- [**memory-runtime**](https://github.com/Tom-Wang898/memory-runtime) - 该项目提供一个自动化的热/冷内存运行时，专为Codex、Claude和Gemini等LLM设计，通过SQLite持久化存储，在不重写提示词的情况下节省token。它基于记忆宫殿模式实现分层存储，支持CLI和Docker部署，是面向AI Agent的显式记忆管理工具，适合需要长上下文高效管理的Agent开发者。
- [**dream-memory**](https://github.com/1731238947/dream-memory) - dream-memory 是一个受大脑做梦机制启发的离线记忆巩固工具，专为 AI 代理设计。它通过模拟睡眠期间的记忆回放与整合，提升代理在长期任务中的反思与自我进化能力。项目支持与 Anthropic Claude、OpenAI 等大模型集成，核心实现采用 Python，目标用户为需要增强代理记忆持久性和泛化能力的开发者。
- [**FSFM: A Biologically-Inspired Framework for Selective Forgetting of Agent Memory**](http://arxiv.org/abs/2604.20300v1) - 该论文提出FSFM框架，受人类认知过程启发（海马索引/巩固理论、艾宾浩斯遗忘曲线），专门针对LLM agent的记忆选择性遗忘机制进行系统研究。核心贡献包括：建立被动衰退、主动删除、安全触发和自适应强化四类遗忘机制分类法，通过智能记忆剪枝提升访问效率（+8.49%）、动态更新过时偏好提高内容信噪比（+29.2%）、主动遗忘恶意输入和敏感数据实现100%安全防护。该框架在资源受限环境中平衡记忆保留与遗忘，为agent长期记忆管理提供认知科学启发的实用解决方案。
- [**Experience Compression Spectrum: Unifying Memory, Skills, and Rules in LLM Agents**](http://arxiv.org/abs/2604.15877v1) - 该论文提出了“经验压缩谱”统一框架，将Agent记忆（如情景记忆）、技能和规则视为沿压缩轴的不同点（5-20倍压缩），通过对22篇论文的引文分析揭示了记忆与技能社区间极低的交叉引用率，并发现现有系统均固定在单一压缩级别，缺乏自适应跨级压缩（“缺失对角线”）。该框架直接关联Agent Memory，为设计可扩展的全谱系Agent学习系统提供了理论基础和设计原则。
- [**When to Forget: A Memory Governance Primitive**](http://arxiv.org/abs/2604.12007v1) - 本文提出了一种名为Memory Worth（MW）的记忆治理原语，通过双计数器追踪记忆与任务成功/失败的共现频率，为智能体记忆系统的遗忘、检索抑制和废弃决策提供了轻量级且理论严谨的度量基础。实验表明，在10,000个episode后，MW与真实效用之间的Spearman秩相关系数达到0.89，显著优于静态评估方法。该工作直接以Agent Memory为核心，解决了记忆质量动态评估的关键问题，适用于需要长期记忆管理的自主智能体系统。
- [**Lightweight LLM Agent Memory with Small Language Models**](http://arxiv.org/abs/2604.07798v3) - 本文提出LightMem，一种基于小语言模型（SLM）的轻量级Agent记忆系统。核心贡献在于模块化记忆检索、写入与长期整合，将在线处理与离线整合分离，在有限计算预算下实现高效记忆调用。系统将记忆组织为短期（STM）、中期（MTM）和长期（LTM），采用两阶段检索（向量粗筛+语义重排）提升准确性，并支持多用户独立维护。实验表明在多种模型规模上平均F1提升约2.5%，为LLM Agent的长期交互提供了低成本、高稳定的记忆方案。
- [**MemReader: From Passive to Active Extraction for Long-Term Agent Memory**](http://arxiv.org/abs/2604.07877v2) - 本文提出MemReader系列，用于智能体系统中的长期记忆主动提取。核心贡献包括：紧凑被动提取器MemReader-0.6B确保准确模式一致的输出，以及基于GRPO优化的主动提取器MemReader-4B，能评估信息价值、引用歧义和完整性，选择性写入记忆、延迟处理或丢弃无关内容。实验证明其在知识更新、时间推理和减少幻觉任务上达到最优，表明推理驱动的选择性记忆提取是构建低噪音动态长期记忆的关键。该工作直接以Agent Memory为核心方法，提供了一套从被动到主动的记忆提取机制。
- [**SuperLocalMemory V3.3: The Living Brain -- Biologically-Inspired Forgetting, Cognitive Quantization, and Multi-Channel Retrieval for Zero-LLM Agent Memory Systems**](http://arxiv.org/abs/2604.04514v1) - 本文提出SuperLocalMemory V3.3（“活脑”），一个本地优先的智能体记忆系统，首次在本地记忆中数学化实现艾宾浩斯遗忘曲线、Fisher-Rao量化感知距离（FRQAD）和7通道认知检索（语义、关键词、实体图、时间、扩散激活、巩固、Hopfield关联）。该系统无需云LLM即可完成记忆生命周期管理，在LoCoMo基准测试中零LLM模式下达到70.4%准确率，为AI编码智能体提供了类人认知记忆架构，显著提升长期记忆效率与可扩展性。
## 记忆剪枝与抽象
> **针对“全模态/巨大状态量”的核心解决方案：** 存储每一帧像素是不现实的。本板块收录通过 **事件触发、语义抽象和动态剪枝** 来压缩记忆容量的技术。

- **基于事件的记忆**：仅在**状态转换**发生时记录元数据（例如，“门开了”而不是连续的视频流）。
- **语义抽象**：将复杂的物理交互压缩为原子语义动作（例如，“抓住了杯子”）。
- **MCP集成**：用于高效地将机器人SDK状态（关节角度、扭矩）流式传输到智能体记忆中心的协议。


- [**memstate-benchmark**](https://github.com/memstate-ai/memstate-benchmark) - 该项目是一个开源的AI Agent内存系统基准测试框架，专为评估和比较不同内存解决方案（如Memstate、mem0）而设计。它基于MCP（Model Context Protocol）实现内存集成，并支持通过OpenRouter调用多种LLM模型（如Claude Opus、Gemini）在真实Agent任务中进行测试。通过提供统一的评估指标，帮助开发者选择最优的Agent内存架构，特别适合研究者和AI工程师优化代理记忆机制。
- [**agentbrain-benchmarks**](https://github.com/AgentBrainHQ/agentbrain-benchmarks) - 项目提供 Agent Brain 在 LongMemEval-M 上的可复现基准测试代码，准确率达 71.7%（Test 0）。它直接面向 Agent 长期记忆评估，利用 dream-cycle、知识图谱和 FSRS 等技术构建记忆评测体系，为研究 Agent Memory 的性能与反思机制提供标准化测试工具。适合从事 Agent 记忆评估与基准测试的研究人员使用。
- [**mnemebrain-benchmark**](https://github.com/mnemebrain/mnemebrain-benchmark) - 该项目提供专门评估AI Agent记忆系统信念动态的基准测试套件，包含48个任务，覆盖矛盾检测、信念修正、溯源推理和时序推理等核心能力。它直接针对Agent Memory领域，通过图数据库和知识图谱实现认知架构中的记忆评估，适合研究Agent记忆机制和认知架构的开发者使用。
- [**agent-memory-eval**](https://github.com/verifiedstate/agent-memory-eval) - 该项目是一个开放的AI智能体记忆系统基准测试套件，专门用于评估智能体在时间推理、冲突检测、多跳检索、弃权能力和溯源等方面的记忆性能。它直接面向Agent Memory生态，提供标准化的评测框架，有助于研究人员和开发者对比不同记忆方案的效果，推动记忆系统的发展与改进。
- [**MemBase**](https://github.com/zjunlp/MemBase) - MemBase 是一个专为长期对话记忆层设计的综合基准测试框架，旨在评估和比较不同记忆机制在 AI 代理（Agent）中的表现。它提供了标准化的测试集和评测指标，直接服务于 Agent Memory 的研发与优化。项目基于 Python 实现，适用于研究大语言模型记忆系统、具身智能记忆管理的开发者。
- [**ATM-Bench**](https://github.com/JingbiaoMei/ATM-Bench) - ATM-Bench 是一个专为评估 AI Agent 长期个性化记忆能力设计的基准测试，覆盖约4年的多模态数据（图像、视频、电子邮件）。它提供引用查询、证据锚定回答及多源推理任务，直接面向 Agent Memory 中的长期记忆与记忆代理机制，适合研究记忆持久化与检索增强生成的团队。
- [**AMA-Bench**](https://github.com/AMA-Bench/AMA-Bench) - 该项目是一个针对智能体长程记忆性能的标准化评估框架，专门衡量代理应用在长上下文保持与长时间跨度记忆任务中的表现。它提供统一的基准测试方法和指标，直接服务于 Agent Memory 领域的研究与开发。适用于需要量化评估智能体记忆能力的开发者与研究人员。
- [**Mem-Gallery**](https://github.com/YuanchenBei/Mem-Gallery) - Mem-Gallery 是一个多模态长期对话记忆基准测试项目，专为 MLLM 智能体设计。它提供标准化的评估框架，测试智能体在长时间交互中记忆、检索和利用多模态信息（文本、图像等）的能力，直接聚焦于 Agent Memory 的核心挑战。项目通过构建包含复杂对话场景的数据集和评测指标，帮助开发者验证和改进智能体的长时记忆机制。适用于研究对话型 AI 代理和多模态记忆系统的研究人员。
- [**agent-memory-benchmark**](https://github.com/vectorize-io/agent-memory-benchmark) - 该项目提供了一个用于评估AI代理记忆系统性能的基准测试框架。它通过标准化指标（如检索精度、召回率和延迟）测试不同记忆策略，特别关注LLM代理的长短期记忆管理。项目实现了可扩展的评估管道，支持自定义记忆模块集成，适用于研究者和开发者量化Agent Memory方案的效率。
- [**AgentMemoryBench**](https://github.com/s010m00n/AgentMemoryBench) - AgentMemoryBench 是一个统一基准测试，用于评估基于LLM的智能体在持续记忆（Continual Agent Memory）方面的能力。它支持在线、离线、回放、迁移和修复五种评估模式，覆盖六个交互任务，兼顾系统记忆与个人记忆机制。该项目直接面向Agent Memory评估，为研究智能体记忆的持久化、检索与进化提供了标准化评测工具，适用于LLM智能体记忆研究者。
- [**MEXTRA**](https://github.com/wangbo9719/MEXTRA) - MEXTRA 是针对大型语言模型（LLM）Agent 记忆系统的隐私风险分析工具与论文源码。该项目系统性地评估了 Agent 长期记忆模块中可能存在的敏感信息泄露途径，提出了一套量化隐私暴露程度的框架与方法。主要面向 AI Agent 安全研究人员及 LLM 记忆系统开发者，帮助识别并缓解记忆模块中的隐私隐患。
- [**agent-memory-tck**](https://github.com/neo4j-labs/agent-memory-tck) - 该项目是Neo4j Agent Memory的技术合规性测试套件（TCK），用于验证各类实现是否符合Neo4j定义的Agent Memory规范。通过提供标准化测试用例，确保基于Neo4j构建的Agent记忆模块在知识图谱持久化、检索和一致性方面达到标准。适用于需要保证Neo4j Agent Memory集成质量的开发者和架构师。
- [**PyramidBench**](https://github.com/zhoujunlingla/PyramidBench) - PyramidBench是一个专注于层级金字塔记忆评估的VLA基准测试项目，用于系统评估具身智能体的长期记忆与分层记忆组织能力。它通过设计特定任务来测试记忆的分层构建、存储与检索效率，与Agent Memory中的层级记忆系统和具身AI记忆紧密相关。该基准主要面向具身AI和VLA模型的研究人员，帮助比较不同记忆架构在物理仿真环境中的表现。
- [**AMSC**](https://github.com/reiiwang/AMSC) - 该项目旨在提供 Agent Memory 解决方案的系统性比较，涵盖多种记忆机制的分析与评估。它专注于代理记忆领域，为开发者选择合适的内存架构提供参考。项目以 Python 实现，目标用户是研究 Agent Memory 的学者与工程师。
- [**Spore: Efficient and Training-Free Privacy Extraction Attack on LLMs via Inference-Time Hybrid Probing**](http://arxiv.org/abs/2604.23711v1) - 本文提出Spore，一种无需训练、在推理阶段通过混合探测高效提取LLM代理记忆隐私的攻击方法。Spore在黑白灰盒设置下均有效，仅需单次查询即可恢复原始隐私信息，揭示了现有代理记忆系统在上下文交互中的严重隐私泄露风险，为提升Agent Memory安全防护提供了量化依据。
- [**FileGram: Grounding Agent Personalization in File-System Behavioral Traces**](http://arxiv.org/abs/2604.04901v1) - 该论文主要贡献是提出FileGram框架，通过文件系统行为轨迹实现智能体记忆与个性化。核心记忆架构FileGramOS将原子动作和内容增量编码为程序性、语义性和情节性记忆通道，支持查询时抽象，解决了隐私限制下多模态轨迹数据稀缺的问题。该框架为Agent Memory提供了细粒度、可扩展的底层记忆构建方法，具有重要应用价值。
- [**Poison Once, Exploit Forever: Environment-Injected Memory Poisoning Attacks on Web Agents**](http://arxiv.org/abs/2604.02623v2) - 本文首次提出环境注入式轨迹记忆中毒攻击（eTAMP），揭示基于LLM的Web智能体在记忆机制中存在严重安全隐患。通过单一被污染的环境观察（如篡改的网页），攻击者即可悄然毒化智能体的长期记忆，并在跨会话、跨站点的后续任务中被触发激活，绕过权限防御。实验表明，该方法在VisualWebArena上对GPT-5-mini等模型达到高达32.5%的攻击成功率，且智能体在环境压力下脆弱性骤增（最多提升8倍）。该工作直接聚焦Agent Memory作为持久攻击面的核心安全问题，对构建安全的记忆系统具有重要警示价值。
- [**MemGround: Long-Term Memory Evaluation Kit for Large Language Models in Gamified Scenarios**](http://arxiv.org/abs/2604.14158v1) - 该论文提出MemGround基准，用于评估大语言模型在游戏化交互场景中的长期记忆能力。核心贡献在于设计了包含表面状态记忆、时间关联记忆和基于推理记忆的三层评估框架，并通过多项指标（如问答得分、记忆片段解锁等）系统衡量智能体在动态环境中的状态追踪和层次推理能力。相关工作直接聚焦Agent Memory评估，为构建具身智能体的记忆系统提供了标准化测试工具。
- [**Diagnosing Retrieval vs. Utilization Bottlenecks in LLM Agent Memory**](http://arxiv.org/abs/2603.02473v2) - 本文提出诊断框架，系统分析LLM Agent记忆写入与检索的瓶颈。通过3x3实验（三种写入策略×三种检索方法）在LoCoMo数据集上发现，检索方法主导性能差异（准确率跨度20点），而写入策略影响仅3-8点。原始分块存储无需LLM调用即可媲美或超越有损压缩策略，揭示当前记忆管线可能丢弃有用上下文。代码开源。
- [**AMA-Bench: Evaluating Long-Horizon Memory for Agentic Applications**](http://arxiv.org/abs/2602.22769v2) - 提出AMA-Bench基准，用于评估LLM代理在真实应用中的长时记忆能力，包含真实代理轨迹与可扩展的合成轨迹。发现现有记忆系统因缺乏因果关系和客观信息、受限于相似性检索的损失性而表现不佳。提出AMA-Agent记忆系统，集成因果图与工具增强检索，在基准上达到57.22%平均准确率，超越最强基线11.16%，为Agent Memory评估提供了标准化框架。
- [**MemoryArena: Benchmarking Agent Memory in Interdependent Multi-Session Agentic Tasks**](http://arxiv.org/abs/2602.16313v1) - 论文提出MemoryArena基准测试平台，专门评估智能体在多会话、相互依赖的任务中如何利用长期记忆指导后续行动。该平台要求智能体在交互中提炼经验存入记忆，并在后续会话中检索使用，涵盖网页导航、偏好约束规划、渐进信息搜索和顺序形式推理等场景。实验表明，现有长上下文记忆基准（如LoCoMo）上表现饱和的智能体在MemoryArena中性能显著下降，揭示了当前评估体系的关键缺口。
- [**TAME: A Trustworthy Test-Time Evolution of Agent Memory with Systematic Benchmarking**](http://arxiv.org/abs/2602.03224v1) - 该论文提出TAME框架，针对agent memory在测试时演化中出现的可信度下降问题（Agent Memory Misevolution），构建了Trust-Memevo基准，系统评估多维可信度。TAME采用双记忆架构，分别演化执行器记忆（提取通用方法提升任务性能）和评估器记忆（基于历史反馈优化安全与效用评估），通过记忆过滤、生成、可信精炼、执行与双轨更新闭环，在保持效用同时提升可信度。核心贡献在于首次系统性研究agent memory的可信演化，并提供有效解决方案。
- [**MemEvolve: Meta-Evolution of Agent Memory Systems**](http://arxiv.org/abs/2512.18746v1) - 提出Meta-Evolution框架MemEvolve，联合进化Agent记忆架构与经验知识，突破传统静态记忆系统的限制。同时开源EvolveLab代码库，统一12种代表性记忆系统（编码、存储、检索、管理）的设计空间，为自我进化Agent提供标准化实验平台。在四个Agent基准测试中提升SmolAgent等框架性能达17.06%，并展现跨任务跨LLM泛化能力。
- [**MemoryGraft: Persistent Compromise of LLM Agents via Poisoned Experience Retrieval**](http://arxiv.org/abs/2512.16962v1) - 本文首次揭示LLM Agent长期记忆与RAG系统的新型攻击面，提出MemoryGraft攻击，通过向Agent经验存储中植入少量恶意模板，利用其语义模仿启发式在检索时触发持久行为漂移。该工作直接以Agent Memory的存储、检索与经验学习机制为核心攻击目标，暴露了记忆系统在信任边界上的安全漏洞，为Agent记忆防护设计提供了关键警示。
- [**Beyond a Million Tokens: Benchmarking and Enhancing Long-Term Memory in LLMs**](http://arxiv.org/abs/2510.27246v2) - 论文提出了BEAM基准和LIGHT框架，BEAM通过自动生成长达10M token的连贯对话评估LLMs的长时记忆，LIGHT则受人类认知启发，为LLMs配备长期情景记忆、短期工作记忆和便签式积累三种互补记忆系统，显著提升模型在长对话中的记忆能力，实验表明在多种模型上平均提升3.5%-12.69%。该工作直接以长时记忆作为核心方法，并设计了类认知架构的记忆系统，属于Agent Memory典型研究。
- [**Evaluating Long-Term Memory for Long-Context Question Answering**](http://arxiv.org/abs/2510.23730v2) - 该论文系统性评估了多种长期记忆机制（语义记忆、情景记忆、程序记忆）在长上下文问答任务中的效果，发现记忆增强方法可减少90%以上token消耗且保持精度。特别分析了代理记忆（agentic memory）和基于反思的情景记忆对模型性能的影响，为Agent Memory系统的设计与复杂度选择提供了实证依据。
- [**Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions**](https://openalex.org/W4415971869) - 该论文提出MemoryAgentBench基准，专门用于评估LLM Agent的记忆能力。基于记忆科学和认知科学，定义了四个核心记忆能力：准确检索、测试时学习、长程理解和选择性遗忘。通过将现有长上下文数据集转换为多轮交互格式，模拟Agent增量积累信息的场景，提供了系统化的测试平台。该基准直接以Agent Memory为核心评估对象，填补了现有基准缺乏对记忆能力全面评估的空白。
- [**Memory, Benchmark & Robots: A Benchmark for Solving Complex Tasks with Reinforcement Learning**](http://arxiv.org/abs/2502.10550v3) - 该论文提出了MIKASA基准，用于评估强化学习智能体在部分可观测环境中的记忆能力。主要贡献包括：(1) 提出了记忆密集型任务的分类框架；(2) 构建了MIKASA-Base统一基准；(3) 开发了MIKASA-Robo，包含32个桌面机器人操作任务，专门测试空间-时间记忆、情景记忆等机制。该基准为记忆增强的具身智能体提供了标准化评估平台，直接关联Agent_Memory的核心方法（记忆增强RL）和环境（机器人操作）。
- [**Evaluating Very Long-Term Conversational Memory of LLM Agents**](https://openalex.org/W4402684150) - 该论文提出了一个机器-人工流水线，基于LLM agent架构和人物角色及时序事件图生成高质量超长对话，并构建了LoCoMo数据集（平均300轮、9K tokens，最多35个会话）。论文以Agent Memory为核心评估要素，设计了问答、事件摘要和多模态对话生成等基准任务，系统评测了LLM在超长对话中的长期记忆能力，揭示了现有长上下文LLM和RAG技术仍显著落后于人类表现。该工作为Agent长期记忆研究提供了重要的评测平台和方法框架。
## 基准与评估
- **FindingDory** *(arXiv, 2025)* - 基于**Habitat Simulator**的基准，包含60个长距离任务。
- **MEMENTO** *(arXiv, 2025)* - 评估物体重新排列任务中的**个性化记忆利用**。
- **LOCOMO** *(Mem0.ai, 2025)* - 长周期对话记忆基准（SOTA准确率68.4%）。


- [**graymatter**](https://github.com/angelnicolasc/graymatter) - Graymatter 是一个轻量级持久化记忆库，旨在通过三行代码为 AI 代理注入长期记忆能力，显著降低 90% 的 token 消耗同时保持回答质量。它采用 Go 语言实现、支持离线优先和自托管部署，直接面向 Agent Memory 场景。适合需要低成本、高效记忆集成的 AI Agent 开发者。
- [**icarus-daedalus**](https://github.com/esaradev/icarus-daedalus) - Icarus Memory Protocol 是一个轻量级的通用 Agent 记忆协议，仅用约50行代码通过本地目录中的 Markdown 文件实现持久化存储。它支持任意框架和平台（Telegram、Slack），并提供双智能体参考实现，可实现跨平台记忆共享与回忆。该项目专注于为 AI Agent 提供极简、通用的记忆机制，适合需要快速集成简易记忆功能的开发者。
- [**agent-memory-server**](https://github.com/redis/agent-memory-server) - 该项目是一个专为AI Agent和应用程序设计的快速灵活内存服务器，基于Redis实现。它提供持久化和检索能力，支持Agent实时读写记忆数据，适用于需要长期记忆、会话状态管理或认知架构的智能体系统。项目直接以Agent Memory为核心，实现了高效的内存存储与查询，目标是帮助开发者构建具备记忆能力的Agent。
- [**memorizer**](https://github.com/petabridge/memorizer) - 该项目是一个基于向量检索的 Agent Memory MCP 服务器，专门为大语言模型代理提供持久化记忆管理与上下文检索能力。它通过 MCP（Model Context Protocol）标准接口与代理系统集成，支持高效存储和查询历史经验与状态，适用于需要长期记忆的对话代理或具身智能场景。主要采用向量搜索实现语义匹配，目标用户为构建 AI Agent 的开发者，特别是需要物理环境底层状态记忆中枢的具身智能项目。
- [**mcp-openmemory**](https://github.com/baryhuang/mcp-openmemory) - 该仓库是一个基于 MCP（Model Context Protocol）的轻量级记忆服务器，旨在为 Claude 等 AI Agent 提供对话记忆和持续学习能力。它实现了 Agent 记忆中枢功能，支持长期记忆存储与检索，使 Agent 能在交互中积累经验并改进行为。适用于希望为 AI Agent 添加持久记忆能力的开发者。
- [**skalex**](https://github.com/TarekRaafat/skalex) - TarekRaafat/skalex 是一个AI优先、零依赖的JavaScript数据库，内置向量搜索、Agent Memory和MCP服务器支持。它为AI Agent提供原生记忆存储与检索，通过MCP协议可连接物理环境状态，适用于Node.js、浏览器及边缘运行时。项目面向需要本地化、轻量级记忆方案的Agent开发者。
- [**memoryOSS**](https://github.com/memoryOSScom/memoryOSS) - memoryOSS是一个为AI代理提供持久性长期记忆的开源工具，通过本地代理和MCP（Model Context Protocol）记忆层实现。它专门适配Claude、Codex及兼容OpenAI的客户端，支持上下文管理和检索，关键技术采用Rust编写以追求高性能。该项目直接面向Agent_Memory领域，可作为具身智能或对话智能体的记忆中枢。
- [**MemState**](https://github.com/scream4ik/MemState) - MemState 为 AI Agent 提供事务性内存管理，通过保持 SQL 和向量数据库（如 ChromaDB）间的 ACID 级一致性来消除幻觉。它整合 LangChain/LangGraph 生态，面向需要可靠状态同步的复杂 Agent 应用，尤其适合对记忆一致性要求高的多步推理场景。
- [**beacon**](https://github.com/ConnorBritain/beacon) - Beacon 是专为跨平台智能代理设计的核心持久化层，利用 Supabase Postgres 实现代理记忆的稳定存储与高效检索。它直接服务于 Agent Memory 场景，支持记忆跨工具和环境的持久化，技术基于关系型数据库。适合需要持久化记忆机制的 AI Agent 开发者。
- [**langgraph-store-vertex-memorybank**](https://github.com/zeroasterisk/langgraph-store-vertex-memorybank) - 该项目为 LangGraph 的 BaseStore 提供基于 Vertex AI Agent Engine Memory Bank 的后端实现，专门用于持久化和检索智能体的长期记忆。它通过 LangGraph 的接口直接集成 Google Cloud 的 Agent Memory 服务，适用于需要云端记忆中枢的 LLM Agent 应用。目标用户是使用 LangGraph 构建具备持久记忆能力的 AI Agent 的开发者。
- [**unified-memory-engine**](https://github.com/chenxi-lee/unified-memory-engine) - 企业级内存增强工具，专为 CoPaw 代理设计，通过 AES-256 加密确保数据安全，并利用分层压缩（Hierarchical Compression）优化存储与检索效率。直接面向 Agent Memory，实现了类似层级记忆管理（Hierarchical Memory Systems）和记忆修剪（Memory Pruning）的能力，适用于需要安全、高效长时记忆的 AI 代理开发场景。
- [**agent-mem**](https://github.com/HanFromTokyoDrift/agent-mem) - agent-mem 是一个用 Go 编写的轻量级高性能知识库中间件，专为增强 AI 代理的长期记忆和自我进化能力而设计。它通过内置的记忆管理和优化协议，支持多模态 LLM 记忆、记忆代理和泛化，为 AI 代理提供持久化记忆存储与检索机制。该项目适合需要构建具备长期记忆和自我改进能力的 AI 代理系统的开发者。
- [**linkledger-cli**](https://github.com/gdiab/linkledger-cli) - LinkLedger CLI 是一款面向智能体的命令行本地记忆工具，支持捕获链接、附加证据并检索紧凑摘要。它使用 SQLite 和 FTS5 实现本地优先的全文检索与持久化存储，主题明确包含 agent-memory。该工具可直接为 Agent 提供轻量级的外部记忆模块，适合需要在终端管理长期记忆的 AI Agent 开发者使用。
- [**history-graph-protocol**](https://github.com/wgsim/history-graph-protocol) - History Graph Protocol 是一个基于 MCP 协议的服务器，为 AI 智能体提供持久化、仅追加的因果历史记录。它通过有向无环图存储事件间的因果关系，支持审计追踪与状态回溯，适合需要长期记忆与可溯源推理的 Agent 场景。该方案直接实现 MCP 连接底层状态，完美契合具身智能记忆中枢需求，目标用户为构建具备因果推理与记忆管理的 AI Agent 开发者。
- [**memledger**](https://github.com/selfradiance/memledger) - MemLedger 是一个仅追加的 CLI 账本工具，专为结构化智能体记忆声明设计，支持来源追踪、置信度评分、可争议性和不可变历史记录。它直接面向 Agent Memory 生态，提供本地优先的持久化方案（基于 SQLite 和 TypeScript），确保记忆完整性与可审计性。适合需要构建可追溯、高可信度记忆系统的 AI Agent 开发者。
- [**amr-agent-memory-server-demo**](https://github.com/AzureManagedRedis/amr-agent-memory-server-demo) - 该项目是一个基于 Redis Agent Memory Server 和 Azure Managed Redis 的聊天应用演示，专门实现了智能体的长期记忆机制。通过 Redis 服务器持久化对话历史，支持上下文回忆与检索，为 LLM 驱动的智能体提供高效的记忆存储与管理能力。适合希望快速集成记忆功能的 Azure 生态开发者。
- [**lucid-memory**](https://github.com/JasonDocton/lucid-memory) - Lucid Memory 是一个专为 AI Agent 设计的本地化、即时、持久化记忆系统。它替代了传统云向量数据库（如 Pinecone）和 RAG 方案，宣称速度快 13 倍、体积缩减 5 倍，能检索到 RAG 遗漏的信息。采用零云、零成本架构，基于 TypeScript 开发，适合需要高效、轻量级 Agent 记忆管理的应用场景。
- [**PrismerCloud**](https://github.com/Prismer-AI/PrismerCloud) - PrismerCloud 是一个自托管的云平台，专门为 AI Agent 提供知识库、记忆管理和 MCP（Model Context Protocol）服务器集成。它支持 Agent 之间通信、持久化记忆存储与 RAG 检索，能够与 Claude、Cursor 等 LLM 工具配合，实现 Agent 长期记忆和上下文增强。项目使用 TypeScript、Next.js 和 Docker 构建，适用于需要 Agent Memory 功能的开发者。
- [**yantrikdb-server**](https://github.com/yantrikos/yantrikdb-server) - YantrikDB 是一个专为AI智能体设计的认知记忆数据库，实现重复合并、矛盾检测和时间衰减机制。作为MCP服务器可直接服务于具身智能系统，通过Model Context Protocol连接物理环境底层状态记忆中枢，支持语义向量和知识图谱存储。采用Rust实现高性能持久化，适合需要长期记忆管理、自我进化的智能体架构师。
- [**mentisdb**](https://github.com/CloudLLM-ai/mentisdb) - MentisDB 是一个为 AI Agent 设计的持久化记忆系统，支持追加式思维链存储和 Git 式技能注册表。它通过版本控制和完整性检查让技能随经验进化，并实现快速检索，使代理不仅记住过去，还能不断改进自身。该项目基于 Rust 实现，适用于需要反思与自我进化记忆机制的智能体开发场景，特别是关注共享 Agent Memory 和技能演化体系的用户。
- [**cortex-hub**](https://github.com/lktiep/cortex-hub) - Cortex-Hub 是一个自托管的 AI Agent 记忆与代码智能平台，专为多智能体协同开发设计。它通过单一 MCP 端点提供持久化记忆、AST 感知的代码搜索和共享知识库，支持 Claude Code、Cursor 等工具集成。核心技术包括向量搜索和 TypeScript 实现，专注于 Agent 长期记忆管理，适合需要统一记忆中枢的 AI 编程团队。
- [**CortexaDB**](https://github.com/anaslimem/CortexaDB) - CortexaDB 是一款专为 AI 智能体记忆设计的嵌入式数据库，提供无需服务器的单文件体验，原生支持向量、图结构和时间序列检索，可高效存储和查询 Agent 的长期记忆、知识图谱与序列化轨迹。适用于需要持久化记忆的自主 Agent 和具身 AI 系统。
- [**amfs**](https://github.com/raia-live/amfs) - AMFS 是一个专为 AI 代理记忆管理的版本控制系统，提供分支、差异、PR 和回滚等 Git 式操作，直接解决 Agent Memory 的持久化与历史追踪需求。它集成 LangGraph、CrewAI 等框架，支持多智能体场景下的记忆协作与审计。适用于需要精细控制代理知识演进、调试或回退的开发团队。
- [**local_faiss_mcp**](https://github.com/nonatofabio/local_faiss_mcp) - 本项目将FAISS向量数据库封装为MCP服务器，为Claude、Copilot等AI Agent提供即插即用的本地语义搜索记忆存储。它通过Model Context Protocol实现Agent记忆的持久化与检索，使智能体能够访问历史交互的向量化上下文，支持完全本地化运行，适合注重隐私与低延迟的Agent应用场景。
- [**hermes-gbrain-bridge**](https://github.com/howardpen9/hermes-gbrain-bridge) - 该项目是Hermes/OpenClaw agent记忆数据的格式转换工具，可将JSONL会话日志与MEMORY.md文件转为Markdown，以便注入gBrain知识图谱。它专为Agent Memory生态设计，处理agent持久化记忆的结构化转换，并支持MCP协议对接，适合需要将agent长期记忆集成到知识管理系统的开发者。
- [**palinode**](https://github.com/phasespace-labs/palinode) - Palinode 是一个专为 AI Agent 和开发者工具设计的记忆底层系统，采用 Git 版本化和文件原生存储，并优先支持 MCP（Model Context Protocol）协议。它集成了 sqlite-vec 向量搜索，可持久化和管理 Agent 的长期记忆，特别适用于需要版本控制与结构化记忆的智能体开发场景。该项目明确面向 Agent Memory，适合构建具备反思与自我进化机制的 AI 智能体。
- [**pluribus**](https://github.com/johnnyjoy/pluribus) - Pluribus 是一个基于 Go 语言实现的持久化内存 MCP 服务器，专为 AI 代理提供遵循 Model Context Protocol 的持久化记忆服务。它通过 MCP 和 REST 接口支持智能体存储与检索历史交互、状态信息，可作为具身智能系统中连接物理环境底层状态记忆的中枢。项目目标用户是构建记忆增强型 AI 代理的开发者，特别适合需要长期记忆与上下文管理的 MCP 生态应用场景。
- [**openclaw-EverMemOS**](https://github.com/ZhenhangTung/openclaw-EverMemOS) - 该项目是EverMemOS为OpenClaw开发的长期记忆后端插件，专为AI Agent提供持久化记忆存储、语义检索和渐进式用户画像构建能力。它采用RAG技术实现记忆的检索增强生成，支持TypeScript集成，核心聚焦于Agent长期记忆管理。适用于构建具备记忆功能的OpenClaw Agent系统的开发者。
- [**tagmem**](https://github.com/codysnider/tagmem) - TagMem 是一个用于 LLM Agent 的结构化本地记忆存储与检索工具，采用 Go 语言实现。它通过嵌入向量（embeddings）进行语义检索，支持离线运行，并实现了 Model Context Protocol (MCP)，可作为记忆中枢连接外部环境或物理状态。该项目直接面向 Agent Memory 生态，适合需要本地优先、可离线工作的 LLM Agent 记忆管理场景。
- [**mem0-api**](https://github.com/OctavianTocan/mem0-api) - 该项目提供了一个基于FastAPI的生产级语义记忆管理接口，底层采用Mem0库实现AI代理记忆的持久化、向量嵌入存储与LLM驱动的语义检索。它支持通过REST API高效存储、搜索和检索代理的长期记忆，适用于构建上下文感知的对话AI系统，尤其适合需要结构化记忆管理的多智能体场景。
## 基础设施与数据库
- **针对时间序列或高维机器人数据优化的向量数据库**

## 相关列表与灵感来源
- [Awesome-AI-Memory (IAAR-Shanghai)](https://github.com/IAAR-Shanghai/Awesome-AI-Memory)
- [Awesome-Embodied-AI](https://github.com/ahundt/awesome-embodied-vision)

---

## 贡献指南
欢迎贡献！请专注于物理世界中**十亿级状态管理**这一课题的发明。


---

<div align="center">

## 🤖 Auto-Generated

This awesome list is automatically maintained by [GPT-Awesome-List-Generator](https://github.com/shaoxiang/GPT-Awesome-List-Generator).

</div>