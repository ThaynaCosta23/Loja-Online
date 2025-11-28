🧶 Loja Online - Banco de Dados em SQLite

Este projeto consiste na criação e manipulação do banco de dados de uma loja online Bella's, incluindo amigurumis, bolsas e tapetes feitos à mão.  
O modelo foi desenvolvido para simular operações reais de e-commerce, como cadastro de clientes, pedidos, pagamentos, produtos e histórico de preços.

---

📌 Objetivo do Projeto

✔ Criar um banco de dados relacional com SQLite Studio  
✔ Implementar entidades com **chaves primárias e estrangeiras
✔ Inserir, consultar, atualizar e excluir dados usando SQL  
✔ Simular transações reais de uma loja virtual  

---

🛠️ Tecnologias Utilizadas

🗂 SQLite Studio
💻 SQL (DDL + DML)
🧮 Modelagem relacional

---

🗃️ Estrutura das Tabelas

O banco de dados é composto pelas seguintes tabelas:

- cliente - Armazena os dados dos clientes
- telefone - Telefones vinculados ao cliente
- endereco - Endereços cadastrados pelo cliente
- categoria - Categorias dos produtos
- produto - Estoque de produtos disponíveis
- pagamento - Tipos e status de pagamento
- pedidos - Pedidos realizados pelos clientes
- itempedido - Produtos incluídos em cada pedido
- historicoprecoproduto - Registro do preço no momento da compra

---

📁 Scripts SQL Utilizados

O projeto contém os seguintes grupos de comandos:

---

📌 DDL – Criação de tabelas

Exemplo:

CREATE TABLE cliente(
    id_cliente INTEGER PRIMARY KEY AUTOINCREMENT,
    nome TEXT NOT NULL,
    cpf TEXT(14),
    email TEXT,
    senha TEXT(6)
);

📌 INSERT – Inserção de dados

Exemplo:

INSERT INTO produto(id_categoria, nome, descricao, preco, estoque)
VALUES 
(1, 'Coelho Amigurumi', 'Com gravata borboleta', 95.00, 10);

📌 UPDATE – Atualização de dados

Exemplo:

UPDATE pedidos
SET status = 'Pago'
WHERE id_pedido = 1;

📌 DELETE – Remoção de dados

Exemplo:

DELETE FROM itempedido
WHERE id_pedido = 3;

📌 SELECT – Consultas ao banco

Exemplo com JOIN:

SELECT 
    pedidos.id_pedido,
    cliente.nome AS cliente,
    pedidos.data_pedido,
    pedidos.status,
    pedidos.valor_total
FROM pedidos
JOIN cliente ON pedidos.id_cliente = cliente.id_cliente;

Exemplo com WHERE, ORDER BY e LIMIT:

SELECT
    id_pedido,
    data_pedido,
    valor_total
FROM pedidos
ORDER BY data_pedido DESC
LIMIT 2;

📈 Funcionamento do Sistema

O banco permite simular:

- Cadastro de clientes e endereços
- Registro de pedidos
- Pagamento e status
- Histórico de preços
- Controle de estoque

🧑‍💻 Autora
Projeto criado por:
Thayná Oliveira
💙 Estudante de Analise e Desemvolvimento de Sistemas.

📍 Status do Projeto
🟢 Concluído