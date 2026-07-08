# Hi 👋 — welcome to my workshop

I'm a platform product manager with 23+ years spent at the seam where deep technology meets real-world use — distributed systems, data infrastructure, AI platforms, and applied cryptography. Along the way I've built and shipped products across cloud infrastructure, developer platforms, privacy and cryptography, and verifiable AI & financial systems.

This repo is a map of the things I build to think — open-source projects, prototypes, and demos. Most of it is me chasing a question end to end: *what does it actually take to make this work?* Browse by theme below, or jump straight to whatever caught your eye.

> Most of this is public and meant to be runnable. That said, some pieces — especially the older ones — may have gone stale or stopped working as dependencies, platforms, and networks moved on. **[Browse all repositories →](https://github.com/abhinavg6?tab=repositories)**

---

## 🧩 Flagship — infrastructure for agent swarms

**[yutha](https://github.com/abhinavg6/yutha)**
A framework-agnostic control plane for groups of AI agents — giving agents from any framework (LangGraph, CrewAI, …) shared identity, attenuated capabilities, signed receipts, declarative constitutions, and an optional on-chain verification layer. Multi-agent systems work in demos and break in production; Yutha is the missing substrate. Docs at [yutha.ai](https://yutha.ai).

---

## 🔐 Confidential finance & payments

Prototypes exploring how cryptography (Seal MPC, Confidential Transfers) and controlled execution let money and markets move on public chains without leaking amounts — and let autonomous agents transact without a trusted middleman.

**[seal-agentic-finance](https://github.com/abhinavg6/seal-agentic-finance)**
Agentic finance on Sui + Seal MPC: AI agents compete with sealed, deposit-backed bids that stay hidden until a deadline, reveal on-chain all at once, and bind the winner to their terms. One auction engine, two markets — best-execution RFQ and lending.

**[seal-programmable-wallet](https://github.com/abhinavg6/seal-programmable-wallet)**
Seal MPC as the authorization layer for agentic commerce: users grant agents scoped, programmable spending mandates, and an MPC committee — not the agent — decides whether each payment is allowed. A compromised agent can't lift its own limits.

**[confidential-autonomous-treasury](https://github.com/abhinavg6/confidential-autonomous-treasury)**
"Helm" — an AI agent runs a company's stablecoin treasury on Sui: sweeping idle funds, allocating across vetted venues, replenishing a buffer, and paying vendors under hard limits it can't break. Every action is authorized outside the agent by Seal MPC + on-chain policy, balances and amounts stay encrypted via Confidential Transfers, and a risk committee gets read-only oversight.

**[confidential-payroll-sui](https://github.com/abhinavg6/confidential-payroll-sui)**
"Stipend" — confidential payroll on Sui. Salaries are encrypted on-chain, each employee sees only their own pay, a finance lead can audit read-only, and employees can prove their income to a lender without revealing any key. Built on Confidential Transfers.

**[confidential-b2b-settlement](https://github.com/abhinavg6/confidential-b2b-settlement)**
"Tessera" — a permissioned consortium settling invoices in a confidential stablecoin, with KYC-gated membership, payment channels, disputes, and regulator oversight turned into scoped, time-boxed, revocable Seal MPC mandates instead of one permanent skeleton key.

**[treasury-rfq-demo](https://github.com/abhinavg6/treasury-rfq-demo)**
A clickable prototype of an institutional treasury workflow on Sui Spheres — scoped multi-dealer RFQs, sealed quotes, loser-blindness, settlement that bridges to public Sui, repo lending, and cause-based regulator reveal. Makes the multi-party privacy story tangible end to end.

**[sui-spheres-interbank-settlement](https://github.com/abhinavg6/sui-spheres-interbank-settlement)**
A demo of interbank settlement — within and across countries — built on Sui Spheres.

---

## 🗄️ Sovereign apps — you own the data

**[sui-stack-crm](https://github.com/abhinavg6/sui-stack-crm)**
A small-team, Airtable-like CRM where the team — not a vendor — owns the data. Records are encrypted in the browser with Seal, stored as content-addressed blobs on Walrus, and gated by an on-chain ACL on Sui, so no operator can read them. A concrete take on what a privacy-first SaaS alternative looks like on the Sui stack.

---

## 🔑 Cryptographic operations

**[seal-mpc-ops](https://github.com/abhinavg6/seal-mpc-ops)**
A REPL coordinator for running Seal MPC committees on Sui: it folds the full lifecycle — DKG ceremony, on-chain register/propose, aggregator deployment, and member rotation — into one coordinator-driven tool, with `--json` output so an AI agent can orchestrate committees end to end.

---

## 🤖 AI agents & memory

**[multi-agent-verifiable-research](https://github.com/abhinavg6/multi-agent-verifiable-research)**
A multi-agent research lab that turns a free-text question into a citation-grounded report. A planner, parallel readers, a critic, and a synthesizer collaborate through shared memory — every source is content-addressed on Walrus and every claim is a clickable, verifiable citation.

**[sui-trader-agent](https://github.com/abhinavg6/sui-trader-agent)**
A complete sample agent that uses MemWal for durable memory and Claude for reasoning, scoped to a paper-trading persona. A live inspector shows what the agent stores, retrieves, and how that memory shapes its next move — in real time.

---

## 🛰️ Sui data stack & developer tooling

Tools built on Sui's post-JSON-RPC data stack (gRPC, GraphQL RPC, Archival Service) — several exploring how AI agents can query a chain without a multi-week SDK integration.

**[sui-mcp-server](https://github.com/abhinavg6/sui-mcp-server)**
A local-first MCP server that lets any agent — Claude Desktop, Claude Code, a custom loop — query Sui in plain English across gRPC, GraphQL, and the Archival Service. Handles transport selection, retention boundaries, and LLM-friendly response shaping so the agent just answers the question.

**[sui-data-stack-explorer](https://github.com/abhinavg6/sui-data-stack-explorer)**
An AI-native Sui explorer that routes across all three transports and *shows you why* in a routing-trace panel. A Claude-powered assistant picks the right transport per question, with live checkpoint streaming and object time-travel.

**[sui-explorer-grpc-graphql](https://github.com/abhinavg6/sui-explorer-grpc-graphql)**
A read-only reference-architecture explorer built end to end on the new data stack — a clean starting point showing how each API maps to real explorer features as JSON-RPC sunsets.

---

## ☁️ Cloud data platforms & streaming

Grouped by topic rather than timeline: provisioning and hardening Databricks on AWS/Azure, and hands-on stream processing with Spark, Storm, Kafka, and Flume. Some of these go back a while — I try to keep the list current regardless.

| Project | What it is |
| --- | --- |
| [awsdb-workspace-provisioner](https://github.com/abhinavg6/awsdb-workspace-provisioner) | End-to-end provisioning of an AWS Databricks E2 workspace and its AWS infra in a single pass. |
| [azuredb-workspace-provisioner](https://github.com/abhinavg6/azuredb-workspace-provisioner) | Scripts to provision and bootstrap an Azure Databricks workspace — deploy, users/groups, notebooks, clusters, and jobs. |
| [awsdb-cf-templates-ext](https://github.com/abhinavg6/awsdb-cf-templates-ext) | CloudFormation templates for AWS Databricks E2 workspaces — BYO VPC, cross-account IAM, DBFS S3, and BYOK KMS. |
| [adb-arm-templates-ext](https://github.com/abhinavg6/adb-arm-templates-ext) | ARM templates for Azure Databricks workspace provisioning, including VNet-injection, no-public-IP, and audit-log variants. |
| [db-initscript-migrate](https://github.com/abhinavg6/db-initscript-migrate) | Tooling to migrate legacy Databricks global init scripts from v1 to v2. |
| [msftosvc-databricks](https://github.com/abhinavg6/msftosvc-databricks) | Azure Databricks demo content from a Microsoft Azure Open Source virtual conference session. |
| [spark-flume-stream](https://github.com/abhinavg6/spark-flume-stream) | A Spark Streaming program processing Avro events from a Flume agent into rolling per-key counts. |
| [spark-queue-stream](https://github.com/abhinavg6/spark-queue-stream) | A Spark Streaming example that reads from a queue and counts events per category in a live window. |
| [Kafka-Storm-Conscomp](https://github.com/abhinavg6/Kafka-Storm-Conscomp) | A Kafka producer + Storm topology computing rolling stats over US consumer-complaints data into MongoDB. |
| [Local-Storm-Repository](https://github.com/abhinavg6/Local-Storm-Repository) | A simple Apache Storm topology run locally — early stream-processing experiments. |
