# funções comuns
obs. as funções variam um pouco entre os SGBDs - sistema gerenciador de banco de dados.

UPPER, LOWER

ROUND

DAY, MONTH, YEAR

EXTRACT, CAST

CONCAT, REPLACE, CHAR_LENGTH

MD5

CASE



# CASE
pegando o exemplo da aula passada com o CONCAT, queremos que o mês fique em 05 e não em 5.

- sintaxe:
```
SELECT
CASE
    WHEN condition_1 THEN result_2
    WHEN condition_2 THEN result_2
    [WHEN ... ]    
    [WHEN else_result]
END
FRON tb_sale
```

- fazendo o exercício da aula:

quando a venda for maior que 500 é cara, e abaixo de 300 é barata.

obs. o CASE entra como terceiro campo nesse código, primeiro tem o id e depois o price.
```
SELECT id, price
CASE
    WHEN price < 500> THEN 'Barata'  
    ELSE 'Cara'
END AS classificacao
FRON tb_sale
```
obs. usamos o AS para dar um apelido a esse CASE, a esse campo.

- mais um exemplo, usando agora 2 WHEN
```
SELECT id, price, 
CASE
	WHEN price < 500 THEN 'Barata'
	WHEN price <= 800 THEN 'Media'
	ELSE 'Cara'
END AS classificacao
FROM tb_sale
```

- resolvendo problema da aula, de colocar o zero na frente do mês caso o mês seja menor que dez.
```
SELECT *, 
CASE
	WHEN EXTRACT(MONTH FROM date) >= 10 THEN CONCAT (EXTRACT(MONTH FROM date), '/', EXTRACT(YEAR FROM date))
	ELSE CONCAT('0', EXTRACT(MONTH FROM date), '/', EXTRACT(YEAR FROM date) ) 
END AS mês_ano
FROM tb_sale
```

