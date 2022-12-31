---
title: "Genesys Architect"
chapter: false
weight: 40
locale: "pt-BR"
---

## Testamdo Nosso Script

Para fechar a parte 1 deste workshop, criaremos um fluxo de Architect simples que chama nossa tabela de dados, define os retornos como variáveis utilizáveis e os mapeia para um script de agente. Estaremos examinando todas as partes do Architect em **Muito** mais detalhes na parte 2. Para esta parte, estamos simplesmente criando um fluxo básico para testar nosso script e garantir que ele funcione.

Para começar vamos construir uma fila:

Se você não atendeu ao workshops de ré-requisito - 
1. Navegue até to Administração > Filas, **Criar Fila**.
![image](/images/queuecreate.PNG)

Atribuir a si mesmo como membro 

![image](/images/queueaddmembers.PNG)

Agora vamos criar um novo fluxo do Architect navegando para **Administração > Architect**, dentro  **Chamada de Entrada** selecionamos **+Adicionar** e damos um none significativo, uam descriçào e selecionamos **Criar Fluxo**.

![image](/images/architectnewflow.PNG)

Com nosso novo fluxo construído, a primeira coisa que faremos é adicionar uma nova tarefa reutilizável. No painel esquerdo, selecione **adicionar tarefa reutilizável aqui**, passar mouse sobre **Barra de Ferramentas** and select **Tarefa**.

![image](/images/architectnewtask.PNG)

Em seguida, definiremos isso como nossa tarefa inicial, conforme definido na parte 2, este será o ponto de entrada para nosso fluxo.

![image](/images/architectsetstart.PNG)

Com nossa nova tela em branco, vamos adicionar alguns itens, sendo o primeiro uma pesquisa de tabela de dados, dentro da caixa de ferramentas, navegue até **Dados > Pesquisa de Tabela de Dados** e sdefina isso como nosso ponto de partida arrastando-o para o nosso canvas.

Ao selecionar este bloco, podemos **escolher a tabela de dados que construímos anteriormente**, definindo nossa entrada - **o que estamos usando para encontrar uma entrada nesta tabela de dados?**. neste caso, vamos atribuir estaticamente nosso **Chave/ANI** no campo de entrada. Bem como nossas saídas, ou **que estamos retornando desta tabela de dados?**.

Nosso mapeamento de entrada/saída deve ter a seguinte aparência - 

![image](/images/architectdt.PNG)

Dentro do caminho encontrado da nossa tabela de dados vamos arrastar um operador **Definir Inicialização de tela**, que pdoe ser encontrado sob **Fluxo**.

![image](/images/architectsetscreen.PNG)

No lado direito, selecionaremos nosso script e começaremos a mapear as **Saídas** de nossa **Tabela de Dados** para as **Variáveis de Entrada** que construimos em nosso script. Simplificando, temos dados saindo de nossa tabela de dados, que precisamos inserir em nosso script para que os agentes vejam.

 Vamos mapear as variáveis que recuperamos de nossa pesquisa de tabela de dados para as entradas solicitadas para nosso script com algumas exceções, seus campos pop-up de tela devem se parecer com o diagrama abaixo, novamente, **isso será esclarecido e declarado na parte 2**. Por enquanto, estamos apenas testando nosso script para garantir que funcione.


![image](/images/architectscriptmap.PNG)

No caminho final, adicionaremos um **Transferir para DAC** navegando dentro da barra de ferramentas em **Transferir > Transferir para DAC** e arrastando isso abaixo do nosso bloco **Definir Inicialização de tela**. Selecione a fila que construímos anteriormente e no caminho de falha do bloco **Transferir para DAC** vamos adicionar um bloco **Desconectar**  que pode ser encontrado na camada base da caixa de ferramentas.

No final, nosso fluxo deve ficar como na imagem abaixo.

![image](/images/architectflowend.PNG)

Se o seu fluxo se parecer com a imagem acima, selecione **Publicar** na barra de ferramentas para fazer suas alterações ao vivo em produção.

![image](/images/architectpublish.PNG)

**O último passo** para testar nosso novo script sofisticado, é atribuir um número ao fluxo que acabamos de construir.

Todo o processo pode parecer inverso, mas não podemos fazer pizza sem forno, certo? E não podemos construir aquele forno sem tijolos... Este processo nos faz começar pelos tijolos. Lançando as bases para o Forno que construiremos na parte 2

Navegue até Administração > Roteamento de chamadas, **Adicione Rota de Chamada**, selecione seu fluxo dentro de **Qual fluxo de chamadas deve ser usado?** e defina os números de chamado em **Números de entrada** a direita, isso se você possuir um número de entrada **DID** na plataforma, ou construiu sua lista de **DID**

![image](/images/callrouting.PNG)

Ao ligar para o número que você atribuiu, você está ligando para o fluxo que acabou de criar com a **DPesquisa na Tabela de Dados e Definir Inicialização de tela**. Se você se atribuiu como membro da fila, poderá receber visualmente os itens que construímos em sua tela.



