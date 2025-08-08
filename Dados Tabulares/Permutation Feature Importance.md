---
tags:
  - post-hoc
  - global
  - model-agnostic
  - pertubation-based
---
Com o modelo devidamente treinado com os dados de treinamento, permutação de uma unica feature mede o decaimento do *score* do modelo a medida que o valor desta feature é alterado aleatoriamente. 
Alterando aleatoriamente os valores deu uma feature, voce destroi a capacidade do modelo de fazer boas predições significativas. **Se o *score* do modelo for muito ruim mudando uma feature, então é possível dizer que aquela feature é considerada importante para as predições do modelo.** 


| Pros                                                                                                      | Contras                                                                                                                                                                                                                                                                  |
| --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Facil de se implementar. Scikit-learn ja fornece funções prontas.                                         | Resultados podem ser ruins quando as features são altamente correlacionadas. **Metodo funciona com features independentes                                                                                                                                                |
| Resultados intuitivos. Métodos de permutação de importância de features são fáceis de explicar e entender | O valor resultante para uma feature não significa o quão boa aquela feature é para prever algo mas sim o quão importante aquela feature é para a predição final gerada pelo mode                                                                                         |
| Funcionam bem com dados tabulares (numéricos e categóricos )                                              | Os valores das importâncias permutadas depende principalmente do embaralhamento das features, e diversas maneiras de embaralhamento também, gerando resultados possivelmente diferentes. Então, é necessário rodar múltiplas vezes para ter uma resposta mais assertiva. |
