<div align="center">

```
██╗   ██╗ █████╗ ███╗   ███╗███████╗██╗  ██╗██╗
██║   ██║██╔══██╗████╗ ████║██╔════╝██║  ██║██║
██║   ██║███████║██╔████╔██║███████╗███████║██║
╚██╗ ██╔╝██╔══██║██║╚██╔╝██║╚════██║██╔══██║██║
 ╚████╔╝ ██║  ██║██║ ╚═╝ ██║███████║██║  ██║██║
  ╚═══╝  ╚═╝  ╚═╝╚═╝     ╚═╝╚══════╝╚═╝  ╚═╝╚═╝

██████╗  █████╗  ██████╗██╗  ██╗██╗   ██╗
██╔══██╗██╔══██╗██╔════╝██║  ██║██║   ██║
██████╔╝███████║██║     ███████║██║   ██║
██╔══██╗██╔══██║██║     ██╔══██║██║   ██║
██████╔╝██║  ██║╚██████╗██║  ██║╚██████╔╝
╚═════╝ ╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝ ╚═════╝
```

<a href="https://github.com/Vamshi9415">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3000&pause=1000&color=00FF41&background=0D111700&center=true&vCenter=true&width=720&height=40&lines=%24+python+-m+vamshi_bachu+--role+ai_engineer;retrieval+%E2%86%92+reasoning+%E2%86%92+action;RAG+%C2%B7+Agents+%C2%B7+MCP+%C2%B7+Guardrails;Making+LLM+systems+useful+beyond+the+demo" alt="typing intro" />
</a>

</div>

---

```bash
vamshi@ai-lab:~$ cat profile.py
```

```python
from dataclasses import dataclass, field

@dataclass
class AIEngineer:
    name: str = "Vamshi Bachu"
    roles: tuple = ("AI Engineer", "Backend Developer")
    languages: list = field(default_factory=lambda: ["Python", "Java", "SQL"])
    builds: list = field(default_factory=lambda: [
        "RAG pipelines", "agentic workflows", "MCP servers", "production backends",
    ])
    principles: list = field(default_factory=lambda: [
        "ship beyond the demo",
        "guardrails by default",
        "retrieval quality before model size",
        "if you can't explain it, you don't own it",
    ])

    def run(self):
        while True:
            self.learn(); self.build(); self.ship()

if __name__ == "__main__":
    AIEngineer().run()
```

---

```bash
vamshi@ai-lab:~$ ls -la ~/projects
```

| 📁 repo | description | stack |
|:--|:--|:--|
| [`docrag-mcp`](https://github.com/Vamshi9415/docrag-mcp) | Document retrieval server over MCP with embeddings, FAISS and reranking | `RAG` `MCP` `FAISS` |
| [`guarded-ai-agent-mcp`](https://github.com/Vamshi9415/guarded-ai-agent-mcp) | Tool-using agent with policy checks, guardrails and human approval flows | `Agents` `MCP` `Guardrails` |
| [`Ad-Forge`](https://github.com/Vamshi9415/Ad-Forge) | Generative ad pipeline: briefs → storyboards → media assets | `GenAI` `Pipelines` |
| [`EnseSmells`](https://github.com/Vamshi9415/EnseSmells_with_explanability_Ai) | Explainable multimodal ensemble for code-smell detection | `ML` `XAI` |
| [`git-like-pdf-diff`](https://github.com/Vamshi9415/git-like-pdf-diff) | Git-style diffing for PDF documents | `Python` `Docs` |
| [`OCR-MARKSHEET`](https://github.com/Vamshi9415/OCR-MARKSHEET) | OCR-based marksheet data extraction | `OCR` `Python` |

---

```bash
vamshi@ai-lab:~$ cat architecture/rag_pipeline.mmd
```

```mermaid
%%{init: {'theme':'dark','themeVariables':{'primaryColor':'#0d1117','primaryTextColor':'#00ff41','primaryBorderColor':'#00ff41','lineColor':'#00ff41','fontFamily':'monospace'}}}%%
flowchart LR
    A[User query] --> B[Embed<br/>sentence-transformers]
    B --> C[(FAISS index)]
    C --> D[Top-k chunks]
    D --> E[Reranker]
    E --> F[LLM]
    F --> G{Guardrails<br/>policy check}
    G -- pass --> H[Answer + sources]
    G -- risky --> I[Human approval]
    I --> H
```

---

```bash
vamshi@ai-lab:~$ python run_agent.py --task "summarize contract and email legal" --verbose
```

```text
[plan]     1. retrieve_docs  2. summarize  3. send_email
[tool]     retrieve_docs(query="contract") -> 6 chunks (reranked)
[llm]      summarize(context=6 chunks) -> 142 tokens
[policy]   send_email -> external recipient -> REQUIRES_APPROVAL
[human]    approve send_email to legal@example.com? [y/N] y
[tool]     send_email(to="legal@example.com") -> ok
[done]     3 steps | 1 approval | 0 policy violations
```

<sub>↑ illustrative trace of the guarded-agent pattern</sub>

---

```bash
vamshi@ai-lab:~$ cat mcp.config.jsonc
```

```jsonc
{
  "mcpServers": {
    "docrag":        { "role": "retrieval over private documents" },
    "guarded-agent": { "role": "tool calling with policy + approval" }
  },
  "principles": ["least privilege", "human in the loop for risky actions", "log everything"]
}
```

---

```bash
vamshi@ai-lab:~$ pip freeze | grep -i "ai-stack"
```

```text
fastapi
langchain
langgraph
torch
sentence-transformers
faiss-cpu
docker
```

<p>
  <img src="https://skillicons.dev/icons?i=python,java,postgres,fastapi,pytorch,docker,aws,linux,git&theme=dark" alt="skills" />
</p>

```text
Languages      : Python, Java, SQL
Backend        : FastAPI, REST APIs
AI / ML        : LLMs, RAG, LangChain, LangGraph, PyTorch
Agent Systems  : MCP, tool calling, guardrails
Retrieval      : FAISS, sentence-transformers, reranking
Infrastructure : Docker, AWS, Linux, Git
```

---

```bash
vamshi@ai-lab:~$ git log --stat --author="vamshi"
```

<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=Vamshi9415&show_icons=true&hide_border=true&bg_color=0D1117&title_color=00FF41&icon_color=00FF41&text_color=C9D1D9&text_bold=false" alt="stats" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Vamshi9415&layout=compact&hide_border=true&bg_color=0D1117&title_color=00FF41&text_color=C9D1D9" alt="top languages" />
</p>

---

```bash
vamshi@ai-lab:~$ cat experiments.todo
```

- [x] RAG with embeddings, FAISS and reranking
- [x] Agents with guardrails and human approval
- [ ] Reliable multi-step agentic workflows
- [ ] Better document processing and retrieval quality
- [ ] Production-ready backend services for LLM apps

---

```bash
vamshi@ai-lab:~$ ./connect.sh
```

<p>
  <a href="https://github.com/Vamshi9415"><img src="https://img.shields.io/badge/github-Vamshi9415-0D1117?style=for-the-badge&logo=github&logoColor=00FF41&labelColor=0D1117&color=00FF41" alt="GitHub" /></a>
  <!-- Add yours:
  <a href="https://linkedin.com/in/YOUR_ID"><img src="https://img.shields.io/badge/linkedin-connect-0D1117?style=for-the-badge&logo=linkedin&logoColor=00FF41&color=00FF41" alt="LinkedIn" /></a>
  <a href="mailto:YOUR_EMAIL"><img src="https://img.shields.io/badge/email-say_hi-0D1117?style=for-the-badge&logo=gmail&logoColor=00FF41&color=00FF41" alt="Email" /></a>
  -->
</p>

```bash
vamshi@ai-lab:~$ echo "Stay curious. Build things. Understand how they work."
Stay curious. Build things. Understand how they work.
vamshi@ai-lab:~$ █
```
