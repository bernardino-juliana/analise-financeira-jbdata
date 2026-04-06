SHOW DATABASES;
CREATE DATABASE jbdata;
USE jbdata;

-- Tabela de clientes
CREATE TABLE clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255),
    tipo VARCHAR(100)
);

-- Tabela de receitas
CREATE TABLE receitas (
    id INT AUTO_INCREMENT PRIMARY KEY,
    cliente_id INT,
    valor DECIMAL(10,2),
    data DATE,
    tipo VARCHAR(100),
    FOREIGN KEY (cliente_id) REFERENCES clientes(id)
);

-- Tabela de despesas
CREATE TABLE despesas (
    id INT AUTO_INCREMENT PRIMARY KEY,
    categoria VARCHAR(100),
    valor DECIMAL(10,2),
    data DATE,
    tipo VARCHAR(100)
);

-- Clientes
INSERT INTO clientes (nome, tipo) VALUES
('Empresa A', 'Recorrente'),
('Empresa B', 'Recorrente'),
('Empresa C', 'Projeto'),
('Empresa D', 'Projeto'),
('Empresa E', 'Recorrente');

-- Receitas (últimos 6 meses, misturando recorrente e projeto)
INSERT INTO receitas (cliente_id, valor, data, tipo) VALUES
(1, 2000.00, '2025-11-05', 'Mensal'),
(1, 2000.00, '2025-12-05', 'Mensal'),
(1, 2000.00, '2026-01-05', 'Mensal'),
(1, 2000.00, '2026-02-05', 'Mensal'),
(1, 2000.00, '2026-03-05', 'Mensal'),
(1, 2000.00, '2026-04-05', 'Mensal'),

(2, 1500.00, '2025-11-10', 'Mensal'),
(2, 1500.00, '2025-12-10', 'Mensal'),
(2, 1500.00, '2026-01-10', 'Mensal'),
(2, 1500.00, '2026-02-10', 'Mensal'),
(2, 1500.00, '2026-03-10', 'Mensal'),
(2, 1500.00, '2026-04-10', 'Mensal'),

(3, 8000.00, '2025-11-15', 'Projeto'),
(4, 12000.00, '2026-01-20', 'Projeto'),
(3, 5000.00, '2026-03-18', 'Projeto'),

(5, 2500.00, '2025-12-05', 'Mensal'),
(5, 2500.00, '2026-01-05', 'Mensal'),
(5, 2500.00, '2026-02-05', 'Mensal'),
(5, 2500.00, '2026-03-05', 'Mensal'),
(5, 2500.00, '2026-04-05', 'Mensal');

-- Despesas (últimos 6 meses, várias categorias)
INSERT INTO despesas (categoria, valor, data, tipo) VALUES
('Marketing', 1000.00, '2025-11-08', 'Fixo'),
('Marketing', 1200.00, '2025-12-08', 'Fixo'),
('Marketing', 1100.00, '2026-01-08', 'Fixo'),
('Marketing', 1300.00, '2026-02-08', 'Fixo'),
('Marketing', 1250.00, '2026-03-08', 'Fixo'),
('Marketing', 1350.00, '2026-04-08', 'Fixo'),

('Freelancer', 2000.00, '2025-11-12', 'Variável'),
('Freelancer', 1800.00, '2025-12-12', 'Variável'),
('Freelancer', 2100.00, '2026-01-12', 'Variável'),
('Freelancer', 1900.00, '2026-02-12', 'Variável'),
('Freelancer', 2200.00, '2026-03-12', 'Variável'),
('Freelancer', 2000.00, '2026-04-12', 'Variável'),

('Software', 500.00, '2025-11-15', 'Fixo'),
('Software', 550.00, '2025-12-15', 'Fixo'),
('Software', 600.00, '2026-01-15', 'Fixo'),
('Software', 600.00, '2026-02-15', 'Fixo'),
('Software', 650.00, '2026-03-15', 'Fixo'),
('Software', 700.00, '2026-04-15', 'Fixo'),

('RH', 1500.00, '2025-11-20', 'Fixo'),
('RH', 1500.00, '2025-12-20', 'Fixo'),
('RH', 1500.00, '2026-01-20', 'Fixo'),
('RH', 1600.00, '2026-02-20', 'Fixo'),
('RH', 1600.00, '2026-03-20', 'Fixo'),
('RH', 1600.00, '2026-04-20', 'Fixo'),

('Administrativo', 800.00, '2025-11-25', 'Fixo'),
('Administrativo', 850.00, '2025-12-25', 'Fixo'),
('Administrativo', 850.00, '2026-01-25', 'Fixo'),
('Administrativo', 900.00, '2026-02-25', 'Fixo'),
('Administrativo', 900.00, '2026-03-25', 'Fixo'),
('Administrativo', 950.00, '2026-04-25', 'Fixo');

SHOW TABLES;

SELECT * FROM clientes LIMIT 10;

SELECT * FROM despesas;

SELECT DATE_FORMAT(data, '%Y-%m') AS mes, 
       SUM(valor) AS receita_total
FROM receitas
GROUP BY mes
ORDER BY mes;

SELECT DATE_FORMAT(data, '%Y-%m') AS mes, 
       categoria, 
       SUM(valor) AS despesa_total
FROM despesas
GROUP BY mes, categoria
ORDER BY mes, categoria;

SELECT 
    r.mes,
    r.receita_total,
    IFNULL(d.despesa_total, 0) AS despesa_total,
    (r.receita_total - IFNULL(d.despesa_total, 0)) AS lucro
FROM
    (SELECT DATE_FORMAT(data, '%Y-%m') AS mes, SUM(valor) AS receita_total
     FROM receitas
     GROUP BY mes) r
LEFT JOIN
    (SELECT DATE_FORMAT(data, '%Y-%m') AS mes, SUM(valor) AS despesa_total
     FROM despesas
     GROUP BY mes) d ON r.mes = d.mes
ORDER BY r.mes;

SELECT tipo, 
       SUM(valor) AS receita_total
FROM receitas
GROUP BY tipo;

SELECT c.nome, 
       SUM(r.valor) AS receita_total
FROM receitas r
JOIN clientes c ON r.cliente_id = c.id
GROUP BY c.nome
ORDER BY receita_total DESC
LIMIT 3;

SELECT categoria,
       ROUND(AVG(valor), 2) AS media_mensal
FROM despesas
GROUP BY categoria
ORDER BY media_mensal DESC;

SELECT DATE_FORMAT(data, '%Y-%m') AS mes,
       SUM(SUM(valor)) OVER (ORDER BY DATE_FORMAT(data, '%Y-%m')) AS receita_acumulada
FROM receitas
GROUP BY mes
ORDER BY mes;

SELECT * FROM receitas
INTO OUTFILE 'C:/ProgramData/MySQL/MySQL Server 9.5/Uploads/receitas.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n';

SELECT * FROM clientes
INTO OUTFILE 'C:/ProgramData/MySQL/MySQL Server 9.5/Uploads/clientes.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n';

SELECT * FROM despesas
INTO OUTFILE 'C:/ProgramData/MySQL/MySQL Server 9.5/Uploads/despesas.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n';
