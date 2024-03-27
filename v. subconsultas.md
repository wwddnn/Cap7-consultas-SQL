# subconsultas

- usado em diferença ou união. 

- ou pode ser usado para a resolução de consultas complexas.


na prática é o seguinte, escrevo um SELECT que vai resultar em uma tabela, e essa tabela posso usar como FROM de uma outra consulta. ou seja, porque o resultado de um select é uma tabela e posso colocar esse resultado em outro from. 


obs. na subconsulta tem que dar um apelido para ela, através do AS. nesse exemplo o nome da junção sera 'juncao'.

```
SELECT date, name
FROM (
	SELECT *
	FROM tb_sale
	INNER JOIN tb_seller ON tb_sale.seller_id = tb_seller.id
) AS juncao
WHERE price < 500
```

obs. usamos a subconsulta que tem o inner join dentro de outra consulta. inserimos justamente no from. e aplicamos a claúsula WHERE para restringir os preços menores que 500. uma observação importante é que toda subconsulta deve ter um apelido, nesse caso usamos o comando AS para dar o apelido de 'juncao'.




