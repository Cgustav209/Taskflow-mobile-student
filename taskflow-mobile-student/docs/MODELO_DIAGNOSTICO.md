# Diagnóstico inicial do aplicativo
 
## 1. Identificação
- Equipe: EquiPiada
- Integrantes: Felipe Aragão da Silva, Heitor Guimarães Almeida e Benjamin Dominique
- Data: 03/08/2026
- Ambiente utilizado: Vscode e Android Studio
 
## 2. Funcionalidades observadas
| Código | Funcionalidade | Situação | Evidência |
 
|CT-001|Criar tarefa|Aprovado, a tarefa foi criada e apareceu na lista|ao tentar criar uma tarefa do 0, colocando descrição e titulo, a tarefa é criada com sucesso|
 
|CT-002| Criar tarefa sem titulo | Reprovado, o sistema cria a tarefa sem titulo| ao tentar criar uma tarefa do 0, sem titulo, o sistema permite a criação invés de emitir um aviso e evitar a criação|
 
 
|CT-003| Escolher prioridade | Aprovado, o Usuario consegue escolher a prioridade | Ao criar uma tarefa, o Usuario pode escolher entre as 3 prioridades, Baixa, média e alta sem problemas |
 
|CT-004| Editar prioridade | Aprovado, a prioridade pode ser alterada sem problemas entre as 3 prioridades | Ao editar uma tarefa, o usuario consegue editar a prioridade da tarefa sem problemas, escolhendo qualquer uma das opções, Baixa, Média, Alta |
 
|CT-005| Excluir tarefa | Reprovado, o Sistema exclui direto, sem aviso de confirmação | Ao tentar excluir uma tarefa, deveria aparecer um Aviso, pedindo a confirmação da exclusão, coisa que não Ocorre, a tarefa é simplismente excluida ao clicar no botão|
 
|CT-006| Editar Tarefa | Aprovado, O Sistema atualiza tarefas sem problemas | ao editar uma tarefa, e salvar, as alterações ocorrem normalmente, e ficam salvas na nova tarefa|
 
|CT-007| Editar tarefa sem titulo | Reprovado, o Sistema aceita a alteração para deixar sem titulo | ao editar uma tarefa, e apagar o titulo, o sistema aceita a alteração, e salva a edição com a tarefa sem titulo|
 
|CT-008| Filtrar Tarefas | Reprovado, o Sistema não filtra por tarefas pendentes ou concluidas | Ao tentar filtrar uma tarefa, o sistema não filtra, fazendo com que Tarefas concluidas aparecam na aba Pendente e vice-versa|
 
|CT-009| Concluir Tarefas | Aprovado, o Sistema conclui tarefas sem problemas | Ao tentar marcar uma tarefa como concluida, altera os status dela sem mais problemas
 
|CT-010| Manter Tarefas Salvas | Aprovado, as tarefas ficam salvas|após criar tarefas, fechar e voltar pro APP, as tarefas se mantem salvas com seus status mantidos|
 
|CT-011| Manter Tarefas Editadas Salvas| Reprovado, as alterações voltam ao padrão | Após editar uma tarefa, e salvar, se fechar o app, e entrar de novo, as alterações da tarefa somem, voltando ao padrão antes das alterações|
 
|CT-012| Funcionar em Diferentes tamanhos | Aprovado, o APP funciona em diferentes tamanhos de tela | Ao colocar em celulares de diferentes tamanhos, o app funciona perfeitamente, sem nenhum problema por resolução

## 3. Problemas encontrados
### BUG-001
- Título: Titulo
- Ambiente:tela inicial
- Pré-condição: estar dentro do app
- Passos para reprodução:Clicar no mais, para criar tarefa, digitar a descrição, escolher prioridade, e salvar tarefa
- Resultado esperado:aparecer um aviso e impedir o usuario de criar a Tarefa sem titulo
- Resultado obtido: a Tarefa é criada sem Titulo
- Frequência: 100% das Tentativas
- Impacto: Baixo
- Evidência:ao se tentar criar uma tarefa, com o campo titulo vazio, ele cria, quando na verdade, deveria emitir um aviso, e impedice o usuario de criar tal tarefa, com a Ausencia de titulo, apos diversos testes, foi compravado que ocorre isso 100% das vezes, porém é possivel editar, fazendo com que seja um erro de baixo impacto

### BUG-002
- Título:Exclusão de tarefa
- Ambiente:Tela da Tarefa 
- Pré-condição: estar na tela de edição de uma tarefa
- Passos para reprodução: clicar em excluir
- Resultado esperado: Ao clicado, deve aparecer um aviso de Confirmação, pra saber se o Usuario tem certeza se quer excluir a tarefa
- Resultado obtido: a Tarefa é excluida sem qulquer confirmação ou aviso
- Frequência:100% das tentativas
- Impacto: Alto
- Evidência: se tentar excluir uma tarefa, deveria aparecer um aviso de confirmação, para saber se o Usuario tem certeza, e evitar exclusões por acidente, mas ao clicar no botão de excluir, a tarefa é excluida e não tem como recuperar, fazendo com que seja um BUG de alto impacto,que ocorre 100% das vezes

### BUG-003
- Título: Status da tarefa
- Ambiente: Tela inicial
- Pré-condição: Ter uma tarefa
- Passos para reprodução: Estar na tela principal, e clicar em pendentes ou concluídas.
- Resultado esperado: O que estiver pendente aparecer em Pendentes, e o que estiver concluída aparecer em Concluídas.
- Resultado obtido: Quando você tem uma tarefa que está pendente, ela aparece em todos os status. E quando você tem uma tarefa concluída, ela só aparece em Todas.
- Frequência: 100% das tentativas
- Impacto: Alto
- Evidência: se marcar a tarefa como concluída, deveria aparecer seu devido status, que é em Concluídas, para ter uma boa organização das tarefas, para não ficar locado em um lugar só, assim virando muita bagunça, a mesma coisa acontece quando deixamos um tarefa pendente, ela aparece em todos os status, isso faz com que haja uma grande desorganização.

### BUG-004
- Título: Salvamento
- Ambiente: Tela principal
- Pré-condição: Ter uma tarefa e edita-lá 
- Passos para reprodução: Editar uma tarefa, e logo em seguida sair e entrar do aplicativo.
- Resultado esperado: Obter o salvamento da tarefa após edita-lá e depois sair e entrar novamente.
- Resultado obtido: Quando o usuário edita uma tarefa, salva e logo em seguida sai e entra no aplicativo, as alterações que ele fez não aparece, ficando do jeito que ele criou sua tarefa.
- Frequência: 100% das tentativas
- Impacto: Alto
- Evidência: Ao criar uma tarefa, edita-lá e clicar em salvar, após sair do aplicativo e entrar novamente, deveria aparecer a tarefa que salva, de quando ele saiu do aplicativo. Mas ao invés disso aparece da mesma forma que você criou a tarefa.

## 4. Oportunidades de melhoria
# 1ª Melhoria
- Título: Fluxo do Usuário
- Ambiente: Aplicação Completa
- Descrição de Melhoria: O projeto apresenta um fluxo de uso confuso devido aos bugs apresentados, portanto uma das opções de melhoria seria incluir  
- um fluxo de uso completo e autoexplicativo, como por exemplo um manual de ajuda/instrução (similar a um bem vindo interativo para os usuários). 

# 2ª Melhoria
- Título: Acessibilidade e Design 
- Ambiente: Aplciação Completa
- Descrição de Melhoria: Por mais que se trate de uma aplicação simples para organização de tarefas cotidianas é necessário que ela seja abrangente 
- para todos os  públicos como por exemplo usuários da terceira idade, daltônicos ou então pessoas com baixa visão. Devido essa finalidade uma opção  
- de melhoria é que o software forneça implementações como lupa, filtros para correção de cores e audiodescrição para os botões. 


## 5. Riscos para publicação
Um dos riscos cruciais para a aplicação são os bugs 004 (edições não salvas) e 002 (exclusão direta), pois trazem uma perca irreparável para os dados compromentendo a confiança do usuário, de maneira perceptível haverão notas baixas e comentários ruins quando a aplicação ser lançada. O bug 003 (filtros não funcionais) fazem com que a organização do usuário seja confusa e o redirecione à desinstalar a aplicação nos primeiros momentos de uso;  

## 6. Parecer final
O aplicativo está pronto para publicação? Justifique.

- Status de Aprovação: Reprovado
- Plano de Ação: Infelizmente, a aplicação ainda não está pronta para publicação. É estritamente necessário realizar reajustes no código para proteger a experiência do usuário, que nas condições atuais se mostra frustrante devido às falhas no salvamento e na organização. Lançar o aplicativo neste estado acarretará em um volume alto de avaliações negativas nas lojas de aplicativos, prejudicando a reputação do produto desde o primeiro dia e causando um impacto financeiro negativo direto para a empresa.
- Meta: Garantir que o aplicativo cumpra sua premissa básica de salvar, filtrar e excluir tarefas com segurança e sem perda de dados do usuário. O aplicativo só será liberado para publicação após a validação dessas correções.
