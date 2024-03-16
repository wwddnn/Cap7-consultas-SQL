# operadores like, in, between
obs operador IN também pode ser usado para tabelas. nas aulas mais a frente o prof nélio vai explicar.


## criar as tabelas e os seeds
```
CREATE TABLE tb_seller (
	id int8 NOT NULL,
	name VARCHAR(255),
	PRIMARY KEY (id)
);

CREATE TABLE tb_sale (
	id int8,
	date date,
	price float8,
	quantity int4,
	seller_id int8,
	PRIMARY KEY (id),
	FOREIGN KEY (seller_id) REFERENCES tb_seller(id)
);

INSERT INTO tb_seller(id, name) VALUES (1, 'Maria da Silva');
INSERT INTO tb_seller(id, name) VALUES (2, 'Ivan Reis');
INSERT INTO tb_seller(id, name) VALUES (3, 'Marcos Dias');
INSERT INTO tb_seller(id, name) VALUES (4, 'Joaquim Silva Borges');

INSERT INTO tb_sale(id, date, price, quantity, seller_id) VALUES (1, '2022-05-01', 300.00, 3, 2);
INSERT INTO tb_sale(id, date, price, quantity, seller_id) VALUES (2, '2022-05-07', 800.50, 2, 1);
INSERT INTO tb_sale(id, date, price, quantity, seller_id) VALUES (3, '2022-05-11', 1000.00, 2, 4);
INSERT INTO tb_sale(id, date, price, quantity, seller_id) VALUES (4, '2022-05-18', 700.84, 1, 4);
INSERT INTO tb_sale(id, date, price, quantity, seller_id) VALUES (5, '2022-05-23', 400.97, 2, 3);
INSERT INTO tb_sale(id, date, price, quantity, seller_id) VALUES (6, '2022-05-27', 200.00, 5, 2);
```



# USAR OPERADOR LIKE
- para consultar na internet: https://www.w3schools.com/sql/sql_like.asp
obs ver no site os wildcards  que são os diferentes símbolos, tem vários.

faço a restrição usando o WHERE e depois o LIKE para procurar somente no campo 'name' os nomes que começam com a letra 'm' e o % é porque pode ter qualquer letra depois do m.
obs tem que usar o símbolo de %, senão dará erro.
```
SELECT *
FROM tb_seller
WHERE name LIKE 'M%'
```

### outro exemplo usando operador LIKE
o like aqui vai buscar onde tem a palavra Silva, por isso tem que usar o % antes e depois do Silva. nesse caso busca onde tiver o Silva.
```
SELECT *
FROM tb_seller
WHERE name LIKE '%Silva%'
```

### outro exemplo usando o LIKE
o like busca onde tem Silv porque o símbolo _ quer dizer qualquer letra, ou seja ele ignora aquela letra.
```
SELECT *
FROM tb_seller
WHERE name LIKE '%Silv_%'
```



# USAR OPERADOR IN
- para consultar na internet http://www.w3schools.com/sql/sql_in.asp

usa o operador IN e entre parênteses diz o que deseja buscar, nesse exemplo busca onde os id sejam 2 ou 4.
especifica uma lista. um conjunto de valores que atendam a minha restrição.
```
SELECT *
FROM tb_seller
WHERE id IN (2,4)
```



# USAR OPERADOR BETWEEN
- para consultar na internet https://www.w3schools.com/sql/sql_between.asp
### uma forma de fazer é essa 
usa o sinal de maior e igual e depois o AND e por fim o sinal de menor e igual.
```
SELECT *
FROM tb_sale
WHERE date >= '2022-05-07' AND date <= '2022-05-23'
```
### agora usando o between
fica ate mais simples do que o caso acima. usamos o between. é uma forma alternativa de especificar o intervalo.
```
SELECT *
FROM tb_sale
WHERE date BETWEEN '2022-05-07' AND '2022-05-23'
```

