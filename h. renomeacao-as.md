# renomeação AS
pode:
1. remove ambiguidades.
2. dar nome a campos calculados.
3. dar nome a tabelas resultantes de subconsultas.



# 1 PARA REMOVER AMBIGUIDADES:
### consulta sem projeção ainda
o select esta com o asterisco, nesse moemnto, ainda não fiz projeção.

```
SELECT *
FROM tb_empregado
INNER JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
```

### consulta com projeção
com o select fiz a projeção agora, pedindo pra trazer os campos id e nome da tabela tb_empregado, assim como o campo nome da tabela tb_departamento.

```
SELECT tb_empregado.id, tb_empregado.nome, tb_departamento.nome
FROM tb_empregado
INNER JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
```

### consulta com projeção e também dando um apelido para o campo nome da tabela tb_departamento (para reduzir ambiguidade dos campos)
com o select fiz a projeção, igual ao exemplo de cima, só que agora vou dar um apelido ao campo nome da tabela tb_departamento, usando a palavra AS. fiz isso porque tem dois campos chamados 'nome', um na tabela tb_empregado e outro na tabela tb_departamento.
assim eliminamos a ambiguidade no nome dos campos, nesse caso os campos 'nome'.

```
SELECT tb_empregado.id, tb_empregado.nome, tb_departamento.nome AS nome_departamento
FROM tb_empregado
INNER JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
```



# 2 PARA DAR NOME A CAMPOS CALCULADOS:
usamos para dar um nome ao campo, que esta sendo usando para algum cálculo qualquer. 
nesse exemplo o campo id da tabela tb_empregado esta multiplicado por 10, e quero um nome difente para esse campo, por isso usei o nome 'calculo'.

```
SELECT tb_empregado.id, tb_empregado.nome, tb_empregado.id * 10 AS calculo
FROM tb_empregado
INNER JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
```



# 3 PARA DAR NOME A TABELAS RESULTANTE DE UMA SUBCONSULTA:
usa um select para servir de from para uma outra consulta.
ver o exemplo abaixo: onde tenho que dar um apelido 'alias' para a tabela de subconsulta. nesse caso o nome que dei foi 'juncao' usando o AS.

```
SELECT dept_id
FROM (
	SELECT *
	FROM tb_empregado
	INNER JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
) AS juncao
```