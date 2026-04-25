# 🤖 Bob — Agente Financeiro Inteligente

Bob é um assistente financeiro conversacional desenvolvido com IA generativa, capaz de analisar o perfil do cliente, interpretar transações e recomendar produtos financeiros adequados — tudo sem inventar informações.

---

## 📌 Caso de Uso

Usuários têm dificuldade em organizar finanças pessoais, controlar gastos e tomar decisões financeiras por falta de visibilidade. O Bob analisa dados reais do cliente e oferece orientações proativas e personalizadas.

**Público-alvo:** Pessoas que desejam melhorar sua organização financeira, de iniciantes a usuários com conhecimento intermediário.

---

## 🧠 Como o Bob funciona

```
Cliente → Interface (Streamlit) → LLM (Ollama local) → Base de Conhecimento → Resposta validada
```

O agente carrega o perfil do cliente, as últimas transações e os produtos financeiros disponíveis no início de cada sessão. Esses dados compõem o contexto enviado ao LLM, que responde com base apenas nas informações fornecidas.

---

## 🗂️ Estrutura do Projeto

```
.
├── data/
│   ├── perfis/                    # Perfis de clientes (JSON)
│   ├── produtos_financeiros.json  # Produtos disponíveis
│   ├── transacoes.csv             # Histórico de transações
│   └── historico_atendimento.csv  # Histórico de atendimentos
├── docs/
│   ├── 01-documentacao-agente.md
│   ├── 02-base-conhecimento.md
│   ├── 03-prompts.md
│   ├── 04-metricas.md
│   └── 05-pitch.md
├── src/
│   └── chatbot.py                 # Aplicação principal
└── README.md
```

---

## 🚀 Como rodar

### 1. Instale o Ollama e baixe o modelo

```bash
ollama pull gpt-oss
```

### 2. Instale as dependências Python

```bash
pip install streamlit pandas requests
```

### 3. Certifique-se de que o Ollama está rodando e execute

```bash
py -m streamlit run src/chatbot.py
```

---

## 🔐 Segurança e Anti-Alucinação

- Respostas baseadas **exclusivamente** nos dados carregados
- Nunca solicita ou armazena dados bancários sensíveis
- Admite limitações quando não possui informação suficiente
- Não recomenda investimentos sem consultar o perfil do investidor
- Não substitui um consultor financeiro profissional

---

## 📊 Métricas de Qualidade

| Métrica | O que avalia |
|---|---|
| **Assertividade** | O agente respondeu o que foi perguntado? |
| **Segurança** | Evitou inventar informações? |
| **Coerência** | A resposta é adequada ao perfil do cliente? |

---

## 🛠️ Tecnologias

- [Streamlit](https://streamlit.io/) — Interface
- [Ollama](https://ollama.com/) — LLM local (`gpt-oss`)
- Python (`pandas`, `requests`, `json`)
