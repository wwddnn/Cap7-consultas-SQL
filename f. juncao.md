
# junção
obs. como veremos mais a frente, podemos obter a junção entre duas tabelas, de duas formas diferentes:

faz o cruzamento entre duas tabelas 'apenas' dos registros correspondentes. esse sim, usaremos bastante. vai buscar a interseção que são os elementos que tem nos dois conjuntos. 

exemplo: junção entre tabelas tb_empregado e tb_departamento.

forma 1, que é usando o INNER JOIN, que é a interseção. essa é a recomendação do prof Nélio! escrever dessa forma!
```
SELECT *
FROM tb_empregado
INNER JOIN tb_departamento ON tb_empregado.dept_id = tb_departamento.id
```

obs. INNER vem de interseção. 
obs. depois do ON vem o predicato indicando a correspondência. nesse exemplo, quando o dept_id da tabela tb_empregado for igual ao id da tabela tb_departamento.


### essa abaixo é uma outra alternativa junção: podemos fazer um produto cartesiano + restrição
obs. é uma combinação do produto cartesiano com a restrição. ou seja, faz uma resrtição em cima do produto cartesiano. 
obs. ou seja, primeiro faz o produto cartesiano e depois faz a restrição. é quebrar o problemão em probleminhas menores.
obs. quando usamos o FROM e mais de uma tabela entre as vírgulas, ele vai fazer o produto cartesiano.
obs. já no WHERE eu aplico uma restrição.

forma 2 quando usamos o produto cartesiano com uma restrição
```
SELECT *
FROM tb_empregado, tb_departamento
WHERE tb_empregado.dept_id = tb_departamento.id
```

