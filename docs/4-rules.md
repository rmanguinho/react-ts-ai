## 1. O que são Rules?

* Instruções fixas adicionadas ao contexto da LLM
* Definem como o modelo deve responder
* Podem vir de
  * System prompt (cliente)
  * Usuário (manual)

## 2. Bons exemplos de Rules

* Remova imports não utilizados
* Use early returns quando possível
* Use camelCase para variáveis
* Use PascalCase para classes
* Responda sempre em inglês
* Prefira const/let ao invés de var
* Não use comentários

## 3. Isso são tarefas, não rules

  * Implemente um login com Firebase
  * Crie testes para o código

## 4. Maus exemplos de Rules

* Regras muito genéricas
  * Faça o código de um jeito organizado
  * Use sempre as melhores práticas
* Regras redundantes (gastam tokens desnecessariamente)
  * Sempre declare variáveis com const em vez de var
  * Evite var, prefira const
* Regras contraditórias
  * Use TailwindCSS para todos os estilos
  * Estilize preferencialmente com Material UI

## 5. Boas práticas

* Cuidado com regras desatualizadas (exemplo: sempre use jest para testes). Sendo que seu time migrou para vitest (precisa atualizar as regras que falam sobre jest)
* Não use regras longas demais
* Defina prioridade em caso de conflito
* Diferencie regra vs guideline (rigidez x flexibilidade)
* Evite nas regras dizer para o modelo **"como"** e **"por que"**. Foque em **"o que"** fazer e **"o que não"** fazer
