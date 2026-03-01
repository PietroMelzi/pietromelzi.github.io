---
layout: page
title: Travel Agent
description: A travel assistant that helps with flights, hotels, cost of living, and more
img: assets/img/proj_travel.jpg
redirect:
importance: 0
category: Personal
---

I built a **Travel Assistant** that can answer with real-time **flight and hotel prices** worldwide.  
Unlike standard LLMs, it uses tools to query APIs for up-to-date data, giving precise answers on demand.

Github: [https://github.com/PietroMelzi/travel-agent](https://github.com/PietroMelzi/travel-agent/)

---

## How It Works

The architecture is designed for experimentation. Even though a single agent could handle all tasks, I implemented a **multi-agent setup** where a **manager agent** coordinates several specialized agents acting as tools:

- Flight search agent  
- Hotel search agent  
- Cost-of-living info agent  

This setup showcases the potential of **tool-equipped LLMs** and **multi-agent systems**.

<img src="../../assets/img/example_conv.png" alt="Trabel Agent Screenshot" width="90%">

---

## Technology Stack

- **Backend / Agent System:** Built with the [OpenAI Agents library](https://platform.openai.com/docs/guides/agents), which simplifies:  
  - Assigning tools to agents  
  - Handling agent handoff 

  An alternative could have been an **MCP server** to expose tools to multiple clients, but for simplicity, I assigned tools directly to my agents.

- **Frontend:** Built with **Streamlit** for a quick proof-of-concept and easy deployment on [Streamlit Cloud](https://streamlit.io/cloud).  
  This avoided the complexity of building a custom frontend at this stage.

---

## Why This Project Matters

This project is not just about a travel assistant.  
It’s a practical exploration of:

- **Tool-equipped LLMs** for real-time data  
- **Multi-agent orchestration**  
- Rapid prototyping and deployment  

It demonstrates how LLMs can act as orchestrators of specialized services, rather than just static answer engines.