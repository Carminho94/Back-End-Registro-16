# SecureFlow API -- Semana 16 🚀

## Plano de Segurança

A API foi protegida com **CORS restrito**, **autenticação/autorização
com token** e **monitoramento via logs**.

## CORS

-   Apenas `http://frontend.secureflow.com` pode consumir a API.
-   Isso previne ataques de outros domínios tentando roubar dados.

## Autenticação e Autorização

-   Middleware verifica a presença de um token válido.
-   Se o token não for enviado ou for inválido → **403 Acesso não
    autorizado**.
-   Autenticação (quem é o usuário) e autorização (o que pode acessar)
    foram aplicadas.

## Monitoramento e Testes

-   Tentativas não autorizadas são registradas em `seguranca.log`.

-   Exemplo de log:

        [2025-08-25T14:30:00Z] Acesso negado de IP: ::1

-   Logs permitem identificar ataques repetitivos ou suspeitos.

## Demonstração

1.  ✅ Requisição com token → retorna lista de pedidos.\
2.  ❌ Requisição sem token → retorna **403** e gera log.
