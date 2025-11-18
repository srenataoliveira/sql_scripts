# sql_scripts
📚 Banco de Dados – Projeto de Biblioteca
📌 O que é um Banco de Dados?

Um banco de dados é um conjunto organizado de informações que podem ser armazenadas, gerenciadas e consultadas de forma eficiente.
Ele serve para guardar dados de maneira estruturada, permitindo que pessoas e sistemas encontrem e usem essas informações rapidamente.

🎯 Objetivo do Projeto

Este projeto consiste em um banco de dados relacional simples, desenvolvido para simular um cenário de Gerenciamento de Estoque de uma Biblioteca.

O banco é composto por tabelas que se relacionam entre si por meio de chaves primárias (PRIMARY KEY) e chaves estrangeiras (FOREIGN KEY).
Seu principal objetivo é servir como uma ferramenta prática para aprendizagem de SQL, modelagem de dados e lógica relacional.

🛠️ Como executar o Script
✅ 1. Executar no MySQL Workbench

Abra o MySQL Workbench.

Conecte ao seu servidor MySQL.

Clique em File → New Query Tab.

Cole todo o script SQL na aba aberta.

Clique no botão Execute (⚡).

✅ 2. Executar pelo XAMPP (phpMyAdmin)

Inicie o MySQL no painel do XAMPP.

Acesse no navegador:

http://localhost/phpmyadmin


Crie um banco de dados (ex.: biblioteca).

Clique no banco criado e vá na aba SQL.

Cole o script e clique em Executar.

🧩 3. DDL e DML

O SQL é dividido em subconjuntos para gerenciar estrutura e dados.
Os dois principais são:

📘 3.1. DDL — Data Definition Language

Definição:
Conjunto de comandos responsáveis por criar, modificar ou excluir estruturas do banco, como tabelas e índices.

Principais comandos:

CREATE – cria novas tabelas ou objetos.

ALTER – modifica estruturas existentes.

DROP – exclui tabelas ou objetos.

📙 3.2. DML — Data Manipulation Language

Definição:
Conjunto de comandos usados para gerenciar os dados dentro das tabelas criadas pela DDL.

Principais comandos:

INSERT – insere registros.

UPDATE – atualiza registros.

DELETE – exclui registros.

SELECT – consulta dados.

🧪 Exemplo de Script SQL (DDL)
CREATE TABLE Clientes (
    ID_Cliente INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(150) NOT NULL,
    cpf VARCHAR(150) NOT NULL,
    data_de_nascimento DATE NOT NULL,
    Endereco TEXT,
    Telefone VARCHAR(20)
);

CREATE TABLE Livros (
    ID_Livro INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(150) NOT NULL,
    Categoria VARCHAR(150),
    Autor VARCHAR(150)
);

CREATE TABLE Vendas (
    ID_Venda INT PRIMARY KEY AUTO_INCREMENT,
    ID_Cliente INT,
    ID_Livro INT,
    Data_de_retirada DATE,
    Data_de_devolucao DATE,
    Quantidade_de_livros INT,
    Valor_Total DECIMAL(10, 2),
    FOREIGN KEY (ID_Cliente) REFERENCES Clientes(ID_Cliente),
    FOREIGN KEY (ID_Livro) REFERENCES Livros(ID_Livro)
