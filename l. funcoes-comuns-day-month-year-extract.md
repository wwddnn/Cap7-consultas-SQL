# funções comuns
obs. as funções variam um pouco entre os SGBDs - sistema gerenciador de banco de dados.

UPPER, LOWER

ROUND

DAY, MONTH, YEAR

EXTRACT, CAST

CONCAT, REPLACE, CHAR_LENGTH

MD5

CASE


# DAY
testando para extrair o dia
```
SELECT id, date, price, CAST( EXTRACT(DAY FROM date) AS int) AS dia.
FROM tb_sale
```
obs. vou extrair o dia do mês usando o EXTRACT com o DAY FROM, e depois vou fazer o casting de double precision para int. e por fim vou dar um apelido para esse campo novo com o AS que sera dia.



# YEAR
outro exemplo é fazer com o YEAR. muito semelhante ao exemplo acima. 

obs. se eu quiser mudar o tipo para inteiro tenho que usar o cast, igual ao exemplo acima.
```
SELECT id, date, price, EXTRACT(YEAR FROM date) AS year
FROM tb_sale
```
obs. vai usar o EXTRACT para extrair o ano e vai dar um apelido para o novo campo que é ano.



# MONTH
com o mês é o mesmo raciocínio dos exemplos acima. 

obs. se eu quiser mudar o tipo para inteiro tenho que usar o cast, igual no primeiro exemplo.
```
SELECT id, date, price, EXTRACT(MONTH FROM date) AS month
FROM tb_sale
```


# usando os casos acima (DAY, MONTH, YEAR) para a restrição
vamos usar o EXTRACT após o where, e procuramos onde o day no campo date, onde o dia da data, é igual a 18. é uma restrição, diferente dos casos acima que são projeções.
```
SELECT id, date, price, CAST( EXTRACT(YEAR FROM date) AS integer) AS dia
FROM tb_sale
WHERE EXTRACT(DAY FROM date) = 18
```

outo exemplo pra buscar o ano = 2022...
```
SELECT *
FROM tb_sale
WHERE EXTRACT(YEAR FROM date) = 2022
AND EXTRACT(MONTH FROM date) = 5
```

