# funções comuns
obs. as funções variam um pouco entre os SGBDs - sistema gerenciador de banco de dados.

UPPER, LOWER

ROUND

DAY, MONTH, YEAR

EXTRACT, CAST

CONCAT, REPLACE, CHAR_LENGTH

MD5

CASE



# MD5
é um algoritmo famoso que gera um código hash a partir do valor que eu passar. usado para armazenar uma senha. quando o usuário entra para digitar a senha no site, por exemplo a senha 123, aí que entra o MD5 que vai criptografar esse registro no banco de dados. isso ocorre no momento da criação dessa senha pelo usuário, quando ele cria o seu login. então no banco de dados não fica a senha exposta do usuário, mas sim um código que é essa senha criptografada pelo MD5. então quando a pessoa vai logar de novo, o sistema tem que comparar o MD5 do que ele digitou, com o hash que já esta no banco de dados.

```
SELECT MD5('nelio123')
```
obs. gera um código hash a partir desse string acima. 

- outro exemplo
```
SELECT *, MD5(name)
FROM tb_seller
```
obs. vou gerar o código MD5 de cada name. ou seja o código hash para cada linha do campo name.
