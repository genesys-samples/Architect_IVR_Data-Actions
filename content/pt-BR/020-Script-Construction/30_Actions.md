---
title: "Ações"
chapter: false
weight: 30
locale: "pt-BR"
---

## Ações integradas e personalizadas

Conforme mencionado, uma das ferramentas mais poderosas em scripts é a capacidade de invocar APIs de plataformas internas ou externas. Isso permite a capacidade de obter, atualizar, criar ou excluir recursos da perspectiva do agente de maneira muito transparente.

Ao navegar até o ícone Play/Ações no canto superior direito, podemos ver uma lista de todas as ações integradas e ter a capacidade de criar ações personalizadas.

O editor de script tem várias ações integradas que podem ser mapeadas para diferentes construtores, como transferência, alteração de página, etc. Para este workshop, criaremos uma ação personalizada selecionando o ícone "**+**".

![image](/images/scriptactions.PNG)

Vamos nomear nossa ação "Atualizar Caso", selecione **Adicionar Etapa (Add Step)**, e selecione **Executar Ação de Dados**, sob Ações.

![image](/images/scriptactionstep1.PNG)

Pesquise a integração do Genesys Cloud Data Action no campo Categoria e selecione a ação de dados que você publicou anteriormente.

Dentro do campo de entrada vamos digitar "**{{**", comece a digitar os nomes das variáveis correspondentes e clique na variável para preencher automaticamente, no exemplo "cu" para "CustomerName -

![image](/images/scriptactionautocomplete.PNG)

Sua ação de dados de execução deve ser semelhante a esta, com todos os campos adicionais acima mapeados -

![image](/images/scriptactionmap.PNG)

"Selecione" **Adicionar Etapa**, e selecione **Se/Então** para adicionar outro passo a nossa ação.

Construtores Se/Então permitem comparar dados e executar ações diferentes dependendo do resultado. 

Eles são simplesmente operadores lógicos que nos permitem dizer coisas como "**Se** isto ugual a isto, **Então** faça isto, ou **se diferente** faça aquilo.

Vamos ajustar **Lado Esquerdo** para sua variável de **successresponse**.

Nosso **Operador** será **Igual a**.

E nosso **Lado Direito** será ajustado para "Atualizado com sucesso"

O que acabamos de construir é a porção **Se** de nossa sentença Se/emtão. Na parte superior da imagem abaixo, o construtor de ação nos diz o que a lógica que inserimos equivale a - 

![image](/images/scriptoutput.PNG)

> **Se a saída da nossa API for igual "Caso atualizado com sucesso" Então...**

Para este workshop, acionaremos um alerta ao agente para que ele saiba que o caso foi atualizado com sucesso. No entanto, você pode acionar várias etapas **Ou Então** adicionais, incluindo outra ação personalizada.

Com a sessão Se finalizada, selecionaremos **Adicionar Etapa** diretamente abaixo dela e selecionaamos **Scripter > Alerta**, e digitamos algo como "Caso atualizado com sucesso" (você também pode colocar sua variável de Saída API aqui) esta será nossa ação **Então**. 

![image](/images/scriptactionif.PNG)

Expanda a ação If/Else clicando na caixa If e adicione uma etapa em **Então**. Você repetirá as etapas de adição de um alerta de scripter, mas desta vez forneceremos um valor de "Falha ao atualizar o caso" (em um cenário do mundo real, provavelmente mapearíamos a resposta de saída aqui).

**Se** sua ação se parecer com a imagem abaixo **Então** selecione Salvar, **Ou então**, faça sua ação ficar parecida com a imagem abaixo (viu o que fizemos nessa frase?) -

![image](/images/scriptactioncomplete.PNG)

Estamos prontos para mapear esta ação!

Selecione o campo de **Texto** você construiu na sessão anterior e selecione a variável "Status do caso" no menu suspenso Valor. No campo de espaço reservado, você pode inserir algo como "Inserir status do caso", este texto será exibido para o agente neste campo antes que ele insira qualquer texto nele (você pode ver o texto do espaço reservado entrando no modo de visualização).

![image](/images/scriptinputfield.PNG)

Selecione o **botão** vazio que você criou na seleção anterior, selecione Nenhuma ação selecionada em Ação de clique e encontre sua ação no menu suspenso personalizado.

![image](/images/scriptbuttonaction.PNG)

Devemos agora **Publicar** nosso script selecionando **Script > Publicar** no canto superior esquerdo.

Agora temos um script totalmente funcional! ou pelo menos esperamos? Hora de testar...

