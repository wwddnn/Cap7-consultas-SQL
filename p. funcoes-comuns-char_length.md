# funções comuns
obs. as funções variam um pouco entre os SGBDs - sistema gerenciador de banco de dados.

UPPER, LOWER

ROUND

DAY, MONTH, YEAR

EXTRACT, CAST

CONCAT, REPLACE, CHAR_LENGTH

MD5

CASE



# CHAR_LENGTH
encontra o tamanho em caracteres de um texto. mostra quantos caracteres tem cada nome. usado em operações mais específicas.

```
SELECT id, name, CHAR_LENGTH(name)
FROM tb_seller
```


