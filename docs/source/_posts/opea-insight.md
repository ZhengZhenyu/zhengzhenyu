---
title: opea-insight
date: 2024-11-02 09:35:40
tags:
---

Open Platform for Enterprise AI (OPEA)是一个由Intel发起并捐赠至 Linux Foundation AI & Data 基金会的开放生态系统编排框架，旨在集成高效的生成式人工智能（GenAI）技术和工作流程，帮助企业更快地采用人工智能并实现业务价值。

<img src=https://opea.dev/wp-content/uploads/sites/9/2024/04/opea-horizontal-color.svg style="zoom:50%;" />

根据OPEA负责人，Intel开源生态负责人Arun Gupta描述，OPEA的出现主要是为了简化目前GenAI领域的复杂的技术栈和多种多样的软件选择，为开发者和用户提供多个领域GenAI应用的端到端解决方案，让用户和开发者可以用一条简单的命令就能在多平台上快速运行GenAI应用。

## OPEA Overview

根据官方说明，OPEA包含以下几个主要功能：

- 覆盖大语言模型（LLMs）、数据存储和提示引擎在内的最先进生成式人工智能(GenAI)系统的可组合构建模块的参考框架和软件组合。

- 端到端可复现的检索增强型生成式人工智能(RAG)组件堆栈结构和工作流程的架构蓝图。

- 多个`Micro-Service`和`Mega-Service`帮助用户快速构建和部署生成式AI应用。

- 四步评估工具，可用于对生成式人工智能系统在性能、功能、可信度和企业级应用就绪度方面进行评分。

#### Microservice:

OPEA的最小组成单元是微服务(Microservice),每一个微服务承担一个独立的功能，通过模块化的微服务组件，可以为用户和开发者提供更灵活、易扩展的功能选择，同时也能更容易的按需组成自己所需的AI应用。如`vllm-endpoint`, `start-microservice-with-python`, `feedback-with-mongodb`等，具体可参考[GenAI Compomnents](https://opea-project.github.io/latest/microservices/index.html#genaicomps)

#### Megaservice

Megaserice对外提供完整和独立的功能，通常包含一个或多个Microservice并对它们进行调度和管理。Megaservice通常包含较为复杂的业务逻辑和工作流，通过协调各Microservice的相互协调来完成特定的应用诉求。在保证了功能的完整性的前提下，仍保留了一定的可扩展性和灵活性。如`ChatQnA`, `CodeGen`, `FaqGen`等，具体可参考[GenAI Examples](https://opea-project.github.io/latest/examples/index.html#genaiexamples)

### Gateways

Gateway作为用户访问Megaservice的接口，根据用户需求提供定制化的访问。它作为传入请求的入口点，将它们路由到巨服务架构中的适当微服务。Gateway支持API定义、API版本控制、速率限制和请求转换等能力，允许对用户与底层微服务的交互进行细粒度控制

