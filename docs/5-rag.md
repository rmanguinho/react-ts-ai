## 1. O que é RAG (Retrieval-Augmented Generation)?

* RAG é uma técnica para turbinar uma LLM com conhecimento externo (não estava no treinamento)
* A LLM só consegue responder sobre coisas que foi treinada
* RAG não é fine-tuning (a LLM não está aprendendo nada novo)
* O processo de adicionar dados ao treinamento da LLM é chamado de "fine-tuning"
* A LLM recebe dados externos e os adiciona no prompt para dar mais qualidade na resposta

## 2. Como funciona o fluxo RAG

* **Fonte de dados**: escolha onde buscar a informação → docs técnicos, FAQs, manuais, tickets, artigos, código, bancos de dados, APIs
* **Chunking**: os documentos são quebrados em pedaços menores (300–1000 tokens, ajustável conforme o caso)
* **Embeddings**: cada chunk é convertido em um vetor numérico que representa semanticamente o conteúdo
* **Indexação**: os vetores são armazenados em um banco vetorial (ex: Pinecone, Chroma)
* **Consulta**: quando o usuário faz uma pergunta, a query também é convertida em embedding
* **Busca**: o sistema compara esse embedding com os do banco vetorial para achar os chunks mais relevantes
* **Construção do prompt**: o prompt final é formado por (instruções fixas + query do usuário + docs recuperados)
* **Geração**: a LLM usa seu conhecimento interno + contexto injetado para produzir a resposta

## 3. Vantagens do RAG

* Atualização em tempo real → não precisa re-treinar a LLM a cada mudança de documentação
* Uso de dados privados → permite integrar informações internas (códigos, manuais, relatórios, históricos)
* Eficiência de tokens → em vez de mandar 200 páginas de doc, injeta só os 2 parágrafos relevantes
* Escalabilidade → pode combinar múltiplas fontes (APIs, DBs, PDFs, tickets, logs)
* Manutenção simples → basta atualizar a base de conhecimento (sem custo de GPU/treinamento)

## 4. Exemplo Prático

* Tenho um app que organiza eventos de futebol com features como presença, rankings, assinaturas, financeiro
* Quero criar um chatbot para tirar dúvidas dos usuários
* Tenho uma documentação interna com todas as features
* Fazemos o processo de criação de embeddings e indexação dos chunks com os dados do FAQ
* O usuário pergunta no chatbot: “Como funciona o controle financeiro?”
* É feita a busca no banco vetorial e são recuperados os chunks mais relevantes
* Injeta esses chunks no prompt junto com a pergunta
* A LLM responde com base nos seus conhecimentos e mais os chunks que foram injetados

## 5. Desafios e Boas Práticas

* Digamos que no exemplo acima, os dados do financeiro tenham 1200 tokens. Como os chunks foram definidos com 1000 tokens, o sistema vai injetar 2 chunks, totalizando 2000 tokens (precisava 1200 tokens apenas)
* Ajustar o chunk size é fundamental
* Se os chunks forem mal feitos, a LLM pode receber dados incompletos, gerando alucinações
* Cuidado para não indexar dados sensíveis
* Usar um modelo mais barato para resumir os chunks antes de injetar
* **Reranking**
  * Quando fazemos uma busca em um banco vetorial, o sistema retorna os chunks que são parecidos com a query
  * Reranking é uma etapa extra que reordena ou filtra os chunks
  * Usa um modelo específico para avaliar a relevância dos chunks (geralmente um modelo mais barato)
  * Faz tipo um top 3 ou top 5 de chunks mais relevantes e os retorna para a LLM
