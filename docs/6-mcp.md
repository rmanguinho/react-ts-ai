## 1. MCP (Model Context Protocol)

* MCP É um padrão (protocolo) para a LLM acessar recursos (arquivos, logs, DBs) e ferramentas (ações/commands) por meio de um cliente (ex: Cursor) falando com servidores MCP
* É usado um modelo cliente-servidor
* O cliente é a aplicação que vai usar o MCP (ex: Cursor)
* O servidor é o MCP (programa que expõe os recursos e ferramentas)
* A LLM atua como um orquestrador (ela sabe qual MCP deve chamar, baseado no prompt)

## 2. O Problema

* Uma LLM pura só interpreta texto
* Ela não consegue, por padrão
  * Ler arquivos do seu projeto
  * Procurar onde algo está no repo
  * Modificar arquivos
  * Rodar testes/linters/scripts
  * Consultar bancos/APIs com segurança
* Resultado: você fica colando/recortando contexto manualmente ou escrevendo integrações ad hoc (cada cliente/IDE faz de um jeito)

## 3. Como o MCP resolve isso?

* Permite a LLM listar e ler arquivos/dados via URIs (resources)
* Permite a LLM executar ações com inputs e outputs bem definidos (tools)
* Permite a LLM ser avisado sobre mudanças (events)

## 4. Vantagens do MCP

* Automação real: a LLM vira um “operador” capaz de agir (rodar testes, abrir PR, aplicar migração)
* Menos atrito: você não precisa colar arquivos nem inventar adapters diferentes para cada ambiente
* Qualidade e segurança: tools com schemas, permissões, logs e políticas (ex: bloquear PR se cobertura < 80%)
* Escala e reuso: o mesmo servidor serve IDE, bot, pipeline, agente de suporte, etc.

## 5. MCP x RAG (quando usar cada um)

* RAG enriquece o contexto com informação relevante
* MCP interage com o mundo externo de forma padronizada e segura
* RAG não executa nada, só injeta texto
* MCP executa tools
* RAG extrai dados dentro de textos embrulhados
* MCP obtem dados de sistemas reais (Git, DB, CI)
* RAG é usado para perguntas/respostas, suporte, leitura de base de conhecimento
* MCP é usado para automação, engenharia assistida, operações
* RAG encontra onde mexer
* MCP edita/valida/commita de verdade

## 6. Sugestões de MCPs

* **Sequential Thinking**
  * Aplica o conceito de Chain of Thoughts (quebra o problema em etapas menores)
  * Mantem estado entre as etapas
  * Permite auditar o raciocínio da LLM
* **Context7**
  * Servidor para documentação de código up-to-date
  * Busca docs e exemplos reais de fontes oficiais
  * Exemplo útil: Prompt "Crie um CRUD em FastAPI com auth, use context7"
* **Perplexity**
  * Permite que a LLM faça pesquisas na internet
  * A LLM sem o Perplexity só consegue buscar dados que estão dentro do seu treinamento
  * Com Perplexity a LLM tem acesso a web em tempo real
  * Sem perplexity a LLM pode alucinar com perguntas sobre eventos recentes
  * Resultados vem com fontes, permitindo auditoria
* **Playwright**
  * É um servidor para automação de browsers
  * Permite scraping, testes E2E, execução de JS e screenshots
  * Exemplo: “Abra /login, tente fluxo OAuth e me mostre screenshot do erro”
* **Figma**
  * Permite extrair metadados de arquivos Figma
  * Ideal para construir layouts seguindo a risca o que foi projetado no Figma
* **PostgreSQL e MongoDB**
  * Cursor não tem acesso nativo a bancos de dados
  * Permite queries, análise de schema, debug de dados
  * Essencial para desenvolvimento backend/fullstack
  * Ex: "Sugira índices para otimizar a tabela users"