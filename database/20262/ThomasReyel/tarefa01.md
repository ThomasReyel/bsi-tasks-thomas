
## Questão 01
**Resposta:** Um banco de dados é um conjunto de dados relacionados armazenados em um dispositivo seja ele eletrônico ou físico. Já um Sistema Gerenciador de Banco de Dados ou SGBD é um sistema de BD projetado para gerir grandes volumes de informações, facilitando as operações necessárias em um banco de dados digital. 

## Questão 02
**Resposta:** Sistema de arquivos possuem diversos problemas como falta de segurança (não pode garantir que pessoas vejam somente o que as compete), inconsistência e redundância de dados (Não possui ferramentas de controle que evite duplicidade de dados ou a sua inconsistência), dificuldade de realizar operações atômicas (várias operações ao mesmo tempo e dependentes uma das outras, é muito difícil de se garantir em sistemas de arquivos) e entre o outros problemas.

## Questão 03
**Resposta:** 
- **Atômicidade:** Evite a perda de dados, registros órfãos e operações atômicas. Um banco de dados com atomicidade fornece transações “tudo ou nada” para que você não perca dados se uma parte de uma transação falhar no meio da operação. Exemplo: No caso de uma transação bancária, primeiro o dinheiro é debitado da conta de quem está transferindo. Caso a operação falhe e o SGBD não possua a propriedade de atomicidade, quem está transferindo perde o dinheiro e a pessoa que receberia não o recebe.
- **Consistência:** As restrições de tabela nos bancos de dados ACID exigem que todas as transações armazenem dados em um formato uniforme. Exemplo: Na criação de uma conta, o CPF do titular tem que ser única (só ele pode ter esse cpf), caso uma outra pessoa vá fazer uma conta nesse banco e informe o mesmo cpf, um banco com a propriedade de consistência tem que cancelar a operação.
- **Isolamento:** Isolamento é uma garantia de que transações executadas simultaneamente não devam interferir umas nas outras. Exemplo: Em um caso de um conta com 500 reais, 2 operações de saque são realizadas ao mesmo tempo, uma com 50 e a outra com 100. Se o SGBD não tiver a características de isolamento a segunda operação pode atropelar a primeira. Assim no final a conta não ficaria com 350 mas com 400.
- **Durabilidade:** Durabilidade é uma garantia de que as alterações feitas por uma transação confirmada não devem ser perdidas. Todas as transações confirmadas devem ser persistidas em armazenamento durável e não volátil, ou seja, em disco. Exemplo: Caso a energia do banco caia, o SGBD com durabilidade tem que garantir que todas as operações que foram confirmadas estejam salvas.
