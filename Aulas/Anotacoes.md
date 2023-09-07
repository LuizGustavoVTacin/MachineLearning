# Anotações em ML

# Tipos de Scalers

## MinMax Scaling (Normalização)

Também conhecida como normalização, essa técnica dimensiona os dados para um intervalo específico, geralmente [0, 1]. É útil quando você deseja que todos os valores estejam na mesma escala.

`X_scaled = (X - X_min) / (X_max - X_min)`

## Standardization (Padronização)

A padronização transforma os dados para que tenham média zero e desvio padrão um. Isso é útil quando você deseja que os dados tenham uma distribuição normal e não seja sensível a valores atípicos.

`X_scaled = (X - X_mean) / X_std`

## Robust Scaling (Escalonamento Robusto)

Similar à padronização, mas usa a mediana e o intervalo interquartil (IQR) em vez da média e do desvio padrão. É mais resistente a valores atípicos.

`X_scaled = (X - X_median) / IQR`

## Log Transformation (Transformação Logarítmica)

Pode ser usada para reduzir a variação de dados com valores altos e positivos. É útil quando você está lidando com dados que seguem uma distribuição exponencial.

`X_scaled = log(X)`

## Box-Cox Transformation

Similar à transformação logarítmica, mas permite ajustar o parâmetro lambda para encontrar a melhor transformação para seus dados

```
X_scaled = ((X^lambda) - 1) / lambda, se lambda != 0
X_scaled = log(X), se lambda = 0
```

## Z-Score Scaling

Uma variação da padronização que dimensiona os dados para que tenham média zero e desvio padrão 1, mas também calcula z-scores negativos para valores abaixo da média

`Z = (X - X_mean) / X_std`

## Max Abs Scaling (Escalonamento pelo Valor Absoluto Máximo)

Escalona os valores pelo maior valor absoluto encontrado nos dados. É útil quando você deseja manter os dados dentro do intervalo [-1, 1] sem afetar o sinal

`X_scaled = X / max(abs(X))`

## Quantile Transformation

Transforma os dados em uma distribuição uniforme ou normal. Pode ser útil quando você deseja que os dados sigam uma distribuição específica