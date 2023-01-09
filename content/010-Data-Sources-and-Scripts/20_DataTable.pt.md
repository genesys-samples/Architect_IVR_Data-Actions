---
title: "Configuração das Tabelas de Dados"
chapter: false
weight: 20
locale: "pt-BR"
---

## Configuração das Tabelas de Dados
![image](/images/DTlimits.PNG)

A ideia desta sessão é criar um repositório para os dados do cliente. Um cliente ligará, por meio de uma consulta básica de URA, encontraremos as informações do cliente em nossa tabela de dados e poderemos apresentá-las ao agente por meio do script que construiremos mais adiante.

Para esta parte do workshop, construiremos uma fonte de dados interna ou **Tabela de Dados**. Esta tabela de dados servirá como um repositório contendo informação do cliente que iremos apresentar aos nossos agente. 

Tendo em mente a ideia base de **"Criar interações com mais significado"**,
a melhor prática ao construir uma tabela de dados, ou qualquer fonte de dados, é fazer a si mesmo duas perguntas -
1. **"Quais informações posso fornecer ao meu agente para simplificar seu trabalho, torná-lo mais confiante e capacitá-lo para criar uma interação significativa"** 
2. **"Que informações devemos ter sobre o cliente e o que eles esperam que saibamos?"**

Independentemente de você estar interagindo com um CRM externo ou uma tabela de dados interna, **mais é mais**. Significando guardar, importar ou conseguir a maior quantidade de informação possível sobre o cliente, mesmo que você não queira usá-la agora, você poderá usar mais tarde. Se eu soubesse o time favorito do clientes, poderia usar esse dado para criar uma interação mais significativa!

>Ressalva: Conhecer o time de esportes favorito do cliente pode ser considerado desagradável e um tanto assustador.

Para começar, vamos navegar até Administrador > Tabelas de Dados e selecionar o ícone **+** no canto superior direito para construir uma tabelas de dados.

Tabelas de Dados tem dois componentes principais que vamos precisar definir antes de ppopular nossa tabela de dados -

  * **Rótulo da chave de referência** - Este será a 'chave', ou o campo de dados que será usado como referência a uma linha específica dentro de nossa tabela de dados. No exemplo abaixo estamos usando ANI (Número do Chamador), ou o telefone do chamador para buscar uma linha de dados específica.
  > **Durante a construção, ANI é simplesmente o nome que estamos dando a esta coluna, ou chave. Você pode inserir qualquer valor neste campo, mas este é o campo que usaremos para encontrar nosso cliente.**

  * **Campos personalizados** - Estes campos são, em última análise, os dados que estamos tentando coletar, procurando pelo ANI dos clientes. Podem ser itens simples, como nome e endereço, ou itens mais avançados, como artigos da base de conhecimento que ajudarão um agente a solucionar problemas de sua conta ou números de contas externas para uso em futuras ações de dados (Data actions). 
> **Na imagem abaixo você pode ver os 4 tipos de variáveis para esses campos. Ao selecionar um tipo de variável, você precisará nomear o campo e, se desejar, fornecer um valor padrão (Isso é útil se muitas linhas abrigarem os mesmos dados para o script ou roteamento do agente).**

![image](/images/datatableconstruction.PNG)

Para nosso caso de uso, vamos montar uma tabela de dados com os seguintes campos do tipo **cadeia (string)** (com a chave ANI) -
  * CustomerName (Nome do Cliente)
  * CaseStatus (Status do Caso)
  * Services (Serviço)
  * EmbeddedMap (Mapa)
  * KBURL 

>**Itens como o mapa integrado e a URL da base de conhecimento (KB url) são adicionados para demonstrar a habilidade de embutir páginas Web de forma a auxiliar nossos agentes baseado em indicadores do clientes como seu endereço (Embedded map) ou artigos da base de conhecimento relacionados aos equipamentos ou serviços prestados (KBURL)**

Vamos começar populando uma única linha nessa tabela de dados ao selecionar o ícone **+** no canto superior direito da página. 

Para ANI, vamos entrar com o número que utilizaremos para chamar (não usaremos .e164 ou traços pois isso vai simplificar a resolução do ANI mais tarde). 

Para **CustomerName** você pode inserir qualquer nome que quiser.

Para **CaseStatus** vamos incluir um estado de caso aleatório

Para **Services** definimos 2 serviços através do uso de uma barra vertical (pipe), como no exemplo "Seguro|Creche".

Para **EmbeddedMap** vamos incluir a seguinte URL -
```
https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4328.119139375052!2d-105.04811270372998!3d39.90911499772483!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x876b8bb21a22f617%3A0xa3877b5da434ea5f!2sOrchard%20Park!5e0!3m2!1sen!2sus!4v1659042755728!5m2!1sen!2sus
```
Para KB URL você pode entrar uma URL de qualquer página que gostar.
> **Nota: Nem toda página da web está configurada para ser i-frameable (permitir inclusão em um i-frame), por isso é importante testar e garantir que essas páginas sejam exibidas corretamente na configuração do script.**

Com nossa primeira linha concluída, adicionaremos mais 1 linha com um ANI diferente que você possa lembrar (como 1234) e campos em branco para o restante das colunas.

Depois de concluir suas entradas de 2 linhas, suas linhas e colunas devem se parecer com isto -

![image](/images/DTrowcomplete.PNG)

Embora possa parecer básico, estabelecemos os blocos de construção para fornecer aos nossos agentes mapas interativos com base na localização do cliente, sugestões de base de conhecimento com base em indicadores da conta do cliente e informações de conta de nível básico que os clientes odeiam ter que contar tanto para a URA quanto para o agente.

Se um cliente ligar e corresponder a esse registro, você pode **ENCANTÁ-LOS** com o que você sabe sobre a conta deles, embora essa seja uma maneira muito rudimentar e difícil de obter as informações de um cliente porque estamos construindo localmente.

 Neste caso, a informação é relativamente estática, mas para uma interface com plataformas de terceiros / externas esta informação pode ser pesquisada em produção imediatamente!

Completamos nossa fonte de dados interna! Você pode continuar a adicionar campos a esta tabela de dados conforme necessário (com as restrições dos limites acima).