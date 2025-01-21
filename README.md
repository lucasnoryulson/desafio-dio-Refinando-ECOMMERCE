# **Modelo de E-Commerce - Bootcamp Suzano | Power BI**

Este projeto apresenta o esquema conceitual e relacional para um sistema de **E-Commerce** desenvolvido como parte do **desafio de projeto** do Bootcamp Suzano - Análise de Dados com Power BI. O objetivo foi criar um modelo que represente as entidades principais, seus atributos e os relacionamentos necessários para o funcionamento de um sistema de comércio eletrônico.

---

## **Descrição do Modelo**

O modelo abrange as seguintes entidades principais do sistema de E-Commerce:

### **Tabelas Principais e Atributos**

1. **Cliente**
   - `idCliente` (INT, PK): Identificador único do cliente.
   - `Nome` (VARCHAR(45)): Nome do cliente.
   - `Endereço` (VARCHAR(45)): Endereço do cliente.
   - `tipoCliente` (VARCHAR(45)): Tipo de cliente, podendo ser PF (Pessoa Física) ou PJ (Pessoa Jurídica).

2. **Produto**
   - `idProduto` (INT, PK): Identificador único do produto.
   - `Categoria` (VARCHAR(45)): Categoria à qual o produto pertence.
   - `Descrição` (VARCHAR(45)): Descrição do produto.
   - `Valor` (DOUBLE): Valor unitário do produto.

3. **Fornecedor**
   - `idFornecedor` (INT, PK): Identificador único do fornecedor.
   - `Razão Social` (VARCHAR(45)): Nome ou razão social do fornecedor.
   - `CNPJ` (INT): Cadastro Nacional da Pessoa Jurídica do fornecedor.

4. **Estoque**
   - `idEstoque` (INT, PK): Identificador único do estoque.
   - `Local` (VARCHAR(45)): Localização do estoque.

5. **Pedido**
   - `idPedido` (INT, PK): Identificador único do pedido.
   - `Status` (VARCHAR(45)): Status atual do pedido (e.g., "em processamento", "finalizado").
   - `Descrição` (VARCHAR(45)): Descrição geral do pedido.
   - `Cliente_idCliente` (INT, FK): Referência ao cliente que realizou o pedido.

6. **Pagamento**
   - `idPagamento` (INT, PK): Identificador único do pagamento.
   - `Tipo de pagamento` (VARCHAR(45)): Método utilizado para o pagamento (e.g., "cartão", "boleto").
   - `Data de pagamento` (DATETIME): Data e hora em que o pagamento foi realizado.
   - `Valor pago` (INT): Valor total pago.
   - `Pedido_idPedido` (INT, FK): Referência ao pedido associado ao pagamento.

7. **Entrega**
   - `idEntrega` (INT, PK): Identificador único da entrega.
   - `Status` (VARCHAR(45)): Status da entrega (e.g., "enviado", "entregue").
   - `Código de rastreio` (VARCHAR(45)): Código para rastrear a entrega.

8. **Cartão**
   - `Número do cartão` (INT, PK): Número único do cartão de pagamento.
   - `Código de segurança` (INT): Código de segurança associado ao cartão.

---

### **Relacionamentos**

1. **Cliente - Pedido**
   - Um cliente pode fazer vários pedidos. A relação é de **1:N** (um para muitos).

2. **Pedido - Pagamento**
   - Cada pedido pode ter um ou mais pagamentos associados. A relação é de **1:N** (um para muitos).

3. **Produto - Fornecedor**
   - Um fornecedor pode disponibilizar vários produtos. A relação é de **1:N**.

4. **Produto - Estoque**
   - Um produto pode estar presente em diferentes estoques. A relação é de **N:N** implementada por meio da tabela associativa `Estoque_has_Produto`.

5. **Pedido - Produto**
   - Um pedido pode conter vários produtos, e cada produto pode estar presente em diferentes pedidos. A relação é de **N:N**, implementada por meio da tabela associativa `Relação de produto por pedido`.

6. **Cartão - Pagamento**
   - Um cartão pode estar associado a vários pagamentos. A relação é de **1:N**.

7. **Entrega - Pedido**
   - Cada pedido pode ter uma entrega associada. A relação é de **1:1** (um para um).

---

### **Destaques do Modelo**

- **Flexibilidade**: O modelo suporta múltiplos métodos de pagamento, rastreamento de entregas, e estoque descentralizado.
- **Consistência**: Chaves primárias (PK) e estrangeiras (FK) foram definidas para garantir a integridade referencial.
- **Escalabilidade**: O modelo pode ser expandido facilmente com novas tabelas ou atributos para atender a requisitos futuros.

---

## **Ferramentas Utilizadas**

- **MySQL Workbench**: Utilizado para a criação do modelo entidade-relacionamento, especificação de chaves primárias e estrangeiras.
- 
---

## **Como Reproduzir**

1. Baixe o arquivo `.mwb` (MySQL Workbench) ou outro formato compatível com ferramentas de modelagem.
2. Abra o arquivo na ferramenta de sua preferência.
3. Analise os relacionamentos e atributos no diagrama gerado.

---

## **Sobre o Autor**

Este modelo foi desenvolvido como parte do desafio de projeto do Bootcamp **Suzano - Análise de Dados com Power BI**. Ele está disponível como referência em meu portfólio para demonstrar habilidades em modelagem de dados e design de banco de dados relacional. Entre em contato para sugestões ou colaborações.

---

### **Licença**
Este projeto é de uso educacional e pode ser utilizado como referência em projetos similares.

---

Se precisar de ajustes ou uma personalização adicional no texto, é só avisar!
