# Prompt Paws: The Cozy 60 FPS AI Agent Bakery Game (RAG, Guardrails, Context Caching & Multi-Agent Orchestration)

![Cozy AI Agent Bakery Banner](assets/cozy_ai_cafe_banner.jpg)

## What I Built

Who said learning **AI System Design** has to be all dark cyberpunk terminal screens and exploding servers?

I built and open-sourced **Prompt Paws: The Cozy AI Agent Cafe & Bakery** (architected with **Google Gemma 4 & Antigravity**) — an interactive **60 FPS AI Agent Architecture Training & Simulation Platform** disguised as a cozy pastel pastry bakery run by **Robot-Cat Chefs**.

**Who would use it?**
- **Engineering Teams, Bootcamps & Developer Relations Programs** training developers on production LLM architecture (where a single uncached system prompt or missing input guardrail can cost thousands of dollars in wasted tokens or security incidents).
- Instead of static slide decks, **Prompt Paws** gives teams an interactive, visual sandbox where every pastry station maps **1-to-1** to a real production AI pattern:

| Cozy Bakery Station | Critter Order Handled | Production AI Engineering Layer |
| --- | --- | --- |
| **Flash Pastry Oven** | Prompt Croissant | **Fast Low-Latency Model (`gemini-2.5-flash` / Gemma 4)** |
| **Context Cache Jar** | Repeat Owl Menu Query | **Prefix & Context Caching (95% Token Savings)** |
| **Guardrail Flour Sieve** | Spicy Injection Jalapeno | **Input Classifier & Prompt-Injection Sanitizer** |
| **Vector Berry Patch** | RAG Berry Tart | **Vector Search & Fact Grounding (Anti-Hallucination)** |
| **Tool-Call Boba Mixer** | Code-Exec Boba Tea | **Deterministic Python Sandbox & Function Calling** |
| **Deep-Think Souffle Oven** | Reasoning Souffle | **Extended Thinking / System-2 Deliberation** |
| **Subagent Sous-Chef Bell** | Parallel Banquet Aura | **Multi-Agent Parallel Delegation (+45% Speed Aura)** |

---

## Live Playable Demo & How to Play in 30 Seconds

- **Play Live in Your Browser (60 FPS HTML5 Canvas):** [https://robinamirbahar.github.io/cozy-ai-agent-cafe-game/](https://robinamirbahar.github.io/cozy-ai-agent-cafe-game/)
- **100% Client-Side Simulation ($0.00 API Cost & Zero Keys Required):** The entire game runs locally inside your browser using a deterministic HTML5 Canvas simulation engine — **no API keys, no sign-ups, and zero paid LLM tokens** are ever used when you or your team play.

![How to Play Prompt Paws in 3 Easy Steps](https://files.catbox.moe/i9wg40.jpg)

### What Is the Core Gameplay Loop?
Think of **Prompt Paws** as a **cozy Tower-Defense & Kitchen-Management game for AI Agent Architecture**:
- **Customer Pastry Orders = Incoming User Prompts** moving along the bakery conveyor belt toward the **Pickup Window**.
- **Robot-Cat Kitchen Stations = Real-World AI Engineering Components** (Fast LLMs, Context Caches, Input Guardrails, RAG Vector DBs, Deterministic Tool Callers, System-2 Reasoning Models, and Multi-Agent Sous-Chefs) that intercept and process prompts before they reach the customer.
- **Win / Lose Condition:** Every order baked by the right AI Chef Station earns **Star Coins**. If an unbaked order, an ungrounded **Hallucination Puff**, or a sneaky **Prompt Injection** slips all the way to the Pickup Window, you lose a **Cafe Reputation Heart**.

### How to Play in 3 Easy Steps:
1. **STEP 1 — Pick an AI Chef Station (Left Menu):** Click a station card on the left sidebar (start with **Flash Pastry Oven** for `60` coins). Check the **Order Forecast chips** under the level story to see which prompt types are coming.
2. **STEP 2 — Click Any `[+ Slot]` Tile on the Map:** Click one of the 8 pastel counter pads (`Slot 1`–`Slot 8`) beside the conveyor belt to place your Robot-Cat Chef. (Tip: Click a placed chef anytime to **Upgrade** its baking speed or **Refund** it.)
3. **STEP 3 — Click `Open Cafe` (or `Auto-Chef Blueprint`):**
   - Click **`Open Cafe`** (or press `Spacebar`) to start the shift and watch your Robot-Cat Chefs bake.
   - **Want to watch an instant demo first?** Click the purple **`Auto-Chef Blueprint`** button in the top bar on any of the **7 Story Shifts** and the game will automatically build the optimal Guardrail, Cache, RAG, and Subagent pipeline and run it for you.

---

## Open-Source Code

- **GitHub Repository:** [https://github.com/RobinaMirbahar/cozy-ai-agent-cafe-game](https://github.com/RobinaMirbahar/cozy-ai-agent-cafe-game)

---

## How I Built It

I built **Prompt Paws** using an open-source, zero-dependency HTML5 Canvas 60 FPS simulation engine (`game.js`), a 7-shift progressive AI engineering curriculum (`levels.js`), and a procedural WebAudio synthesizer (`audio.js`), orchestrated via **Antigravity** and open agentic workflows.

### 1. Order Routing & Guardrail Sanitization (`game.js`)
Each station inspects passing orders on the winding bakery conveyor ribbon and only picks up tasks that match its architectural role. Notice how **Spicy Prompt-Injection Jalapenos** cannot be safely baked by normal ovens until a **Guardrail Flour Sieve** sanitizes them into safe croissants:

```javascript
function canStationProcessOrder(stationType, ord) {
  // 1. Only the Guardrail Flour Sieve can catch and sanitize Spicy Prompt Injections!
  if (stationType === 'guardrail_sieve') {
    return ord.kind === 'jalapeno';
  }
  // Unfiltered prompt injections bypass normal ovens and damage Cafe Reputation Hearts!
  if (ord.kind === 'jalapeno') {
    return false;
  }

  // 2. Context Cache Jar serves repeated menu queries at 3x speed + bonus Star Coins
  if (stationType === 'cookie_cache') {
    return ord.kind === 'cached' || ord.kind === 'croissant';
  }

  // 3. Vector Berry Patch grounds Berry Tarts so they don't become Hallucination Puffs
  if (stationType === 'vector_garden') {
    return ord.kind === 'tart';
  }

  // 4. Tool-Call Boba Mixer runs deterministic calculations & API recipes
  if (stationType === 'tool_blender') {
    return ord.kind === 'boba';
  }

  // 5. Deep-Think Souffle Oven handles multi-step System-2 reasoning
  if (stationType === 'reasoning_oven') {
    return ord.kind === 'souffle' || ord.kind === 'croissant';
  }

  // 6. Flash Pastry Oven handles high-throughput everyday Prompt Croissants
  if (stationType === 'flash_oven') {
    return ord.kind === 'croissant' || ord.kind === 'cached';
  }

  // 7. Subagent Sous-Chef Bell orchestrates parallel helpers
  if (stationType === 'subagent_bell') {
    return ord.kind !== 'jalapeno';
  }
  return false;
}
```

### 2. Real-Time AI Architecture Linter ("Chef Whiskers")
Before you open the cafe doors, **Chef Whiskers (Staff AI Pastry Architect)** performs live static analysis on your placed stations and warns you about architectural vulnerabilities:

```javascript
function evaluateKitchenArchitecture() {
  const lvl = window.CAFE_LEVELS[currentLevelIdx];
  const weights = lvl.orderWeights;
  const typesPlaced = Object.values(placedStations).map((s) => s.type);
  const alerts = [];

  if (weights.jalapeno && !typesPlaced.includes('guardrail_sieve')) {
    alerts.push({
      kind: 'warn',
      text: 'Prompt Injection Risk! Place a Guardrail Flour Sieve near Slot 1 or 2 to neutralize spicy raccoon orders!'
    });
  }
  if (weights.tart && !typesPlaced.includes('vector_garden')) {
    alerts.push({
      kind: 'warn',
      text: 'Hallucination Warning! Berry Tarts need a Vector Berry Patch (RAG) so chefs do not guess facts!'
    });
  }
  if (weights.boba && !typesPlaced.includes('tool_blender')) {
    alerts.push({
      kind: 'warn',
      text: 'Math/API Alert! Add a Tool-Call Boba Mixer to run deterministic calculations accurately.'
    });
  }
  return alerts;
}
```

---

## Why Open-Source Visual Sandboxes Matter

Open-source AI models, open agent harnesses, and inspectable system design sandboxes ensure that **every developer — not just giant enterprises — can master safe, cost-efficient AI engineering**. By making the entire simulation engine, curriculum (`levels.js`), and architecture blueprints open-source with zero proprietary build steps and **$0.00 API token cost**, any educator or developer community can fork **Prompt Paws**, add new open-weight model stations (like local Gemma 4 or Ollama nodes), and teach agentic reliability visually.


---

## 👩‍💻 About the Author

<div align="center">
  <img src="https://raw.githubusercontent.com/RobinaMirbahar/RobinaMirbahar/main/ProfileImages/Hi-Robina.gif" height="75" width="75" alt="Robina Mirbahar" />

  ### **Robina Mirbahar — Google Cloud & AI Architect**

  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=18&pause=1000&color=4285F4&center=true&vCenter=true&width=720&lines=Google+Cloud+%26+Agentic+AI+Solutions+Architect;Author+of+'AI+Engineering'+(2026);Pakistan+Lead+%40+IEEE+AI+Caravan+(94+Countries);Women+Techmakers+Ambassador+%26+Mentor+%40+Google+for+Startups" alt="Robina Mirbahar Dynamic Headline" />

  <p>
    AI Researcher, Cloud Solutions Architect, and Author of <b><i>"AI Engineering: From Classical ML to RAG &amp; Agentic AI Systems"</i> (2026)</b>.<br/>
    Bridging cutting-edge open-weights AI research (Gemma 4, Google ADK, Multi-LoRA, MCP &amp; A2A) with production-grade Cloud Run &amp; Vertex AI engineering.
  </p>

  [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/robinamirbahar)
  [![Amazon Book](https://img.shields.io/badge/Amazon-Book%20(2026)-FF9900?style=for-the-badge&logo=amazon&logoColor=white)](https://amazon.com/dp/B0GWCZWCF4)
  [![Google Developer](https://img.shields.io/badge/Google%20Developer-Profile-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://developers.google.com/profile/u/106918534005910641104)
  [![DEV Community](https://img.shields.io/badge/DEV-Articles-0A0A0A?style=for-the-badge&logo=devdotto&logoColor=white)](https://dev.to/robinamirbahar)
  [![Medium](https://img.shields.io/badge/Medium-Blog-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@romiaiblog)
  [![YouTube](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@robinacodesai)
  [![Twitter/X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://twitter.com/robinamirbahar)
  [![Stack Overflow](https://img.shields.io/badge/Stack%20Overflow-F58025?style=for-the-badge&logo=stackoverflow&logoColor=white)](https://stackoverflow.com/users/21196122/robina-mirbahar)
  [![Credly](https://img.shields.io/badge/Credly-FF6B35?style=for-the-badge&logo=credly&logoColor=white)](https://www.credly.com/users/robinamirbahar)

</div>

### 🚀 Featured Google Cloud & Agentic AI Repositories by Robina Mirbahar

| Repository | Architecture Focus | Live Repo & Dynamic Status |
| :--- | :--- | :--- |
| **[gemma4-multilora-adk-eval](https://github.com/RobinaMirbahar/gemma4-multilora-adk-eval)** | Dynamic Multi-LoRA Hot-Swapping & CI/CD Agent Evaluation (`adk eval`) on Cloud Run GPUs with Gemma 4 & vLLM | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/gemma4-multilora-adk-eval?style=flat-square&color=4285F4) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/gemma4-multilora-adk-eval?style=flat-square) |
| **[slothsre-napops](https://github.com/RobinaMirbahar/slothsre-napops)** | SlothSRE ("NapOps") — Overnight Gemma 4 & Google ADK Incident Digest Agent with OpenTelemetry & Sentry AI Monitoring | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/slothsre-napops?style=flat-square&color=34A853) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/slothsre-napops?style=flat-square) |
| **[streamforge-event-adk](https://github.com/RobinaMirbahar/streamforge-event-adk)** | Real-Time Event-Driven Multi-Agent Pipelines on Google Cloud with ADK (`ParallelAgent` & `LoopAgent`), Eventarc & Pub/Sub | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/streamforge-event-adk?style=flat-square&color=FBBC04) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/streamforge-event-adk?style=flat-square) |
| **[a2a-mcp-mesh-cloudrun](https://github.com/RobinaMirbahar/a2a-mcp-mesh-cloudrun)** | Agent-to-Agent (A2A) & Multi-MCP Mesh on Cloud Run with Gemma 4, Google ADK, Spanner Graph & AlloyDB | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/a2a-mcp-mesh-cloudrun?style=flat-square&color=EA4335) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/a2a-mcp-mesh-cloudrun?style=flat-square) |
| **[cloudguard-gemma-agent](https://github.com/RobinaMirbahar/cloudguard-gemma-agent)** | 6-Part Production Gemma Enterprise Agent Series (ADK, Cloud Run L4 GPU, Firestore, Model Armor, Vertex AI QLoRA) | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/cloudguard-gemma-agent?style=flat-square&color=4285F4) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/cloudguard-gemma-agent?style=flat-square) |
| **[cozy-ai-agent-cafe-game](https://github.com/RobinaMirbahar/cozy-ai-agent-cafe-game)** | Prompt Paws: 60 FPS Cozy AI Agent Bakery Simulation Game teaching RAG, Guardrails, Context Caching & Multi-Agent Loops | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/cozy-ai-agent-cafe-game?style=flat-square&color=7928CA) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/cozy-ai-agent-cafe-game?style=flat-square) |

<div align="center">
  <img src="https://raw.githubusercontent.com/RobinaMirbahar/RobinaMirbahar/main/ProfileImages/GithubBanner.svg" alt="Robina Mirbahar Banner" width="100%" />
</div>

