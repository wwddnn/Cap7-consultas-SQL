
# tipos de junção

link https://www.w3schools.com/sql/sql_join.asp

### inner join
vai retornar registros que tem correspondências nas duas tabelas. é a interseção entre dois conjuntos.
obs. o inner é disponsável de escrever, mas o prof nelio prefere sim escrever.

### left (outer) join
escrever o outer é opcional, não precisa, o prof nélio nao escreve ela.
retorna todos os registros da tabela da esquerda e mais a correspondência entre as tabelas.

### right (outer) join
retorna todos os registros da tabela da direita e mais a correspondência entre as tabelas.

### full (outer) join
retorna todos de todos os registros de todas as tabelas. mesmo os que não tem corresponência entre as tabelas. ex: registros com null.

# exemplo da aula, exercício:
### criar as tabelas e faer as inserções dos dados
```
CREATE TABLE tb_departamento (
	id int8,
	nome VARCHAR(100),
	PRIMARY KEY (id)
);

CREATE TABLE tb_empregado (
	id int8,
	nome VARCHAR(100),
	dept_id int8,
	PRIMARY KEY (id),
	FOREIGN KEY (dept_id) REFERENCES tb_departamento(id)
);

INSERT INTO tb_departamento(id, nome) VALUES (1, 'Financeiro');
INSERT INTO tb_departamento(id, nome) VALUES (2, 'Recursos Humanos');
INSERT INTO tb_departamento(id, nome) VALUES (3, 'Comercial');

INSERT INTO tb_empregado(id, nome, dept_id) VALUES (1, 'Maria', 1);
INSERT INTO tb_empregado(id, nome, dept_id) VALUES (2, 'João', 2);
INSERT INTO tb_empregado(id, nome, dept_id) VALUES (3, 'Ana', 1);
INSERT INTO tb_empregado(id, nome, dept_id) VALUES (4, 'Carlos', null);
```

### fazer as consultas INNER JOIN
obs. não vai retornar o Carlos que esta na tabela tb_empregado, justamente porque o Carlos não tem departamento. ou seja o Carlos não esta na interseção entre as tabelas. todos os outros dados esse select vai retornar normalmente.
```
SELECT *
FROM tb_empregado
INNER JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
```
### fazer consultas com LEFT JOIN
obs. traz todos os registros da tabela da esquerda, inclusive os registros que não tem relação com a tabela da direita.
```
SELECT *
FROM tb_empregado
LEFT JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
```
### fazer consultas com RIGHT JOIN
obs. traz todos os registros da tabela da direita.
```
SELECT *
FROM tb_empregado
RIGHT JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
```
### fazer consultas com FULL JOIN
obs. traz tudo. é a união dos dois conjuntos. 
```
SELECT *
FROM tb_empregado
FULL JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
```