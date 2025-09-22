## 1. O que é um prompt?

* É a instrução que você dá para a LLM
* A qualidade do prompt define a qualidade da resposta
* Imagine que você recebe uma tarefa super genérica do seu chefe. Qual é a chance de você fazer a tarefa da forma correta (que ele realmente esperava)?
* Com A LLM é a mesma coisa. Se você for muito genérico a LLM vai responder o que ela acha que você quer. Isso abre margem para erros e alucinações

## 2. Princípios para bons prompts

* Seja direto, objetivo e específico
* Inclua contexto e restrições claras (formato, limite de caracteres, estilo)
* Divida tarefas em etapas (ex: código → docs → testes)
* Trate o prompt como código reutilizável: limpo e organizado
* Evite pedidos vagos (“me dê um texto legal”)
* Evite misturar várias tarefas no mesmo prompt
* Evite elogios e agradecimentos

### Lembre-se

* Prompts vagos = respostas longas, com desperdício de tokens
* Prompts muito curtos = respostas pobres
* O segredo é clareza + limites definidos
* Não é sobre ser o menor possível, mas o mais específico possível

## 3. Exemplos práticos

### ❌ Exemplo ruim

> Preciso, por favor, de um código em React com Tailwind, que gere um botão verde arredondado estilizado seguindo melhores práticas e que também venha documentado e com testes

### 👍 Exemplo bom

> Crie um botão verde arredondado com Tailwind e React

### ❌ Exemplo ruim

> Gere um texto de agradecimento pela compra

### 👍 Exemplo bom

> Gere um título para notificação push de agradecimento pela compra (use no máximo 30 caracteres)

### 4. Tipos de prompts

* **Zero-Shot**
  * Você só dá a instrução
  * O modelo usa o que aprendeu no treinamento
  * Ex: “Crie um botão verde arredondado com React/Tailwind”
* **One-Shot**
  * Você dá um exemplo como guia
  * Ex: Mostra um card de produto pronto → pede outro igual para outro produto
* **Few-Shots**
  * Você dá vários exemplos para o modelo seguir um padrão
  * Quanto mais exemplos, mais consistente o resultado

## 5. Técnicas Avançadas

* **Chain-of-Thought**
  * A LLM monta um raciocínio passo a passo antes de dar a resposta final
  * Ajuda em tarefas complexas
  * “Explique passo a passo como se calcula a raiz quadrada de 16”
* **Role Prompting**
  * A LLM assume um papel específico antes de responder
  * Isso ajuda a alinhar tom, estilo e profundidade da resposta
  * Ex: “Você é um professor de matemática. Explique o conceito como se fosse para um aluno de 12 anos”
* **DICA**
  * Muitas vezes você pode usar ambas as técnicas juntas
  * Ex: "Você é um consultor de startups. Raciocine passo a passo como avaliaria o modelo de negócio X e depois me diga se é viável"
