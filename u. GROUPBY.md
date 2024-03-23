# GROUPBY
geralmente usamos com o groupby, logo no comeco, uma projeção que é uma funcao de agregação ja vista anteriormente como o count, sum etc. 

```
SELECT date, COUNT(date) AS contagem
FROM tb_Sale
GROUP BY date
```
obs. consegui agrupar e a contagem de data. gera um relatório agrupado por data e a contagem de data.


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
