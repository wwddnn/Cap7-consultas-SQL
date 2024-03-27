# união

- faz a união, como se fosse a união entre 2 conjuntos, igual na matemática. ou seja pega só os elementos únicos dos dois conjuntos mas sem repetição. como exemplo temos o primeiro conjunto com elementos A,B e o segundo conjunto com elementos B,C, nesse caso com union, ficará A,B,C que representa a união mas sem a repetião do elemento B já que ele tem nos dois conjuntos.

- obs. se quisermos com repetição, usamos o UNION ALL, por exemplo se o primeiro conjunto tem A,B e o segundo conjunto tem B e C, nesse caso do union all o resultado será A,B,B,C.


- usamos a palavra UNION para unir os 2 select.

```
SELECT id, date
	FROM tb_sale
	WHERE price > 800

	UNION

	SELECT tb_sale.id, tb_sale.date
	FROM tb_sale
	INNER JOIN tb_seller ON tb_sale.seller_id = tb_seller.id
	WHERE name = 'Joaquim Silva Borges'
```

obs. são dois select. o primeiro vai pesquisar onde o price é maior que 800. e o segundo select vai pesquisar onde o nome é Joaquim Silva Borges. depois o próximo passo é colocar a palavra UNION para fazer a união entre esses dois select.



- usando o código acima, e acrescentando o ORDER BY para ordenar de forma crescente por id, usamos o select novamente e essa união como uma subconsulta, para deixar tudo em order crescente:

```
SELECT *
FROM (
	SELECT id, date
	FROM tb_sale
	WHERE price > 800

	UNION

	SELECT tb_sale.id, tb_sale.date
	FROM tb_sale
	INNER JOIN tb_seller ON tb_sale.seller_id = tb_seller.id
	WHERE name = 'Joaquim Silva Borges') AS uniao
ORDER BY id
```
