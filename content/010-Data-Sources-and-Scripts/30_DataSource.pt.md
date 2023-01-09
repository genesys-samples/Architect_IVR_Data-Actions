---
title: "Referenciando uma Fonte de Dados"
chapter: false
weight: 30
locale: "pt-BR"
---

## Referenciando uma Fonte de Dados

>**Nota: Vamos referenciar nossa tabela de dados como um "CRM Simulado" ou "BD", essas fontes de dados não foram projetadas para substituir um CRM.**

Os scripts podem ser usados para fornecer ferramentas poderosas, como ferramentas de incorporação/integração, fornecendo sugestões de bases de conhecimento e informações do cliente. Uma das funções mais poderosas que os scripts oferecem é a capacidade de vincular chamadas de API aos botões e campos com os quais os agentes estão interagindo dentro da interface de script do agente.

Do ponto de vista do agente, podemos atualizar um caso de cliente, agendar uma consulta ou muitas outras opções sem sair de nossa interface Genesys Cloud. Do ponto de vista do cliente, isso equivale a uma interação simplificada em que a pessoa com quem estou interagindo conclui rapidamente essas tarefas. 

Para este workshop, usaremos a tabela de dados interna que acabamos de criar como uma fonte de dados externa simulada. Vamos importar uma ação de dados (Data action) que atualiza o campo **CaseStatus** de uma linha de nossa tabela de dados. Embora esta seja uma ação de dados interna, a metodologia pode ser usada para ações externas.

### Vamos começar

Ainda dentro da tabela de dados que construímos, copiaremos o GUID da tabela de dados e o armazenaremos para referência posterior. Isso pode ser encontrado na barra de endereços, conforme mostrado abaixo - 

![image](/images/DTguid.PNG)

Com nosso GUID da tabela de dados salvo, vamos fazer download e importar uma ação de dados (Data action) já construída.

Se você não tem um cliente Oauth com permissões **Data Table Write**, ou não tem uma integração **Genesys Cloud Data Actions** instalada, por favor, use como referência a seguinte página [**Data Action Workshop**](https://workshop.genesys.com/workshops/DataActionsWorkshop/020-configuration/30_third.html), notar que isto não determina um Oauth role específico, mas demonstra como construir o cliente Oauth e alocar as permissões.

Para importar a ação de dados (data action), navegue até - **https://github.com/GSC-Shared-Resources/ArchitectWorkshopContent**, selecione o botão verde **Code**, e faça download do arquivo zip.

![image](/images/githubdl.PNG)

Depois de extrair esta pasta em sua máquina local, navegue até o Genesys Cloud > Administração > Ações, selecione "Importar" e navegue para o arquivo .json que acabou de extrair. Selecione um nome para a integração e forneça um nome para a ação de dados (Data action).

![image](/images/daconstruct.PNG)

Para validar se a ação de dados funciona corretamente, dentro da ação de dados que acabamos de importar, navegaremos para Configuração > Testar, insira informações simuladas para cada campo **exceto o ANI** para o qual entraremos o ANI que fornecemos (1234) para nossa linha em branco, assim como o **DataTableID** onde vamos entrar o GUID da tabela de dados que reservamos. Selecione **Executar Ação (Run Action)**, se a ação retornar verde/successo, podemos navegar de volta para nossa tabela de dados e ver as atualizações para aquela linha, contudo nesse ponto deveríamos ser capazes de **Salvar e Publicar (Save & Publish)** nossa ação de dados.

![image](/images/DAtest.PNG)

Agora criamos uma ação de dados para atualizar nosso CRM/BD simulado que pode ser usado no script do agente para permitir que os agentes façam atualizações em plataformas 'externas' sem precisar sair de seu único painel de vidro.