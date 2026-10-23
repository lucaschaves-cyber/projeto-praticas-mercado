# Projeto Práticas de Mercado

Sistema Web desenvolvido em Laravel para a disciplina Projeto Aplicado: Práticas de Mercado.

## Tecnologias Utilizadas

- Laravel
- PHP 8.5
- SQLite
- Nginx
- Ubuntu Server
- AWS EC2
- GitHub
- GitHub Actions
- Certbot
- DuckDNS

## Aplicação

URL:

https://lucaschavespos.duckdns.org

## Funcionalidades

- Login
- Dashboard protegido
- Logout

## Segurança

- HTTPS habilitado
- Certificado SSL/TLS
- Chaves SSH
- Fail2Ban
- Controle de acesso por autenticação

## OWASP Top 10

### A01 - Broken Access Control

Rotas protegidas por autenticação.

### A07 - Identification and Authentication Failures

Autenticação implementada com Laravel Breeze.

### A08 - Software and Data Integrity Failures

Proteção CSRF nativa do Laravel.

## Infraestrutura

- AWS EC2
- Ubuntu Server
- Nginx
- Certbot SSL

## CI/CD

GitHub Actions realizando deploy automático para AWS.

## Autor

Lucas Chaves
