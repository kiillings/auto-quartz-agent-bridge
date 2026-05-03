# Auto-Quartz

Auto-Quartz：基于多 Agent 协作的自托管知识库自动化增强流水线

项目成立的初衷：
在通过 Quartz 部署个人知识库，但面临两个瓶颈：
一、 Obsidian 中的原始笔记缺乏结构化元数据（Tags, Categories），导致 Web 端检索效率低下；
二、笔记间的双向链接（Backlinks）需要手动维护，难以形成有效的知识图谱。传统脚本无法理解复杂的语义联系，导致知识库长期处于“信息孤岛”状态。

项目的核心逻辑：
构建了一个基于 LangGraph 的多 Agent 协作系统：
语义分析 Agent：利用长链推理（Chain-of-Thought）分析 Markdown 文档内容，自动提取关键实体并生成符合 SEO 标准的 Frontmatter。
知识链接 Agent：扫描全局库，通过向量相似度计算，在不破坏原意的前提下，自动在笔记末尾推荐“相关阅读”并补全双向链接。
自动化部署 Agent：监控 GitHub 仓库变更，自动通过云端环境完成 npx quartz build 并同步至 Nginx 生产环境，同时处理 Git 代理端口冲突等网络层异常。

目前项目是个人在主要维护。
