# Desafio Shuster
## Desenvolvedor .NET Core

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Este projeto refere-se a um exemplo bem básico de controle de acesso utilizando JWT. Abaixo seguem as tecnologias utilizadas para confecção do mesmo.

- Crud de vallidação dos dados pessoais do usuário
- Login tokenizado com JWT
- .Net Core 6 com C#
- API implementando RestFull
## Features

- Gerenciamento de cadastros de validações de acesso.
- Gerenciamento de dados para recuperação de acesso.
- Controle de tokens JWT para as requisições

Lembrando que se trata de apenas um esboço de sistema, conforme solicitado para finalização nesta data. 
As [Shuster Roberto] writes on the [![Linkekin]()](https://www.linkedin.com/in/shuster-roberto-gon%C3%A7alves-da-silva-7ba4a2235/) [][df1]

> Aqui estou fazendo o controle dos tokens JWT. No arquivo ClassesJWT adicionado na pasta raíz do projeto.

```using System.Security.Cryptography;
using Microsoft.IdentityModel.Tokens;
namespace APIQuestions
{
    public class TokenConfigurations
    {
        public string Audience { get; set; }
        public string Issuer { get; set; }
        public int Seconds { get; set; }
    }

    public class SigningConfigurations
    {
        public SecurityKey Key { get; }
        public SigningCredentials SigningCredentials { get; }
        public SigningConfigurations()
        {
            using (var provider = new RSACryptoServiceProvider(2048))
            {
                Key = new RsaSecurityKey(provider.ExportParameters(true));
            }

            SigningCredentials = new SigningCredentials(
                Key, SecurityAlgorithms.RsaSha256Signature);
        }
    }
}
``` 
> É possível validar no diretório abaixo a estrututa de controle de usuário do sistema
>    /desafioStefanini/apiQuestions/Controllers/LoginController.cs
> publishable as-is, as plain text, without
> looking like it's been marked up with tags
> or formatting instructions.
```
using System;
using Microsoft.AspNetCore.Mvc;
using Microsoft.AspNetCore.Authorization;
using System.IdentityModel.Tokens.Jwt;
using System.Security.Claims;
using System.Security.Principal;
using Microsoft.IdentityModel.Tokens;
using APIQuestions.Business;
using APIQuestions.Models;

namespace APIQuestions.Controllers
{
```
## Tech
Dillinger uses a number of open source projects to work properly:

- [AngularJS] - HTML enhanced for web apps!
- [markdown-it] - Markdown parser done right. Fast and easy to extend.
- [Twitter Bootstrap] - great UI boilerplate for modern web apps
- [Express] - fast node.js network app framework [@tjholowaychuk]
- [jQuery] - duh

## Repositório do projeto
https://github.com/shusterroberto/desafioStefanini/blob/main/README.md

Dillinger requires [Node.js](https://nodejs.org/) v10+ to run.

Install the dependencies and devDependencies and start the server.
## Development

Want to contribute? Great!
#### Building for source
For production release:
## Docker
