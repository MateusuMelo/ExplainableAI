
Explicações que utilizam parte de predições de modelos são chamadas de explicações *intrinsecas*. Para gerar explicações intrínsecas muito das vezes é necessário realizar modificações no modelo.

$$
Pred(y) = 0.1 \cdot feature_A + 0.7\cdot feature_B + 0.4\cdot feature_C
$$
Suponha os valores:
$$
A = 10; B =20; C=40
$$
O modelo retorna $Pred(y) =31$. Para obtermos uma boa explicação do modelo devemos criar uma explicação que descreve como cada feature influencia na predição do modelo. **No caso deste exemplo de modelo linear, uma explicação intrínseca nada mais é que os pesos atrelados a cada feature**, no exemplo acima e possível dizer que a feature B possui uma alta influencia na predição do modelo. Neste caso podemos confiar na explicabilidade pois trata-se de um modelo linear que podemos provar seu funcionamento.