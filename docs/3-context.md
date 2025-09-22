## 1. O que é Contexto?

* Tudo que o modelo recebe para entender a tarefa atual
* Inclui:
  * Sua pergunta (input)
  * Histórico da conversa
  * Instruções fixas (rules, system prompt)
  * Docs/códigos colados
  * Inputs multimodais (imagem, áudio, vídeo)
* Cada interação é input + output, e ambos ocupam tokens

## 2. Como o Contexto Impacta no Custo

* Se você envia 50 tokens e recebe 100 tokens, o custo foi 150 tokens
* Na próxima pergunta (30 tokens), o modelo precisa reler o histórico → 30 + 150 = 180 tokens
* Respostas longas aumentam o contexto
* Imagens podem equivaler a milhares de tokens

## 3. Short-Term Memory (STM)

* Cada modelo tem uma janela de contexto
* A janela de contexto é a quantidade máxima de tokens que o modelo consegue “enxergar” de uma vez
* Essa janela é chamada de Short-Term Memory (STM)
* Cada modelo tem um limite para a janela de contexto (ex: 16K tokens)
* Se a conversa cresce demais, o cliente (ChatGPT, Cursor, etc.) precisa escolher o que fazer com o histórico antigo
* Estratégias usadas
  * Truncamento: corta fora o histórico mais antigo (perda de informação)
  * Resumo: compacta o histórico antigo e injeta em forma resumida (não tem todos os detalhes, mas mantem a essência da conversa)
* **Importante**: quem decide isso é a aplicação cliente, não a LLM

## 4. Long-Term Memory (LTM)

* LTM não é nativa da LLM, mas criada pela aplicação
* É persistida fora do modelo
  * Bancos de dados
  * Embeddings/vetores
  * Arquivos e resumos periódicos
* Permite a LLM “se lembrar” de interações passadas, preferências ou dados do usuário
* Exemplo
  * ChatGPT guardando preferências de escrita
  * Cursor lembrando instruções de projeto em arquivos de config

## 5. Resumo

* Contexto = combustível da LLM
* Quanto maior o contexto → mais caro e mais lento
* Aprenda a limpar e controlar o histórico
* STM = janela de contexto (limitada)
* LTM = memória persistente (aplicação decide)
