# KNN (K-Nearest Neighbors)

* Algortimo de classificação
* Dados devem ser numéricos
* Pressupõe que os dados de mesma classe estão próximos no espaço

O algoritmo calcula a distância da amostra de teste entre N pontos de treino. Desta forma, imagina-se um círculo de raio R com o ponto de teste no centro. Se há mais pontos da classe A dentro deste círculo, então presupõe-se que o ponto de teste é da classe A.

No KNN, as personalizações do método ocorrem na escolha do número de pontos de comparação K e forma do cálculo de distância dos pontos.

Distância de Minkowski:

$(\sum_{i=1}^n{|x_i - y_i|^p})^{1/p}$

* Com p = 1, equivalente a distância de Manhattan

* Com p = 2, equivalente a distância euclidiana

# Parâmetros do KneighborsClassifier()

### n_neighbors: int, default= 5

Especifica o K pontos a serem comparados.

### Weights: {'uniform','distance'}, default= 'uniform'

Atribui pesos ao pontos próximos para comparação. No default, os pesos possuem os mesmos pesos. Em distance, pontos mais próximos possuem pesos maiores

### Algorithm: {'auto','ball_tree','kd_tree', 'brute'}, default= ' auto'

Seleciona o algoritmo para cálculo do pontos próximos.
'ball_tree' utiliza o método BallTree, 'kd_tree' utiliza o método KDTree, 'brute' utilizará uma busca por força bruta e, por fim, auto que decidirá a opção apropriada.

### leaf_size: int, default= 30

leaf_size é um parâmetro passado ao BallTree ou KDTree e pode afetar velocidade de construção, enfileiramento e memória necessária.

### p: int, default= 2

Potência para a métrica de Minkowski. P = 1 é para o uso da distância de Manhattan. P = 2 para a distância Euclidiana. Pode-se usar outros para p inteiros dentro do intervalo (0, $\inf$).