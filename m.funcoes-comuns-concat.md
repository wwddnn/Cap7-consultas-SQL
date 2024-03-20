# funções comuns
obs. as funções variam um pouco entre os SGBDs - sistema gerenciador de banco de dados.

UPPER, LOWER

ROUND

DAY, MONTH, YEAR

EXTRACT, CAST

CONCAT, REPLACE, CHAR_LENGTH

MD5

CASE

# CONCAT
concatena as partes do texto.

```
SELECT *, CONCAT(EXTRACT(MONTH FROM date), '/', EXTRACT(YEAR FROM date) ) AS mês_/_ano
FROM tb_sale
```
obs. usei primeiro o EXTRACT para extrair o mês e o ano do campo date, e depois por fora coloquei o CONCAT para concatenar ambos com a barra. fiz uma projeção. e renomeei como mês_ano.

obs. também pode usar o CONCAT dentro do WHERE se for necessário.



