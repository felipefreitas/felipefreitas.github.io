---
layout: post
title:  "Aplicando BDD a testes de integração"
date:   2016-01-12 15:28:00
categories: development
---

Sabemos que BDD ('Behavior Driven Development') trouxe uma abordagem diferente quanto as metodologias de testes para guiar o desenvolvimento. Sua forma, aproximou ainda mais o TDD ('Test Driven Development') a linguagem que descreve o negócio. A proposta de Dan North era aproximar mais o aspecto comportamental do domínio do negócio. E pensando nisso, apliquei este conceito em um projeto a partir da API, seguindo uma abordagem top-down com foco no valor que a API entregaria aos consumidores. Bom, isso me levou a pensar em testes de integração. Mas como assim? 

[IMAGEM DE UMA FEATURE TESTANDO UM RECURSO DA API]

A idéia principal de aplicações testáveis gira em torno do desacoplamento, quanto mais desacoplada sua aplicação mais ela é tesável. Para obter isso vou utilizar o OWIN que é um padrão aberto de desenvolvimento de interfaces desacopladas do servidor que nos permitirá obter back-end e front-end testáveis. A Microsoft disponibiliza um pacote de ferramentas de desenvolvimento para isso o 'Microsoft.Owin' e basta seguir os padrões especificados no OWIN. Explicar esse 'start do OWIN' pode tornar o POST longo e cansativo pois o objetivo aqui é abordar os testes através do BDD.

#Microsoft.OWIN.Testing

Existem outras formas de testar a API, a que vou utilizar é uma mais simples e fácil de aprender. Nesse contexto, o framework de teste irá criar todo o pipeline do OWIN em memória juntamente com a aplicação simulando uma execução no IIS e nela rodar os cenários de testes criados. O pacote Microsoft.Owin.Testing nos permite criar esse ambiente em memória para testes, nele iremos configurar o pipeline da aplicação em OWIN, definindo o container de dependências, configurações de rotas e interface HTTP, etc.

[IMAGEM DE CONFIGURAÇÃO DO STARTUP.cs]

