# funções comuns
obs. as funções variam um pouco entre os SGBDs - sistema gerenciador de banco de dados.

UPPER, LOWER

ROUND

DAY, MONTH, YEAR

EXTRACT, CAST

CONCAT, REPLACE, CHAR_LENGTH

MD5

CASE



# CAST e ROUND
round vai arredondar.
cast faz a conversão de um tipo para outro tipo.

- round, arredonda o número 400.97 em uma casa decimal, nesse caso é o 1 que coloquei entre parênteses.
```
SELECT ROUND(400.97, 1)
```

- vou usar o cast, porque tenho que converter o price do postgres que é double precision para numeric, ai sim ele faz o arredondamento que é um numérico arredondado, isso é uma característica do postgres somente essa conversão cast que tem que fazer.

nesse exemplo vou arredondar duas casas decimais.
```
SELECT id, date, ROUND( CAST(price AS NUMERIC), 2), quantity
FROM tb_sale
```
