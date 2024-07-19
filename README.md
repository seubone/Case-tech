# Case Processo Seletivo: Sistema de gerenciamento de vendas

Já fabricamos mais de 4 milhões de bonés personalizados com a marca de mais de 40 mil empresas de todo o Brasil durante esses 8 anos. Com o crescimento da empresa, foi necessário ter uma atenção maior à quantidade de vendas realizadas e aos valores de cada uma delas. A fim de facilitar o processo de auditoria dos pedidos, você foi contratado para criar um sistema de gerenciamento de vendas.
Esse sistema tem o intuito cadastrar e listar vendas, mas caso a venda possua um desconto maior do que o permitido, ela deve gerar uma solicitação para que o gerente aprove-a (ou não). O valor total de um pedido é dado por: `SOMA DOS PRODUTOS` + `VALOR DO FRETE` + `ADICIONAL DE PRAZO` - `DESCONTO`. Caso o valor total do pedido exceda o `DESCONTO MÁXIMO PERMITIDO`, é necessário criar uma solicitação e, após a aprovação desta, o vendedor pode cadastrar sua venda, caso contrário, ele precisa receber algum feedback visual informando que a venda não foi permitida pelo gerente.

- SOMA DOS PRODUTOS: Para cada produto, é necessário multiplicar a sua **QUANTIDADE** pelo **PREÇO**;
- VALOR FRETE: Sinta-se livre para definir sua lógica de cálculo de frete. Lembre-se que entregamos para todo o Brasil;
- ADICIONAL DE PRAZO: **PADRÃO**, **TURBO** e **SUPER TURBO** são nossos 3 tipos de prazo. Caso o prazo seja padrão, não há adicional. Caso o prazo seja **TURBO**, o adicional será igual a 10% da `SOMA DOS PRODUTOS`. Caso o prazo seja **SUPER TURBO**, o adicional será igual a 20% da `SOMA DOS PRODUTOS`;
- DESCONTO: O desconto pode ser um campo numérico livre.
- DESCONTO MÁXIMO PERMITIDO: Esse valor é condicionado ao tipo de prazo. Caso seja **PADRÃO**, o desconto máximo é o maior valor entre `VALOR DO FRETE` e `5% DA SOMA DOS PRODUTOS`. Caso seja **TURBO**, o desconto máximo é o maior valor entre `VALOR DO FRETE` e `10% DA SOMA DOS PRODUTOS`. Por fim, caso seja **SUPER TURBO**, o desconto máximo é o maior valor entre `VALOR DO FRETE` e `20% DA SOMA DOS PRODUTOS`.

Para cadastrar uma venda, é necessário informar quais produtos foram negociados. Para tanto, o repositório possui um arquivo (___produtosCaseSB.js___) que disponibiliza um array de objetos que representam nossos produtos! Você notará que, para cada produto, existe o `PRECO_CHEIO` e `PRECO_DESCONTADO`. O preço cheio é cobrado quando a forma de pagamento é via cartão de crédito, enquanto o preço descontado é cobrado para os pagamentos em pix e boleto.

## Requisitos:

### 1. Login e cadastro:

Para esse sistema, terão 2 níveis de usuários: gerente e vendedor. O gerente pode listar vendas e solicitações, aprovar/reprovar solicitações e criar novos vendedores. Enquanto isso, o vendedor pode criar vendas e pedidos, além de listar vendas e pedidos.

> Diferencial: JWT e persistência de login.

### 2. Criar vendas e solicitações:

É necessário que o sistema possua um formulário para cadastrar a venda. Caso esta possua descontos acima do permitido, uma solicitação será criada para que o gerente comercial aprove-a ou não. Lembre-se: uma venda só é cadastrada se o desconto for abaixo do permitido ou algum gerente já aprovou a solicitação gerada pela venda. Caso recusado, o usuário deve receber um feedback visual.

> Diferencial: React Hook Form (se optar por React), armazenamento de imagens e feedbacks visuais.

### 3. Aprovar/Reprovar pedidos:

Uma solicitação nada mais é do que um pedido do vendedor para cadastrar a venda em questão. Nesse caso, é necessário que o sistema permita que o usuário gerente consiga aprovar e reprovar pedidos.

> Diferencial: Notificações pro outro usuário ao criar/alterar status da solicitação. Ex.: Vendedor receber notificação quando sua solicitação for aprovada, gerente receber notificação quando houver criação de uma solicitação, etc.

### 4. Listar solicitações e vendas por filtros:

A fim de facilitar a visualização de vendas/solicitações para possíveis análises, é interessante que seja possível filtrar os itens da tabela por filtros Alguns exemplos: ordem crescente de desconto, intervalos de desconto, maior valor total;

> Diferencial: filtros no backend;
