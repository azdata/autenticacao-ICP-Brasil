# Autenticação ICP Brasil
Instruções para autenticar um token/certificado A1/A3 no site, apresentando o e-CPF ou e-CNPJ

Instruções para os seguintes cenários:

1. **Utilizando o servidor NGINX** como autenticador para o certificado, e obtendo os dados de e-CPF e/ou e-CNPJ em aplicativos PHP ou Node.JS
2. **Utilizando o servidor Node.JS** como autenticador para o certificado através do módulo Express para autenticar o certificado e obter os dados de e-CPF e/ou e-CNPJ para utilização no Node.JS
3. **Utilizando um servidor APACHE** como autenticador para o certificado (TODO)
4. **Utilizando o API GATEWAY do AWS** no caso de aplicações serverless (AWS Lambda) (TODO)

Na pasta CA, temos o bundle completo de chaves para autenticação, obtido através do gist https://gist.github.com/anzileiro/e93d9605ea6198cf6c22b7a1e236011c

Obs:
Os dados do CPF ou CNPJ estão na variável CN, no formato XXX:NNN, onde o XXX é o nome do titular do CPF ou razão social da empresa e o NNN é o numero do CPF ou CNPJ. Então o ideal é usar um comando split com o caracter ':' como divisor e você terá um array onde o item 0 é o nome/razão social e o item 1 é o número do cpf/cnpj. Remova os 3 primeiros caracteres do item 0, pois estes tem sempre o 'CN='
