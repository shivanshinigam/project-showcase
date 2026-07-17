<div align="center">

# Shivanshi Nigam — Project Showcase

<img src="https://readme-typing-svg.demolab.com/?font=Fira+Code&size=16&pause=1000&color=57E389&center=true&width=560&lines=Permission-Aware+RAG+Gateway;Verifying+Code+Review+Agent;built%2C+proven%2C+and+documented" alt="typing" />

</div>

---

<table width="100%">
<tr>
<td width="50%" valign="top">
<div style="background:#161b22;border:1px solid #30363d;border-top:4px solid #C97C5D;border-radius:10px;padding:24px;height:100%;">

### 🔐 Permission-Aware RAG Gateway

<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/RAG-C97C5D?style=flat-square" />
<img src="https://img.shields.io/badge/LLM-C97C5D?style=flat-square" />
<img src="https://img.shields.io/badge/Access%20Control-C97C5D?style=flat-square" />

**What it is**
<br/>
Middleware between real company data sources (Google Drive, Slack) and an LLM chatbot that enforces each source's actual access-control rules — so the bot can never surface information a given user isn't permitted to see, even when every document lives in the same vector index.

**Why it exists**
<br/>
Naive RAG pipelines dump every document into one vector database. Embeddings don't know about ACLs. The moment a Drive folder holding both a public onboarding guide and a confidential salary spreadsheet gets indexed, any employee can ask the wrong question and get an answer they were never meant to see. This is the real reason security teams block internal AI pilots.

**The proof**
<br/>
Same corpus, two users — Alice (HR, has access) and Bob (regular employee, doesn't) — asked identical sensitive questions. Alice gets the real figures. Bob gets a clean "I don't have access," with zero leaked fragments, verified by scanning raw output text rather than trusting a self-reported "grounded" flag. The system fails closed: unknown access defaults to denied.

**Next 10 hours**
<br/>
Swap the manual YAML identity mapping for real SSO/directory integration; move the in-memory permission store to something DB-backed for scale.

**What was cut**
<br/>
Granular view/comment/edit permissions (binary access proves the read gate); connector breadth (two — one granular, one simple — proves the abstraction generalizes better than ten would).

<br/>

[![Repo](https://img.shields.io/badge/View%20Repo-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/shivanshinigam/permission-aware-rag-gateway)

</div>
</td>
<td width="50%" valign="top">
<div style="background:#161b22;border:1px solid #30363d;border-top:4px solid #C9A876;border-radius:10px;padding:24px;height:100%;">

### 🕵️ Verifying Code Review Agent

<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/LLM-C9A876?style=flat-square" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Agentic%20AI-C9A876?style=flat-square" />

**What it is**
<br/>
An AI code review agent that doesn't just have opinions about a pull request — it proves them. Every LLM finding is routed through a category-specific verification pass and actually checked before a human ever sees it.

**Why it exists**
<br/>
Every other AI review bot (CodeRabbit and its clones included) posts every LLM guess straight to the PR. The result is review fatigue — engineers learn to skim past AI comments because too many are wrong. This agent treats a finding as a hypothesis, not a fact.

**How it verifies**
<br/>
Logic bugs get a minimal repro script generated and actually executed in a resource-limited, network-disabled Docker container. Cross-file breaks get confirmed against a real, locally-indexed caller so the model can't hallucinate one that doesn't exist. Security findings go through taint-tracing that must prove a real data-flow path from attacker-controlled input to a dangerous sink. Style comments stay separate, clearly labeled as unverified opinion.

**The proof**
<br/>
Three deliberately seeded bugs in a toy repo, one per category — the full pipeline recalled 3 out of 3, at 100% precision. Most AI review tools never publish this number.

**Next 10 hours**
<br/>
Extend past Python — the AST chunking and taint-tracing architecture generalizes to other languages, but the parsers and repro-generation prompts are Python-specific right now.

**What was cut**
<br/>
Broader language support, and a stronger sandbox isolation boundary for genuinely adversarial code — solid today for reviewing your own or public repos, not yet hardened for hostile input.

<br/>

[![Repo](https://img.shields.io/badge/View%20Repo-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/shivanshinigam/verifying-code-review-agent)

</div>
</td>
</tr>
</table>

<br/>

<div align="center">
<sub>Built solo. Evaluated, not just demoed.</sub>
</div>
