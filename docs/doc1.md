---
id: doc1
title: PROCESSO DE CARGEBACK
sidebar_label: Resoluções e Políticas
---

Check the [documentation](https://docusaurus.io) for how to use Docusaurus.

## Definições Gerais 

### O que é o Chargeback?

O chargeback é a contestação de uma compra efetuada por cartão de crédito ou débito em um estabelecimento comercial, seja em loja física ou virtual. Esta solicitação é feita pelo card holder, o dono do cartão, para o card issuer, o emissor.
![Image chargeback](https://i.ibb.co/ydgZk31/fluxo-chargeback.png)

### Termos Envolvidos no Processo de Chargeback

Mesmo o mais simples processo de chargeback tem interações de múltiplas partes:
1. **Portador do Cartão ou Cardholder**: O dono do cartão envolvido na transação.
2. **Comerciante ou Merchant**: A parte que vendeu os bens ou serviços em disputa.
3. **Banco Emissor ou Issuer**: A instituição financeira que emitiu o cartão para o portador do cartão. Também podem se referir ao banco emissor como "operadora do cartão de crédito",
4. **Adquirente ou Acquirer**: Empresas responsáveis de liquidar transações financeiras, a conexão entre o Issuer e o Comerciante.
5. **Bandeira ou Card Association**: Uma bandeira do cartão realiza a mediação das operações de venda que são realizadas em um estabelecimento comercial, junto à operadora do cartão de crédito.

### Informações Necessárias para Validar o Processo

Pelo de fato de ser uma política interna entre empresas, o processo, apesar de parecido, pode varias de acordo com o Issuer Bank, a Bandeira, a Adquirente e a Subadquirente.

## Disputas

O processo de chargeback é variável e depende da empresa e instituições financeiras que estão envolvidas.

### Fluxo de Disputas

1. O processo começa quando o cardholder entra em contato com o emissor do cartão, a instituição financeira responsável por emitir o cartão.

O processo de chargeback também pode ser iniciado pelo emissor do cartão, chamada de "Bank Chargeback".

2. A card issuer revisa a solicitação. Nessa etapa, se ele decidir que a requisição é indevida, o chargeback vai ser simplesmente rejeitado e não será passado para frente. Se for verificado um erro com a compra, o caso vai passar pelo processo burocrático de chargeback.

3. Um estorno provisório é lançado para o cardholder. 

4. O banco emissor do cartão lança um código numérico como representação do motivo da solicitação do chargeback, e transmite todas as informações da solicitação para a adquirente. 

5. A adquirente revisa a solicitação de estorno. A adquirente pode tanto resolver o processo sozinha ou encaminhar a reivindicação para o próximo membro da cadeia de chargeback, no caso, a Zoop, que também pode deliberar com seus próprios recursos ou encaminhar para a ZiroPay. 

6. Podemos aceitar o pedido de chargeback ou encaminhar para o Lojista. Ele pode acatar a reivindicação do pedido ou protestar e disputar pela transação. 

PS: É importante ter todos os documentos que comprovem o protesto da solicitação. É dever do lojista poder comprovar que todos os bens vendidos foram entregues devidamente.

7. A loja irá emitir a resposta, junto com todas as evidências, encaminhar para a subadquirente, que encaminhará para a adquirente.

8. O banco adquirente vai representar e apresentar eletronicamente a disputa de chargeback com o banco emissor, que vai revisar as informações. há três coisas que podem acontecer:

    1. **O banco emite parecer a favor do lojista.** Seu caso tem informaçøes suficientes para o banco validar a transação original. O valor da transação é novamente cobrado nos lançamentos do cardholder e seus fundos são depositados na sua conta.

    2. **O banco emite parecer a favor do cardholder.** suas evidências não foram o suficiente para o banco reverter a decisão de chargeback e mantém sua posição, a menos que o lojista queira recorrer e busque uma arbitragem

    3. **O lojista vende, mas o "Issuer" preenche um segundo chargeback.** O issuer bank tem direito de preencher o processo de chargeback novamente em caso de ter descoberto novas informações sobre o caso e mudar o código de motivo.


### Fluxo de Chargeback na Zoop:

1. O cliente solicita ao emissor o estorno / cancelamento de uma transação;

2. O emissor informa à adquirente e consequentemente à Zoop que esta transação foi contestada pelo cliente;

3. A Zoop atualiza o status da transação para "dispute" e suspende os pagamentos de recebíveis a vencer associados a esta venda;
4. A notificação sobre transações em disputa é realizada automaticamente pelo sistema através do disparo do evento de transaction.
disputed devendo este evento ser monitorado pelo marketplace para que possa atuar caso desejado;

5. Caso o EC ou o Marketplace envie a documentação necessária por e-mail no prazo de 7 dias (corridos) a Zoop encaminha a documentação ao adquirente / emissor e aguarda o resultado do processo, que pode ocorrer no prazo de até 30 dias (corridos);

6. Caso o retorno seja favorável ao EC, a Zoop é notificada, confirma o processo de disputa e dispara o evento transaction.dispute.
succeeded, altera o status da transação para succeeded e remove a suspensão dos recebíveis pendentes de pagamento;

7. Caso o retorno seja favorável ao comprador, ou a Zoop não receba retorno no prazo estipulado, o processo de disputa é encerrado e o status da transação é alterado em definitivo para charged_back, sendo disparado o evento transaction.charged_back e realizado o débito na conta do EC ou do Marketplace, dependendo de quem for o responsável pelos chargebacks no contrato comercial;

8. Caso o Marketplace / EC não envie a documentação dentro do prazo, o processo de disputa é encerrado e o status da transação é atualizado em definitivo para charged_back;


## Fraudes no processo de Chargeback

O Processo de chargeback pode, e é compreendido, como um processo que pode acontecer, e é normal de acontecer. Entretanto, o que mais nos devemos atentar é nos casos de fraude dentro do processo de chargeback, que é extremamente subjetivo a cada situação e as instituições bancárias, adquirentes e lojistas que participam do processo como um todo. 

### Auto-Fraude

Pessoas podem usar milhões de motivos para pedir chargeback, uma vez que é um processo subjetivo, e nem todas elas podem ser verdadeiras ou aceitáveis. Entre esses motivos, os mais comuns são:

* A intenção do cardholder era de ter alguma coisa de graça.
* O cardholder simplesmente não entendeu o que o processo significa.
* O cardholder teve remorso ou arrependimento da compra e não teve vontade de confrontar o lojista;
* Um membro da família fez a compra, mas o cardholder principal não sabia ou simplesmente não quis honrar as cobranças.
* O cardholder não reconheceu a compra ou esqueceu que realizou a compra.
* O cardholder não se enquadra num refund tradicional (por exemplo, por exceder o tempo limite de reembolso).

É importante ressaltar que todos essas tentativas podem partir do dono do cartão. Entretanto, as fraudes não estão limitadas apenas ao dono do cartão. Elas também podem estar associadas à uma atividade criminosa.

### Fraudes por Terceiros

* **Ataques cibernéticos**: acontece quando um hacker consegue acessar os dados dos clientes, modificando os endereços de entrega;
* **Fraude por dispositivos mobile**: ocorre quando ladrões roubam um algum dispositivo mobile e usam os dados bancários da vítima para fazer compras em lojas virtuais;
* **Estelionato virtual**: quando um estelionatário obtém dados pessoais e bancários da vítima e utiliza essas informações para efetuar compras online;

## Política de Chargeback

1. DEFINIÇÕES:

As seguintes palavras e expressões terão os seguintes significados na presente Política:
CHARGEBACK: A contestação de uma transação, também conhecida como chargeback, ocorre quando o comprador entra em contato com a operadora do cartão e alega que não recebeu o produto/serviço ou não reconhece o lançamento em sua fatura.
2. REGRAS GERAIS

    2.1. O vendedor estará protegido do chargeback (contestação) quando:

    * Enviar comprovação válida de entrega do produto e/ou prestação do serviço no prazo de 2 dias, quando solicitado, através da Central de Soluções em sua ZiroConta;

    * Comprovar a participação do Comprador na especificação do produto e/ou serviço. Ex.: escolha de tamanho, cor, quantidade e etc.;

    * Comprovar a entrega do produto através do AR (Aviso de Recebimento) assinado pelo portador do cartão ou pelo comprador;
    
    * Informar o código de rastreamento válido de envio do produto (confirmado pelo site dos Correios ou transportadoras) nos detalhes da transação em sua ZiroConta;
 
    * Efetuar a entrega do produto somente nos endereços cadastrados pelo comprador na ZiroPay;
    
    * Enviar documentação completa solicitada pela ZiroPay para análise e possível desbloqueio do pagamento contestado;
    
    * Comprovar que houve esforços para resolver junto ao comprador problemas de desacordo comercial (exemplo: impossibilidade da prestação de serviços ofertados, produto indisponível ou avariado, etc.);
    
    * Nos casos de duplicidade de pagamento, enviar comprovação válida de entrega dos 2 (ou mais) produto(s) e/ou prestação do 
    serviço, no prazo de 2 dias, quando solicitado, através da Central de Soluções em sua conta PagSeguro;

    2.2.  São entendidos como comprovantes válidos:
    
    * Código de rastreamento e aviso de recebimento (A.R.) assinado;
    
    * Comprovante com o número de referência/conhecimento aéreo ou outro número de localização do envio, nota fiscal de entrega no endereço cadastrado pelo usuário na ZiroPay que contenha a assinatura, data, nome completo, documento legível do recebedor;
    
    * Protocolo de recebimento no endereço cadastrado pelo usuário na ZiroPay que contenha a assinatura, data, nome completo, documento legível do recebedor;
    
    * Cópia do cupom com a imagem da oferta do produto ou serviço contendo claramente as regras, prazos de validade e dados que comprovem a utilização pelo comprador (dados que identifiquem o usuário);
    
    * Log de acesso, imagem e dados dos créditos que comprovem a utilização pelo comprador (dados que identifiquem o usuário).
    
    * Tela de cadastro com dados do comprador (se possível, que comprove a data da utilização/retirada), Regras de Uso da oferta OU Contrato, Cópia do e-ticket enviado por e-mail OU comprovante de envio do ingresso pelos Correios OU recibo assinado a retirada do ingresso na bilheteria e Cópia do documento do recebedor (se houver).
    
    2.3. vendedor poderá ser debitado pelo chargeback (contestação) quando:
    
    * Não enviar comprovação válida de entrega do produto e/ou prestação do serviço no prazo de 2 dias, quando solicitado, através da Central de Soluções em sua ZiroConta;
    
    * Enviar AR (Aviso de Recebimento) sem assinatura do recebedor ou código de rastreamento inválido (Correios ou transportadoras);
    
    * Enviar um código de rastreamento cujo status (nos Correios ou Transportadora) não demonstre que o produto foi entregue com sucesso ao destinatário (exemplo: devolvido ao remetente, extraviado, entre outros);
    
    * Enviar um código de rastreamento cujo não seja possível localizá-lo na data da análise da contestação, nos sites de logística (Correios ou Transportadoras);
    
    * Efetuar a entrega do produto em endereços divergentes dos cadastrados pelo comprador na ZiroPay;
    
    * Realizar entrega em mãos sem recibo assinado e sem cópia de documento (RG e/ou documento válido em território nacional) que contenha assinatura idêntica ao recibo;
    
    * Efetuar o cadastro na ZiroPay em nome do comprador e o pagamento vir a ser contestado pelo portador do cartão;
    
    * Se não efetuar o cancelamento, por solicitação da ZiroPay, de um pagamento já aprovado e que fora posteriormente identificadas irregularidades;
    
    * Nos casos de duplicidade de pagamento, não enviar comprovação válida de entrega dos 2 (ou mais) produto(s) e/ou prestação do serviço;
    
    * Houver duplicidade de pagamento por múltiplos adquirentes;
    
    * A contestação for decorrente de uma transação efetuada com instrumento de pagamento (dispositivos móveis ZiroPay), sendo o vendedor exclusivamente responsável por tais ações decorrentes de seus compradores, conforme cláusula contratual 09 do Anexo I - TRANSAÇÕES COMERCIAIS COM INSTRUMENTO DE PAGAMENTO (DISPOSITIVOS MÓVEIS ZiroPay).
    
    No caso de contestação de pagamento por problemas relacionados a prazos de entrega, condições do produto e/ou serviços prestados pelo VENDEDOR, não serão aceitas justificativas quando:
    
    * Produtos e/ou serviços não estiverem de acordo com as especificações da oferta. Exemplo: o comprador declara que a qualidade do produto recebido não está de acordo com as informações contidas no site do vendedor;
    
    * Cancelamento da prestação de serviços ocorrer sem prévio aviso e/ou sem informe de nova data a ser realizada;
    
    * As Políticas ou Termos e Condições do site do VENDEDOR não estiverem claros ou onerem o consumidor;
    
    * O COMPRADOR comprovar que efetuou a solicitação do cancelamento da compra no prazo de até 7 (sete) dias a contar de sua assinatura (data da compra) ou do ato de recebimento do produto ou serviço, como garante o art. 49 do Código de Defesa do Consumidor e o VENDEDOR não cancelar a transação;
    
    * O VENDEDOR entregar produtos com vícios de qualidade que os tornem impróprios ou inadequados ao consumo a que se destinam;
    
    * O COMPRADOR comprovar através de código de rastreamento que devolveu o produto ao VENDEDOR;
    
    * O COMPRADOR comprovar que tentou solucionar o problema com o vendedor, mas não obteve resposta;
    
    * O VENDEDOR recusar o recebimento do produto devolvido;
    
    * O VENDEDOR não divulgar apropriadamente possíveis atrasos na entrega do produto e/ou serviços;
    
    * O VENDEDOR comercializar produtos/serviços diferentes da categoria informada em sua conta PAGSEGURO;
    
    * O VENDEDOR desmembrar o valor do produto/serviço em mais de uma transação e que isto seja identificado pelo comprador como duplicidade de pagamento;
    
    * Realizar o envio do produto ou a prestação de serviço somente em data igual ou posterior a data do recebimento da contestação;
    
3. Caso não seja aceita a justificativa encaminhada pelo VENDEDOR, a ZIROPAY PODERÁ SUSPENDER E/OU REVOGAR A APROVAÇÃO DE QUAISQUER TRANSAÇÕES COMERCIAIS, SUSPENDENDO, REVERTENDO E/OU CANCELANDO A REALIZAÇÃO DOS RESPECTIVOS PAGAMENTOS OU MOVIMENTAÇÕES, BEM COMO COBRANDO, SE NECESSÁRIO, AS RESPECTIVAS QUANTIAS DO VENDEDOR, nos termos da presente Política e do Contrato de Prestação de Serviços de Gestão de Pagamentos e Outras Avenças firmado entre as partes no momento da contratação.

4. Além das disposições da presente Política, aplicam-se as questões relacionadas ao chargeback todas as disposições do Contrato de Prestação de Serviços de Gestão de Pagamentos e Outras Avenças, disponível no endereço eletrônico: https://pagseguro.uol.com.br/contrato_de_servicos.jhtml
