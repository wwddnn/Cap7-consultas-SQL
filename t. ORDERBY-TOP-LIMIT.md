# ORDER BY
ordena os resultados. 

obs. no final, depois do SELECT, do FROM e do WHERE, é aí que vou colocar o ORDER BY.

### em ordem crescente, usamos ASC ou não usamos nada:
```
SELECT *
FROM tb_sale
ORDER BY price
```
obs. o resultado da tabela final vem ordenado de forma crescente por price.

obs. para vir o resultado na ordem crescente, ou não coloco nada depois, ou entao coloco a palavra ASC.


### em ordem decrescente, usamos DESC ou não usamos nada:
- em ordem decrescente ficaria assim, usando o DESC:
```
SELECT *
FROM tb_sale
ORDER BY price DESC
```


###  é possível ordenar por mais de um valor:
vamos supor que quero ordenar por cada id de vendedor e também por preço dentro de cada vendedor.
```
SELECT *
FROM tb_sale
ORDER BY seller_id, price
```
obs. nesse caso vou colocar depois do ORDER_BY o seller_id e o price para que ele ordene pelo id do vendedor e também pelo price, dessa forma.


### é possível também ordenar por mais de um valor, sendo um na orde crescente e outro na ordem decrescente:
```
SELECT *
FROM tb_sale
ORDER BY seller_id, price DESC
```
obs. vou ordenar em ordem crescente por id de vendedor, e na ordem decrescente por price.


# TOP
nem todo banco de dados tem essa cláusula, como é o caso no postgres que não tem. 

já a cláusula LIMIT tem. 


# LIMIT 
usa no final da consulta. no final de tudo, antes vem o SELECT, FROM, WHERE, ORDER BY, e por último que colocamos essa cláusula LIMIT. ele vai buscar as n primeiras linhas que eu quiser.

```
SELECT *
FROM tb_sale
ORDER BY price DESC
LIMIT 3
```
obs. para saber as 3 maiores vendas que teve. só fica as 3 primeiras linhas. 

obs. repara que o ORDER BY esta em ordem decrescente. e também que o LIMIT vem no final de tudo, depois do ORDER BY.


- outro exemplo: muito comum de usar. 
```
SELECT price
FROM tb_sale
ORDER BY price DESC
LIMIT 1
```
obs. se quiser saber somente a maior price de todos. coloco o price após o SELECT para fazer a projeção. e no final do código SQL coloco a cláusula LIMIT para ficar somente 1 price.


- outro exemplo: é fazer ''paginação''.
nesse exemplo só tenho na minha tabela inicial 6 linhas, mas imagina uma tabela de banco de dados grande, de uma empresa, quantas linhas não vou ter. então quando eu vou exibir um relatório dessa empresa, eu trago de pouco em pouco, ou seja, trago poucas linhas de cada vez, chamamos isso de ''paginação''. vou paginar os resultados. e posso dar um limite para buscar somente uma parte, e divido em páginas.

obs no postgres tem uma palavra que se chama ''OFFSET'' que vai me falar quantas linhas vou pular para começar a pegar as linhas que quero. 

obs. como exemplo do estudo da aula, usamos o LIMIT 2 e depois o OFFSET 0, então primeiro vai trazer as 2 primeiras linhas e não pula nenhuma. já no código a seguir faz o LIMIT 2 e OFFSET 2 para pular as duas primeiras linhas e buscar as duas seguintes. e posso ainda fazer no código a seguir LIMIT 2 OFFSET 4, que vai pegar as duas linhas mas vai pular as 4 anteriores justamente porque já foram exibidas.

o código completo ficaria assim :
```
SELECT *
FROM tb_sale
ORDER BY price DESC
LIMIT 2 OFFSET 0

SELECT *
FROM tb_sale
ORDER BY price DESC
LIMIT 2 OFFSET 2

SELECT *
FROM tb_sale
ORDER BY price DESC
LIMIT 2 OFFSET 4
```
obs. esse tema de ''paginação'' muda um pouco de banco para banco, mas no postgres funciona assim como o prof nelio ensinou na aula. usando o LIMIT para escolher a quantidade de linhas a serem exibidas, e usando o OFFSET para dizer quantas linhas tem que pular naquela vez.
