
# projeção

é uma operação que 'filtra' as colunas da tabela.

exemplo: projeção das colunas id e nome da tabela tb_empregado. vai buscar somente esses dois campos na tabela e exibir numa nova tabela.

```
SELECT id, nome
FROM tb_empregado
```

exemplo abaixo é o estudo da aula: criar as duas tabelas, e seus seeds.

```
CREATE TABLE tb_departamento (
	id INT8,
	nome VARCHAR(100),
	PRIMARY KEY (id)
);

CREATE TABLE tb_empregado (
	id INT8,
	nome VARCHAR(100),
	dept_id INT8,
	PRIMARY KEY (id),
	FOREIGN KEY (dept_id) REFERENCES tb_departamento(id)
);

INSERT INTO tb_departamento (id, nome) VALUES (1, 'Financeiro');
INSERT INTO tb_departamento (id, nome) VALUES (2, 'Recursos Humanos');
INSERT INTO tb_departamento (id, nome) VALUES (3, 'Comercial');

INSERT INTO tb_empregado (id, nome, dept_id) VALUES (1, 'Maria', 1);
INSERT INTO tb_empregado (id, nome, dept_id) VALUES (2, 'João', 2);
INSERT INTO tb_empregado (id, nome, dept_id) VALUES (3, 'Ana', 1);
INSERT INTO tb_empregado (id, nome, dept_id) VALUES (4, 'Carlos', 2);
```


fazer a projeção que desejo, que é filtrar apenas o id e nome da tabela tb_empregado. segue a solução:
fiz uma projeção com id e nome, da tabela original.

```
SELECT id, nome
FROM tb_empregado
```