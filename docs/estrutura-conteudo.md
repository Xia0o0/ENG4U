# Estrutura proposta do conteúdo — ENG4U

## 1. Objetivo

Definir uma organização inicial em JSON para o material didático do projeto Abrindo Portas: Inglês para todos.

A estrutura permitirá que o aplicativo apresente conteúdos e exercícios localmente, seguindo a hierarquia:

**Módulo → Capítulo → Lição → Exercício**

**Status:** proposta de estruturação; integração ao aplicativo pendente.

Os exemplos deste documento são demonstrativos e não representam conteúdo oficial das apostilas.

## 2. Organização dos dados

| Elemento | Responsabilidade |
|---|---|
| Módulo | Agrupar capítulos de uma etapa de aprendizagem. |
| Capítulo | Agrupar lições relacionadas a um tema. |
| Lição | Apresentar conteúdo didático e seus exercícios. |
| Exercício | Definir a atividade, seu gabarito e a explicação. |
| Alternativa | Representar uma opção de múltipla escolha. |

Progresso e tentativas não fazem parte do conteúdo didático estático. Esses registros serão armazenados separadamente no dispositivo.

## 3. Campos principais

### Documento

| Campo | Tipo | Finalidade |
|---|---|---|
| versaoEstrutura | Número inteiro | Identificar a versão do formato JSON. |
| versaoConteudo | Texto | Identificar a versão do material distribuído. |
| demonstrativo | Booleano | Informar se o material é apenas ilustrativo. |
| modulos | Lista de objetos | Reunir os módulos disponíveis. |

Os campos de versão são uma proposta técnica para facilitar alterações futuras.

### Módulo

| Campo | Tipo | Finalidade |
|---|---|---|
| id | Texto | Identificador estável do módulo. |
| titulo | Texto | Nome apresentado ao aluno. |
| ordem | Número inteiro | Posição na sequência didática. |
| capitulos | Lista de objetos | Capítulos pertencentes ao módulo. |

### Capítulo

| Campo | Tipo | Finalidade |
|---|---|---|
| id | Texto | Identificador estável do capítulo. |
| titulo | Texto | Nome apresentado ao aluno. |
| ordem | Número inteiro | Posição dentro do módulo. |
| licoes | Lista de objetos | Lições pertencentes ao capítulo. |

### Lição

| Campo | Tipo | Finalidade |
|---|---|---|
| id | Texto | Identificador estável da lição. |
| titulo | Texto | Nome apresentado ao aluno. |
| ordem | Número inteiro | Posição dentro do capítulo. |
| conteudo | Texto | Explicação didática, com exemplos e vocabulário. |
| exercicios | Lista de objetos | Atividades relacionadas à lição. |

Nesta proposta inicial, `conteudo` é textual, conforme o diagrama de classes. A representação de tabelas, imagens e outros elementos deverá ser detalhada antes da integração do material oficial.

### Exercício

| Campo | Tipo | Finalidade |
|---|---|---|
| id | Texto | Identificador estável do exercício. |
| tipo | Texto | MULTIPLA_ESCOLHA ou LACUNA. |
| enunciado | Texto | Instrução apresentada ao aluno. |
| explicacao | Texto | Orientação exibida após a correção. |
| respostasAceitas | Lista de textos | Gabaritos aceitos nos exercícios de lacuna. |
| alternativas | Lista de objetos | Opções dos exercícios de múltipla escolha. |

### Alternativa

| Campo | Tipo | Finalidade |
|---|---|---|
| id | Texto | Identificador estável da opção. |
| texto | Texto | Resposta apresentada ao aluno. |
| correta | Booleano | Indicação de que a alternativa é o gabarito. |

## 4. Exemplo demonstrativo

```json
{
  "versaoEstrutura": 1,
  "versaoConteudo": "demo-1",
  "demonstrativo": true,
  "modulos": [
    {
      "id": "mod-01",
      "titulo": "Primeiros passos",
      "ordem": 1,
      "capitulos": [
        {
          "id": "cap-01",
          "titulo": "Construindo frases",
          "ordem": 1,
          "licoes": [
            {
              "id": "lic-01",
              "titulo": "Verb to be",
              "ordem": 1,
              "conteudo": "O verbo to be pode significar ser ou estar. Usamos am com I, is com he, she e it, e are com you, we e they. Exemplo: I am a student. Tradução: Eu sou estudante.",
              "exercicios": [
                {
                  "id": "exe-01",
                  "tipo": "MULTIPLA_ESCOLHA",
                  "enunciado": "Complete: I ___ a student.",
                  "explicacao": "Com o pronome I, usamos am.",
                  "respostasAceitas": [],
                  "alternativas": [
                    {
                      "id": "alt-01",
                      "texto": "am",
                      "correta": true
                    },
                    {
                      "id": "alt-02",
                      "texto": "is",
                      "correta": false
                    },
                    {
                      "id": "alt-03",
                      "texto": "are",
                      "correta": false
                    }
                  ]
                },
                {
                  "id": "exe-02",
                  "tipo": "LACUNA",
                  "enunciado": "Complete: She ___ a teacher.",
                  "explicacao": "Com o pronome she, usamos is.",
                  "respostasAceitas": ["is"],
                  "alternativas": []
                }
              ]
            }
          ]
        }
      ]
    }
  ]
}
```

## 5. Regras de consistência propostas

- Os identificadores devem ser únicos em todo o conjunto de conteúdo.
- Os identificadores devem permanecer estáveis enquanto representarem o mesmo item.
- Alterações de título ou ordem não devem, por si só, alterar o identificador.
- Módulos, capítulos e lições devem seguir a sequência didática definida.
- Os valores de `ordem` devem ser positivos e não se repetir entre elementos do mesmo nível e agrupamento.
- Campos obrigatórios não devem apresentar texto vazio.
- Cada exercício deve pertencer a uma lição.
- Exercícios de múltipla escolha devem possuir pelo menos duas alternativas e exatamente uma correta.
- Exercícios de lacuna devem possuir pelo menos uma resposta aceita.
- A lista não utilizada pelo tipo do exercício deve permanecer vazia.
- O embaralhamento deve preservar o identificador e o gabarito de cada alternativa.
- Mudanças no gabarito ou no significado de um exercício exigem revisão de sua relação com tentativas anteriores.

Essas regras deverão ser verificadas na preparação do conteúdo e no carregamento dos dados pelo aplicativo.

## 6. Uso no aplicativo

O aplicativo deverá:

1. Carregar o arquivo JSON disponível no dispositivo.
2. Verificar sua estrutura e os campos obrigatórios.
3. Organizar os elementos pela hierarquia e pela ordem.
4. Apresentar o conteúdo selecionado.
5. Consultar os exercícios e seus gabaritos.
6. Utilizar os identificadores para relacionar conteúdo, progresso e tentativas.

O arquivo JSON poderá ser incluído nos recursos do aplicativo, permitindo leitura e prática sem conexão.

## 7. Busca local

A busca utilizará os títulos e os textos disponíveis, incluindo vocabulários, traduções e regras presentes no material.

O resultado deverá preservar a referência ao módulo, capítulo e lição de origem.

A estratégia de indexação e comparação textual será definida durante a implementação. A estrutura proposta não exige um servidor para a pesquisa.

## 8. Separação entre conteúdo e dados de estudo

| Grupo | Exemplos | Armazenamento previsto |
|---|---|---|
| Conteúdo didático | Módulos, capítulos, lições, exercícios e gabaritos | JSON |
| Dados de estudo | Estado das lições, respostas enviadas, acertos e datas | Persistência local |

Essa separação permite manter o material didático independente dos registros de uso.

A política para atualizar conteúdos sem comprometer os registros anteriores ainda deverá ser definida.

## 9. Relação com o diagrama de classes

A estrutura corresponde às classes:

- Modulo.
- Capitulo.
- Licao.
- Exercicio.
- Alternativa.

As listas aninhadas representam os relacionamentos de composição entre esses elementos.

ProgressoLicao e Tentativa serão tratados pela persistência local e referenciarão as lições e os exercícios por seus identificadores.

## 10. Integração do material oficial

Antes de incorporar as apostilas, será necessário:

- Conferir a organização real dos módulos e capítulos.
- Transcrever e revisar o conteúdo.
- Preservar os créditos do material.
- Conferir enunciados e gabaritos.
- Definir a representação de imagens, tabelas e outros recursos presentes.
- Validar os arquivos JSON e sua apresentação no aplicativo.

## 11. Relação com o cronograma

A estruturação inicial do conteúdo em JSON está prevista na Sprint 1.

A leitura e apresentação dos dados fazem parte da Sprint 2.

Os exercícios e seus gabaritos apoiam a implementação da Sprint 3, enquanto os identificadores permitem integrar progresso e pontuação na Sprint 4.

Esta documentação descreve a proposta de organização e não declara que essas etapas já foram implementadas.