---
tags:
  - Cohort
---
Esta entre [[Explicabilidade Local]] e [[Explicabilidade global]]. Onde usa as técnicas usadas de explicabilidade global aplicando em um pequeno conjunto de amostras. **A principal vantagem é que uma explicação cohort pode ser comparada com outra cohort podendo gerar insights sobre o comportamento global do modelo** que podem não ser aparentes se somente usássemos explicabilidades globais. **Essas comparações são uteis para testar e validar imparcialidades do modelo**.

Tecnicas *fairness* ou tecnicas de justiça procuram validar a performance do modelo comparando uma predição de cohort (corte) com outra, com a finalidade de garantir que o modelo gere predições semelhantes baseado em fatores relevantes. Um exemplo clássico seria como um modelo determinaria se um individuo pode receber ou não um empréstimo treinado nos dados históricos dos EUA, onde contém discriminação racial presente. Analisar a imparcialidade do modelo nos diria se o modelo esta aprendendo esta discriminação racial, ou se estaria baseando suas decisões no histórico de pagamentos do individuo. 