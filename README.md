# Games Api - Doc
Esta API REST desenvolvida com NODE.JS, a mesma foi criada para dá início a um projeto pessoal na qual programadores 
poderão consumir nas suas aplicações informações sobre games.

## Endpoints 
Responsável por buscar todos os games e informações relativas as mesmas na base de dados.

### POST /auth
Esse endponit é responsável por retornar o processo de login.
#### Parâmetros
Email: E-mail do usuário cadastrado no sistema.

Password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo: 
```
{
	"email": "meuemail@exemplo.com",
	"password": "minhasenha"
}
```
#### Respostas
##### ok! 200
Caso essa resposta aconteça, você receberá o token JWT para conseguir acesso os endpoints protegidos na API.

Exemplo de resposta:
```
{
 "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ0aWFnb2
		       dvbWVzMUBnbWFpbC5jb20iLCJpYXQiOjE2ODgxMjcyNDQsImV4cCI6MTY4ODMwMDA0NH0.
           i5tjCAElNvxuAVdopMh9lc80YKOvxZK0PdUjqxR3sr0"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação
dá requisição. Motivos: Senha ou email incorretos. 
Exemplo de resposta:
```
{
	"err": "Credenciais invalidas!"
}
```
### GET /games
Responsável por buscar todos os games e informações relativas as mesmas na base de dados.
#### Parâmetros
Sem parâmetros

#### Respostas 
##### ok! 200
Caso essa resposta aconteça, você receberá a listagem de todos os games.
Exemplo de resposta:
```
[
   {
      "id": 23,
      "title": "Call of duty",
      "year": 2019,
      "price": 60
   },
   {
      "id": 51,
      "title": "Sea of thieves",
      "year": 2018,
      "price": 40
   },
   {
      "id": 3,
      "title": "Minecraft",
      "year": 2012,
      "price": 20
   }
]      
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação
dá requisição. Motivos: Token inválido, Token expirado. 
Exemplo de resposta:
```
 {
	"err": "Token inválido!"
 }
```

