# Protótipo das interfaces — ENG4U

## 1. Objetivo

Apresentar a proposta visual do aplicativo de apoio ao projeto de extensão Abrindo Portas: Inglês para todos.

As telas servirão como referência para a implementação do aplicativo Android e para a apresentação acadêmica.

## 2. Situação atual

Protótipo visual elaborado com conteúdo, progresso e resultados ilustrativos.

As telas não comprovam a implementação de busca, correção, cálculos, persistência ou funcionamento offline.

A navegação demonstrativa estará disponível conforme as conexões configuradas no Figma.

## 3. Acesso ao protótipo

[Visualizar as telas do ENG4U no Figma](https://www.figma.com/proto/SxCsOgbautun5fREI3Zk6s/Abrindo-Portas-Prototype?node-id=0-1)

[Consultar as imagens das telas neste repositório](telas/)

O protótipo apresenta as interfaces propostas para o aplicativo Android, com conteúdo e resultados ilustrativos.

A versão compartilhada permite visualizar as telas, sem navegação interativa configurada. O acesso público está definido como somente visualização.

As interfaces servirão como referência para a implementação do aplicativo.

## 4. Telas e responsabilidades

| Tela | Finalidade | Elementos principais |
|---|---|---|
| Início | Apresentar um resumo do estudo | Progresso, lição em andamento e atalhos |
| Módulos | Organizar os conjuntos de conteúdo | Lista de módulos, descrições e avanço ilustrativo |
| Capítulos e lições | Apresentar a sequência didática | Capítulos, lições, estados de estudo e acesso à revisão |
| Leitor da lição | Disponibilizar o conteúdo didático | Objetivo, explicação, regras, exemplos e acesso à prática |
| Busca | Representar a localização de conteúdos | Campo de pesquisa e resultados por tipo |
| Múltipla escolha | Representar a seleção de uma resposta | Enunciado, alternativas e botão de verificação |
| Preenchimento de lacunas | Representar a entrada de uma resposta textual | Enunciado, campo e botão de verificação |
| Feedback de acerto | Confirmar e explicar a resposta correta | Identificação de acerto e explicação |
| Feedback de erro | Orientar a correção | Resposta enviada, gabarito e explicação |
| Resultado | Resumir o desempenho na atividade | Acertos, percentual e opções para continuar |
| Progresso | Diferenciar avanço e desempenho | Lições concluídas e indicadores por capítulo |
| Revisão por capítulo | Permitir escolher o conteúdo a revisar | Seleção de capítulo e acesso à revisão |

Estados adicionais, como busca sem resultados e alternativa não selecionada, podem ser representados como variações dessas telas.

## 5. Fluxo principal de estudo

1. Acessar a tela inicial.
2. Selecionar um módulo.
3. Localizar um capítulo e uma lição.
4. Consultar o conteúdo no leitor.
5. Acessar a prática.
6. Responder a um exercício.
7. Consultar o feedback.
8. Continuar a atividade.
9. Visualizar o resultado.
10. Retornar ao conteúdo ou às lições.

## 6. Fluxos complementares

### Continuação do estudo

Início → Continuar estudando → Leitor da lição.

### Busca

Buscar → Resultados → Conteúdo correspondente.

### Revisão

Revisar → Seleção de capítulo → Exercícios → Feedback → Resultado.

A revisão também pode ser acessada pelos botões da tela de capítulos e lições.

### Acompanhamento

Progresso → Consulta dos indicadores de conclusão e desempenho.

Esses percursos descrevem a navegação proposta. As conexões efetivamente disponíveis devem ser conferidas no protótipo.

## 7. Estados visuais

O protótipo representa:

- Lições concluídas, em andamento e não iniciadas.
- Alternativa selecionada.
- Campo de resposta vazio.
- Botão de verificação habilitado ou desabilitado.
- Resposta correta e incorreta.
- Resultado de uma prática.
- Capítulo selecionado para revisão.

Os valores exibidos são fixos e demonstrativos.

## 8. Diretrizes visuais

- Interface em português do Brasil.
- Conteúdo de inglês acompanhado de explicações e traduções.
- Identidade visual consistente entre as telas.
- Destaque para a ação principal de cada etapa.
- Navegação e controles de retorno identificáveis.
- Feedback com textos e símbolos, além das cores.
- Distinção entre conclusão de atividades e percentual de acertos.
- Layout pensado para dispositivos móveis.

A legibilidade e a facilidade de navegação deverão ser avaliadas conforme o plano de testes.

## 9. Relação com os requisitos

| Funcionalidade prevista | Representação no protótipo |
|---|---|
| Leitura do material didático | Leitor da lição |
| Organização hierárquica | Módulos, capítulos e lições |
| Busca local | Campo de busca e resultados ilustrativos |
| Exercícios interativos | Múltipla escolha e lacunas |
| Correção imediata | Estados de acerto e erro |
| Acompanhamento de progresso | Início e tela de progresso |
| Revisão por capítulo | Seleção de capítulo e reutilização das telas de exercícios |

## 10. Limites desta etapa

- O conteúdo demonstrativo não deve ser identificado como apostila oficial.
- Resultados e indicadores não representam dados reais de alunos.
- A correção real dependerá da implementação.
- A persistência dependerá da implementação.
- O funcionamento offline é uma característica planejada do aplicativo Android, não uma garantia do ambiente de apresentação do protótipo.
- Telas repetidas para diferentes questões não precisam ser desenhadas individualmente quando utilizarem o mesmo formato.

## 11. Organização das imagens

Sugestão de nomes:

| Arquivo | Tela |
|---|---|
| 01-inicio.png | Início |
| 02-modulos.png | Módulos |
| 03-capitulos-licoes.png | Capítulos e lições |
| 04-leitor.png | Leitor da lição |
| 05-busca.png | Busca |
| 06-multipla-escolha.png | Múltipla escolha |
| 07-lacuna.png | Preenchimento de lacunas |
| 08-feedback-acerto.png | Feedback de acerto |
| 09-feedback-erro.png | Feedback de erro |
| 10-resultado.png | Resultado |
| 11-progresso.png | Progresso |
| 12-revisao.png | Revisão por capítulo |

Os nomes devem corresponder aos arquivos realmente enviados. Estados adicionais podem receber nomes próprios.

## 12. Próximos passos

- Revisar a consistência das interfaces e conexões.
- Avaliar o protótipo com as tarefas propostas no plano de testes.
- Adaptar o conteúdo à estrutura oficial das apostilas.
- Implementar as telas na tecnologia escolhida.
- Integrar leitura, busca, exercícios e persistência local.