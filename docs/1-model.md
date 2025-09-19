## 1. O que é uma LLM (Large Language Model)?

* LLM é um tipo de inteligência artificial treinada para entender e gerar texto
* Ela aprende lendo uma quantidade enorme de textos (livros, sites, artigos, conversas)
* Depois, usa esse “conhecimento estatístico” para prever qual palavra deve vir depois da outra em uma frase
* É como um “super autocompletar” de celular, só que muito mais avançado
* Ela pode responder perguntas, escrever e traduzir textos, criar resumos, código e até conversar de forma natural
* Treinar uma LLM é um processo caro e complexo, que envolve enormes quantidades de dados e computação

## 2. Quem é Quem?

* Empresas
  * OpenAI
  * Anthropic
  * Google
  * xAI
* Famílias de modelos
  * GPT (OpenAI)
  * Claude (Anthropic)
  * Gemini (Google)
  * Grok (xAI)
* Modelos
  * GPT 5
  * GPT 5 mini
  * Claude Opus 4
  * Claude Sonnet 4
  * Gemini Pro 2.5
  * Gemini Flash 2.5
  * Grok 3
  * Grok 3 mini
* Clientes
  * ChatGPT
  * Cursor
  * Claude
  * Copilot
  * Perplexity

* Quem é então a LLM?

## 3. Tokens e Precificação

* Toda LLM precisa quebrar texto em unidades menores (tokens) para processar
* Em geral, 1.000 tokens ≈ 750 palavras em inglês
* O custo e o limite de contexto sempre são medidos em tokens
* O custo é calculado por cada 1.000 tokens
* Como os treinamentos são feitos majoritariamente em inglês, fazer prompts em inglês tende a ser mais econômico em tokens
* O português (assim como francês, alemão, etc.) tem palavras mais longas, acentos, flexões verbais → acabam virando mais tokens por palavra
* A diferença não é absurda, mas em uso massivo (milhões de tokens/mês), pode representar 10–20% a mais de custo

## 4. Comparativo de Modelos

* Problemas mais complexos, análises profundas
  * GPT 5 - $1,25 a $10,00 por 1M tokens
  * Gemini 2.5 Pro - $1,25/2,50 a $10,00/15,00 por 1M tokens
  * Claude Opus - $15,00 a $75,00 por 1M tokens
  * Claude Sonnet 4 - $3,00 a $15,00 por 1M tokens
  * Grok 3 - $3,00 a $15,00 por 1M tokens
* Tarefas rotineiras, correções simples, autocomplete
  * GPT 5 mini - $0,25 a $2,00 por 1M tokens
  * Gemini 2.5 Flash - $0,3 a $5,00 por 1M tokens
  * Claude Haiku 3.5 - $0,8 a $4,00 por 1M tokens
  * Grok Code Fast 1 - $0,20 a $1,50 por 1M tokens
* Snippets rápidos, tarefas básicas
  * GPT 5 nano - $0,05 a $0,40 por 1M tokens
  * Gemini 2.5 Lite - $0,10 a $0,40 por 1M tokens
  * Grok 3 Mini - $0,30 a $0,50 por 1M tokens

## 5. Thinking Mode

* Isso vai fazer o modelo pensar um pouco mais antes de responder
* É útil para tarefas complexas e que precisam de uma resposta mais detalhada
* Vai gastar quase o dobro de tokens
* É uma implamentação prática do Chain of Thoughts - uma técnica de raciocínio que faz o modelo pensar passo a passo para chegar a uma resposta
