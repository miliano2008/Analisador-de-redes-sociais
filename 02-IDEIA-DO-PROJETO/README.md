 NEXO — Ponto de Conexão

1. Visão Geral

O NEXO — Ponto de Conexão é um projeto acadêmico voltado para a **análise de redes aplicada a transações financeiras**.

A proposta do projeto é transformar uma base de transações financeiras em uma estrutura de grafo, permitindo representar visualmente e matematicamente as relações existentes entre diferentes contas.

Dentro dessa representação:

- Cada conta financeira é representada como um nó (vértice);
- Cada transação é representada como uma aresta que conecta duas contas;
- O sentido da transação é representado pela direção da aresta;
- O valor da transação pode ser utilizado como peso da conexão;
- Os relacionamentos entre as contas formam uma rede que pode ser analisada por meio de conceitos de Teoria dos Grafos, Álgebra Linear e Matemática Computacional.

O objetivo do NEXO não é simplesmente apresentar uma lista de transações, mas permitir uma visão estrutural da rede, ajudando a identificar contas que possuem maior relevância dentro do conjunto de relacionamentos analisado.

---

2. Problema

Grandes volumes de transações financeiras podem gerar uma quantidade significativa de dados, tornando difícil identificar manualmente quais contas possuem maior importância dentro da estrutura de relacionamentos.

Uma conta pode, por exemplo:

- receber recursos de diversas contas;
- enviar recursos para diversas contas;
- conectar diferentes grupos de contas;
- participar de cadeias de transações;
- apresentar mudanças significativas em sua posição dentro da rede;
- fazer parte de uma comunidade específica de contas;
- atuar como uma conexão entre diferentes grupos.

Quando essas informações são analisadas apenas como uma tabela de transações, os relacionamentos existentes podem ser difíceis de visualizar.

O NEXO surge com a proposta de transformar esses dados tabulares em uma **rede de relacionamentos**, permitindo analisar não apenas cada transação individualmente, mas também a posição estrutural de cada conta dentro da rede.

---

# 3. Objetivo do Projeto

O principal objetivo do NEXO é desenvolver uma ferramenta capaz de:

1. Receber dados de transações financeiras;
2. Organizar esses dados em uma estrutura adequada para análise;
3. Construir uma representação em forma de grafo;
4. Identificar contas e conexões relevantes dentro da rede;
5. Calcular métricas de análise de redes;
6. Identificar padrões estruturais;
7. Detectar comunidades de contas;
8. Permitir a exploração das conexões entre contas;
9. Comparar alterações estruturais entre diferentes períodos;
10. Apresentar os resultados de forma visual e compreensível.

O sistema deve servir como uma ferramenta de apoio à análise, fornecendo informações que possam orientar uma investigação humana.

O NEXO não deve determinar automaticamente que uma conta com determinada característica é fraudulenta. As métricas e padrões encontrados devem ser tratados como indicadores para análise e investigação.

---

4. Conceito Matemático

A estrutura principal do NEXO é baseada na representação de uma rede por meio de um grafo:

G = (V, E)

Onde:

- V representa o conjunto de vértices ou nós;
- E representa o conjunto de arestas ou conexões.

No contexto do NEXO:

V = conjunto de contas

E = conjunto de transações

Exemplo:

Se a conta A001 envia R$ 500,00 para a conta A002:

```text
A001 ───────────────→ A002
       R$ 500,00
```

A conta A001 representa a origem da transação, enquanto A002 representa o destino.

Quando diversas transações são adicionadas, a estrutura passa a formar uma rede:

```text
             A002
            ↗    ↘
         A001    A005
           ↓      ↑
          A003 ───┘
```

Essa representação permite analisar a estrutura da rede como um todo.

---

# 5. Representação das Transações

Cada transação possui informações que podem ser utilizadas na construção do grafo.

Entre os principais dados considerados estão:

- Conta de origem;
- Conta de destino;
- Valor da transação;
- Data;
- Horário;
- Tipo da transação.

Uma transação pode ser representada conceitualmente da seguinte forma:

```text
Origem → Destino
Valor
Data
Hora
Tipo
```

Essas informações são mantidas na base de dados e podem ser relacionadas às conexões representadas no grafo.

Dessa maneira, o sistema permite sair de uma visão exclusivamente tabular e chegar a uma visão estrutural da rede.

---

# 6. Métricas de Análise

O NEXO utiliza métricas de Teoria dos Grafos para identificar diferentes características das contas dentro da rede.

## 6.1 Degree

O **Degree** representa a quantidade de conexões de um determinado nó.

Em um grafo direcionado, podemos analisar separadamente:

### In-Degree

Representa a quantidade de conexões que chegam à conta.

Exemplo:

```text
A001 → A005
A002 → A005
A003 → A005
```

Nesse caso:

```text
In-Degree(A005) = 3
```

A conta A005 recebeu conexões de três contas diferentes.

### Out-Degree

Representa a quantidade de conexões que saem da conta.

Exemplo:

```text
A005 → A006
A005 → A007
A005 → A008
```

Nesse caso:

```text
Out-Degree(A005) = 3
```

---

# 7. Fluxo Financeiro

Além da quantidade de conexões, o NEXO considera os valores financeiros associados às transações.

Entre os indicadores utilizados estão:

### InValue

Representa o valor financeiro total recebido por uma conta.

### OutValue

Representa o valor financeiro total enviado por uma conta.

### Flow

Representa o fluxo financeiro total associado à conta, considerando entradas e saídas.

De forma conceitual:

```text
Flow = InValue + OutValue
```

Esses indicadores permitem diferenciar uma conta que possui muitas conexões, mas movimenta valores pequenos, de uma conta que possui uma quantidade menor de conexões, porém movimenta valores significativamente maiores.

---

# 8. Diferença e Imbalance

O projeto também considera a relação entre valores recebidos e enviados.

A diferença pode ser utilizada para identificar o desequilíbrio entre entrada e saída de recursos.

Conceitualmente:

```text
Diferença = |InValue - OutValue|
```

O **Imbalance** representa essa diferença em relação ao fluxo total.

Conceitualmente:

```text
Imbalance = Diferença / Flow
```

Esse indicador ajuda a compreender o comportamento financeiro estrutural de uma conta.

Uma conta pode apresentar grande volume de entradas e saídas relativamente equilibradas, enquanto outra pode apresentar uma diferença significativa entre os valores recebidos e enviados.

Essas informações devem ser utilizadas como **indicadores analíticos**, e não como uma conclusão automática sobre irregularidade.

---

# 9. Betweenness Centrality

A **Betweenness Centrality** mede a importância de um nó como intermediário ou ponte dentro da rede.

Uma conta pode não possuir o maior número de conexões, mas ainda assim ser importante porque está localizada entre diferentes grupos de contas.

Exemplo:

```text
A001 → A002 → A003
```

A002 funciona como uma conexão intermediária entre A001 e A003.

Em uma rede maior:

```text
Grupo A

A001 ── A002
          \
           A005
          /
A003 ── A004

Grupo B
```

Se A005 for responsável por conectar diferentes partes da rede, sua importância estrutural pode ser elevada.

Por isso, a Betweenness é frequentemente interpretada como uma medida relacionada à ideia de **ponte**.

---

# 10. Closeness Centrality

A **Closeness Centrality** representa a proximidade de um nó em relação aos demais nós da rede.

Uma conta com alta proximidade estrutural pode alcançar outros nós por caminhos relativamente curtos.

De forma simplificada:

- Degree → quantidade de conexões;
- Betweenness → capacidade de atuar como ponte;
- Closeness → proximidade dentro da rede.

Essas métricas analisam características diferentes e, por isso, devem ser consideradas em conjunto.

---

# 11. Comunidades — Louvain

O NEXO também utiliza análise de comunidades.

O algoritmo de **Louvain** pode ser utilizado para identificar grupos de nós que apresentam maior concentração de relacionamentos entre si.

Por exemplo:

```text
Comunidade A

A001 ── A002
 │       │
 A003 ── A004


Comunidade B

A010 ── A011
 │       │
 A012 ── A013
```

O objetivo é identificar estruturas de relacionamento dentro da rede.

Além de apresentar as comunidades, o NEXO deve permitir analisar as conexões existentes:

- dentro da própria comunidade;
- entre comunidades diferentes;
- entre contas específicas.

---

# 12. Ego-Graph

Uma das principais funcionalidades planejadas para o NEXO é o **Ego-Graph**.

O Ego-Graph permite selecionar uma conta e visualizar
