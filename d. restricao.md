
# restrição (seleção)
é uma operação que filtra as linhas da tabela. vou aplicar uma restrição na tabela original onde tem as linhas dept_id = 2. ou seja eu quero as linhas que sejam dept_id = 2.
filtras as linhas da tabela que atendem ao predicado, ou seja a essa condição que vou escolher. nesse caso escolho onde tenha dept_id = 2.

exemplo: restrição na tabela tb_empregado das linhas tal que dept_id = 2

```
SELECT *
FROM tb_empregado
WHERE dept_id = 2
```
obs. o dept_id = 2 é o predicado que eu quero. é onde quero fazer o filtro. quero todas as linhas onde o dept_id seja igual a dois.


outro exemplo abaixo, no caso é uma combinação de projeção com restrição:
```
SELECT id, nome
FROM tb_empregado
WHERE dept_id = 2
```
obs.  primeiro sera feira a restrição que é o where dept_id = 2, e depois ele me traz a projeção que é o select id, nome.
