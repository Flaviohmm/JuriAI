## JuriAI — Secretária Autônoma e Assistente Jurídico com Agentes de IA

O **JuriAI** é uma aplicação de ponta desenvolvida durante o workshop **Arcane 3**, focada em automatizar a rotina de advogados e escritórios de advocacia. O projeto utiliza a biblioteca **Agno** para criar agentes inteligentes capazes de realizar consultas processuais em tempo real e analisar documentos complexos através do **Agente RAG**.

### 📑 Visão Geral

O sistema atua como um assistente virtual especializado, integrando-se diretamente à base de dados do **Conselho Nacional de Justiça (CNJ)** via API do **DataJud**. Ele permite que o usuário consulte o status de processos judiciais de forma conversacional e obtenha insights baseados em uma base de conhecimento privada (contratos, petições e jurisprudência).

---

### 🚀 Funcionalidades Principais


#### ⚖️ Consulta de Processos (DataJud API)

- **Busca em Tempo Real:** Ferramenta integrada para consultar a API pública do DataJud (CNJ).
- **Suporte Multitribunal:** Capaz de filtrar dados de tribunais superiores (STJ, TST, TSE) e estaduais (TJSP, TJMG, etc.).
- **Extração de Movimentações:** Retorna partes envolvidas, histórico de movimentações e decisões judiciais estruturadas.

#### 🧠 Agente RAG (Retrieval-Augmented Generation)

- **Base de Conhecimento Vetorial:** Utiliza o **LanceDb** para armazenamento de documentos jurídicos transformados em vetores (Embeddings).

- **Filtros Dinâmicos:** O agente pode aplicar filtros específicos na base de conhecimento durante a execução para garantir que a resposta seja fundamentada no documento correto.

- **Embeddings OpenAI:** Integração com ``OpenAIEmbedder`` para garantir precisão semântica nas buscas.

#### 💾 Persistência e Contexto

- **Memória de Longo Prazo:** Implementação de ``SqliteDb`` para que o agente "lembre" de interações passadas, mantendo a continuidade do atendimento jurídico.

- **Instruções Especializadas:** Persona configurada para manter um tom profissional, objetivo e fundamentado.

---

### 🛠️ Stack Tecnológica

- **Linguagem:** Python 3.10+

- **Framework de Agentes:** Agno

- **Banco de Dados Vetorial:** LanceDB

- **Banco de Dados de Memória:** SQLite3

- **LLM & IA:** OpenAI GPT-4 

- **Integração:** API DataJud (CNJ)

---

### ⚙️ Configuração e Instalação

##### Pré-requisitos

- Chave de API da OpenAI (para embeddings e chat).
- Token da API DataJud (fornecido no workshop).

##### Passo a Passo

1. **Clonar o repositório:**

```bash
git clone https://github.com/Flaviohmm/JuriAI.git
cd JuriAI
```

2. **Criar e ativar o ambiente virtual:**

```bash
python -m venv.venv
source.venv/bin/activate  # Linux/macOS
#.venv\Scripts\activate   # Windows
```
3. **Instalar dependências:**

```bash
pip install -r requirements.txt
```

4. **Configurar variáveis de ambiente:** Crie um arquivo .env com as seguintes chaves:

```bash
OPENAI_API_KEY=seu_token_aqui
```

---

### 📊 Fluxo de Trabalho

1. **Input:** O usuário pergunta sobre o status de um processo ou uma cláusula contratual.
2. **Busca:** O agente decide se deve usar a **Tool de Pesquisa (DataJud)** ou o **Conhecimento (RAG)**.
3. **Processamento:** A IA interpreta os dados brutos (JSON do CNJ ou Chunks do LanceDB).
4. **Output:** Resposta formatada em tom profissional para o advogado ou cliente final.

---

### 👨‍💻 Créditos e Contexto

Projeto desenvolvido como parte do **Workshop Arcane 3** da **Pythonando**. O objetivo central é capacitar desenvolvedores a construírem aplicações Full-Stack que unem o poder do desenvolvimento Web (Django) com Agentes de IA autônomos.