# funções comuns
obs. as funções variam um pouco entre os SGBDs - sistema gerenciador de banco de dados.

UPPER, LOWER

ROUND

DAY, MONTH, YEAR

EXTRACT, CAST

CONCAT, REPLACE, CHAR_LENGTH

MD5

CASE



# LOWER e UPPER
obs. é importante usar, porque não sabemos se o que esta registrado no banco esta em maiúsculo ou minúsculo.


- uma forma de fazer, ele vai projetar tudo para minúsculo. vai buscar o lower. nesse exemplo vai buscar o lower dos names da tabela tb_seller
```
SELECT id, LOWER(name)
FROM tb_seller
```

- já nesse exemplo, vai projetar o name, mas faz a restrição com where e traz todos os nomes para lower, e depois com o like procura onde esta o 'mar%' minúsculo.
```
SELECT id, name
FROM tb_seller
WHERE LOWER(name) LIKE 'mar%'
```

- usando o upper seria assim:
```
SELECT id, name
FROM tb_seller
WHERE UPPER(name) LIKE 'MAR%'
```



