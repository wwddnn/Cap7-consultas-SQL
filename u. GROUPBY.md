# GROUPBY
geralmente usamos com o groupby, logo no começo, uma projeção que é uma funcao de agregação ja vista anteriormente como o count, sum, min, max, avg. 

```
SELECT date, COUNT(date) AS contagem
FROM tb_Sale
GROUP BY date
```

obs. consegui agrupar por data e junto de cada data terá a contagem de data. gera um relatório agrupado por data e a contagem de data.


- outro exemplo

```
SELECT date, SUM(price) AS soma
FROM tb_Sale
GROUP BY date
ORDER BY date ASC
```

obs. eu quero agrupar por data, cada linha do resultado mostra a data. e vai mostrar a soma dos preços dessas datas. com o AS dei um apelido para essa coluna nova resultante. e com order by asc ficou em ordem crescente.


- outro exemplo

```
SELECT tb_seller.name, SUM(price * quantity)
FROM tb_sale
INNER JOIN tb_seller ON tb_sale.seller_id = tb_seller.id
GROUP BY tb_seller.name
```

obs. com o SUM achei o total de vendas fazendo price * quantity por vendedor. para não dar ambiguidade no SELECT colocar nome da tabela e campo tb_seller.name, assim como no GROUP BY também.


- outro exemplo

```
SELECT tb_seller.name, ROUND(CAST(SUM(price) AS numeric), 2)
FROM tb_sale
INNER JOIN tb_seller ON tb_sale.seller_id = tb_seller.id
GROUP BY tb_seller.name
```

obs. vai fazer a projeção para apresentar o name, e a soma dos price, e vai arredondar com 2 casas decimais usando o ROUND, e o CAST vai transformar para numeric. o group by vai agrupar por nome do vendedor.


- evolução do código acima, onde agora vamos calcular a venda mesmo que é o preço * quantity

```
SELECT tb_seller.name, ROUND(CAST(SUM(price * quantity) AS numeric), 2) AS total_vendas
FROM tb_sale
INNER JOIN tb_seller ON tb_sale.seller_id = tb_seller.id
GROUP BY tb_seller.name
ORDER BY total_vendas DESC
```

obs. podemos agrupar com o group by, e colocar na ordem crescente com o order by esse total de vendas. 