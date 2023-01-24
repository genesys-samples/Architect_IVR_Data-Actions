---
title: "Variáveis e Modelos"
chapter: false
weight: 20
locale: "pt-BR"
---

## Variáveis

Tudo (ou quase tudo) dentro de um script **pode** ser uma variável. Nem tudo precisa ser, ou deveria ser uma variável. Para demonstrar isso, adicionaremos uma caixa de texto ao nosso contêiner vertical principal clicando em nosso **raiz contêiner vertical (main vertical container)** e selecionar o ícone texto -

![image](/images/scripttextbox.PNG)

Dentro desta caixa de texto, vamos colar o texto abaixo. (com base no exemplo abaixo, você pode simplesmente digitar algo aqui se não quiser copiar e colar)

```
Olá, super obrigado por ligar para nossa empresa bacana que faz coisas muito legais! 
```
Nosso script agora exibe uma saudação estática que os agentes podem ler em todas as chamadas. A próxima pergunta é: e se quisermos que os agentes digam seus nomes? ou cumprimente os chamadores de forma diferente caso a caso. É aqui (em um nível muito básico) que as variáveis absolutamente brilham (de uma maneira não incrivelmente gloriosa)!

Existem alguns tipos diferentes de variáveis que dividiremos em duas categorias - 

**1. Variáveis do Scripter.**

**2. Variáveis Persoanlizadas.**

 #### Variáveis do Scripter

Antes de extrair quaisquer dados externos, é sempre importante revisar quais dados podem ser nativos na interface do script: Variáveis de script integradas podem ser encontradas em nosso centro de recursos - https://help.mypurecloud.com/articles/built-in-script-variables/. Isso fornecerá uma lista de itens que são armazenados nativamente sem exigir uma pesquisa de dados.

Esses são elementos de dados que podem ser referenciados sem qualquer configuração adicional, como o agente e o nome da fila. Uma lista completa pode ser encontrada selecionando a variável (ou ícone em forma de cubo no canto superior direito) e expandindo o menu suspenso "Scripter".

![image](/images/scriptscriptervariables.PNG)

Alguns campos exigem a seleção de sua variável em uma lista suspensa, enquanto em outros campos você pode referenciar/inserir uma variável digitando 2 **chaves duplas/colchetes** (como são conhecidos na comunidade científica), ou **{{** ao interagir com um campo de entrada, como uma caixa de texto.

Ao digitar esses **colchetes** dentro de sua caixa de texto, será apresentado uma lista de variáveis personalizadas e de scripter que podem ser inseridas selecionando uma. Essa lista também pode ser pesquisada por nome de variável, portanto, é uma prática recomendada usar convenções de nomenclatura lógica se você optar por criar uma variável personalizada.

No exemplo abaixo, faremos um script totalmente personalizado simplesmente adicionando "Meu nome é" e usando os colchetes para localizar "Scripter.Agent Name"

![image](/images/scriptagentvariable.PNG)

Abaixo está um exemplo onde pesquisamos "Nome" no campo de busca (a pesquisa torna-se muito útil à medida que seus scripts crescem para dezenas ou centenas de variáveis personalizadas).

![image](/images/scriptvariablesearch.PNG)

As variáveis que não são de entrada, juntamente com muitos outros componentes, podem ser testadas selecionando o script de visualização no canto superior direito da interface do script.

![image](/images/scriptpreview.PNG)

Na janela de visualização, podemos ver que nossa variável {{Scripter.Agent Name}} agora está exibindo o nome em nossa conta. A janela de visualização é útil para testar componentes e exibir o script sem toda a formatação e variáveis do contêiner. Ele pode ser encerrado selecionando o botão de script de visualização novamente.

#### Variáveis Persoanlizadas
Essas variáveis são criadas por você para customizar seu script, acionar visibilidade, ações de dados, ações de script, etc.

Navegando de volta ao painel de variáveis no canto superior direito e selecionando o ícone **+** você pode ver uma lista de tipos diferentes de variáveis. Vamos dar foco nos tipos **Cadeia (String)** para este workshop. Você pode clicar [**Aqui**](https://help.mypurecloud.com/articles/dynamic-script-variables/) para informações sobre variáveis dinâmicas.

O construtor de variável permite definir se os valores da variável serão 
 * Saída do script para ser usada em outro fluxo ou plataforma externa (existe uma plataforma externa que queremos atualizar a partir deste script?)
 ou
 * Entrada para o script de outra fonte (existe uma plataforma externa que queremos para preencher este script?).
 
 Você também pode definir valores padrão para exibir informações estáticas se nenhum valor for definido.

Vamos construir as seguintes 6 variáveis **string** que mapeiam diretamente para a tabela de dados que construímos anteriormente, todos eles serão alternados para **Entrada Sim (Input Yes)** com **nenhum valor padrão (no default value)** - 
  * ANI 
  * CustomerName
  * Services
  * EmbeddedMap
  * KBURL
  * DataTableID

![image](/images/scriptcustomvariable.PNG)

Adicionaremos mais 2 variáveis de string sem direção definida **(deixar Saída e Entrada em não)** - 
  * CaseStatus
  * successresponse

Quando terminar, você deve ter uma lista parecida com esta - 

![image](/images/scriptvariablelist.PNG)

### Construindo nosso Script

Com nossas variáveis criadas, vamos adicionar os componentes necessários para mapeá-las.

Para começar, vamos apagar os 2 botões que criamos (selecionando o botão e clicando na lixeira do lado direito), tomando cuidado para não deletar os próprios contêineres. Nos contêineres, agora vazios, adicionaremos páginas da Web selecionando o ícone de **globo** enquanto interage com o recipiente. O resultado deve ficar assim - 

![image](/images/scriptwebpages.PNG)

> **Você pode selecionar a página da web e navegar até o layout para ajustar o tamanho**

Agora vamos mapear nossa variável **EmbeddedMap** e **KB URL** a esses selecionando um componente de página web e entrando com a variável no campo "Origem da página da Web".

![image](/images/scriptwebpagesource.PNG)

Com ambas as nossas páginas web mapeadas, vamos inserir o nome do cliente em nossa caixa de texto de saudação. Sua caixa de texto deve ser algo como - 

```
Olá {{Customer Name}}, super obrigado por ligar para nossa empresa bacana que faz coisas muito legais! Meu nome é {{Scripter.Agent Name}}
```

Se você acabou com sua caixa de texto abaixo das páginas da Web, pode deslocar o componente selecionando o componente e clicando na seta para cima ou para baixo no lado direito. 

![image](/images/scriptupdown.PNG)

Terminaremos adicionando um campo de entrada e um botão abaixo dessas páginas da web

![image](/images/scriptbuttoninput.PNG)

Atualizaremos esses 2 campos na próxima parte do nosso workshop.

Seu projeto de script agora está completo! Deve parecer algo como - 

![image](/images/scriptcomplete2.PNG)

Legal né?! Neste ponto, gostamos de considerar esta arte CX contemporânea moderna... Agora selecione **Script > Salvar**.

O último item no script básico é a capacidade de criar modelos de componentes e modelos de script a partir de contêineres, componentes individuais ou scripts inteiros. 

Você pode criar um modelo de componente selecionando um contêiner ou componente e clicando no ícone da caixa ao lado das setas e nomeando-o - 

![image](/images/scriptcomponenttemplate.PNG)

Estes podem ser inseridos em scripts usando o mesmo ícone na barra de ferramentas na parte superior e selecionando o modelo pelo nome

Modelos de script completos são criados selecionando **Script > Criar modelo com base em Script**. Eles são selecionados ao criar um novo script.

Os modelos de componente e script são ferramentas poderosas para minimizar e padronizar a construção de novos scripts.