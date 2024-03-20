# funções comuns
obs. as funções variam um pouco entre os SGBDs - sistema gerenciador de banco de dados.

UPPER, LOWER

ROUND

DAY, MONTH, YEAR

EXTRACT, CAST

CONCAT, REPLACE, CHAR_LENGTH

MD5

CASE



# REPLACE
substituição de strings. não é uma função muito usada.

- exemplo:
```
SELECT REPLACE('Maria Silva Silveira', 'Sil', 'XYZ')
```
obs. no nome Maria Silva Silveira, vai substituir o Sil, por XYZ.

- exemplo:
passar todo silva do campo name, que é Silva, para maiúsculo. ou seja todas as ocorrências de Silva ficam maiúscula.
```
SELECT id, name, REPLACE(name, 'Silva', 'SILVA')
FROM tb_seller
```


