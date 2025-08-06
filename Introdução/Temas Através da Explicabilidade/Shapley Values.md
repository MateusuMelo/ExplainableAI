Baseado na teoria do jogo, proposta por Lloyd Shapley e publicada em 1951. Shapley analisa como cada feature influencia na predição do modelo gerando varias predições baseadas em subconjuntos de features usadas pelos modelos e comparando seus resultados com os valores preditos. 

Shapley podem ser descritos de duas formas: [[Shapley Coalitions]] e [[Shapley paths]]


## Funcionamento

### Por Coalizão

Originalmente Shapley foi formulado para descobrir uma maneira de dividir o pagamento justo para todos os jogadores de um jogo cooperativo. Em contexto de *ML* consideramos o **pagamento** como a saída da função do modelo $v$  e o conjunto de todas as features do modelo $N$ como os **jogadores**. 
Calcular Shapley depende dos resultados de $v$ para uma coalizão ([[Shapley Coalitions]]) de features, onde cada subconjunto de features $N$ é chamado de $S$ . Dentro de uma cohort([[Explicabilidade Cohort]]) $S$, denominamos o valor Shapley atribuído a uma feature $i$ como $s_i$. A formula para calcular individualmente os valores Shapley de $i$ por coalizão:

$$
s_i = \frac{1}{|N|!} \sum_{S \subseteq N \setminus \{i\}} |S|! \cdot (|N| - |S| - 1)! \left[ v(S \cup \{i\}) - v(S) \right]
$$

Resumidamente, Shapley value é o calculo marginal de contribuição da coalizão com a feature $i$ e sem $i$ (como, $v(S\cup i)-v(S)$) somados com todas coalizões que não possuem $i$ (como, ${S \subseteq N \setminus \{i\}}$). Cada um desses cálculos marginais são ponderados por todas as possibilidades possíveis de se obter este calculo marginal (em, $|S|!(|N| - |S| -1)!$) divididos por todas as possíveis coalizões ($|N|!$). No total, a soma de todas as atribuições de features devem ser iguais a $v(N)$ 


### Por Paths

Alternativamente, podemos calcular Shapley usando a formulação [[Shapley paths]] que é mais comum para Explicabilidade, definindo uma ordem(permutação) de features (*paths*) como $R$, e $P_i^R$ cada conjunto de features contidas em $N$, ou *paths* parciais que precedem $i$ na ordem de $R$. Então a formula para calcular Shapley de cada $i$ usando método paths:

$$
s_i = \frac{1}{|N|!} \sum_{R} \left[ v\left(P_i^R \cup \{i\}\right) - v\left(P_i^R\right) \right]
$$
## Exemplo

No exemplo de climatologia, por enquanto somente ha duas features, temperatura e cobertura de nuvens. Para calcular Shapley values para cada feature individual, precisamos primeiro computar as predições individuais para cada combinação diferente de features do dataset. 
- $P({})=0$ ; Inicialmente nenhuma feature
- $P({\text{temperatura}})=2 \space inches$
- $P({\text{cobertura de nuvens}})=5 \space inches$ 
- $P({\text{cobertura de nuvens},\text{temperatura}})=6 \space inches$  
