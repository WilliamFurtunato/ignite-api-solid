# App

Gympass style app.

## RFs (Requisitos funcionais)

- [x] Deve ser possível cadastrar usuário;
- [x] Deve ser possível autenticar usuário;
- [x] Deve ser possível obter o perfil de um usuário logado;
- [x] Deve ser possível obter o número de check-ins realizados pelo usuário logado;
- [x] Deve ser possível o usuário obter seu histórico de check-ins;
- [x] Deve ser possível o usuário buscar academias próximas (até 10km);
- [x] Deve ser possível o usuário buscar academias pelo nome;
- [x] Deve ser possível o usuário realizar check-in em uma academia;
- [x] Deve ser possível validar o check-in de um usuário;
- [x] Deve ser possível cadastrar uma academia;

## RNs (Regras de negócio)

- [x] O usuário não deve poder se cadastrar com um e-mail duplicado;
- [x] O usuário não pode fazer 2 check-ins no mesmo dia;
- [x] O usuário não pode fazer check-in se não estiver perto (100m) da academia;
- [x] O check-in só pode ser validado até 20 minutos após criado;
- [ ] O check-in só pode ser validado por administradores;
- [ ] A academia só poder ser cadastrada por administradores;

## RNFs (Requisitos não-funcionais)

- [x] A senha do usuário precisa estar criptografada;
- [x] Os dados da aplicação precisam estar persistidos em um banco PostreSQL;
- [x] Todas listas de dados precisam estar paginadas com 20 itens por página;
- [ ] O usuário deve ser identificado por um JWT (Json Web Token);

## Note

Commit: Refresh Token & RBAC - Estratégia de refresh de token

Integrando com front-end
Caso precise integrar com o front-end, você deve ter se deparado com o refreshToken não sendo setado nos cookies do navegador, para resolver esse problema, ilustraremos a solução utilizando o Axios:

No servidor, adicione a propriedade credentials como true:
app.register(cors, {
origin: true,
credentials: true,
})
No create ou nas requisições do Axios, adicione o withCredentials como true:
const api = axios.create({
baseURL: 'http://localhost:3333',
withCredentials: true,
})
