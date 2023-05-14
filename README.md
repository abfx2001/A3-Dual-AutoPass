<div align="center">

<h1> Projeto UC Dual AutoPass </h1>
<img src="https://github.com/abfx2001/A3-Dual-AutoPass/assets/71567139/fe44d000-b886-4ef4-ad0e-0cf389b36e4f"width="80rem">
<h2> Integrantes do Grupo: </h2>
<h3> Arthur Batista Furlan, RA: 820140000 </h3>
</div>

# Sumary

* [Sumary](#sumary)
* [About](#about-project)
* [Technology Used](#technology-used)
* [1 - Application Characteristics and Requirements](#1---application-characteristics-and-requirements)
  * [Functional Requirements](#functional-requirements)
  * [User Flow](#user-flow)
* [2 - Personas](#2---personas)
* [3 - Scenery](#3---scenery)

# About Project

O projeto tem como pauta o `re-design` e `desenvolvimento` de novos módulos para uma aplicação usada em `ATMs`
de recarga de bilhete de transporte público.

A empresa em questão é a `AutoPass` que oferece os serviços dos bilhetes `TOP`, é uma empresa voltada a descobrir novas tecnologias e implanta-las nas suas regras de negócios para trazer aquilo de melhor para os seus clientes.

O foco do projeto é aprimorar a `usabilidade` e `UX (experiência do usuário)` trazendo uma aplicação amigável e intuitiva, além de incentivar todos a baixarem o APP, que é o foco atual da empresa.

A identidade visual da empresa será mantida, mas vai ser trazido um novo design para a aplicação, moderno e intuitivo, que irá agradar o público destinado.

# Technology Used

* [HTML5](https://html.spec.whatwg.org/)
* [JavaScript](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)
* [CSS3](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [NodeJs](https://nodejs.org/docs/latest-v20.x/api/)
* [NPM](https://docs.npmjs.com/)

# 1 - Application Characteristics and Requirements

A `AutoPass` pode ser considerada a maior empresa privada que traz soluções para a área de bilhetagem eletrônica no Brasil, realizando e gerindo mais de 4,5 milhões de transações diárias. Com 12 anos no mercado, ela traz como diferencial as inúmeras ferramentas tecnológicas capazes de se adaptar a qualquer tipo de plataforma, trazendo inteligência, flexibilidade e rapidez em seus serviços.

No caso da aplicação em estudo, os `ATMs`, é necessário uma nova cara para os mesmo, pois ainda é um serviço muito utilizado na grande São Paulo e como é um produto caro de implantar, seu funcionamento deve ser otimizado e ajustado para atender todo o público, a seguir os serviços oferecidos diretamente nos `ATMs`:

Recarga/Status do `Cartão TOP`: o cartão TOP é similar ao bilhete único, com ele é possível embarcar em nos transportes públicos que abrangem as `estações da CPTM e Metrô` além do transporte `intermunicipais de ônibus da EMTU`.

Emissão de `Bilhete Digital QR Code`: é um bilhete digital emitido em um papel com QR Code, destinado ao embarque nas mais de 180 `estações da CPTM e Metrô` de São Paulo.

Recarga/Status do `Bilhete Único`: o bilhete único é muito utilizado, ele é gerido pela `SPTrans, CPTM e Metrô`, oferecendo o armazenamento de crédito para pagamento de tarifas nos transportes públicos na cidade de São Paulo.

## Functional Requirements

* [x] Recarregar Cartão TOP em Dinheiro

* [x] Recarregar Cartão TOP via Cartão de Débito

* [ ] Recarregar Cartão TOP via PIX

* [x] Consultar o saldo do Cartão TOP

* [x] Vender Bilhete Digital QR Code via Cartão de Débito

* [ ] Vender Bilhete Digital QR Code via PIX

* [x] Verificar/Re-imprimir Bilhete Digital QR Code

* [x] Recarregar Bilhete Único em Dinheiro

* [x] Recarregar Bilhete Único via Cartão de Débito

* [ ] Recarregar Bilhete Único via PIX

* [x] Consultar o saldo do Bilhete Único

## User Flow

```mermaid
---
title: Fluxo de Usuário com o Cartão TOP
---
graph LR 
A[início] --> B[Tela \n Principal]
B --> C[Inserir \n Cartão TOP]
C --> C1[Selecionar \n Cartão TOP]
C1 --> D1[Ver Saldo \n de Tarifas]
C1 --> D2[Recarregar \n Cartão] 
D2 --> D3{Tipo de \n Recarga}
D3 -->|V.T.| D4
D3 -->|Comum| D4
D3 -->|Escolar| D4

D4{Selecionar \n forma de \n Pagamento}
D4 --> |Dinheiro| D5
D4 --> |Cartão de Débito| D5
D4 --> |PIX| D5
D5[Escolher \n Quantidade] --> E[Efetuar \n Pagamento]
E --> G[Emitir \n Comprovante]
G --> H[Fim]
```

```mermaid
---
title: Fluxo de Usuário com o Bilhete Digital QR Code
---
graph LR 
A[início] --> B[Tela \n Principal]
B --> C[Selecionar \n Bilhete Digital \n QR Code]
C --> DE[Re-imprimir QR Code] 
C --> DR[Consultar QR Code] 
C --> DC[Comprar QR Code] 
DC --> D2[Escolher \n Quantidade] 
D2 --> D3{Selecionar \n forma de \n Pagamento}
D3 -->|PIX| E
D3 -->|Cartão de Débito| E
E[Efetuar \n Pagamento]
E --> G[Emitir \n Código QR Code]
G --> H[Emitir \n Comprovante]
H --> I[Fim]
```

```mermaid
---
title: Fluxo de Usuário com o Bilhete Único
---
graph LR 
A[início] --> B[Tela \n Principal]
B --> C[Inserir \n Bilhete Único]
C --> C1[Selecionar \n Bilhete Único]
C1 --> D1[Ver Saldo \n de Tarifas]
C1 --> D2[Recarregar \n Cartão] 
D2 --> D3{Tipo de \n Recarga}
D3 -->|V.T.| D4
D3 -->|Comum| D4
D3 -->|Escolar| D4

D4{Selecionar \n forma de \n Pagamento}
D4 --> |Dinheiro| D5
D4 --> |Cartão de Débito| D5
D4 --> |PIX| D5
D5[Escolher \n Quantidade] --> E[Efetuar \n Pagamento]
E --> G[Emitir \n Comprovante]
G --> H[Fim]
```

```mermaid
---
title: Fluxo de Usuário Durante o Pagamento
---
graph LR 
A[início] --> B{Tipo de \n Pegamento}
B --> |PIX| C[Efetuar transferência \n pela leitura do QR Code]
B --> |Dinheiro| D[Selecionar o valor \n referente as cedulas]
B --> |Cartão de Débito| E[Inserir o cartão na máquina]
C --> C1[Compra Efetuada]
D --> D1[Inserir Cedulas]
E --> E1[Digitar Senha]
D1 --> C1
E1 --> C1
C1 --> I[Informativo para \n Utilização do Aplicativo]
C1 --> F[Imprimir Comprovante]
F --> G[Fim]
```

# 2 - Personas

<iframe src="https://app.milanote.com/1PY3FG1lEWvXbZ?p=bnJFryhCiY4" width="800" height="500" frameborder="0"></iframe>

* [LINK PARA PERSONAS COMPLETO](https://app.milanote.com/1PY3FG1lEWvXbZ?p=bnJFryhCiY4)

# 3 - Scenery
