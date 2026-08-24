Trama - Mapeamento e Análise de Redes de Influência

 1. Visão Geral

O Trama é um projeto que tem como objetivo analisar redes de conexões entre pessoas ou entidades.

A ideia é transformar essas conexões em um grafo, permitindo visualizar a rede e descobrir quais pessoas ou entidades possuem maior importância dentro dela.

Para isso, serão utilizadas métricas de análise de redes, como Degree, Betweenness e Closeness.

---

 2. Problema

Em uma rede com muitas pessoas e conexões, pode ser difícil perceber quem realmente tem influência ou quem é importante para manter diferentes grupos conectados.

Uma pessoa pode ter muitas conexões, mas outra, mesmo tendo poucas, pode ser responsável por ligar dois grupos diferentes.

Por isso, o projeto busca responder:

> Como identificar as pessoas ou entidades mais importantes dentro de uma rede analisando suas conexões?

---

 3. Solução Proposta

O Trama irá receber dados sobre as conexões e transformar essas informações em um grafo.

No grafo:

- os nós representam pessoas ou entidades;
- as arestas representam as conexões;
- os pesos podem representar a frequência ou intensidade das conexões.

Depois disso, o sistema irá analisar a rede e calcular as métricas de centralidade para encontrar os elementos mais relevantes.

---

 4. Objetivo Geral

Criar uma ferramenta capaz de representar e analisar uma rede de conexões, mostrando quais elementos possuem maior importância dentro dela.

---

 5. Objetivos Específicos

- Criar uma representação da rede utilizando grafos;
- Analisar as conexões entre os nós;
- Calcular métricas de centralidade;
- Identificar os nós mais influentes;
- Encontrar nós que funcionam como ligação entre diferentes grupos;
- Mostrar os resultados de forma visual;
- Comparar diferentes redes;
- Facilitar a interpretação dos dados.

---

 6. Métricas Utilizadas

 Degree

Mostra quantas conexões diretas um determinado nó possui.

Pergunta que responde:

> Quem possui mais conexões?

 Betweenness

Mostra quais nós aparecem com mais frequência nos caminhos entre outros nós.

Pergunta que responde:

> Quem funciona como uma ponte entre diferentes grupos?

 Closeness

Analisa o quão próximo um nó está dos demais elementos da rede.

Pergunta que responde:

> Quem consegue chegar aos outros nós com mais facilidade?

---

 7. Diferencial do Projeto

Uma das principais ideias do NetLens é criar um **Detector de Pontes Frágeis**.

O sistema irá procurar nós que, mesmo tendo poucas conexões, possuem uma posição importante na estrutura da rede.

Esses nós podem funcionar como uma ligação entre grupos diferentes.

Se esse nó deixar de existir, parte da rede pode perder sua conexão com outra parte.

Isso permite encontrar pessoas ou entidades que parecem pouco importantes, mas que possuem um papel importante na rede.

---

 8. Visualização

O projeto terá uma visualização da rede para facilitar a análise.

O usuário poderá visualizar:

- os nós;
- as conexões;
- os grupos;
- os nós mais influentes;
- as pontes entre grupos;
- as métricas calculadas.

Os nós considerados mais importantes poderão ser destacados na visualização.

---

9. Comparação de Redes

Outra funcionalidade planejada será a comparação entre duas redes.

Por exemplo:

- uma rede antes e depois de uma mudança;
- duas organizações diferentes;
- duas comunidades;
- uma rede em períodos diferentes.

A comparação permitirá observar o que mudou na estrutura da rede e quais nós ganharam ou perderam importância.

---

 10. Possíveis Aplicações

O projeto pode ser utilizado para analisar diferentes tipos de redes, como:

- Redes sociais;
- Redes corporativas;
- Redes acadêmicas;
- Redes de fornecedores;
- Redes de comunicação;
- Comunidades;
- Redes com comportamentos considerados suspeitos.

---

 11. Exemplo

Imagine uma rede com cinco pessoas:

Ana, Bruno, Carla, Diego e Eduardo.

Carla possui poucas conexões, porém é responsável por conectar dois grupos que não possuem ligação direta.

Nesse caso, Carla pode apresentar um valor alto de Betweenness.

Mesmo tendo menos conexões que outras pessoas, ela possui uma função importante para manter a rede conectada.

Esse é um dos tipos de situação que o NetLens pretende encontrar.

---

 12. Tecnologias Planejadas

 Backend

- Python
- NetworkX
- Pandas
- FastAPI

 Frontend

- React
- D3.js ou Cytoscape.js
- Plotly

---

 13. Resultado Esperado

Ao final do projeto, esperamos ter uma ferramenta capaz de receber dados de uma rede, montar o grafo, calcular as métricas e apresentar os resultados de uma forma simples de entender.

A ideia é que o usuário consiga visualizar a rede e identificar rapidamente os nós mais importantes e as principais conexões entre os grupos.

---

 14. Status

 Projeto em desenvolvimento.

 Próximas etapas

- [ ] Definir como os dados serão armazenados;
- [ ] Criar o modelo do grafo;
- [ ] Implementar Degree;
- [ ] Implementar Betweenness;
- [ ] Implementar Closeness;
- [ ] Criar a visualização da rede;
- [ ] Criar o ranking dos nós;
- [ ] Desenvolver o Detector de Pontes Frágeis;
- [ ] Criar a comparação entre redes;
- [ ] Realizar testes.
