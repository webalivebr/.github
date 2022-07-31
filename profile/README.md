# Alive Web Services 
# API-GATEWAY

![image](https://user-images.githubusercontent.com/63611601/154838658-c2866f4b-3e74-475b-a265-2ac77ca6b643.png)


A solicitação é tratada da seguinte forma:

1. Uma solicitação HTTP é feita à API, que inclui um token de acesso no formato JWT fornecido por um emissor de token (por exemplo, Auth0.)
2. A solicitação é recebida pelo API Gateway, que passa o token para o Autorizador JWT para validação.
3. O JWT Authorizer envia uma solicitação ao endpoint JSON Web Key Set (JWKS) para recuperar a chave pública do servidor de autorização usada para verificar o JWT.
4. O servidor de autorização retorna a chave pública para o autorizador JWT.
5. O JWT Authorizer valida o token de acesso, confirmando com o API Gateway que a solicitação pode continuar.
6. O API Gateway executa o Lambda implementando a lógica de negócios da API.
7. O Lambda chama o DynamoDB para ler ou gravar registros, dependendo da solicitação
8. Se necessário, os dados são retornados do DynamoDB para a função do Lambda.
9. O Lamda termina a execução e retorna um objeto JSON que representa a resposta HTTP ao API Gateway.
10. O API Gateway retorna uma resposta HTTP para o aplicativo solicitante.

# Barbearia App


![example workflow](https://github.com/webalivebr/alive-app-xamar/actions/workflows/dotnet.yml/badge.svg)

# AUTHSERVER


![example workflow](https://github.com/webalivebr/AuthServer-Barber/actions/workflows/django.yml/badge.svg)
