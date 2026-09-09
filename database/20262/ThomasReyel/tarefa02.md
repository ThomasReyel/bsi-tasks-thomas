## Questão 1
**Resposta:**

Entidade: É um objeto que existe e é parte do negócio seja ele um objeto real ou abstrato (ex: carro ou venda). Uma entidade é um conjunto de atributos

Atributos: São características comuns a instâncias das entidades. São divididas em 2 tipos
- Simples: É atômico (ex: Idade: numérico; Nome: cadeia de caracteres).
- Composto: Contém sub atributos que compõem o atributo (ex: Endereço: (rua, número, bairro, cidade)).

Relacionamento: são a forma e a quantidade na qual as entidades se relacionam entre si. pra ver a cardinalidade sempre se pergunte "1 instância dessa está em quantas instâncias da outra". OBS: Na cardinalidade a relação só é total quando não existe a opção de uma instância de relacionar. E parcial se possuir a opção de uma instância se relacionar.

## Questão 2
**Resposta:**

- Notação de Chen: Criada por Peter Chen (o pioneiro do modelo), utiliza formas geométricas distintas para cada elemento.
- Notação Pé de Galinha (Crow's Foot): Focada na legibilidade, posiciona os atributos dentro do bloco da entidade e utiliza símbolos 
na extremidade das linhas. Essa é a notação utilizada no mermaid, por exemplo.
- Notação UML: Adaptada da orientação a objetos, utiliza caixas de classes para representar entidades e multiplicidades numéricas.

## Questão 3
**Resposta: **

```mermaid
erDiagram

CLIENTE{

  int id
  string código
  string nome
  string email
}

FUNCIONÁRIO{

  int id
  string código
  string nome
  string email
  string função
}

TAREFA{

  int id
  string código
  string descrição
  string prioridade
  string situação
  string horas
}

SPRINT {

  int id
  int numero
  date data_inicio
  date data_final
}

RELEASE {

  int id
  string versão
  date data_planejada
}
EQUIPE{

  int id
  string nome
}

PROJETO{

  int id
  string código
  date data_inicio
  date data_final
}

FUNCIONÁRIO }|--|| EQUIPE : trabalha
TAREFA }|--|| EQUIPE : resolve
TAREFA }|--|| PROJETO : pertence
EQUIPE ||--|{ SPRINT : possui
TAREFA }|--|| RELEASE : agrupa
RELEASE }|--|| PROJETO : possui
CLIENTE ||--|{ PROJETO : possui
```

## Questão 04
**Resposta:**

```mermaid
erDiagram

CLIENTE{
  int id PK
  string código
  string nome
  string email
}

FUNCIONÁRIO{
  int id PK
  int id_equipe FK
  string código
  string nome
  string email
  string função
}

TAREFA{
  int id PK
  int id_equipe FK
  int id_projeto FK
  int id_release FK
  string código
  string descrição
  string prioridade
  string situação
  string horas
}

SPRINT {
  int id PK
  int id_equipe FK
  int numero
  date data_inicio
  date data_final
}

RELEASE {
  int id PK
  int id_projeto FK
  string versão
  date data_planejada
}

EQUIPE{
  int id PK
  string nome
}

PROJETO{
  int id PK
  int id_cliente FK
  string código
  date data_inicio
  date data_final
}

FUNCIONÁRIO }|--|| EQUIPE : trabalha
TAREFA }|--|| EQUIPE : resolve
TAREFA }|--|| PROJETO : pertence
EQUIPE ||--|{ SPRINT : possui
TAREFA }|--|| RELEASE : agrupa
RELEASE }|--|| PROJETO : possui
CLIENTE ||--|{ PROJETO : possui
```



