# Plano de testes — ENG4U

## 1. Objetivo

Planejar a avaliação da navegação, da clareza das interfaces e das funcionalidades do aplicativo de apoio ao projeto Abrindo Portas: Inglês para todos.

Este documento reúne verificações do protótipo e testes previstos para a implementação Android.

**Situação:** testes planejados, sem resultados de execução registrados.

## 2. Escopo e limitações

### Protótipo
Permite avaliar a organização visual, a compreensão dos elementos e a navegação entre as telas conectadas.

Conteúdos, respostas, resultados e indicadores ilustrativos não comprovam o funcionamento dos algoritmos.

### Aplicativo Android
Permitirá testar busca real, validação de respostas, cálculos, persistência, embaralhamento e funcionamento offline.

Esses testes dependem da implementação das funcionalidades.

## 3. Preparação

Para avaliar o protótipo:

- Disponibilizar o link navegável do Figma.
- Informar que se trata de um protótipo com dados demonstrativos.
- Registrar quais telas e interações estão disponíveis.
- Utilizar tarefas curtas, sem explicar antecipadamente onde clicar.

Para avaliar o aplicativo:

- Registrar a versão testada e o dispositivo Android utilizado.
- Disponibilizar conteúdo e exercícios com gabaritos conhecidos.
- Conhecer as regras aprovadas de progresso e pontuação.
- Registrar o estado inicial dos dados antes de cada teste.

## 4. Testes do protótipo

| ID | Item | Procedimento | Resultado esperado | Situação |
|---|---|---|---|---|
| TP01 | Tela inicial | Solicitar que o participante identifique onde continuar estudando. | O participante localiza a ação principal e entende qual lição será retomada. | Planejado |
| TP02 | Módulos e capítulos | Solicitar que encontre uma lição a partir da home. | O participante compreende a hierarquia e chega à lição pelas telas conectadas. | Planejado |
| TP03 | Retorno | Solicitar que volte da lição à lista anterior. | O controle de retorno é identificado e leva ao nível esperado. | Planejado |
| TP04 | Leitura | Solicitar que encontre a explicação, um exemplo e o acesso à prática. | Os elementos são localizados e o conteúdo pode ser lido com clareza. | Planejado |
| TP05 | Busca | Solicitar que encontre o acesso à busca e interprete os resultados ilustrativos. | O participante identifica a busca e distingue os tipos de resultado. | Planejado |
| TP06 | Múltipla escolha | Solicitar que selecione uma alternativa e identifique como enviar a resposta. | A seleção e a ação de verificação são compreendidas. | Planejado |
| TP07 | Lacunas | Solicitar que identifique onde inserir e enviar uma resposta. | O campo e o botão são reconhecidos. A digitação só será avaliada se estiver disponível no protótipo. | Planejado |
| TP08 | Feedback | Mostrar os estados de acerto e erro e perguntar o significado de cada um. | O participante compreende o resultado e identifica a explicação, sem depender apenas das cores. | Planejado |
| TP09 | Resultado | Solicitar que interprete a pontuação e encontre como revisar ou tentar novamente. | Os indicadores e as próximas ações são compreendidos. | Planejado |
| TP10 | Revisão | Solicitar que encontre a revisão e escolha um capítulo. | O participante entende a seleção e identifica como iniciar a atividade. | Planejado |
| TP11 | Progresso | Perguntar a diferença entre conclusão e percentual de acertos. | O participante distingue avanço no conteúdo e desempenho. | Planejado |
| TP12 | Legibilidade | Percorrer as telas e observar textos, ícones, botões e rolagem. | As informações principais são legíveis, os controles identificáveis e não há sobreposição impeditiva. | Planejado |

Se uma interação não estiver conectada, registrar a limitação. Não considerar uma funcionalidade real validada apenas pela visualização de sua tela.

## 5. Testes previstos para o aplicativo Android

| ID | Funcionalidade | Procedimento | Resultado esperado | Situação |
|---|---|---|---|---|
| TA01 | Carregamento do conteúdo | Abrir módulos, capítulos e lições com dados conhecidos. | O conteúdo corresponde ao JSON e à hierarquia definida. | Planejado |
| TA02 | Busca com correspondência | Pesquisar um vocabulário, tradução ou regra existente. | Os resultados pertinentes são apresentados e abrem o conteúdo correspondente. | Planejado |
| TA03 | Busca sem correspondência | Pesquisar um termo ausente. | O aplicativo informa que não encontrou resultados e permite nova pesquisa. | Planejado |
| TA04 | Múltipla escolha correta | Enviar a alternativa correta de um exercício conhecido. | O aplicativo registra acerto e apresenta o feedback correspondente. | Planejado |
| TA05 | Múltipla escolha incorreta | Enviar uma alternativa incorreta. | O aplicativo registra erro e apresenta o gabarito e a explicação previstos. | Planejado |
| TA06 | Lacuna correta | Enviar uma resposta presente no gabarito. | A resposta é aceita conforme as regras aprovadas. | Planejado |
| TA07 | Lacuna incorreta | Enviar uma resposta não aceita. | O aplicativo informa o erro e apresenta a orientação prevista. | Planejado |
| TA08 | Normalização textual | Testar espaços e diferenças de maiúsculas e minúsculas. | A comparação segue a política documentada de normalização. | Planejado |
| TA09 | Resposta vazia | Tentar verificar sem selecionar ou preencher uma resposta. | O aplicativo solicita uma resposta, sem registrar uma tentativa válida. | Planejado |
| TA10 | Envio repetido | Acionar a verificação mais de uma vez para a mesma resposta. | A mesma submissão não é contada em duplicidade. | Planejado |
| TA11 | Pontuação | Concluir uma atividade de três questões com dois acertos. | O resultado apresenta 2 de 3 acertos e aproximadamente 67%, conforme o arredondamento adotado. | Planejado |
| TA12 | Nova tentativa | Refazer uma atividade concluída. | As respostas da nova execução são reiniciadas e o histórico segue a política definida. | Planejado |
| TA13 | Progresso | Iniciar e concluir uma lição conforme as regras aprovadas. | O estado e os indicadores são atualizados de maneira consistente. | Planejado |
| TA14 | Persistência | Registrar progresso, fechar e reabrir o aplicativo. | Os registros salvos permanecem disponíveis. | Planejado |
| TA15 | Revisão por capítulo | Iniciar uma revisão de um capítulo conhecido. | Os itens pertencem ao capítulo selecionado. | Planejado |
| TA16 | Embaralhamento | Executar revisões repetidas e verificar os gabaritos. | As alternativas preservam suas respostas corretas independentemente da posição. A ordem pode variar entre execuções. | Planejado |
| TA17 | Leitura offline | Desativar a internet e abrir conteúdo já disponível no dispositivo. | O conteúdo é apresentado sem depender de conexão. | Planejado |
| TA18 | Prática offline | Com a internet desativada, responder exercícios e consultar o progresso. | Correção, resultado e salvamento local continuam funcionando. | Planejado |
| TA19 | Exibição no Android | Executar a versão nos dispositivos ou emuladores definidos pela equipe. | Não há cortes ou sobreposições que impeçam o uso dos fluxos principais. | Planejado |

## 6. Avaliação de usabilidade

Quando possível, realizar sessões com pessoas do público-alvo.

Apresentar as tarefas sem indicar os botões e observar:

- Conclusão com ou sem ajuda.
- Caminhos incorretos e retornos.
- Dificuldades de leitura.
- Dúvidas sobre ícones, termos e indicadores.
- Sugestões do participante.

Ao final, perguntar:

1. Foi fácil encontrar o conteúdo?
2. Ficou claro como responder e verificar um exercício?
3. As mensagens de acerto e erro foram compreensíveis?
4. Você entendeu a diferença entre progresso e desempenho?
5. O que mudaria para facilitar o uso?

A quantidade de participantes e os critérios de avaliação serão definidos pela equipe antes da execução.

## 7. Registro de execução

Preencher somente após realizar cada teste.

| Data | ID do teste | Versão/ambiente | Resultado observado | Situação | Evidência ou problema |
|---|---|---|---|---|---|
| A preencher | A preencher | A preencher | A preencher | Não executado | A preencher |

Situações possíveis:

- Não executado.
- Aprovado.
- Reprovado.
- Bloqueado: não foi possível executar por uma dependência ou limitação.

## 8. Tratamento dos problemas

Cada problema encontrado deverá registrar:

- Tela ou funcionalidade afetada.
- Passos para reproduzir.
- Resultado esperado e observado.
- Evidência, quando disponível.
- Impacto no uso.
- Responsável pelo acompanhamento.

Após a correção, repetir o teste afetado e verificar os fluxos relacionados.

## 9. Critério proposto para conclusão

Antes da entrega funcional:

- Executar os testes dos fluxos principais.
- Corrigir falhas que impeçam leitura, prática ou consulta do progresso.
- Verificar pontuação e persistência.
- Confirmar leitura e prática offline.
- Registrar limitações e problemas ainda conhecidos.

## 10. Relação com o cronograma

A revisão visual acompanha a prototipação e o refinamento das interfaces.

Os testes funcionais serão executados conforme os recursos forem implementados. A Sprint 5, de 11/11 a 29/11/2026, concentra testes de usabilidade, correções e preparação da entrega final.

Este documento é um plano. Não declara que os testes já foram executados.