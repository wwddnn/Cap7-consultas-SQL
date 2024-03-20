# funções comuns
obs. as funções variam um pouco entre os SGBDs - sistema gerenciador de banco de dados.

UPPER, LOWER

ROUND

DAY, MONTH, YEAR

EXTRACT, CAST

CONCAT, REPLACE, CHAR_LENGTH

MD5

CASE



# DISTINCT
retorna dados únicos, sem repetição. 

isso é feito porque algumas consultas podem resultar em uma tabela que tem linhas repetidas. e para eliminar essas repetições eu uso a cláusula DISTINCT.

obs. pesquisar no w3shools.

```
SELECT *
FROM tb_sale
INNER JOIN tb_seller ON tb_seller.id = tb_sale.seller_id
WHERE price > 500
```
obs. pesquisa todas as colunas onde o price > 500. mas também junta as tabelas com o INNER JOIN. e dessa forma mostra em uma tabela final, essa junção, mas com a restrição de price > 500.

...

- aprimorando o código acima...

```
SELECT tb_seller.id, tb_seller.name
FROM tb_sale
INNER JOIN tb_seller ON tb_seller.id = tb_sale.seller_id
WHERE price > 500
```
obs. agora temos uma projeção de 'id' e 'nome', ambos da tabela tb_seller. além de fazer a pesquisa como no código anterior, onde traz o price > 500. 
em resumo, mostra a tabela final que é uma junção e mostra também os campos que tem price > 500. porém aqui ainda tenho as linhas repetidas. 

- aprimorando mais ainda o código acima, agora tirando as linhas repetidas ...

```
SELECT DISTINCT tb_seller.id, tb_seller.name
FROM tb_sale
INNER JOIN tb_seller ON tb_seller.id = tb_sale.seller_id
WHERE price > 500
```
obs. acrescento após o SELECT a palavra DISTINCT, onde dessa forma ele só vai trazer 1 de cada. nesse caso traz um vendedor de cada sem repetição de vendedor.


