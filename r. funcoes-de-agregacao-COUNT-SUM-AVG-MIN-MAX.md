# FUNCOES DE AGREGACAO
essas funcoes sao de agregação porque so trabalham com a coluna inteira. pega todas as linhas e gera um valor agregado.

obs quando a funcao é comum e nao é o caso aqui, vai operar linha a linha e vai gerar esses valores. já aqui são funções de agregação, que trabalham com a coluna inteira.


COUNT, SUM, AVG, MIN, MAX


### COUNT
vai contar a quantidade. nesse exemplo quantas vendas tem preço maior que 500.
```
SELECT COUNT(id)
FROM tb_sale
WHERE price > 500
```
obs. geralmente coloca só o id entre parênteses, para ficar mais leve, dai conta somente os ids.


### SUM
vai somar. é uma função de agregação. nesse exemplo soma os preços, onde o price é maior que 500.
```
SELECT SUM(price)
FROM tb_sale
WHERE price > 500
```
obs. a soma vai agregar todos esses num resultado final.


### AVG
calcula a média. semelhante aos casos acima. nesse exemplo a média dos preços que sejam maior que 500.
```
SELECT AVG(price)
FROM tb_sale
WHERE price > 500
```
obs quanto o resultado da consulta é vazio, ele vai dar null no resultado final. exemplo se não tiver nenhum price > 5000 nesse caso, ele vai retornar null.



### MIN
calcula o mínimo dentre um conjunto de valores. nesse exemplo calcula o mínimo do price, dentro dos valores que sejam price < que 500.
```
SELECT MIN(price)
FROM tb_sale
WHERE price > 500
```


### MAX
idem ao caso acima. calcula o máximo dentre um conjunto de valores. nesse exemplo vai trazer o valor máximo, dentre os que tem price > 500.
```
SELECT MAX(price)
FROM tb_Sale
WHERE price > 500
```
