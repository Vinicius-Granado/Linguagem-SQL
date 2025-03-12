# Linguagem-SQL
--Inserindo  Dados da "tabelapedidos" em uma nova tabela de clientes ouro: tabelapedidosgold--

CREATE TABLE tabelapedidosgold (
id_pedido INT PRIMARY KEY,
data_pedido DATE (200),
status_pedido VARCHAR(200),
total_pedido DECIMAL(10,2),
cliente VARCHAR(200),
data_envio DATE(200),
FOREIGN KEY (cliente) REFERENCES tabelaclientes(id_cliente)
);
insert into tabelapedidosgold (
id_pedido,
data_pedido,
status_pedido,
total_pedido,
cliente,
data_envio)
SELECT
tabelapedidos.id,
tabelapedidos.data_do_pedido,
tabelapedidos.status,
tabelapedidos.total_do_pedido,
tabelapedidos.cliente,
tabelapedidos.data_de_envio_estimada
FROM tabelapedidos
JOIN tabelapedidos ON tabelaclientes.id_cliente = tabelapedidos.Cliente 
WHERE total_do_pedido >= 400;

SELECT*from tabelapedidosgold
