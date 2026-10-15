# ENG4U
Plataforma de ensino do Abrindo Portas 🔑

Aplicativo mobile proposto para apoiar o projeto de extensão **Abrindo Portas: Inglês para todos**, da **Universidade Tecnológica Federal do Paraná — Campus Cornélio Procópio**.

Projeto desenvolvido na disciplina **Certificadora de Competência 2**, do curso de Engenharia de Computação.

## Sobre o projeto

O Abrindo Portas busca democratizar o acesso ao aprendizado de inglês para a comunidade e conta com a produção de apostilas didáticas.

Nossa proposta é transformar esse conteúdo em uma experiência de estudo interativa, permitindo que os alunos revisem as lições, pratiquem exercícios e acompanhem seu progresso fora da sala de aula.

O aplicativo complementará as atividades do projeto de extensão, mantendo o alinhamento com seu material didático.

## Objetivo

Desenvolver um aplicativo mobile, inicialmente para Android, que organize o conteúdo das apostilas e ofereça recursos de estudo autônomo, com prioridade para leitura e prática offline.

## Funcionalidades previstas

- **Leitor de conteúdo:** teoria, vocabulário, regras gramaticais e exemplos.
- **Organização didática:** navegação por módulos, capítulos e lições.
- **Busca local:** pesquisa de vocabulários, traduções e regras gramaticais.
- **Exercícios interativos:** múltipla escolha e preenchimento de lacunas.
- **Correção imediata:** validação das respostas no dispositivo.
- **Revisão por capítulo:** quizzes com variação de questões e alternativas.
- **Acompanhamento:** registro de progresso e desempenho.
- **Persistência local:** manutenção dos registros após fechar o aplicativo.

## Situação atual

O projeto está na etapa de documentação e preparação para implementação.

| Parte | Situação |
|---|---|
| Planejamento e definição do escopo | Elaborados |
| Protótipo das interfaces | Elaborado |
| Arquitetura e diagrama de classes | Propostos |
| Implementação do aplicativo Android | Pendente |
| Estruturação e integração do conteúdo oficial | Pendente |
| Persistência e lógica dos exercícios | Pendentes |
| Testes da versão funcional | Pendentes |

As telas do protótipo utilizam conteúdo e resultados ilustrativos. Elas representam a experiência planejada e não comprovam a implementação das funcionalidades.

## Arquitetura proposta

O aplicativo será organizado em três partes:

| Parte | Responsabilidade |
|---|---|
| Interface | Apresentar conteúdos, exercícios, busca, revisão e progresso |
| Lógica local | Consultar conteúdos, validar respostas, calcular desempenho e organizar revisões |
| Dados | Disponibilizar conteúdo em JSON e persistir progresso e tentativas localmente |

As funções principais não dependerão inicialmente de um servidor externo. O conteúdo disponível no dispositivo poderá ser utilizado para leitura e prática offline.

O framework e a tecnologia de persistência ainda precisam ser confirmados pela equipe.

## Aplicação de algoritmos e estruturas de dados

- **Listas e dicionários:** organização dos conteúdos e exercícios.
- **Hierarquia lógica em árvore:** relação entre módulos, capítulos, lições e exercícios.
- **Busca textual:** localização de conteúdos no material disponível.
- **Lógica condicional:** validação de respostas e controle dos estados das atividades.
- **Cálculos de desempenho:** quantidade e percentual de acertos.
- **Aleatoriedade:** embaralhamento de alternativas e seleção de itens para revisão.

## Documentação

- [Planejamento e cronograma](docs/planejamento/)
- [Requisitos do sistema](docs/requisitos.md)
- [Diagramas da arquitetura e modelagem](docs/diagramas/)
- [Telas e referência do protótipo](docs/prototipo/)
- [Estrutura proposta do conteúdo](docs/estrutura-conteudo.md)
- [Regras propostas para exercícios e progresso](docs/regras-exercicios.md)
- [Roteiro de testes de usabilidade](docs/testes-usabilidade.md)

## Cronograma de referência

| Sprint | Período de 2026 | Atividades planejadas |
|---|---|---|
| 1 — Modelagem e setup | 17/09 a 29/09 | Escolha do framework, prototipação e estruturação do conteúdo em JSON |
| 2 — Motor de dados e interface base | 30/09 a 13/10 | Navegação, leitura dos dados e interface do leitor |
| 3 — Exercícios e algoritmos | 14/10 a 27/10 | Validação de respostas, busca textual e interface dos exercícios |
| 4 — Progresso e refinamento | 28/10 a 10/11 | Persistência, embaralhamento e refinamento visual |
| 5 — Testes e entrega | 11/11 a 29/11 | Testes, correções, geração da versão final e apresentação |

Este é o cronograma original de referência. As datas não indicam conclusão automática das atividades; pendências e reprogramações devem ser registradas conforme o andamento real.

## Equipe

| Integrante | Responsabilidade prevista no planejamento |
|---|---|
| Thiago Guilherme Curo Molina | Gestão, arquitetura, revisão de código e suporte técnico |
| Mateus Rodrigues Meretica | Lógica, estrutura de dados e persistência |
| Felipe Xavier Lorevice | Lógica, estrutura de dados e persistência |
| Daniella Lima de Oliveira | Interface, integração, organização do conteúdo e usabilidade |
| Claudinei Soares Junior | Interface, integração, organização do conteúdo e usabilidade |

As responsabilidades podem envolver colaboração entre os integrantes. As contribuições realizadas serão registradas nos documentos e no histórico do repositório.

## Execução

Ainda não há uma versão funcional do aplicativo Android disponível neste repositório.

As instruções de instalação, configuração e execução serão acrescentadas junto à implementação.

## Material didático

A estrutura definitiva das lições seguirá as apostilas disponibilizadas pelo projeto de extensão.

Os exemplos usados na prototipação são demonstrativos e não devem ser confundidos com o conteúdo oficial. Na incorporação do material, serão preservados os créditos e as condições de uso informadas pelo projeto.