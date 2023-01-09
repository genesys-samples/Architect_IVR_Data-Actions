---
title: "Projeto"
chapter: false
weight: 10
locale: "pt-BR"
---

## Elementos de Projeto do Scripter (Editor de Scripts)

Para começar, navegaremos para Administração > Scripts e criaremos um novo script. Depois de fornecer um nome, você receberá uma lista de opções de script padrão, para este workshop usaremos um **Script em Branco**.


Bem-vindo à tela em branco!

![image](/images/scriptcanvas.PNG)

Para quem é novo na plataforma, ou contact centers em geral, a interface de script do agente não precisa ser bonita, tem apenas que funcionar. Isso significa sem logotipos ou cores extravagantes, apenas enquadrando um site ou colocando uma área de conversa em uma caixa de texto, podemos reforçar e melhorar a experiência de nosso agente. Abordaremos a formatação e a funcionalidade abaixo, mas é importante entender que **você pode fortalecer seus agentes com o mínimo de esforço** simplesmente incorporando algumas ferramentas ou criando alguns campos.

Embora encorajemos todas as formas de design artístico, para esta parte do workshop vamos construir um script que, embora não seja o mais bonito, demonstra a simplicidade de fornecer informações poderosas ao agentes.

## Conceitos do Projeto

Antes de começar, é importante entender os conceitos e fundamentos da construção do script. 

Ao selecionar **"Script" (canto superior esquerdo de seu script em branco) > Propriedade do Script (Script Properties)** vemos as funcionalidades do script. Scripts pode ser acionados por tips de mídia diferentes, habilitados para acessar ações de dados (data actions) e dados UUI, ou carregados com uma lista de contatos de uma campanha de Outbound. Para esse workshop, vamos habilitar **Entrada (Inbound)** e **Ações de Dados (Data Actions)**. Isso informa ao script que vamos usá-lo para interações de entrada e nos permite executar a ação de dados que acabamos de importar.

![image](/images/scriptproperties.PNG)

>**No mesmo botão "Script", você vai ver tambémum botão de "Salvar". É recomendado que voc6e salve frequentemente para evitar perder seu trabalho (de arte)!**

Os scripts podem ser muito simples com componentes estáticos, o que significa que podemos exibir o mesmo script para um conjunto de agentes (ou todos os agentes) em todas as chamadas. Mesmo um script estático pode fornecer informações incrivelmente benéficas ou até mesmo ferramentas incorporadas a um agente.

Como veremos, os scripts também podem crescer e se tornar mais avançados com ações de dados externos e variáveis totalmente dinâmicas. Usando ações de script personalizadas, você pode permitir que os agentes acionem chamadas de API para sistemas internos ou externos com o clique de um botão, como atualizar um registro de cliente em um CRM externo.

### Conteineres e Layout

Os blocos básicos de construção de scripts são **Conteiner Horizontal Empilhado** e **Conteiner Vertical Empilhado**. Simplificando, você deseja que seus componentes se alinhem da esquerda para a direita? ou de cima para baixo? O script começa de forma padrão, como contêiner vertical raiz.

Na imagem abaixo, você pode ver 2 tipos de conteineres horizontal e vertical na barra de ferramentas superior. 

![image](/images/scriptcontainers.PNG)

Conteineres são capazes de serem aninhados, o que significa que você pode ter contêineres dentro de contêineres. Na parte inferior da tela, você pode ver com qual contêiner está interagindo no momento e navegar facilmente entre esses contêineres clicando nos contêineres de nível inferior ou superior.

![image](/images/scriptnesting.PNG)


Vamos começar a construção do nosso script visualizando o aninhamento-

**1. Adicione um contêiner horizontal em nossa tela selecionando o botão de contêiner horizontal -**

![image](/images/scripthorizontalfirst.PNG)

**2. Selecione o mesmo botão de contêiner horizontal para aninhar um contêiner dentro do contêiner inicial que acabamos de adicionar. Passando o mouse sobre nosso contêiner, podemos ver um contorno pontilhado de seu aninhamento atual (em algum momento vamos parar de dizer contêiner) -**

![image](/images/scripthorizontalsecond.PNG)

**3. Adicionaremos mais 1 contêiner selecionando o contêiner horizontal inicial que construímos, selecionando o contorno dele representado acima e selecionando o botão do contêiner horizontal mais uma vez**

Com este terceiro contêiner adicionado, temos um contêiner horizontal (retratado como a caixa pontilhada do lado de fora) com 2 contêineres horizontais aninhados empilhados lado a lado. Podemos ver que estamos interagindo com um desses contêineres horizontais aninhados conforme ele aparece em negrito. 

![image](/images/scripthorizontalstack.PNG)


Isso nos permite dividir um único contêiner horizontal em 2 contêineres separados lado a lado e inserir componentes, como botões, em partes separadas da tela. 

Agora vamos selecionar o contêiner a esquerda desses dois dispostos lad- a lado e selecionar o botão **"Botão"**, para adicionar um botão dentro deste contêiner (o palavreado fica menos bobo depois) -

![image](/images/scriptbuttonleft.PNG)

Adicionaremos um botão ao contêiner correto que permitirá aos agentes ver uma separação visual desses elementos em uma chamada ao vivo e nosso script deveria se parecer com -

![image](/images/scriptbuttons.PNG)

>Formatação com aninhamento será importante quando começarmos a apresentar mais informações a um agente.

Existem vários editores visuais que podemos adicionar a esses contêineres, como cor de fundo ou bordas (ambos podem ser encontrados selecionando o contêiner e selecionando a aparência no lado direito).

![image](/images/scriptcontainerappearance.PNG)

### Conceitos adicionais de visualização

Dentro de layout, podemos definir visualizações como largura e altura, assim como **Organização dos Filhos** (Quero meus botões centralizados, no início ou no final de um contêiner?) e se é **Visível** (eu só quero mostrar este componente com base em outros parâmetros?)

Largura e altura tudo para você definir o tamanho de um componente. Para alguns componentes, como contêineres, deixá-los esticar ou dimensionar automaticamente permitirá que preencham o espaço necessário. Componentes como imagens podem precisar ser dimensionados manualmente.

Ao selecionar cada um dos nossos contêineres de botões e definir a disposição dos filhos para **centro** podemos ver que o botão muda para centro do contêiner.

![image](/images/scriptcentered.PNG)

Ao selecionar um botão (ou até mesmo o próprio contêiner), podemos encontrar a cor de fundo ou a cor do texto, quando aplicável, nas caixas de ferramentas **Comum** e **Aparência**. As cores podem ser definidas em nível hexadecimal para esquemas de cores mais granulares.

![image](/images/scriptcolorhex.PNG)

As cores também podem ser definidas como uma variável, permitindo que diferentes esquemas de cores sejam inseridos dinamicamente.

![image](/images/scriptcolorvariable.PNG)

Dentro da seção de layout de um componente, podemos configurar se o componente é **Visível**. Ser visível nos permite definir uma variável booleana para determinar se um componente exibido ou não.

No exemplo abaixo, atribuímos uma variável booleana chamada "Existing Customer (Cliente existente)?", que nos permitiria ocultar componentes de script (como campos de conta) se o cliente não for um cliente existente.

![image](/images/scriptvisibility.PNG)
