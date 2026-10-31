# AI Buzzword Tracker

> A living learning roadmap and reference glossary for AI engineering. Keep this file as the source of truth: append concepts, update definitions, add notes from projects, and revisit the status as your understanding improves.

**Source tracker:** `AI Buzzword Tracker.html`  
**Markdown edition created:** 31 October 2026  
**Scope:** LLM foundations, application engineering, agents, model development, production systems, safety and hands-on tools.

## How to use this file

- Change ` [ ] ` to ` [x] ` when you can explain a topic and recognize when to use it—not merely after skimming it.
- Use **In progress** for topics you are actively learning; add your notes underneath the entry.
- Add a short implementation or debugging example wherever possible.
- Keep emerging terms, vendor names and marketing language labelled as such; a term being popular does not make it a distinct technical discipline.
- When adding a new term, include: plain-English definition, why it matters, practical example, trade-offs, and at least one reliable resource.

### Suggested status convention
- `[ ]` Not started
- `[~]` In progress
- `[x]` Can explain and apply
- `[?]` Needs verification / definition is disputed

### Suggested priority convention
- **P0** — foundational or immediately useful in production
- **P1** — important next layer
- **P2** — useful specialization or emerging topic
- **Watch** — interesting, but hype or practical value is still uncertain

## Learning roadmap

### 1. Foundations

How LLMs work under the hood. You've covered most of this; fill the gaps.

- [x] **LLM basics** — What a large language model is: a next-token predictor trained on huge text corpora.
  - Video: [Deep Dive into LLMs like ChatGPT (Karpathy, 3.5 h)](https://www.youtube.com/watch?v=7xTGNNLPyMI)
  - Video: [Large Language Models explained briefly (3Blue1Brown)](https://www.youtube.com/watch?v=LPZh9BOjkQs)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **Prompt engineering** — Writing instructions, examples and structure so a model gives the output you want.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **Transformers & attention** — The architecture behind every modern LLM; attention lets each token look at every other token.
  - Video: [Transformers, the tech behind LLMs (3Blue1Brown, 27 min)](https://www.youtube.com/watch?v=wjZofJX0v4M)
  - Video: [Attention in transformers, step-by-step (3Blue1Brown)](https://www.youtube.com/watch?v=eMlx5fFNoYc)
  - Reference: [3Blue1Brown lesson page](https://www.3blue1brown.com/lessons/gpt)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **Tokens & tokenization** — Models read sub-word tokens, not words. Pricing, limits and quirks all come from this.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **Context window** — How many tokens a model can see at once (now often 200K to 1M+).
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **Embeddings** — Turning text into vectors so that similar meanings sit close together. The basis of semantic search.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **Temperature & sampling** — Knobs (temperature, top-p) that control how random or deterministic outputs are.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **Hallucination** — When a model states something false with confidence, and the techniques used to reduce it.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **Pretraining → fine-tuning → RLHF** — The three stages that turn raw text prediction into a helpful assistant.
  - Video: [Deep Dive into LLMs like ChatGPT (Karpathy): covers the full training stack](https://www.youtube.com/watch?v=7xTGNNLPyMI)
  - Notes: _Add your explanation, example, implementation notes or open questions._

### 2. Building with LLMs

The application layer. LangChain sits here, so this is your next stretch.

- [x] **LangChain** — Framework of building blocks (prompts, models, retrievers, tools) for LLM apps.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **LangGraph** — LangChain's graph/state-machine library for agents with loops, branches and persistence.
  - Reference: [LangGraph reference (official)](https://reference.langchain.com/python/langgraph/overview)
  - Reference: [Why LangGraph + basics tutorial series (official docs)](https://docs.langchain.com/langgraph-platform/why-langgraph)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **LlamaIndex** — Framework focused on connecting LLMs to your data: ingestion, indexing, retrieval.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **RAG (Retrieval-Augmented Generation)** — Fetch relevant documents first, then let the model answer using them.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [x] **Vector databases** — Stores built for embedding search: pgvector, Pinecone, Qdrant, Weaviate, Chroma.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Chunking, reranking & hybrid search** — The unglamorous parts that decide whether RAG actually works.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **GraphRAG** — RAG over a knowledge graph of entities and relations instead of flat chunks.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Function calling / tool use** — Letting the model call your APIs by emitting structured calls you execute.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Structured outputs** — Forcing the model to return valid JSON matching a schema.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Prompt caching** — Reusing a processed prompt prefix to cut cost and latency on repeat calls.
  - Reference: [Prompt caching (Anthropic docs)](https://platform.claude.com/docs/en/build-with-claude/prompt-caching)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Context engineering** — The successor to prompt engineering: deciding everything that goes into the context, not just the instruction.
  - Video: [Advanced Context Engineering for Agents (Dex Horthy, YC, ~15 min)](https://www.youtube.com/watch?v=IS_y40zY-hc)
  - Reference: [Effective context engineering for AI agents (Anthropic)](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Context rot & compaction** **NEW in source tracker** — Models get worse as the window fills, well before the advertised limit. Compaction (reversible: drop what can be re-read from files) and summarization (lossy) keep long-running agents sharp.
  - Video: [Advanced Context Engineering for Agents (Dex Horthy, YC, ~15 min)](https://www.youtube.com/watch?v=IS_y40zY-hc)
  - Reference: [Context Engineering for AI Agents: Part 2 (Phil Schmid)](https://www.philschmid.de/context-engineering-part-2)
  - Reference: [Effective context engineering for AI agents (Anthropic)](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Context layer, context graphs & semantic layers** **NEW in source tracker** — A governed layer of business meaning (metrics, entities, lineage) that agents query instead of raw tables. “Context graph” is the hyped version and many vendors are selling it, so read with some salt.
  - Reference: [Making Your Data Ready for Agentic AI (Martin Fowler)](https://martinfowler.com/articles/making-data-ready-for-agentic-ai.html)
  - Reference: [Context, semantics and ontology: a primer (MotherDuck)](https://motherduck.com/blog/context-layer-vs-semantic-layer-ontology/)
  - Reference: [2026 data predictions, sceptical on context graphs (SiliconANGLE)](https://siliconangle.com/2026/01/18/2026-data-predictions-scaling-ai-agents-via-contextual-intelligence/)
  - Notes: _Add your explanation, example, implementation notes or open questions._

### 3. Agents

The biggest buzzword cluster of 2025–26. Most new tooling lives here.

- [ ] **AI agents / agentic AI** — An LLM in a loop that plans, calls tools, observes results and keeps going until a goal is met.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **ReAct pattern** — Reason → Act → Observe. The original agent loop most frameworks still follow.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Multi-agent systems** — Several agents with different roles coordinating, e.g. orchestrator plus worker subagents.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **MCP (Model Context Protocol)** — Open standard for plugging tools and data sources into any AI app. Think "USB-C for AI".
  - Reference: [Official MCP site and docs](https://modelcontextprotocol.io/)
  - Video: [Building Agents with MCP, full workshop (Mahesh Murag, Anthropic, 1 h 44 m; AI Engineer page)](https://ai.engineer/talks/building-agents-with-mcp)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **A2A (Agent-to-Agent protocol)** — Standard for agents from different vendors to talk to and delegate to each other.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Agent Skills** — Packaged folders of instructions and scripts an agent loads on demand for a specific task.
  - Reference: [Agent Skills overview (Anthropic docs)](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
  - Reference: [Skill authoring best practices (Anthropic docs)](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices)
  - Reference: [Using Skills with the API (Anthropic docs)](https://platform.claude.com/docs/en/build-with-claude/skills-guide)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Agent memory** — Short-term (context) vs long-term (stored, retrieved) memory so agents remember across sessions.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Computer use & browser agents** — Agents that see a screen and click and type like a human.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Coding agents** — Claude Code, Codex, Cursor and friends: agents that read, edit and run code in your repo.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Vibe coding** — Building software mostly by describing it to an AI and steering, rather than writing code by hand.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Agentic engineering** **NEW in source tracker** — Karpathy’s name for the grown-up version of vibe coding: you orchestrate coding agents under specs, tests and review instead of writing most of the code yourself.
  - Video: [Simon Willison on Lenny’s Podcast (1h40, covers his agentic engineering patterns)](https://lennysnewsletter.com/p/an-ai-state-of-the-union)
  - Reference: [Agentic engineering guide](https://www.morphllm.com/agentic-engineering)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Spec-driven development** **NEW in source tracker** — Write a structured spec first and let agents build against it, so the spec rather than the chat history is the source of truth. Tools: GitHub Spec Kit, Amazon Kiro.
  - Reference: [From vibe coding to spec-driven development](https://towardsdatascience.com/from-vibe-coding-to-spec-driven-development/)
  - Reference: [From vibes to specs](https://www.itential.com/resource/blog/vibes-to-specs-development/)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Human-in-the-loop** — Approval checkpoints where an agent pauses for a person before risky actions.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Long-horizon / background agents** — Agents that run for hours on their own, often on a schedule or in the cloud.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Harness engineering** **NEW in source tracker** — Agent = model + harness: everything around the model (tools, memory, sandbox, guardrails, feedback loops). Named in early 2026; who coined it is disputed, but the claim is that the harness often matters more than the model.
  - Video: [What is an Agentic Harness? (Google Cloud Tech)](https://www.youtube.com/watch?v=W9BX0jyzd2k)
  - Video: [AI Harness Engineering Explained in 27 Minutes](https://www.youtube.com/watch?v=rEeBqCJyvEE)
  - Video: [Ryan Lopopolo: Harness Engineering, when humans steer and agents execute](https://www.youtube.com/watch?v=c8bE0cj7vHY)
  - Reference: [Agent harness engineering (O’Reilly Radar)](https://www.oreilly.com/radar/agent-harness-engineering/)
  - Reference: [Harness engineering for coding agent users (Böckeler)](https://martinfowler.com/articles/harness-engineering.html)
  - Reference: [State of AI Harness Engineering 2026 (reading list)](https://marmelab.com/blog/2026/09/24/the-state-of-ai-harness-engineering-2026.html)
  - Reference: [Harness engineering with Codex (OpenAI, Feb 2026)](https://openai.com/index/harness-engineering/)
  - Reference: [Improving deep agents with harness engineering (LangChain)](https://www.langchain.com/blog/improving-deep-agents-with-harness-engineering)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Proactive & personal agents** **NEW in source tracker** — Agents that act without being asked: they watch your apps, send a morning brief and keep working in their own cloud VM. Meta Muse (Sep 8), OpenAI Dots (Sep 29), Claude Duet (Oct 21, research preview), plus xAI’s Grok Bot. Duet asks approval before sending, paying, signing or deleting.
  - Reference: [Claude Duet vs Muse vs Dots (Engadget)](https://www.engadget.com/2293646/claude-duet-is-anthropics-answer-to-meta-muse-and-openai-dots/)
  - Reference: [9to5Google (includes video)](https://9to5google.com/2026/10/21/claude-duet-anthropic-ai-agent-waitlist/)
  - Reference: [Anthropic’s Claude Duet page](https://claude.com/resources/articles/claude-duet)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **AGENTS.md** **NEW in source tracker** — A plain markdown file in your repo telling coding agents how to build, test and behave. Now stewarded by the Agentic AI Foundation under the Linux Foundation.
  - Reference: [agents.md](https://agents.md/)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **AI coworkers (persistent work agents)** **NEW in source tracker** — Always-on agents with their own identity (email, calendar, directory entry) that take objectives instead of step-by-step instructions, spin up temporary subagents and can run for hours or days. Google’s Gemini agent, announced Oct 8 in early access, can route work between Gemini and Claude models.
  - Reference: [Google Cloud announces the Gemini agent (9to5Google)](https://9to5google.com/2026/10/08/gemini-agent-google-cloud/)
  - Reference: [Gemini agent adds Claude models and AI coworkers](https://techgenyz.com/google-gemini-agent-enterprise-ai/)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Agentic commerce (UCP, ACP, AP2)** **NEW in source tracker** — Agents that find, compare and buy on your behalf, built on a protocol stack: UCP (Google and Shopify) for discovery through checkout, ACP (OpenAI and Stripe) for checkout inside a chat, AP2 (Google-initiated) for signed proof that a human approved the spend, and x402 for stablecoin payments over HTTP.
  - Reference: [AP2, x402, ACP and UCP explained](https://dev.to/brudy_dev24/agentic-commerce-protocols-explained-ap2-x402-acp-and-ucp-1hbb)
  - Reference: [ACP, AP2 and the payment-rail race](https://www.honeyb.ai/blog/agentic-commerce-protocols)
  - Notes: _Add your explanation, example, implementation notes or open questions._

### 4. Models & reasoning

What's changing in the models themselves and why new releases matter.

- [ ] **Reasoning models & test-time compute** — Models that "think" longer before answering, trading compute for accuracy.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Chain-of-thought** — Having the model write out intermediate steps; the seed of today's reasoning models.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Mixture of Experts (MoE)** — Huge models where only a few "expert" sub-networks activate per token. Cheaper to run.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Small language models (SLMs)** — Compact models (Phi, Gemma, small Qwen/Llama) that run cheaply or on-device.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Open-weight models** — Models you can download and host: Llama, Qwen, DeepSeek, Mistral, Gemma, gpt-oss.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Multimodal models** — Models that take and produce images, audio and video as well as text.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Distillation** — Training a small model to imitate a big one.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Quantization** — Shrinking weights to 8/4-bit so models fit on smaller hardware.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Synthetic data** — Training data generated by models, now a major ingredient in training.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Scaling laws** — The empirical rule that more data, parameters and compute predictably improve models.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Task time horizon (METR)** **NEW in source tracker** — METR’s yardstick for agents: the length of task, measured in human working time, that a model completes at 50% reliability. They found it doubling roughly every 7 months; the 80% reliability horizon is much shorter.
  - Reference: [METR: Measuring AI ability to complete long tasks](https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/)
  - Reference: [Toby Ord: Is there a half-life for AI agent success rates?](https://tobyord.com/writing/half-life)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **World models** — Models that learn how environments behave, used for video generation and robotics.
  - Notes: _Add your explanation, example, implementation notes or open questions._

### 5. Training & customization

How teams adapt models to their own domain.

- [ ] **Fine-tuning** — Further training a base model on your own examples.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **LoRA / QLoRA / PEFT** — Fine-tuning a tiny set of extra weights instead of the whole model. Cheap and popular.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **RLHF** — Reinforcement learning from human feedback: how assistants learn preferred behaviour.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **DPO** — Direct Preference Optimization: a simpler alternative to RLHF using preference pairs.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **RLVR & RL environments** — RL with automatically checkable rewards (tests pass, math is right). Key to reasoning models.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Constitutional AI** — Training a model against a written set of principles, with AI feedback.
  - Notes: _Add your explanation, example, implementation notes or open questions._

### 6. Production & LLMOps

Closest to your day job: making LLM systems reliable, observable and cheap.

- [ ] **Evals** — Test suites for LLM behaviour. The thing that separates demos from products.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **LLM-as-a-judge** — Using a model to grade another model's outputs at scale.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Tracing & observability** — Logging every prompt, tool call and token: LangSmith, Langfuse, Arize, OpenTelemetry.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Guardrails** — Input and output checks that block unsafe, off-topic or malformed responses.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Prompt injection** — Malicious text in data that hijacks the model. The #1 security risk for agents.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Lethal trifecta** **NEW in source tracker** — Simon Willison’s name for the risky agent combination: access to private data, exposure to untrusted content, and a way to communicate externally. With all three, one prompt injection can leak your data; the safe design removes a leg.
  - Reference: [The lethal trifecta for AI agents (original post)](https://simonwillison.net/2025/Jun/16/the-lethal-trifecta/)
  - Reference: [His annotated talk at the Bay Area AI Security Meetup](https://simonwillison.net/2025/Aug/9/bay-area-ai/)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Agent identity (non-human identity)** **NEW in source tracker** — Treating each agent as its own identity: named, authenticated, least-privilege, monitored, revocable and tied to a human owner. Fast becoming a core piece of agent security and governance.
  - Reference: [What kind of identity should your AI agent have?](https://aembit.io/blog/what-kind-of-identity-should-your-ai-agent-have/)
  - Reference: [Microsoft: What are non-human identities?](https://www.microsoft.com/en-us/security/business/security-101/what-are-non-human-identities)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Inference serving** — vLLM, TGI, SGLang; KV cache, batching and speculative decoding for speed.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Model routing & AI gateways** — Sending each request to the cheapest model that can handle it, behind one API.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Token economics** — Cost per million tokens, input vs output pricing, and latency budgets.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **On-device / edge AI** — Running models locally on phones and laptops for privacy and speed.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Rogue agents & agent permissions** **NEW in source tracker** — In 2026 several countries, most recently India (CERT-In, Oct 16), reported test agents reaching live systems and reading data they shouldn’t. The cause was basic: exposed credentials and over-broad access. Least privilege and logging are the fix.
  - Reference: [India reports rogue AI agent activity (TechCrunch)](https://techcrunch.com/2026/10/16/india-becomes-the-latest-country-to-report-rogue-ai-agent-activity/)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **WebAI (Opera)** **NEW in source tracker** — Opera’s proposed web standard, announced Oct 27, for running open-weight models like Gemma locally in the browser. Brand new, so treat it as an announcement, not an established standard.
  - Reference: [AI news roundup, Oct 26–30 (Newegg)](https://www.newegg.com/insider/ai-news-this-week-october-26-30-2026)
  - Notes: _Add your explanation, example, implementation notes or open questions._

### 7. Safety & the big picture

The debates and terms you'll hear in news and podcasts.

- [ ] **Alignment** — Making AI systems pursue what their builders actually intend.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Mechanistic interpretability** — Reverse-engineering what's happening inside a neural network.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Red teaming** — Deliberately attacking a model to find failures before release.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Jailbreaks** — Prompts that trick a model into ignoring its safety training.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Sycophancy** — Models telling users what they want to hear instead of what's true.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **AGI / ASI** — Artificial general / superintelligence: what labs say they're aiming for, and the arguments over timelines.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Recursive self-improvement** **NEW in source tracker** — AI systems doing a growing share of the work of building their own successors. Labs say AI is already speeding up AI development, but fully autonomous self-improvement hasn’t happened, and some experts argue it mostly compresses timelines within existing limits.
  - Reference: [Anthropic: When AI builds itself](https://www.anthropic.com/institute/recursive-self-improvement)
  - Reference: [CACM: Is recursive self-improvement really here? (skeptical view)](https://cacm.acm.org/news/is-recursive-self-improvement-really-here/)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Frontier labs landscape** — Who's who: Anthropic, OpenAI, Google DeepMind, Meta, xAI, DeepSeek, Mistral, Qwen.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **AI regulation** — EU AI Act, US policy and export controls, India's AI governance push. The EU’s Digital Omnibus (in force 27 Jul 2026) pushed stand-alone high-risk obligations to 2 Dec 2027; bans and general-purpose model rules were not delayed.
  - Reference: [EU AI Omnibus enters into force (White & Case)](https://www.whitecase.com/insight-alert/eu-ai-omnibus-enters-force-amending-ai-act)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Sovereign AI** — Countries building their own models and compute, e.g. the IndiaAI Mission.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **GEO (AI search optimization)** **NEW in source tracker** — Writing content so AI answers quote it, not just so search ranks it. On Oct 15 Google said it will show source links higher in AI Overviews and AI Mode; Pew found people click far less when an AI summary appears.
  - Reference: [Google pushes links higher in AI answers (PPC Land)](https://ppc.land/google-pushes-links-higher-in-ai-answers-as-preferred-sources-use-rises-7x/)
  - Reference: [Clicks drop when an AI summary appears (Pew)](https://www.pewresearch.org/short-reads/2025/07/22/google-users-are-less-likely-to-click-on-links-when-an-ai-summary-appears-in-the-results/)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Neoclouds & the AI-bubble debate** **NEW in source tracker** — Neoclouds are GPU-rental cloud providers. Nvidia financing its own customers faces a test as credit tightens (CNBC, Oct 24), which feeds the argument over whether AI spending is a bubble.
  - Reference: [Nvidia’s role as AI financier faces first big test (CNBC)](https://www.cnbc.com/2026/10/24/nvidias-role-as-ai-financier-faces-first-big-test-as-neoclouds-take-market-hit.html)
  - Reference: [AI bubble (Wikipedia)](https://en.wikipedia.org/wiki/AI_bubble)
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **SaaSpocalypse** **NEW in source tracker** — 2026 shorthand for the software-stock sell-off and the doubts it raised about per-seat SaaS licences. Opinionated source, so treat the causes as contested.
  - Reference: [When Software Gets Cheap: 2026’s Tech Sell-Off (Cirrus)](https://cirrusdesignstudio.co.uk/when-software-gets-cheap-what-2026s-tech-sell-off-means-for-business-systems/)
  - Notes: _Add your explanation, example, implementation notes or open questions._

### 8. Tools to try

Hands-on tools. Tick one off once you've actually used it, not just read about it. Start with Ollama, Langfuse and a coding agent.

- [ ] **Claude Code / Codex / Gemini CLI** — Coding agents that work in your terminal and repo.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Cursor / Windsurf** — VS Code-style editors with AI built in.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **GitHub Copilot** — AI pair programmer; still the default in most companies.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **CrewAI** — Role-based multi-agent setups, quick to prototype.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Microsoft Agent Framework** — AutoGen and Semantic Kernel merged into one agent framework.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Lab agent SDKs** — OpenAI Agents SDK, Claude Agent SDK and Google ADK: each lab's own toolkit for building agents.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Pydantic AI** — Type-safe agents built on Pydantic models.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **DSPy** — Write LLM programs and let it optimize the prompts for you.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Ollama** — One command to run Llama, Qwen, Gemma or DeepSeek on your laptop.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **LM Studio** — Run local models through a GUI.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **vLLM** — The standard engine for serving open models in production.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **pgvector** — Vector search inside Postgres; often all a RAG app needs.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Qdrant / Pinecone / Weaviate / Chroma** — Dedicated vector databases.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Unstructured / Docling / LlamaParse** — Turn messy PDFs and documents into clean text for RAG.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Firecrawl** — Turns websites into LLM-ready markdown.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **LangSmith / Langfuse / Arize Phoenix** — Trace every LLM call and tool call. Langfuse is open source.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Braintrust / Promptfoo / DeepEval** — Run eval suites like unit tests.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **OpenRouter** — One API key for hundreds of models; handy for comparing them.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **LiteLLM** — Gateway that puts every provider behind an OpenAI-style API, with routing and cost tracking.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Hugging Face** — The hub for open models, datasets and demos.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **n8n** — Open-source workflow automation with AI nodes.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Dify / Flowise** — Visual builders for LLM apps.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **NotebookLM** — Upload papers and chat with them, or get a podcast-style summary.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **Perplexity** — AI search with citations.
  - Notes: _Add your explanation, example, implementation notes or open questions._
- [ ] **v0 / Lovable / Bolt** — Describe an app and get working UI code.
  - Notes: _Add your explanation, example, implementation notes or open questions._

---

## Additional concepts to add to your radar

These entries are additions to the original tracker, not claims that the original definitions were wrong. They fill practical gaps that become important when moving from demos to reliable AI-backed software.

### Building with LLMs

- [ ] **Agent vs. workflow** <sub>ADDED · P1/P2 depending on your work</sub> — A workflow follows a mostly predefined sequence; an agent chooses actions dynamically at runtime. Prefer workflows when the path is known, and agents when decisions genuinely depend on intermediate results.
  - Reference: [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)
  - Reference: [Google Cloud: Production-ready AI agents](https://cloud.google.com/blog/products/ai-machine-learning/a-devs-guide-to-production-ready-ai-agents/)
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Query rewriting & decomposition** <sub>ADDED · P1/P2 depending on your work</sub> — Transforming a user's question into better retrieval queries, or splitting a complex question into smaller sub-questions before retrieval.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Hybrid search** <sub>ADDED · P1/P2 depending on your work</sub> — Combining lexical retrieval (such as BM25) with vector similarity. It often performs better than either approach alone, especially for exact names, IDs and domain terminology.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Reranking** <sub>ADDED · P1/P2 depending on your work</sub> — A second-stage model reorders retrieved candidates by relevance to the query. It can improve RAG quality, at the cost of extra latency and compute.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Parent-child retrieval** <sub>ADDED · P1/P2 depending on your work</sub> — Index small chunks for precise matching, then return a larger parent section for sufficient context.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Agentic RAG** <sub>ADDED · P1/P2 depending on your work</sub> — An agent decides whether to retrieve, which sources or tools to query, and whether another retrieval pass is needed. More flexible, but harder to evaluate and control.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Semantic caching** <sub>ADDED · P1/P2 depending on your work</sub> — Reuse a prior answer or computation for a semantically similar request, rather than requiring an exact text match. Requires careful freshness and correctness rules.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **MCP host, client & server** <sub>ADDED · P1/P2 depending on your work</sub> — The host is the AI application; its MCP client manages a connection; the MCP server exposes tools, resources and prompts. These roles matter when designing integrations.
  - Reference: [Official MCP documentation](https://modelcontextprotocol.io/)
  - Reference: [MCP Python SDK: first steps](https://py.sdk.modelcontextprotocol.io/get-started/first-steps/)
  - Notes: _Add a concrete example and trade-offs._

### Agents

- [ ] **Planning vs. execution** <sub>ADDED · P1/P2 depending on your work</sub> — Separate deciding what should happen from carrying out actions. Plans should be inspectable, bounded, revisable and checked against actual tool results.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Durable execution & resumable workflows** <sub>ADDED · P1/P2 depending on your work</sub> — Persist workflow state so long-running tasks can recover after process crashes, retries or deployments without repeating unsafe side effects.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Agent orchestration** <sub>ADDED · P1/P2 depending on your work</sub> — The control plane that schedules steps, routes tasks, manages state, handles retries and coordinates agents or tools.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Delegation & subagent boundaries** <sub>ADDED · P1/P2 depending on your work</sub> — Assigning a bounded task to another agent or worker, with explicit inputs, outputs, permissions and resource limits.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Tool contracts & schema design** <sub>ADDED · P1/P2 depending on your work</sub> — Treat tools as APIs: precise names, descriptions, typed arguments, validation, clear errors, idempotency and bounded side effects.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Agent sandboxing** <sub>ADDED · P1/P2 depending on your work</sub> — Run untrusted code or tool actions in isolated environments with restricted filesystem, network, credentials, CPU and memory access.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Checkpointing & state persistence** <sub>ADDED · P1/P2 depending on your work</sub> — Save meaningful progress and execution state so an agent can resume, recover, or request human approval without losing its work.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Agent trajectory** <sub>ADDED · P1/P2 depending on your work</sub> — The complete sequence of model decisions, tool calls, observations and state changes during a task. Useful for debugging and evaluation.
  - Notes: _Add a concrete example and trade-offs._

### Models & reasoning

- [ ] **Vision-language models (VLMs)** <sub>ADDED · P1/P2 depending on your work</sub> — Models that jointly process visual inputs and language, enabling image understanding, document interpretation and visual question answering.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Diffusion models** <sub>ADDED · P1/P2 depending on your work</sub> — Generative models that learn to produce data by progressively denoising noise. Widely used in image, audio and video generation.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Flow matching** <sub>ADDED · P1/P2 depending on your work</sub> — A generative modelling approach that learns a continuous transformation from a simple noise distribution to data; used in some modern image and video generation systems.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Speech-to-speech / real-time voice models** <sub>ADDED · P1/P2 depending on your work</sub> — Models or systems that process audio and generate audio directly, often preserving conversational timing and expressive cues rather than using a separate text-only pipeline.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Inference-time scaling** <sub>ADDED · P1/P2 depending on your work</sub> — Spending additional compute at inference—through more reasoning, sampling, search or verification—to improve performance on difficult tasks.
  - Notes: _Add a concrete example and trade-offs._

### Training & customization

- [ ] **Supervised fine-tuning (SFT)** <sub>ADDED · P1/P2 depending on your work</sub> — Training a pretrained model on curated input-output examples to teach desired formats, tasks or behaviours.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **PPO (Proximal Policy Optimization)** <sub>ADDED · P1/P2 depending on your work</sub> — A policy-gradient reinforcement-learning algorithm historically used in RLHF pipelines to update a model while constraining large policy changes.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **GRPO (Group Relative Policy Optimization)** <sub>ADDED · P1/P2 depending on your work</sub> — A reinforcement-learning method that compares multiple sampled outputs for a prompt and uses relative rewards, often without a separate critic model.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Reward models** <sub>ADDED · P1/P2 depending on your work</sub> — Models trained to score or rank outputs according to preferences or task quality; their scores can guide preference optimization or reinforcement learning.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Reward hacking / specification gaming** <sub>ADDED · P1/P2 depending on your work</sub> — When a model or agent exploits flaws in a reward or metric instead of achieving the intended goal. A high score does not necessarily mean the task was done correctly.
  - Notes: _Add a concrete example and trade-offs._

### Production & LLMOps

- [ ] **TTFT (time to first token)** <sub>ADDED · P1/P2 depending on your work</sub> — Latency from request arrival until the first generated token. Important for perceived responsiveness in interactive applications.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **TPOT (time per output token)** <sub>ADDED · P1/P2 depending on your work</sub> — Average time between generated output tokens after generation begins. Important for streaming throughput and user experience.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Continuous batching** <sub>ADDED · P1/P2 depending on your work</sub> — An inference-serving technique that dynamically adds and removes requests from batches as they progress, improving accelerator utilization.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **KV cache** <sub>ADDED · P1/P2 depending on your work</sub> — Cached attention keys and values from prior tokens, avoiding recomputation during autoregressive generation. Memory use becomes a major serving constraint.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Speculative decoding** <sub>ADDED · P1/P2 depending on your work</sub> — A smaller or faster draft model proposes tokens that a larger model verifies, potentially increasing generation speed without changing the target model's output distribution.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Prefix / KV-cache caching** <sub>ADDED · P1/P2 depending on your work</sub> — Reusing cached computation for repeated prompt prefixes. Related to prompt caching, but the implementation and cache scope depend on the inference stack.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Model fallback & resilience** <sub>ADDED · P1/P2 depending on your work</sub> — Fallback policies for provider outages, rate limits or model failures, with explicit quality, privacy, cost and latency trade-offs.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Online evaluations & production feedback** <sub>ADDED · P1/P2 depending on your work</sub> — Evaluate live system behaviour using sampled traffic, user feedback, task outcomes and monitoring—while controlling privacy and avoiding feedback-loop bias.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Trace replay & deterministic test fixtures** <sub>ADDED · P1/P2 depending on your work</sub> — Replay captured requests, tool results and state transitions to reproduce failures and compare changes. Exact determinism may be impossible when model outputs are stochastic or providers change.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Rate limits, quotas & backpressure** <sub>ADDED · P1/P2 depending on your work</sub> — Control request and token throughput across tenants and providers. Queueing, admission control, retries and backpressure prevent overload and noisy-neighbour effects.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Cost per successful task** <sub>ADDED · P1/P2 depending on your work</sub> — Measure total cost across model calls, retries, tools, retrieval and infrastructure, divided by successfully completed tasks—not just cost per model call.
  - Notes: _Add a concrete example and trade-offs._

### Safety & the big picture

- [ ] **Indirect prompt injection** <sub>ADDED · P1/P2 depending on your work</sub> — Malicious instructions embedded in content an agent reads—such as web pages, emails or documents—rather than supplied directly by the user. Tool access makes this especially consequential.
  - Reference: [Anthropic: Mitigating prompt injections in browser use](https://www.anthropic.com/research/prompt-injection-defenses)
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Data exfiltration** <sub>ADDED · P1/P2 depending on your work</sub> — Unauthorized transfer of sensitive data through tool calls, generated content, network requests or connected applications. Treat outbound channels as security boundaries.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Least privilege & scoped credentials** <sub>ADDED · P1/P2 depending on your work</sub> — Give each agent only the minimum permissions, data and credential lifetime required for its task; separate read and write capabilities where possible.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Approval gates for consequential actions** <sub>ADDED · P1/P2 depending on your work</sub> — Require explicit human confirmation before irreversible or high-impact operations such as payments, deletion, external communication or production changes.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Data provenance & lineage for AI** <sub>ADDED · P1/P2 depending on your work</sub> — Track where retrieved or generated information came from, how it was transformed, and which source supported a model response or decision.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Benchmark contamination** <sub>ADDED · P1/P2 depending on your work</sub> — When evaluation questions or answers leak into training data, making benchmark scores look stronger than genuine generalization.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **Model & prompt drift** <sub>ADDED · P1/P2 depending on your work</sub> — Changes in provider models, prompts, retrieval corpora, tools or user traffic can alter system behaviour over time. Versioning and regression evals help detect this.
  - Notes: _Add a concrete example and trade-offs._

### Tools to try

- [ ] **MLflow** <sub>ADDED · P1/P2 depending on your work</sub> — Track experiments, package models and manage evaluation or deployment workflows; it also has LLM/agent-oriented capabilities.
  - Reference: [MLflow documentation](https://mlflow.org/docs/latest/)
  - Notes: _Add a concrete example and trade-offs._
- [ ] **OpenTelemetry** <sub>ADDED · P1/P2 depending on your work</sub> — Vendor-neutral traces, metrics and logs. Useful for connecting LLM calls and tool execution to the rest of a distributed system.
  - Reference: [OpenTelemetry documentation](https://opentelemetry.io/docs/)
  - Notes: _Add a concrete example and trade-offs._
- [ ] **LiteLLM Proxy** <sub>ADDED · P1/P2 depending on your work</sub> — A deployable gateway for routing model requests, managing provider keys, budgets and observability; distinguish it from using the LiteLLM Python library.
  - Notes: _Add a concrete example and trade-offs._
- [ ] **OWASP GenAI Security Project** <sub>ADDED · P1/P2 depending on your work</sub> — Security guidance and risk taxonomies for LLM applications and agentic systems.
  - Reference: [OWASP GenAI Security Project](https://genai.owasp.org/)
  - Notes: _Add a concrete example and trade-offs._

## Practical engineering checklist

Use this checklist when evaluating an LLM or agent feature for production.

- [ ] **Problem fit:** Is an LLM or agent actually needed, or would deterministic code/search/rules be simpler?
- [ ] **System boundary:** Which parts are model-driven and which remain deterministic?
- [ ] **Data:** Are sources current, permissioned, traceable and suitable for model use?
- [ ] **Retrieval:** Have chunking, hybrid search, reranking and retrieval quality been measured?
- [ ] **Tools:** Are tool schemas narrow, validated, documented and safe to retry?
- [ ] **State:** Can the system resume after timeouts, restarts and partial failures?
- [ ] **Security:** Are credentials scoped, untrusted content isolated, and outbound actions controlled?
- [ ] **Evaluation:** Is there a representative test set with task-level success criteria and regression tests?
- [ ] **Observability:** Can you inspect prompts, model versions, retrieval results, tool calls, latency and failures?
- [ ] **Economics:** Do you know cost per successful task, not just token price?
- [ ] **Fallbacks:** What happens on provider outage, rate limiting, malformed output or tool failure?
- [ ] **Human control:** Which actions require review or explicit approval?

## Metrics worth knowing

| Metric | What it tells you |
|---|---|
| Task success rate | Whether the end-to-end job was actually completed correctly |
| Groundedness / citation accuracy | Whether claims are supported by retrieved sources |
| Tool-call success rate | Whether integrations are invoked correctly and reliably |
| TTFT | Time until the first generated token |
| TPOT | Time between generated output tokens |
| p50 / p95 / p99 latency | Typical and tail response times |
| Tokens per task | Prompt and completion consumption for a complete task |
| Cost per successful task | Total model and tool cost divided by successful outcomes |
| Retry / fallback rate | How often the system needs recovery paths |
| Human-escalation rate | How often the system cannot safely complete without a person |

## Recommended reading shelf

- [Anthropic — Effective context engineering for AI agents](https://www.anthropic.com/research/effective-context-engineering-for-ai-agents) — Context management, context rot and agent design.
- [Anthropic — Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) — A practical distinction between workflows and agents, plus common orchestration patterns.
- [Google Cloud — A developer's guide to production-ready AI agents](https://cloud.google.com/blog/products/ai-machine-learning/a-devs-guide-to-production-ready-ai-agents/) — Production concerns: evaluation, state, security and operations.
- [MCP — Official specification and documentation](https://modelcontextprotocol.io/) — Protocol concepts, transports, authorization and server/client responsibilities.
- [NIST — AI Agent Standards Initiative](https://www.nist.gov/news-events/news/2026/02/announcing-ai-agent-standards-initiative-interoperable-and-secure) — Interoperability and security standardization context.
- [UK AI Security Institute — Engineering Playbook](https://engineering-playbook.aisi.org.uk/) — Evaluation infrastructure, sandboxing, provider proxies and scalable research systems.
- [Princeton — Emerging Trends in AI Agent Evaluation](https://sage.cs.princeton.edu/trends/) — Research-oriented map of how agent evaluation is evolving.
- [AWS — Agentic AI Lens](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentic-ai-lens.html) — Architecture and operational considerations for production agentic systems.

## Glossary maintenance log

| Date | Change | Source / rationale |
|---|---|---|
| 31 Oct 2026 | Converted the HTML tracker into an editable Markdown roadmap; retained original sections and added practical engineering concepts. | Original uploaded tracker plus the reference shelf above. |

## Open questions / topics to investigate

- [ ] Which agent workloads genuinely benefit from autonomy rather than a deterministic workflow?
- [ ] What is the smallest useful evaluation suite for an agent that can call production tools?
- [ ] How should multi-tenant AI workloads enforce per-tenant quotas, isolation and cost attribution?
- [ ] When is a vector database justified over Postgres + pgvector or lexical search?
- [ ] What is the right boundary between model context, external memory and a conventional database?

## Notes

_Use this space for your own mental models, architecture sketches, links, interview explanations and lessons learned._