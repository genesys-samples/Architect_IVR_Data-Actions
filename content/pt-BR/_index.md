---
title: "Interações com Significado Parte 1"
chapter: true
weight: 1
locale: "pt-BR"
---

# A Arte de Criar Interações com Significado - Parte 1

## Qual o Objetivo deste Workshop?

O objetivo da parte 1 desta série de workshops de 2 partes é mostrar como podemos utilizar roteiros de atendimento (scripts) para fornecer ferramentas incrivelmente poderosas aos agentes com o mínimo de esforço. No final, teremos construído e testado um script de agente que fornecerá mapas interativos, artigos da base de conhecimento e permitirá que os agentes atualizem um registro de cliente falso. O público-alvo é qualquer pessoa

Passaremos pela construção de fonte de dados simples, bem como uma compreensão da interface de scripting para apresentar os conceitos básicos necessários para criar scripts mais avançados. Seguiremos então, para ações de script personalizadas para mostrar em um nível intermediário como podemos usar scripts para permitir que nossos agentes executem funções poderosas, como por exemplo, atualizar registros de clientes

## Quem é o público-alvo?

O público-alvo deste workshop é qualquer pessoa  (Parceiro ou Cliente) para a qual a interface de script do agente seja uma novidade, principalmente clientes em potencial ou novos clientes que desejam aprender como podemos aproveitar uma ferramenta nativa poderosa para começar a ajudar nossos agentes e melhorar a experiência de nossos clientes.

## Como você define uma interação com significado?

Vamos começar com o nível básico: **Interação** - De modo muito simples definida como uma comunicação ou envolvimento direto com alguém ou algo.

Do ponto de vista do contact center, podemos restringir isso a um cliente interagindo com uma plataforma, um bot, um agente ou qualquer outra mídia ou ponto de contato que possa consumir. Para este workshop vamos definir uma interação como um engajamento entre um cliente e um agente, afinal, é simples fornecer um bot com mais respostas, mas como capacitar nossos agentes?

Para muitos de nós, consumidores, uma interação significativa pode ser tão simples quanto aquelas pilhas de dados que inserimos na URA sendo repassado ao agente. Simplificando, inserimos nosso número de conta e o agente não precisou nos pedir quando finalmente nos conectamos. Eles abriram nossa conta e as informações que inserimos pareciam ter significado, um propósito.

Mas como nós, como agentes, administradores ou mesmo supervisores do outro lado da interação, nos conectamos com nossos clientes em um nível mais profundo?

Vamos começar nos colocando no lugar do cliente. Temos nossa conta há anos, atualizamos, fizemos alterações, abrimos casos e o mais importante - **Nós interagimos com ela porque somos nós**. Por que, então, parece que toda vez que interagimos com alguém é a primeira vez que eles ouvem falar de nós? Claramente, sou apenas uma conta, sou apenas uma métrica para eles que vai estar em um relatório tarde.

Em seguida, vamos nos colocar no lugar do provedor - Para qualquer pessoa que tenha trabalhado em uma central de atendimento como um atendente, nós **interagimos** com muitos clientes todos os dias e o motivo de suas reclamações geralmente é transparente para nós, ou fora de nosso controle. Atendemos uma chamada, às vezes não sabemos quem está ligando, mas nós os validamos e tentamos resolver seus problemas. As reclamações constantes de "Já digitei isso no seu sistema telefônico (URA)" não nos ajudam, afinal não construímos o a árvore da URA e estamos aqui apenas para ajudar. Temos muitos sistemas separados e a solução da liderança é adicionar mais monitores e guias para acompanhar com quem estamos falando e quando.

O fato é que os problemas dos clientes são resultados dos problemas dos agentes. O longo tempo de espera de um cliente é derivado do longo tempo de atendimento do agente. No entanto, não podemos olhar para o cliente em busca de dicas sobre por que ele está esperando por tanto tempo, a ênfase vai imediatamente para o agente.

Com os recursos certos, um agente pode fazer conexões significativas com seus clientes, muito além de pedir o número da conta e informar o status do caso...


### Pré-requisitos
  * Wokshop Architect 100  
  * Workshop de construção de Data Action

### Objetivos do Aprendizado

**Neste workshop, você vai aprender...**

1. Como construir uma fonte de dados interna
2. Como fazer referencia e atualizar esta fonte de dados dentro da interface de script do agente
3. Como construir um script com referências de variáveis totalmente dinâmicas
4. Como usar funções avançadas no script tais como ações personalizadas (custom actions)

