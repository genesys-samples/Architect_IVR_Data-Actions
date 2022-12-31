---
title: "Definições"
chapter: false
weight: 10
locale: "pt-BR"
---

## Definições

### Fontes de Dados
Uma fonte de dados é qualquer lugar em uma organização onde dados de clientes (ou outros) estejam armazenados e que possamos querer referenciar para usar em uma decisão de rotemamento ou fornecer ferramentas poderosas ao agente.

Dividiremos essas fontes em 2 tipos, **Fontes de Dados Internas** e **Fontes de Dados Externas**.

### Fontes de Dados Internas
Como você deve se lembrar do Workshop de Construção de Ação de Dados (Data Action), utilizamos Genesys Cloud API para fazer referência aos dados da fila. Do ponto de vista do Genesys Cloud, isso será considerado uma fonte de dados interna, pois não estamos invocando dados de sistemas externos.

Genesys Cloud também tem um construtor de 'base de dados', chamado **Tabelas de Dados**. Para o propósito deste workshop, faremos referência a uma tabela de dados para popular a maioria das variáveis dentro do nosso script.

### Fontes de Dados Externa
Qualquer sistema externo ao ambiente Genesys Cloud que hospeda dados que queremos referenciar para roteamento e para o script é considerado uma fonte de dados externa. Exemplos típicos seriam CRM e bases de dados. A interação com esses sistemas geralmente requer ações de dados (data action) ou integrações personalizados.

### Scripts
Scripts (Roteiros de Atendimento) são o que a Genesys define como a tela do agente. Usando dados de fontes internas e externas, agentes podem ter em sua tela ferramentas poderosas tais como informação do registo do cliente, artigos de bases de conhecimento, a habilidade de executar ações de dados (data actions) com um click de mopuse e muitas outras funcionalidades que permitem que as centrais de atendimento criem **interações com significado**.


