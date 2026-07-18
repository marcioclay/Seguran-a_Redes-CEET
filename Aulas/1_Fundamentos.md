## Fundamentos de Segurança de Redes

[![Containerlab](https://img.shields.io/badge/Containerlab-v0.50+-blue?logo=linux)](https://containerlab.dev)
[![Docker](https://img.shields.io/badge/Docker-required-blue?logo=docker)](https://www.docker.com)
[![eBPF](https://img.shields.io/badge/eBPF-XDP-orange)](https://ebpf.io)
[![Licença](https://img.shields.io/badge/licença-GPL--2.0-green)](LICENSE)
[![Linguagem](https://img.shields.io/badge/linguagem-C-blue)](https://en.wikipedia.org/wiki/C_(programming_language))
 
A segurança é vista como uma qualidade de serviço que garante o fornecimento do serviço, mesmo diante de ações de indivíduos não autorizados no sistema.

### - Como pensam especialistas em segurança 

<img width="900" height="200" alt="image" src="https://github.com/user-attachments/assets/47261c3f-d8bb-428e-b651-a661d689a384" /> 

<img width="900" height="200" alt="image" src="https://github.com/user-attachments/assets/ece97e3e-a420-4c93-bb8c-580ceedaa13a" /> 


### - Confidencialidade, Integridade e autenticidade

Na segurança de redes de computadores, proteger uma informação não significa apenas impedir que ela seja roubada. Também é necessário garantir que a informação não seja alterada indevidamente e que seja possível confirmar quem enviou ou produziu aquela informação.

Por isso, três conceitos fundamentais são:

- Confidencialidade;
- Integridade;
- Autenticidade.

### 1. :alien: Confidencialidade 

A confidencialidade garante que uma informação seja acessada apenas por pessoas ou sistemas autorizados.

Imagine que um funcionário envie a senha de acesso a um servidor pela rede:

Usuário ─────────────► Servidor
       senha: 123456

Se a comunicação não estiver protegida, um atacante que consiga capturar o tráfego poderá visualizar a senha.

Para proteger a confidencialidade, a informação pode ser criptografada:

Usuário ─────────────► Servidor
       8A7F2B9C1D...

O atacante pode até capturar os dados, mas não consegue compreender facilmente seu conteúdo.

Mecanismos utilizados
- Criptografia;
- HTTPS/TLS;
- VPN;
- Controle de acesso;
- Senhas;
- Autenticação multifator (MFA).

Exemplo

Um banco de dados contém informações de clientes. A confidencialidade garante que apenas usuários autorizados possam consultar esses dados.

### 2. :fire: Integridade

A integridade garante que uma informação não seja modificada de forma indevida.

Considere o seguinte arquivo:

saldo.txt
Saldo: R$ 1.000,00

Se um atacante alterar o arquivo para:

Saldo: R$ 100.000,00

a informação perdeu sua integridade.

Um dos mecanismos utilizados para verificar se um arquivo foi alterado é o hash criptográfico.

Arquivo original
       │
       ▼
     SHA-256
       │
       ▼
   Hash A

Depois, o arquivo pode ser verificado novamente:

Arquivo atual
       │
       ▼
     SHA-256
       │
       ▼
   Hash B

Se:

Hash A = Hash B

é uma evidência de que o arquivo não foi alterado.

Se:

Hash A ≠ Hash B

o arquivo foi modificado.

Mecanismos utilizados
- Funções hash;
- HMAC/MAC;
- Assinaturas digitais;
- Controle de permissões;
- Logs e auditoria.

Exemplo

Ao baixar um programa, o fabricante pode fornecer o hash do arquivo. O usuário calcula o hash do arquivo baixado e compara os valores.

### 3. :foggy: Autenticidade

A autenticidade permite verificar se uma pessoa, dispositivo ou sistema é realmente quem afirma ser.

Imagine que um computador receba uma mensagem:

"Desligue o servidor."

A pergunta é:

Quem enviou essa mensagem?

Ela foi enviada pelo administrador de redes ou por um atacante?

A autenticidade permite confirmar a origem da comunicação.

Exemplos de autenticação
- Usuário e senha;
- Certificado digital;
- Chave criptográfica;
- Biometria;
- Token;
- MFA.

Exemplo

Quando um usuário acessa um servidor:

Usuário
   │
   ├── Usuário
   ├── Senha
   └── MFA
   │
   ▼
Servidor

O servidor verifica a identidade do usuário antes de permitir o acesso.

Os três conceitos juntos

Em uma comunicação segura, os três conceitos podem atuar simultaneamente:

┌───────────────────────────────────┐
│          Comunicação              │
│                                   │
│ Confidencialidade → dados ocultos │
│ Integridade       → dados intactos│
│ Autenticidade     → origem válida │
└───────────────────────────────────┘

Exemplo: acesso a um banco pela Internet

Quando um usuário acessa um banco utilizando HTTPS:

Confidencialidade: os dados são criptografados;
Integridade: os dados não devem ser alterados durante a comunicação;
Autenticidade: o certificado digital ajuda a confirmar que o usuário está conectado ao servidor legítimo.  





