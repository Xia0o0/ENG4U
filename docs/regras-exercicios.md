# Regras propostas de exercícios e progresso — ENG4U

## 1. Objetivo e situação

Definir as regras de correção, pontuação, revisão e acompanhamento do estudo no aplicativo.

**Status:** proposta para revisão da equipe; implementação pendente.

O planejamento prevê essas funcionalidades. As políticas específicas descritas aqui detalham a proposta e poderão ser ajustadas antes da implementação.

## 2. Tipos de exercício

| Tipo | Entrada do aluno | Forma de correção |
|---|---|---|
| MULTIPLA_ESCOLHA | Seleção de uma alternativa | Comparação pelo identificador da alternativa e seu gabarito |
| LACUNA | Resposta textual | Comparação com a lista de respostas aceitas |

Cada exercício deverá possuir enunciado, identificador e explicação de apoio à correção.

## 3. Múltipla escolha

- Permitir somente uma alternativa selecionada por questão.
- Exigir seleção antes do envio.
- Cada exercício terá exatamente uma alternativa correta.
- Verificar a resposta pelo identificador da alternativa, não pela posição na tela.
- Após a verificação, bloquear alterações naquela resposta.
- Impedir que toques repetidos registrem a mesma submissão mais de uma vez.
- Permitir uma nova resposta somente em uma nova execução da atividade.

Exemplo:

Enunciado: Complete: I ___ a student.

| Alternativa | Correção |
|---|---|
| am | Correta |
| is | Incorreta |
| are | Incorreta |

## 4. Preenchimento de lacunas

A resposta será comparada aos valores de `respostasAceitas` do exercício.

### Normalização proposta

Aplicar tanto à entrada quanto aos gabaritos:

1. Remover espaços no início e no fim.
2. Reduzir espaços consecutivos a um único espaço.
3. Desconsiderar diferenças entre maiúsculas e minúsculas.

Não remover automaticamente acentos, pontuação ou apóstrofos. Essas diferenças podem alterar o significado ou a forma avaliada.

Variações válidas deverão ser cadastradas explicitamente no gabarito. Exercícios que avaliem maiúsculas ou espaçamento precisarão de uma regra específica antes de sua inclusão.

Exemplo:

Enunciado: Complete: She ___ a teacher.

Respostas aceitas: ["is"]

| Entrada | Resultado esperado |
|---|---|
| is | Correta |
| IS | Correta |
| " is " | Correta após normalização |
| are | Incorreta |
| is. | Incorreta, salvo se cadastrada como resposta aceita |

Respostas vazias ou compostas apenas por espaços não serão registradas como tentativas válidas.

## 5. Feedback

Após o envio, apresentar:

- Indicação textual e visual de acerto ou erro.
- Resposta enviada.
- Gabarito, em caso de erro.
- Explicação associada ao exercício.
- Ação para continuar a atividade.

As cores deverão ser acompanhadas por textos e símbolos.

O feedback e a validação serão processados localmente.

## 6. Pontuação da atividade

Cada questão terá o mesmo peso nesta proposta inicial.

Percentual de acertos = (quantidade de acertos / quantidade de questões) × 100

Exemplo:

- Questões: 3.
- Acertos: 2.
- Percentual: 66,67%.
- Exibição arredondada: 67%.

Regras:

- Contar uma única resposta por questão em cada execução.
- Não modificar o resultado de uma resposta já verificada.
- Exibir o resultado final após responder todas as questões da atividade.
- Uma execução interrompida não será apresentada como atividade concluída.
- Não calcular percentual quando não houver questões; apresentar uma mensagem de atividade indisponível.

## 7. Novas tentativas

Ao selecionar “Tentar novamente”:

- Iniciar uma nova execução.
- Limpar seleção, texto digitado e pontuação da execução anterior na interface.
- Preservar as tentativas já salvas no histórico.
- Registrar as novas respostas separadamente.

### Política proposta de desempenho

- O resultado da atividade representa a execução que acabou de ser concluída.
- O resumo de desempenho utiliza a última execução completa de cada atividade.
- Execuções incompletas não substituem o último resultado completo.
- Uma nota menor em nova tentativa não desfaz a conclusão da lição.

Para calcular a média geral, somar os acertos e as questões das últimas execuções completas consideradas. Não fazer média simples de percentuais de atividades com quantidades diferentes de questões.

## 8. Registro das tentativas

Cada resposta válida deverá registrar:

- Identificador da tentativa.
- Identificador do exercício.
- Resposta enviada.
- Indicação de acerto ou erro.
- Data e hora.

Em múltipla escolha, a resposta enviada será o identificador da alternativa. Em lacunas, será o texto informado pelo aluno.

Para distinguir repetições da mesma atividade, propõe-se acrescentar um identificador de execução e seu contexto, como prática de lição ou revisão de capítulo.

Essa identificação complementar ainda deverá ser incorporada ao detalhamento da modelagem antes da implementação.

## 9. Progresso das lições

| Estado | Regra proposta |
|---|---|
| NAO_INICIADA | A lição ainda não foi aberta. |
| EM_ANDAMENTO | A lição foi aberta, mas sua prática ainda não foi concluída. |
| CONCLUIDA | Todos os exercícios da prática da lição foram respondidos em uma execução completa. |

Regras complementares:

- A conclusão não exige 100% de acertos.
- Refazer uma prática não deve apagar a conclusão anterior.
- Cada lição possui no máximo um registro de progresso no contexto local.
- A data de atualização deve acompanhar as mudanças do registro.
- Para lições sem exercícios, a regra de conclusão deverá ser definida antes de disponibilizá-las; abrir a tela não será considerado conclusão automática.

## 10. Indicadores de progresso

Percentual de conclusão = (lições concluídas / total de lições disponíveis) × 100

Exemplo:

- Lições disponíveis: 12.
- Lições concluídas: 4.
- Progresso exibido: 33%.

Apresentar separadamente:

- Quantidade e percentual de lições concluídas.
- Lições em andamento.
- Desempenho nos exercícios.

Quando não houver prática concluída, apresentar “Sem resultado” ou equivalente, em vez de atribuir nota zero.

Para módulos sem lições disponíveis, apresentar “Conteúdo indisponível”, sem divisão por zero.

## 11. Revisão por capítulo

- Permitir selecionar um capítulo.
- Utilizar somente exercícios das lições pertencentes a esse capítulo.
- Selecionar até três exercícios distintos por rodada na proposta inicial.
- Se houver menos de três disponíveis, utilizar a quantidade existente.
- Não repetir o mesmo exercício na mesma rodada.
- Se não houver exercícios, informar que a revisão está indisponível.
- Permitir refazer a revisão em uma nova execução.

O limite de três questões é uma decisão inicial de demonstração, ajustável pela equipe.

### Relação com o progresso

A revisão registra seu próprio resultado, mas não conclui automaticamente as lições do capítulo.

Nesta proposta, os resultados das revisões ficam separados do desempenho das práticas das lições.

## 12. Embaralhamento

As alternativas poderão ser embaralhadas com um algoritmo como Fisher–Yates.

Regras:

- Embaralhar os objetos completos, preservando identificador, texto e gabarito.
- Não utilizar a posição visual como referência de correção.
- Manter a ordem estável enquanto o aluno responde à questão.
- Realizar novo embaralhamento ao iniciar outra execução, se previsto.
- Aceitar que duas execuções possam apresentar a mesma ordem por acaso.

A seleção de exercícios deverá ocorrer sem reposição dentro de cada rodada.

## 13. Persistência e funcionamento offline

Salvar localmente:

- Progresso das lições.
- Respostas e tentativas.
- Identificação das execuções e resultados necessários aos indicadores.

O aplicativo deverá recuperar os registros após ser fechado e reaberto.

A retomada de uma execução incompleta não é garantida nesta proposta inicial. O progresso já concluído e as tentativas salvas deverão ser preservados.

A correção, o cálculo e o salvamento funcionarão sem conexão para o conteúdo disponível no dispositivo.

Se ocorrer falha no salvamento, o aplicativo não deverá informar que os dados foram persistidos com sucesso.

## 14. Consistência com o conteúdo

- Referenciar lições, exercícios e alternativas por identificadores estáveis.
- Verificar se os gabaritos correspondem ao tipo de exercício.
- Evitar questões ambíguas.
- Conferir respostas aceitas com o material didático.
- Preservar os vínculos entre conteúdo e registros locais.
- Definir uma política de atualização antes de alterar exercícios que já possuam tentativas registradas.

## 15. Relação com o cronograma

| Etapa | Regras relacionadas |
|---|---|
| Sprint 3 — Exercícios e algoritmos | Entrada de respostas, validação, feedback e cálculo de acertos |
| Sprint 4 — Progresso e refinamento | Persistência, indicadores, revisão e embaralhamento |
| Sprint 5 — Testes e entrega | Verificação das regras, correções e validação dos fluxos |

## 16. Pontos para aprovação da equipe

Antes da implementação, confirmar:

- Normalização das respostas textuais.
- Uso da última execução completa no desempenho.
- Regra de conclusão das lições.
- Quantidade de questões por revisão.
- Separação entre resultados de revisão e prática.
- Identificação das execuções na modelagem.
- Política para atualização de conteúdo e registros anteriores.

Este documento apresenta regras propostas e não declara que as funcionalidades já estão implementadas.