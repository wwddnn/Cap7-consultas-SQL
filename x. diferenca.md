# diferença

é a diferença do conjunto A menos o conjunto B. 

obs. usa o operador IN, que será usado como NOT IN. justamente para exluir algo do conjunto.

- fazer a subconsulta primeiro e depois fazer a consulta. nesse exemplo queremos todas as vendas, exceto as vendas que foram feitas na data do vendedor Ivan Reis.

```
SELECT tb_sale.id, date, quantity
FROM tb_sale
INNER JOIN tb_seller ON tb_sale.seller_id = tb_seller.id
WHERE date NOT IN(
	SELECT date
	FROM tb_sale
	INNER JOIN tb_seller ON tb_sale.seller_id = tb_seller.id
	WHERE name = 'Ivan Reis'
)
```

obs. usamos NOT IN como uma subconsulta. 