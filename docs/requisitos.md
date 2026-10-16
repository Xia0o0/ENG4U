# Requisitos do sistema — Abrindo Portas

Este documento descreve os requisitos previstos para o aplicativo de apoio ao projeto de extensão **Abrindo Portas: Inglês para todos**, conforme o planejamento acadêmico.

As interfaces estão prototipadas. A representação de uma funcionalidade nas telas não significa que sua implementação esteja concluída.

Os critérios de aceitação detalham como verificar os requisitos durante o desenvolvimento.

## 1. Requisitos funcionais

| ID | Requisito | Descrição | Critério de aceitação |
|---|---|---|---|
| RF01 | Disponibilizar o material didático | Apresentar textos, vocabulários, regras gramaticais e exercícios das apostilas do projeto. | O conteúdo incorporado pode ser consultado no aplicativo e corresponde ao material disponibilizado pelo projeto. |
| RF02 | Organizar o conteúdo | Estruturar o material em módulos, capítulos, lições e exercícios. | Cada conteúdo está associado ao seu nível na hierarquia. |
| RF03 | Permitir navegação | Permitir selecionar módulos, capítulos e lições e retornar aos níveis anteriores. | O aluno consegue acessar uma lição pelo módulo e retornar à listagem correspondente. |
| RF04 | Oferecer leitor dinâmico | Apresentar o conteúdo didático em uma interface adequada à leitura no celular. | Textos, exemplos e demais elementos podem ser consultados integralmente, com rolagem quando necessária. |
| RF05 | Buscar conteúdo local | Pesquisar vocabulários, traduções e regras gramaticais no conteúdo disponível no dispositivo. | A busca apresenta correspondências e informa quando não encontra resultados. |
| RF06 | Disponibilizar prática por lição | Associar exercícios de fixação ao conteúdo estudado. | O aluno consegue acessar as atividades relacionadas à lição escolhida. |
| RF07 | Responder múltipla escolha | Permitir selecionar uma alternativa e enviar a resposta. | A alternativa enviada é comparada ao gabarito do exercício. |
| RF08 | Responder lacunas | Permitir inserir uma resposta textual para completar um enunciado. | A resposta é comparada às respostas aceitas definidas no exercício. |
| RF09 | Corrigir imediatamente | Validar as respostas no dispositivo e informar acerto ou erro. | O feedback é apresentado após o envio, sem depender de servidor externo. |
| RF10 | Calcular desempenho | Calcular a quantidade e o percentual de acertos. | O resultado corresponde às respostas registradas na atividade, sem duplicidade de contagem. |
| RF11 | Registrar progresso | Acompanhar o avanço na leitura e nas atividades. | O aplicativo identifica o estado das lições conforme a regra de conclusão definida pela equipe. |
| RF12 | Salvar registros localmente | Persistir progresso e pontuações no dispositivo. | Os registros permanecem disponíveis após fechar e reabrir o aplicativo. |
| RF13 | Apresentar dashboard | Mostrar a conclusão do material e o desempenho nos exercícios. | Os indicadores correspondem aos registros locais e distinguem conclusão de atividade e percentual de acertos. |
| RF14 | Oferecer revisão por capítulo | Disponibilizar quizzes baseados no capítulo estudado. | Os itens apresentados correspondem ao capítulo escolhido. |
| RF15 | Variar as revisões | Embaralhar alternativas e selecionar itens para revisão conforme a estratégia adotada. | A ordem pode variar sem alterar os gabaritos nem apresentar itens de capítulos indevidos. |

## 2. Requisitos não funcionais

| ID | Requisito | Descrição | Critério de aceitação |
|---|---|---|---|
| RNF01 | Prioridade para Android | Desenvolver o MVP inicialmente para Android. | A versão final pode ser instalada e executada no ambiente Android definido pela equipe. |
| RNF02 | Funcionamento offline | Permitir leitura e prática com o conteúdo disponível no dispositivo. | As atividades principais podem ser realizadas com a conexão à internet desativada. |
| RNF03 | Processamento local | Executar busca, validação, cálculos e controle do progresso no dispositivo. | As operações principais não exigem chamadas a uma API externa. |
| RNF04 | Persistência local | Manter os registros de estudo em armazenamento persistente. | Progresso e pontuações sobrevivem ao encerramento e à reabertura do aplicativo. |
| RNF05 | Usabilidade | Oferecer navegação intuitiva e leitura confortável em dispositivos móveis. | Os testes verificam se o aluno consegue localizar, ler e praticar uma lição. |
| RNF06 | Consistência dos dados | Manter coerência entre respostas, gabaritos, resultados e progresso. | As informações permanecem consistentes entre as telas e após o embaralhamento das alternativas. |
| RNF07 | Qualidade da entrega | Verificar os fluxos principais e corrigir os problemas encontrados antes da entrega. | A versão final permite concluir os fluxos de leitura, prática e consulta do progresso sem falhas impeditivas conhecidas. |

## 3. Restrições e decisões técnicas previstas

| ID | Definição | Aplicação |
|---|---|---|
| RT01 | Aplicativo stand-alone | As funções principais operam de forma autônoma no dispositivo. |
| RT02 | Conteúdo em JSON | O material didático é representado em arquivos estruturados, inicialmente incluídos no aplicativo. |
| RT03 | Listas e dicionários | Organizam as coleções de conteúdos, exercícios e seus atributos. |
| RT04 | Hierarquia lógica em árvore | Representa a relação Módulo → Capítulo → Lição → Exercício. |
| RT05 | Busca textual | Utiliza comparação de textos e filtros. Busca binária é uma possibilidade apenas quando os dados estiverem adequadamente ordenados. |
| RT06 | Validação condicional | Compara respostas com gabaritos e controla o estado dos exercícios. |
| RT07 | Aleatoriedade | Utiliza embaralhamento, como Fisher–Yates, ou seleção aleatória de itens para revisão. |
| RT08 | Persistência a definir | A tecnologia deve ser compatível com o framework escolhido. SQLite e AsyncStorage são alternativas citadas no planejamento, não decisões confirmadas. |
| RT09 | Framework a definir | A implementação pode ser nativa ou multiplataforma. React Native e Flutter aparecem como possibilidades no planejamento. |
| RT10 | Nuvem opcional | Uma fonte remota pode distribuir conteúdo, sem ser obrigatória para ler e praticar o material já disponível localmente. |
| RT11 | Custos previstos | Priorizar ferramentas gratuitas e tecnologias abertas, sem contratação inicial de hospedagem dedicada. |
| RT12 | Prazo do MVP | A entrega da primeira versão funcional está prevista para 29/11/2026. |

## 4. Regras que precisam ser definidas pela equipe

Antes da implementação, a equipe deverá detalhar:

- Quando uma lição passa a ser considerada iniciada ou concluída.
- Quais respostas textuais são aceitas nos exercícios de lacunas.
- Como tratar diferenças de maiúsculas, minúsculas, espaços e pontuação.
- Como registrar novas tentativas e calcular o desempenho apresentado.
- Quantos itens compõem cada revisão e como serão selecionados.
- Qual framework será utilizado e qual tecnologia armazenará o progresso.

Essas definições complementam a implementação sem alterar o escopo principal.

## 5. Correspondência com o cronograma

| Sprint | Período de 2026 | Atividades planejadas |
|---|---|---|
| 1 — Modelagem e setup | 17/09 a 29/09 | Escolha do framework, prototipação e estruturação do material em JSON. |
| 2 — Motor de dados e interface base | 30/09 a 13/10 | Navegação, leitura dos dados JSON e interface inicial do leitor. |
| 3 — Exercícios e algoritmos | 14/10 a 27/10 | Validação de respostas, busca textual e telas dos exercícios. |
| 4 — Progresso e refinamento | 28/10 a 10/11 | Salvamento de progresso e pontuações, embaralhamento e refinamento visual. |
| 5 — Testes e entrega | 11/11 a 29/11 | Testes de usabilidade, correções, geração da versão final e apresentação. |

As datas representam o planejamento original. O andamento real e eventuais reprogramações devem ser registrados separadamente.

## 6. Limites do escopo atual

Não estão previstos no MVP:

- Cadastro e autenticação de usuários.
- Painel administrativo ou painel de professores.
- Chatbot ou correção por inteligência artificial.
- Pagamentos, assinaturas ou ranking.
- Sincronização de progresso entre dispositivos.

O foco é o estudo individual com conteúdo didático, exercícios, revisão e acompanhamento local.
