# Projeto Práticas de Mercado

Sistema Web desenvolvido em Laravel para a disciplina **Projeto Aplicado: Práticas de Mercado**, com foco na aplicação de conceitos de segurança da informação, autenticação de usuários, infraestrutura em nuvem e integração contínua.

---

# Objetivo do Projeto

Desenvolver uma aplicação web segura utilizando boas práticas de mercado, hospedada em ambiente cloud e integrada a um fluxo automatizado de CI/CD.

---

# Tecnologias Utilizadas

- Laravel 12
- PHP 8.5
- SQLite
- Nginx
- Ubuntu Server
- AWS EC2
- Git
- GitHub
- GitHub Actions
- Laravel Breeze
- Certbot
- Let's Encrypt
- DuckDNS
- Fail2Ban

---

# Aplicação Publicada

**URL de Produção**

https://lucaschavespos.duckdns.org

---

# Funcionalidades Implementadas

## Autenticação

- Login de usuários
- Logout de usuários
- Controle de sessão
- Dashboard protegido

## Área Restrita

Após autenticação o usuário é direcionado para uma área interna protegida contra acesso não autorizado.

---

# Infraestrutura

A aplicação está hospedada em ambiente AWS utilizando recursos gratuitos (Free Tier).

## Servidor

- AWS EC2
- Ubuntu Server
- Nginx como servidor web
- PHP 8.5
- SQLite

## Acesso Remoto

- SSH utilizando chave pública/privada
- Autenticação por chave SSH
- Sem utilização de senha de acesso ao servidor

---

# Segurança

## HTTPS

A aplicação utiliza criptografia TLS através de certificados emitidos pelo Let's Encrypt.

### Recursos Implementados

- HTTPS habilitado
- Certificado SSL/TLS válido
- Renovação automática via Certbot
- Redirecionamento automático HTTP → HTTPS

---

## Fail2Ban

Proteção contra tentativas de acesso indevidas.

Configuração utilizada:

```ini
[sshd]
enabled = true
maxretry = 4
bantime = 24h
```

### Benefícios

- Bloqueio de tentativas de força bruta
- Proteção da porta SSH
- Restrição automática de IPs maliciosos

---

# Controle de Versão

Repositório GitHub:

https://github.com/lucaschaves-cyber/projeto-praticas-mercado

## Recursos Utilizados

- Git
- GitHub
- Histórico de commits
- Versionamento do código
- Repositório público

---

# CI/CD

Foi implementada uma pipeline automatizada utilizando GitHub Actions.

## Fluxo de Deploy

```text
Desenvolvimento
      ↓
Git Commit
      ↓
Git Push
      ↓
GitHub Repository
      ↓
GitHub Actions
      ↓
AWS EC2
      ↓
Deploy Automático
```

## Workflow

O deploy é executado automaticamente sempre que ocorre um push para a branch principal.

Arquivo:

```text
.github/workflows/deploy.yml
```

Etapas executadas:

- Acesso seguro via SSH
- Atualização do código
- Instalação de dependências
- Execução de migrations
- Limpeza de cache
- Reinício do Nginx

---

# OWASP Top 10 - Controles de Segurança Implementados

A aplicação foi desenvolvida seguindo o conceito de **Secure by Design** e implementa controles para mitigação de vulnerabilidades do OWASP Top 10.

---

## A01 - Broken Access Control

Foi implementado controle de acesso através do middleware de autenticação do Laravel.

Exemplo:

```php
Route::middleware('auth')->group(function () {
    Route::get('/dashboard', function () {
        return view('dashboard');
    });
});
```

### Mitigações

- Bloqueio de acesso não autenticado
- Proteção de páginas internas
- Restrição de recursos sensíveis

---

## A07 - Identification and Authentication Failures

A autenticação foi implementada utilizando Laravel Breeze.

Controles implementados:

- Login seguro
- Logout seguro
- Sessões autenticadas
- Armazenamento de senha com hash BCrypt

Exemplo:

```php
Hash::make($password);
```

### Mitigações

- Proteção contra exposição de senhas
- Gerenciamento seguro de sessões
- Controle de autenticação

---

## A08 - Software and Data Integrity Failures

A aplicação utiliza proteção CSRF nativa do Laravel.

Exemplo:

```blade
<form method="POST">
    @csrf
</form>
```

### Mitigações

- Proteção contra requisições forjadas
- Garantia de integridade dos formulários
- Segurança nas operações autenticadas

---

# Estrutura da Aplicação

```text
Login
 ├── Autenticação
 ├── Dashboard
 └── Logout
```

---

# Boas Práticas Adotadas

- Uso de HTTPS
- Chaves SSH
- Fail2Ban
- GitHub Actions
- Controle de acesso
- Middleware de autenticação
- Proteção CSRF
- Versionamento com Git
- Deploy automatizado

---

# Evidências de Conformidade

✅ AWS EC2

✅ Ubuntu Server

✅ Nginx

✅ Laravel

✅ Login

✅ Dashboard Protegido

✅ Logout

✅ HTTPS

✅ Certbot

✅ Chave SSH

✅ Fail2Ban

✅ GitHub Público

✅ GitHub Actions

✅ CI/CD Automatizado

✅ OWASP Top 10

---

# Autor

**Lucas Chaves**

Projeto desenvolvido para a disciplina **Projeto Aplicado: Práticas de Mercado**.
