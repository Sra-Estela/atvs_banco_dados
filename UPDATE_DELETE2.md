# (UPTADE + DELETE) 2:

```MySQL
create database db_estoque;
use db_estoque;

CREATE TABLE tb_produtos (
    pro_id INT PRIMARY KEY AUTO_INCREMENT,
    pro_nome VARCHAR(100) NOT NULL,
    pro_descricao TEXT,
    pro_preco DECIMAL(10, 2) NOT NULL,
    pro_quantidade_estoque INT NOT NULL,
    pro_categoria VARCHAR(50),
    pro_data_cadastro DATE NOT NULL,
    pro_status ENUM('disponível', 'indisponível') NOT NULL,
    pro_marca VARCHAR(50),
    pro_data_validade DATE,
    pro_peso DECIMAL(5, 2)
);

INSERT INTO tb_produtos
(pro_nome, pro_descricao, pro_preco, pro_quantidade_estoque, pro_categoria, pro_data_cadastro, pro_status, pro_marca, pro_data_validade, pro_peso)
VALUES
('Coca-Cola', 'Refrigerante de cola, 2 litros.', 7.99, 100, 'Refrigerante', '2024-08-20', 'disponível', 'Coca-Cola', '2025-01-01', 2.00),
('Pepsi', 'Refrigerante de cola, 2 litros.', 7.49, 80, 'Refrigerante', '2024-08-20', 'disponível', 'Pepsi', '2025-01-01', 2.00),
('Guaraná Antarctica', 'Refrigerante de guaraná, 1 litro.', 5.49, 120, 'Refrigerante', '2024-08-20', 'disponível', 'Antarctica', '2024-12-01', 1.00),
('Suco de Laranja Del Valle', 'Suco de laranja, 1 litro.', 6.99, 50, 'Suco', '2024-08-20', 'disponível', 'Del Valle', '2024-11-01', 1.00),
('Água Mineral Crystal', 'Água mineral sem gás, 500 ml.', 1.99, 200, 'Água', '2024-08-20', 'disponível', 'Crystal', '2025-06-01', 0.50),
('Red Bull', 'Bebida energética, 250 ml.', 9.99, 75, 'Energético', '2024-08-20', 'disponível', 'Red Bull', '2025-02-01', 0.25),
('Monster Energy', 'Bebida energética, 473 ml.', 12.99, 60, 'Energético', '2024-08-20', 'disponível', 'Monster', '2025-02-01', 0.47),
('Chá Gelado Lipton', 'Chá gelado sabor limão, 1,5 litros.', 8.49, 90, 'Chá', '2024-08-20', 'disponível', 'Lipton', '2024-12-01', 1.50),
('Café Gelado Starbucks', 'Café gelado com leite, 280 ml.', 11.99, 45, 'Café', '2024-08-20', 'disponível', 'Starbucks', '2025-03-01', 0.28),
('Sprite', 'Refrigerante de limão, 2 litros.', 7.99, 110, 'Refrigerante', '2024-08-20', 'disponível', 'Sprite', '2025-01-01', 2.00),
('Detergente Ypê', 'Detergente líquido para louças, 500 ml.', 2.49, 150, 'Limpeza', '2024-08-01', 'disponível', 'Ypê', '2026-01-01', 0.50),
('Desinfetante Pinho Sol', 'Desinfetante multiuso, 1 litro.', 6.99, 80, 'Limpeza', '2024-08-02', 'disponível', 'Pinho Sol', '2025-05-01', 1.00),
('Água Sanitária Qboa', 'Água sanitária, 2 litros.', 3.99, 100, 'Limpeza', '2024-08-03', 'disponível', 'Qboa', '2025-12-01', 2.00),
('Sabão em Pó Omo', 'Sabão em pó para roupas, 1 kg.', 10.99, 120, 'Limpeza', '2024-08-04', 'disponível', 'Omo', '2026-02-01', 1.00),
('Esponja Scotch-Brite', 'Esponja multiuso, pacote com 3 unidades.', 4.99, 90, 'Limpeza', '2024-08-05', 'disponível', 'Scotch-Brite', '2027-01-01', 0.15),
('Lustra Móveis Peroba', 'Lustra móveis com aroma de lavanda, 500 ml.', 9.99, 70, 'Limpeza', '2024-08-06', 'disponível', 'Peroba', '2026-01-01', 0.50),
('Limpa Vidros Veja', 'Limpa vidros, 500 ml.', 7.99, 60, 'Limpeza', '2024-08-07', 'disponível', 'Veja', '2025-11-01', 0.50),
('Cloro Gel Sanol', 'Cloro em gel para limpeza pesada, 1 litro.', 5.49, 75, 'Limpeza', '2024-08-08', 'disponível', 'Sanol', '2026-01-01', 1.00),
('Sabonete Líquido Protex', 'Sabonete líquido antibacteriano, 250 ml.', 6.49, 110, 'Higiene', '2024-08-09', 'disponível', 'Protex', '2025-09-01', 0.25),
('Lava Roupas Ariel Líquido', 'Detergente líquido para roupas, 3 litros.', 18.99, 85, 'Limpeza', '2024-08-10', 'disponível', 'Ariel', '2026-03-01', 3.00),
('Caderno Universitário Tilibra', 'Caderno universitário, 10 matérias, capa dura.', 29.99, 100, 'Papelaria', '2023-12-01', 'disponível', 'Tilibra', NULL, 0.80),
('Caneta Esferográfica Bic', 'Caneta esferográfica azul, ponta fina.', 1.49, 500, 'Papelaria', '2024-01-15', 'disponível', 'Bic', NULL, 0.02),
('Lápis Preto Faber-Castell', 'Lápis preto HB, pacote com 12 unidades.', 3.99, 200, 'Papelaria', '2024-02-10', 'disponível', 'Faber-Castell', NULL, 0.10),
('Marca Texto Stabilo', 'Marca texto amarelo, ponta chanfrada.', 2.99, 150, 'Papelaria', '2024-03-05', 'disponível', 'Stabilo', NULL, 0.03),
('Caderno de Anotações Moleskine', 'Caderno de anotações, capa mole, 200 folhas.', 59.99, 80, 'Papelaria', '2024-04-20', 'disponível', 'Moleskine', NULL, 0.70),
('Bloco de Notas Post-it', 'Bloco de notas adesivas, pacote com 12 blocos.', 15.99, 120, 'Papelaria', '2024-05-15', 'disponível', 'Post-it', NULL, 0.25),
('Pasta Suspensa São Domingos', 'Pasta suspensa, pacote com 10 unidades.', 25.49, 90, 'Papelaria', '2024-06-01', 'disponível', 'São Domingos', NULL, 0.50),
('Clip de Papel 32 mm', 'Clips de papel, pacote com 100 unidades.', 4.99, 250, 'Papelaria', '2024-07-10', 'disponível', NULL, NULL, 0.05),
('Regua de Plástico 30 cm', 'Régua de plástico transparente, 30 cm.', 1.99, 300, 'Papelaria', '2024-08-05', 'disponível', NULL, NULL, 0.05),
('Papel A4 Sulfite', 'Pacote de papel sulfite A4, 500 folhas.', 12.99, 70, 'Papelaria', '2024-09-15', 'disponível', NULL, NULL, 2.00),
('Caneta Marcadora Pilot', 'Caneta marcadora preta, ponta média.', 4.49, 130, 'Papelaria', '2024-10-20', 'disponível', 'Pilot', NULL, 0.03),
('Apontador com Depósito', 'Apontador de lápis com depósito para aparas.', 3.49, 180, 'Papelaria', '2024-11-05', 'disponível', NULL, NULL, 0.07),
('Caneta Gel Zebra', 'Caneta gel preta, ponta 0.7 mm.', 2.79, 160, 'Papelaria', '2024-12-01', 'disponível', 'Zebra', NULL, 0.03),
('Borracha Branca Faber-Castell', 'Borracha branca, pacote com 4 unidades.', 2.99, 220, 'Papelaria', '2025-01-10', 'disponível', 'Faber-Castell', NULL, 0.04),
('Furador de Papel 2 Furos', 'Furador de papel, capacidade para 20 folhas.', 8.99, 110, 'Papelaria', '2025-02-20', 'disponível', NULL, NULL, 0.30),
('Pastas de Arquivo Coloridas', 'Pastas de arquivo coloridas, pacote com 10 unidades.', 18.99, 85, 'Papelaria', '2025-03-15', 'disponível', NULL, NULL, 0.40),
('Etiquetas Adesivas', 'Etiquetas adesivas brancas, pacote com 100 unidades.', 5.49, 200, 'Papelaria', '2025-04-10', 'disponível', NULL, NULL, 0.10),
('Bloco de Rascunho', 'Bloco de rascunho, 200 folhas, capa brochura.', 6.99, 140, 'Papelaria', '2025-05-05', 'disponível', NULL, NULL, 0.60),
('Calculadora Científica Casio', 'Calculadora científica, modelo FX-82MS.', 22.99, 60, 'Papelaria', '2025-06-20', 'disponível', 'Casio', NULL, 0.15),
('Caderno de Desenho Artline', 'Caderno de desenho, 100 folhas, papel A3.', 34.99, 90, 'Papelaria', '2025-07-15', 'disponível', 'Artline', NULL, 1.00),
('O Alquimista', 'Romance sobre a busca de um jovem por seu destino.', 29.90, 150, 'Livros', '2024-01-10', 'disponível', 'Companhia das Letras', NULL, 0.30),
('1984', 'Romance distópico sobre totalitarismo.', 39.90, 100, 'Livros', '2024-02-05', 'disponível', 'HarperCollins', NULL, 0.35),
('A Brief History of Time', 'Livro de física teórica e cosmologia.', 49.90, 80, 'Livros', '2024-03-12', 'disponível', 'Bantam Books', NULL, 0.40),
('Dom Casmurro', 'Romance clássico da literatura brasileira.', 25.90, 120, 'Livros', '2024-04-08', 'disponível', 'Editora Globo', NULL, 0.30),
('Harry Potter e a Pedra Filosofal', 'Primeiro livro da série Harry Potter.', 59.90, 90, 'Livros', '2024-05-15', 'disponível', 'Rocco', NULL, 0.45),
('Cornflakes Kellogg\'s', 'Cereal matinal de milho, 500 g.', 7.99, 200, 'Cereais', '2024-01-20', 'disponível', 'Kellogg\'s', '2025-01-01', 0.50),
('Granola Mãe Terra', 'Granola orgânica, 300 g.', 12.99, 150, 'Cereais', '2024-02-18', 'disponível', 'Mãe Terra', '2024-12-01', 0.30),
('Muesli Nestlé', 'Muesli com frutas e nozes, 400 g.', 9.49, 180, 'Cereais', '2024-03-25', 'disponível', 'Nestlé', '2025-02-01', 0.40),
('Aveia Quaker', 'Aveia em flocos, 1 kg.', 8.99, 200, 'Cereais', '2024-04-10', 'disponível', 'Quaker', '2025-03-01', 1.00),
('Cereal de Arroz Unilever', 'Cereal de arroz, 250 g.', 5.99, 250, 'Cereais', '2024-05-15', 'disponível', 'Unilever', '2024-10-01', 0.25),
('Sabonete Dove', 'Sabonete em barra, 90 g.', 3.99, 300, 'Higiene Pessoal', '2024-01-15', 'disponível', 'Dove', NULL, 0.09),
('Shampoo Head & Shoulders', 'Shampoo anti-caspa, 400 ml.', 15.99, 120, 'Higiene Pessoal', '2024-02-20', 'disponível', 'Head & Shoulders', '2025-03-01', 0.40),
('Creme Dental Colgate', 'Creme dental, 90 g.', 4.49, 250, 'Higiene Pessoal', '2024-03-25', 'disponível', 'Colgate', '2025-06-01', 0.09),
('Desodorante Rexona', 'Desodorante roll-on, 50 ml.', 6.49, 180, 'Higiene Pessoal', '2024-04-05', 'disponível', 'Rexona', '2025-02-01', 0.05),
('Luva de Banho', 'Luva de banho em esponja.', 2.99, 200, 'Higiene Pessoal', '2024-05-10', 'disponível', NULL, NULL, 0.07),
('Sardinha em Óleo Gomes da Costa', 'Sardinha em óleo, 125 g.', 4.49, 150, 'Enlatados', '2024-01-25', 'disponível', 'Gomes da Costa', '2025-03-01', 0.15),
('Feijão Carioca Camil', 'Feijão carioca enlatado, 300 g.', 5.99, 130, 'Enlatados', '2024-02-10', 'disponível', 'Camil', '2025-04-01', 0.30),
('Milho Verde Quero', 'Milho verde em conserva, 340 g.', 3.99, 200, 'Enlatados', '2024-03-05', 'disponível', 'Quero', '2025-05-01', 0.35),
('Tomate Pelado Mutti', 'Tomate pelado enlatado, 400 g.', 6.49, 120, 'Enlatados', '2024-04-15', 'disponível', 'Mutti', '2025-06-01', 0.40),
('Atum em Óleo Coqueiro', 'Atum em óleo, 170 g.', 7.99, 100, 'Enlatados', '2024-05-20', 'disponível', 'Coqueiro', '2025-07-01', 0.18),
('Chocolate ao Leite Lacta', 'Chocolate ao leite, 90 g.', 4.99, 250, 'Chocolates', '2024-01-30', 'disponível', 'Lacta', '2024-12-01', 0.09),
('Chocolate Meio Amargo Nestlé', 'Chocolate meio amargo, 100 g.', 5.49, 200, 'Chocolates', '2024-02-25', 'disponível', 'Nestlé', '2025-01-01', 0.10),
('Chocolate Branco Garoto', 'Chocolate branco, 90 g.', 4.49, 180, 'Chocolates', '2024-03-15', 'disponível', 'Garoto', '2024-11-01', 0.09),
('Chocolate Amargo 70% Cacau', 'Chocolate amargo 70% cacau, 80 g.', 6.99, 150, 'Chocolates', '2024-04-10', 'disponível', NULL, '2025-02-01', 0.08),
('Chocolate com Avelã Ferrero Rocher', 'Chocolate com avelãs, pacote com 12 unidades.', 24.99, 100, 'Chocolates', '2024-05-05', 'disponível', 'Ferrero Rocher', '2025-03-01', 0.30),
('Chocolate ao Leite Hershey\'s', 'Chocolate ao leite, 110 g.', 5.99, 140, 'Chocolates', '2024-06-10', 'disponível', 'Hershey\'s', '2024-12-15', 0.11),
('Chocolate com Menta Nestlé', 'Chocolate com menta, 90 g.', 4.99, 160, 'Chocolates', '2024-07-15', 'disponível', 'Nestlé', '2025-01-01', 0.09),
('Chocolate com Café Lindt', 'Chocolate com café, 100 g.', 7.99, 110, 'Chocolates', '2024-08-20', 'disponível', 'Lindt', '2025-02-01', 0.10),
('Chocolate Vegano Ruby', 'Chocolate vegano, 80 g.', 6.49, 130, 'Chocolates', '2024-09-10', 'disponível', 'Ruby', '2025-03-01', 0.08),
('Chocolate com Caramelo Cadbury', 'Chocolate com caramelo, 100 g.', 5.79, 140, 'Chocolates', '2024-10-05', 'disponível', 'Cadbury', '2025-04-01', 0.10),
('Smartphone Samsung Galaxy S23', 'Smartphone com 128 GB de armazenamento.', 3999.00, 50, 'Eletrônicos', '2024-01-05', 'disponível', 'Samsung', NULL, 0.20),
('Fone de Ouvido Bluetooth JBL', 'Fone de ouvido sem fio com cancelamento de ruído.', 299.90, 80, 'Eletrônicos', '2024-02-10', 'disponível', 'JBL', NULL, 0.25),
('Smartwatch Apple Watch Series 8', 'Smartwatch com monitoramento de saúde e GPS.', 2499.00, 30, 'Eletrônicos', '2024-03-15', 'disponível', 'Apple', NULL, 0.15),
('Laptop Dell Inspiron', 'Laptop com 16 GB de RAM e 512 GB SSD.', 4499.00, 40, 'Eletrônicos', '2024-04-20', 'disponível', 'Dell', NULL, 1.50),
('Câmera DSLR Canon EOS 90D', 'Câmera digital com lente de 18-55 mm.', 6999.00, 20, 'Eletrônicos', '2024-05-25', 'disponível', 'Canon', NULL, 1.80),
('Panela de Pressão Tramontina', 'Panela de pressão de alumínio, 4 L.', 179.90, 60, 'Utensílios Domésticos', '2024-01-10', 'disponível', 'Tramontina', NULL, 1.50),
('Liquidificador Philips', 'Liquidificador com 5 velocidades e função pulsar.', 249.90, 70, 'Utensílios Domésticos', '2024-02-15', 'disponível', 'Philips', NULL, 1.20),
('Jogo de Talheres Brinox', 'Conjunto com 24 peças em inox.', 99.90, 100, 'Utensílios Domésticos', '2024-03-20', 'disponível', 'Brinox', NULL, 0.90),
('Assadeira de Alumínio Tekbond', 'Assadeira antiaderente com capacidade para 2 L.', 59.90, 90, 'Utensílios Domésticos', '2024-04-15', 'disponível', 'Tekbond', NULL, 0.70),
('Cafeteira Elétrica Arno', 'Cafeteira com capacidade para 12 xícaras.', 139.90, 50, 'Utensílios Domésticos', '2024-05-20', 'disponível', 'Arno', NULL, 1.00),
('Camisa Polo Lacoste', 'Camisa polo em algodão, tamanho M.', 299.90, 70, 'Vestuário', '2024-01-15', 'disponível', 'Lacoste', NULL, 0.30),
('Calça Jeans Levis', 'Calça jeans em denim, tamanho 42.', 249.90, 80, 'Vestuário', '2024-02-20', 'disponível', 'Levis', NULL, 0.60),
('Tênis Nike Air Max', 'Tênis esportivo com amortecimento Air Max.', 399.90, 60, 'Vestuário', '2024-03-25', 'disponível', 'Nike', NULL, 0.80),
('Vestido de Verão Hering', 'Vestido floral de algodão, tamanho P.', 129.90, 90, 'Vestuário', '2024-04-10', 'disponível', 'Hering', NULL, 0.25),
('Casaco de Lã Zara', 'Casaco de lã, tamanho G.', 499.90, 40, 'Vestuário', '2024-05-05', 'disponível', 'Zara', NULL, 1.20),
('Carrinho de Controle Remoto', 'Carrinho com controle remoto, escala 1:18.', 159.90, 50, 'Brinquedos', '2024-01-25', 'disponível', 'Estrela', NULL, 0.40),
('Boneca Barbie Fashionista', 'Boneca Barbie com roupas e acessórios.', 199.90, 70, 'Brinquedos', '2024-02-20', 'disponível', 'Mattel', NULL, 0.35),
('Quebra-Cabeça 1000 Peças', 'Quebra-cabeça com imagem de paisagens.', 89.90, 100, 'Brinquedos', '2024-03-15', 'disponível', 'Grow', NULL, 0.50),
('Jogo de Tabuleiro Monopoly', 'Jogo de tabuleiro clássico, 2-6 jogadores.', 129.90, 80, 'Brinquedos', '2024-04-10', 'disponível', 'Hasbro', NULL, 0.80),
('Lego City - Estação de Polícia', 'Conjunto de Lego com 500 peças.', 349.90, 40, 'Brinquedos', '2024-05-05', 'disponível', 'Lego', NULL, 1.00),
('Óculos de Sol Ray-Ban', 'Óculos de sol com proteção UV, modelo Wayfarer.', 699.90, 30, 'Acessórios de Moda', '2024-01-30', 'disponível', 'Ray-Ban', NULL, 0.20),
('Bolsa de Couro Michael Kors', 'Bolsa de couro com alças ajustáveis.', 999.00, 20, 'Acessórios de Moda', '2024-02-15', 'disponível', 'Michael Kors', NULL, 0.80),
('Relógio Casio Digital', 'Relógio digital com cronômetro e alarme.', 129.90, 60, 'Acessórios de Moda', '2024-03-20', 'disponível', 'Casio', NULL, 0.10),
('Cinto de Couro Diesel', 'Cinto de couro com fivela metálica.', 149.90, 70, 'Acessórios de Moda', '2024-04-15', 'disponível', 'Diesel', NULL, 0.20),
('Pulseira de Prata Vivara', 'Pulseira de prata com design elegante.', 299.90, 50, 'Acessórios de Moda', '2024-05-25', 'disponível', 'Vivara', NULL, 0.10),
('Chapéu de Palha', 'Chapéu de palha com proteção UV.', 79.90, 90, 'Acessórios de Moda', '2024-06-10', 'disponível', 'N/A', NULL, 0.20),
('Cachecol de Lã', 'Cachecol de lã, disponível em várias cores.', 89.90, 80, 'Acessórios de Moda', '2024-07-05', 'disponível', 'N/A', NULL, 0.30),
('Carteira de Couro', 'Carteira de couro com compartimentos para cartões.', 139.90, 70, 'Acessórios de Moda', '2024-08-15', 'disponível', 'N/A', NULL, 0.15),
('Boné Adidas', 'Boné ajustável com logo Adidas.', 69.90, 100, 'Acessórios de Moda', '2024-09-10', 'disponível', 'Adidas', NULL, 0.10),
('Óculos de Natação Speedo', 'Óculos de natação com lentes antiembaçantes.', 49.90, 120, 'Acessórios de Moda', '2024-10-05', 'disponível', 'Speedo', NULL, 0.05),
('Arroz Integral Tio João', 'Arroz integral, 5 kg.', 18.90, 200, 'Alimentos', '2024-01-10', 'disponível', 'Tio João', '2025-01-01', 5.00),
('Açúcar Cristal União', 'Açúcar cristal, 1 kg.', 3.49, 300, 'Alimentos', '2024-02-15', 'disponível', 'União', '2025-02-01', 1.00),
('Feijão Preto Camil', 'Feijão preto, 1 kg.', 6.99, 150, 'Alimentos', '2024-03-20', 'disponível', 'Camil', '2025-03-01', 1.00),
('Óleo de Soja Soya', 'Óleo de soja, 900 ml.', 5.49, 180, 'Alimentos', '2024-04-25', 'disponível', 'Soya', '2025-04-01', 0.90),
('Macarrão Espaguete Barilla', 'Macarrão espaguete, 500 g.', 7.99, 250, 'Alimentos', '2024-05-30', 'disponível', 'Barilla', '2025-05-01', 0.50),
('Suco de Laranja Del Valle', 'Suco de laranja 1 L.', 4.99, 200, 'Bebidas', '2024-01-15', 'disponível', 'Del Valle', '2024-12-01', 1.00),
('Água Mineral Crystal', 'Água mineral sem gás, 500 ml.', 1.49, 300, 'Bebidas', '2024-02-20', 'disponível', 'Crystal', '2025-01-01', 0.50),
('Refrigerante Coca-Cola', 'Refrigerante de cola, 2 L.', 6.99, 150, 'Bebidas', '2024-03-25', 'disponível', 'Coca-Cola', '2024-11-01', 2.00),
('Cerveja Skol', 'Cerveja, lata 350 ml.', 2.49, 200, 'Bebidas', '2024-04-15', 'disponível', 'Skol', '2025-01-01', 0.35),
('Vinho Tinto Casa Valduga', 'Vinho tinto, 750 ml.', 49.90, 100, 'Bebidas', '2024-05-10', 'disponível', 'Casa Valduga', '2027-05-01', 0.75),
('Detergente Ypê', 'Detergente para louças, 500 ml.', 3.99, 250, 'Produtos de Limpeza', '2024-01-20', 'disponível', 'Ypê', '2025-01-01', 0.50),
('Sabão em Pó Omo', 'Sabão em pó, 1 kg.', 9.99, 200, 'Produtos de Limpeza', '2024-02-25', 'disponível', 'Omo', '2025-03-01', 1.00),
('Desinfetante Pinho Sol', 'Desinfetante com fragrância, 1 L.', 7.49, 150, 'Produtos de Limpeza', '2024-03-15', 'disponível', 'Pinho Sol', '2025-06-01', 1.00),
('Amaciante Comfort', 'Amaciante de roupas, 800 ml.', 6.99, 180, 'Produtos de Limpeza', '2024-04-10', 'disponível', 'Comfort', '2025-02-01', 0.80),
('Esponja de Aço Panan', 'Esponja de aço com 5 unidades.', 2.99, 300, 'Produtos de Limpeza', '2024-05-05', 'disponível', 'Panan', NULL, 0.10),
('Caderno 10 Matérias Tilibra', 'Caderno com 10 matérias, capa dura.', 29.90, 150, 'Papelaria', '2024-01-30', 'disponível', 'Tilibra', NULL, 0.80),
('Caneta Esferográfica BIC', 'Pacote com 10 canetas esferográficas azuis.', 6.49, 200, 'Papelaria', '2024-02-20', 'disponível', 'BIC', NULL, 0.05),
('Marca Texto Stabilo', 'Marca texto, cor amarela.', 4.99, 180, 'Papelaria', '2024-03-25', 'disponível', 'Stabilo', NULL, 0.10),
('Lápis de Cor Faber-Castell', 'Conjunto com 24 lápis de cor.', 12.99, 150, 'Papelaria', '2024-04-15', 'disponível', 'Faber-Castell', NULL, 0.25),
('Agenda 2024', 'Agenda com capa em couro.', 39.90, 120, 'Papelaria', '2024-05-10', 'disponível', 'N/A', NULL, 0.40),
('Smart TV Samsung 50"', 'Televisor LED 50 polegadas, 4K.', 2499.00, 40, 'Eletrônicos', '2024-01-15', 'disponível', 'Samsung', NULL, 12.00),
('Câmera de Segurança Intelbras', 'Câmera de segurança com visão noturna.', 399.90, 60, 'Eletrônicos', '2024-02-20', 'disponível', 'Intelbras', NULL, 0.50),
('Caixa de Som Bluetooth JBL Flip 5', 'Caixa de som portátil, resistência à água.', 699.90, 50, 'Eletrônicos', '2024-03-10', 'disponível', 'JBL', NULL, 0.70),
('Tablet Lenovo Tab P11', 'Tablet com 128 GB de armazenamento.', 1499.00, 30, 'Eletrônicos', '2024-04-05', 'disponível', 'Lenovo', NULL, 0.60),
('Impressora Multifuncional HP', 'Impressora com função de cópia e digitalização.', 799.90, 40, 'Eletrônicos', '2024-05-15', 'disponível', 'HP', NULL, 4.00),
('Jogo de Panelas Tramontina', 'Conjunto com 5 panelas em alumínio.', 299.90, 60, 'Utensílios Domésticos', '2024-01-20', 'disponível', 'Tramontina', NULL, 2.50),
('Tábua de Corte Plasvale', 'Tábua de corte em plástico, tamanho grande.', 39.90, 80, 'Utensílios Domésticos', '2024-02-25', 'disponível', 'Plasvale', NULL, 0.50),
('Rolo de Massas Mimo', 'Rolo de massas em madeira.', 29.90, 100, 'Utensílios Domésticos', '2024-03-10', 'disponível', 'Mimo', NULL, 0.40),
('Panos de Prato Karsten', 'Pacote com 6 panos de prato.', 29.90, 150, 'Utensílios Domésticos', '2024-04-15', 'disponível', 'Karsten', NULL, 0.30),
('Escorredor de Louça Metal', 'Escorredor de louça em aço inox.', 89.90, 90, 'Utensílios Domésticos', '2024-05-20', 'disponível', 'N/A', NULL, 1.00),
('Calça Legging Gymshark', 'Calça legging preta, tamanho P.', 119.90, 70, 'Vestuário', '2024-01-25', 'disponível', 'Gymshark', NULL, 0.30),
('Camisa de Viscose Hering', 'Camisa feminina de viscose, tamanho M.', 89.90, 80, 'Vestuário', '2024-02-15', 'disponível', 'Hering', NULL, 0.20),
('Tênis Converse All Star', 'Tênis branco, tamanho 42.', 249.90, 60, 'Vestuário', '2024-03-20', 'disponível', 'Converse', NULL, 0.70),
('Jaqueta de Couro Schott', 'Jaqueta de couro marrom, tamanho G.', 599.90, 40, 'Vestuário', '2024-04-10', 'disponível', 'Schott', NULL, 1.50),
('Blusa de Frio Adidas', 'Blusa de frio, tamanho GG.', 149.90, 90, 'Vestuário', '2024-05-15', 'disponível', 'Adidas', NULL, 0.40),
('Brinquedo de Madeira', 'Brinquedo educativo de madeira.', 79.90, 60, 'Brinquedos', '2024-01-30', 'disponível', 'N/A', NULL, 0.50),
('Pelúcia Ursinho', 'Ursinho de pelúcia, 30 cm.', 99.90, 70, 'Brinquedos', '2024-02-20', 'disponível', 'N/A', NULL, 0.40),
('Construtor de Blocos Lego', 'Blocos de construção, 200 peças.', 129.90, 50, 'Brinquedos', '2024-03-25', 'disponível', 'Lego', NULL, 0.70),
('Carro de Brinquedo Hot Wheels', 'Carro de brinquedo, escala 1:64.', 24.90, 90, 'Brinquedos', '2024-04-20', 'disponível', 'Hot Wheels', NULL, 0.20),
('Jogo de Montar Magnético', 'Conjunto de peças magnéticas para montar.', 149.90, 40, 'Brinquedos', '2024-05-25', 'disponível', 'N/A', NULL, 0.60),
('Óculos de Sol Vogue', 'Óculos de sol com proteção UV, modelo aviador.', 399.90, 30, 'Acessórios de Moda', '2024-01-15', 'disponível', 'Vogue', NULL, 0.25),
('Bolsa Feminina Michael Kors', 'Bolsa de couro com alças ajustáveis.', 1299.00, 20, 'Acessórios de Moda', '2024-02-20', 'disponível', 'Michael Kors', NULL, 0.80),
('Relógio Analógico Fossil', 'Relógio com pulseira de couro.', 299.90, 60, 'Acessórios de Moda', '2024-03-10', 'disponível', 'Fossil', NULL, 0.30),
('Chapéu de Feltro', 'Chapéu de feltro, cor preta.', 89.90, 50, 'Acessórios de Moda', '2024-04-05', 'disponível', 'N/A', NULL, 0.30),
('Cinto de Couro Calvin Klein', 'Cinto de couro com fivela metálica.', 179.90, 40, 'Acessórios de Moda', '2024-05-15', 'disponível', 'Calvin Klein', NULL, 0.25),
('Cachecol de Lã', 'Cachecol de lã, cor cinza.', 79.90, 70, 'Acessórios de Moda', '2024-06-20', 'disponível', 'N/A', NULL, 0.20),
('Pulseira de Couro', 'Pulseira de couro com detalhes em metal.', 119.90, 80, 'Acessórios de Moda', '2024-07-15', 'disponível', 'N/A', NULL, 0.10),
('Boné Nike', 'Boné ajustável com logo Nike.', 89.90, 100, 'Acessórios de Moda', '2024-08-10', 'disponível', 'Nike', NULL, 0.15),
('Carteira de Couro', 'Carteira de couro com compartimentos.', 159.90, 90, 'Acessórios de Moda', '2024-09-05', 'disponível', 'N/A', NULL, 0.20),
('Óculos de Natação Speedo', 'Óculos de natação com lentes antiembaçantes.', 39.90, 110, 'Acessórios de Moda', '2024-10-15', 'disponível', 'Speedo', NULL, 0.10),
('Chocolate ao Leite Nestlé', 'Chocolate ao leite 90 g.', 5.49, 80, 'Chocolates', '2024-01-10', 'disponível', 'Nestlé', '2024-01-01', 0.09),
('Chocolate Amargo Lindt', 'Chocolate amargo 70% cacau, 100 g.', 12.99, 70, 'Chocolates', '2024-02-15', 'disponível', 'Lindt', '2024-02-01', 0.10),
('Chocolate Branco Kopenhagen', 'Chocolate branco com amêndoas, 150 g.', 9.99, 90, 'Chocolates', '2024-03-20', 'disponível', 'Kopenhagen', '2024-03-01', 0.15),
('Feijão Preto Camil', 'Feijão preto, 1 kg.', 6.99, 150, 'Alimentos', '2024-01-15', 'disponível', 'Camil', '2024-01-01', 1.00),
('Arroz Branco Tipo 1', 'Arroz branco tipo 1, 5 kg.', 19.90, 100, 'Alimentos', '2024-02-10', 'disponível', 'N/A', '2024-02-01', 5.00),
('Açúcar Cristal União', 'Açúcar cristal, 1 kg.', 3.49, 200, 'Alimentos', '2024-03-25', 'disponível', 'União', '2024-03-01', 1.00),
('Detergente Omo', 'Detergente para louças, 500 ml.', 3.99, 120, 'Produtos de Limpeza', '2024-01-30', 'disponível', 'Omo', '2024-01-01', 0.50),
('Sabão em Pó Ariel', 'Sabão em pó, 1 kg.', 8.99, 150, 'Produtos de Limpeza', '2024-02-20', 'disponível', 'Ariel', '2024-02-01', 1.00),
('Desinfetante Pinho Sol', 'Desinfetante com fragrância, 1 L.', 7.49, 100, 'Produtos de Limpeza', '2024-03-05', 'disponível', 'Pinho Sol', '2024-03-01', 1.00),
('Suco de Laranja Del Valle', 'Suco de laranja 1 L.', 4.99, 90, 'Bebidas', '2024-01-20', 'disponível', 'Del Valle', '2024-01-01', 1.00),
('Água Mineral Crystal', 'Água mineral sem gás, 500 ml.', 1.49, 150, 'Bebidas', '2024-02-15', 'disponível', 'Crystal', '2024-02-01', 0.50),
('Refrigerante Guaraná Antártica', 'Refrigerante, 2 L.', 6.49, 80, 'Bebidas', '2024-03-30', 'disponível', 'Guaraná Antártica', '2024-03-01', 2.00),
('Corn Flakes Kellogg\'s', 'Cereal matinal de milho, 500 g.', 8.99, 110, 'Cereais', '2024-01-25', 'disponível', 'Kellogg\'s', '2024-01-01', 0.50),
('Granola Mãe Terra', 'Granola integral, 300 g.', 12.49, 90, 'Cereais', '2024-02-10', 'disponível', 'Mãe Terra', '2024-02-01', 0.30),
('Aveia Quaker', 'Aveia em flocos, 1 kg.', 7.99, 100, 'Cereais', '2024-03-15', 'disponível', 'Quaker', '2024-03-01', 1.00),
('Suco de Laranja Del Valle', 'Suco de laranja 1 L.', 4.99, 100, 'Bebidas', '2024-01-15', 'disponível', 'Del Valle', '2024-01-01', 1.00),
('Refrigerante Coca-Cola', 'Refrigerante de cola, 2 L.', 6.99, 80, 'Bebidas', '2024-03-25', 'disponível', 'Coca-Cola', '2024-03-01', 2.00),
('Macarrão Espaguete Barilla', 'Macarrão espaguete, 500 g.', 7.99, 120, 'Alimentos', '2024-05-30', 'disponível', 'Barilla', '2024-05-01', 0.50),
('Detergente Ypê', 'Detergente para louças, 500 ml.', 3.99, 150, 'Produtos de Limpeza', '2024-01-20', 'disponível', 'Ypê', '2024-01-01', 0.50),
('Caderno 10 Matérias Tilibra', 'Caderno com 10 matérias, capa dura.', 29.90, 100, 'Papelaria', '2024-01-30', 'disponível', 'Tilibra', NULL, 0.80),
('Tênis Nike Air Max', 'Tênis esportivo com amortecimento Air Max.', 399.90, 50, 'Vestuário', '2024-03-25', 'disponível', 'Nike', NULL, 0.80),
('Brinquedo de Madeira', 'Brinquedo educativo de madeira.', 79.90, 60, 'Brinquedos', '2024-01-30', 'disponível', 'N/A', NULL, 0.50),
('Óculos de Sol Vogue', 'Óculos de sol com proteção UV, modelo aviador.', 399.90, 30, 'Acessórios de Moda', '2024-01-15', 'disponível', 'Vogue', NULL, 0.25),
('Jogo de Panelas Tramontina', 'Conjunto com 5 panelas em alumínio.', 299.90, 60, 'Utensílios Domésticos', '2024-01-20', 'disponível', 'Tramontina', NULL, 2.50),
('Relógio Casio Digital', 'Relógio digital com cronômetro e alarme.', 129.90, 60, 'Acessórios de Moda', '2024-03-20', 'disponível', 'Casio', NULL, 0.10);

select * from tb_produtos;

/*1. Atualize o status para 'indisponível' e aumente o preço em 15% para produtos da categoria 'Cereais' ou 'bebidas' que têm `pro_quantidade_estoque` menor que 100 e `pro_preco` menor que 15.00.*/
UPDATE tb_produtos
SET pro_status = 'indisponível', pro_preco = ROUND(pro_preco * 1.15, 2)
WHERE (pro_categoria = 'Cereais' OR pro_categoria = 'Bebidas') 
AND pro_quantidade_estoque < 100 AND pro_preco < 15.00;

/*2. Exclua todos os produtos com data de validade vencida e cujo preço é maior que 50.00 da tabela `tb_produtos`.*/
DELETE FROM tb_produtos
WHERE pro_data_validade < CURDATE() 
AND pro_preco > 50.00;

/*3. Aumente a quantidade em estoque em 50 unidades e defina a marca como 'Novo Produto' para produtos da categoria 'Produtos de Limpeza' que foram cadastrados há mais de 6 meses e cujo `pro_preco` é menor que 10.00.*/
UPDATE tb_produtos
SET pro_quantidade_estoque = pro_quantidade_estoque + 50, pro_marca = 'Novo Produto'
WHERE pro_categoria = 'Produtos de Limpeza' 
AND pro_data_cadastro < CURDATE() - INTERVAL 6 MONTH 
AND pro_preco < 10.00;

/*4. Reduza o valor em 15 % de todos os produtos da categoria 'Chocolates' que têm `pro_quantidade_estoque` menor que 100 e foram cadastrados há mais de três meses e quinze dias.*/
UPDATE tb_produtos
SET pro_preco = pro_preco * 0.85
WHERE pro_categoria = 'Chocolates' 
AND pro_quantidade_estoque < 100 
AND pro_data_cadastro < CURDATE() - INTERVAL 3 MONTH - INTERVAL 15 DAY;

/*5. Aumente o preço em 20% e defina a data de validade como 3 meses a partir da data atual para produtos da categoria 'Alimentos' que têm `pro_quantidade_estoque` maior que 50 e `pro_data_validade` menor que a data atual.*/
UPDATE tb_produtos
SET pro_preco = pro_preco * 1.20, pro_data_validade = CURDATE() + INTERVAL 3 MONTH
WHERE pro_categoria = 'Alimentos' 
AND pro_quantidade_estoque > 50 
AND pro_data_validade < CURDATE();

/*6. Exclua todos os produtos da categoria 'Produtos de Limpeza' que têm validade vencida, peso menor que 1kg e seja da marca Omo ou Ariel.*/
DELETE FROM tb_produtos
WHERE pro_categoria = 'Produtos de Limpeza' 
AND pro_data_validade < CURDATE() 
AND pro_peso < 1 
AND (pro_marca = 'Omo' OR pro_marca = 'Ariel');

/*7. Atualize a descrição para 'Promoção Especial' e defina o status como 'disponível' para produtos com quntidade entre 50 e 100 e preco maior que 20.00.*/
UPDATE tb_produtos
SET pro_descricao = 'Promoção Especial', pro_status = 'disponível'
WHERE pro_quantidade_estoque BETWEEN 50 AND 100 
AND pro_preco > 20.00;

/*8. Exclua todos os produtos da categoria 'Bebidas' ou 'Papelaria' cujo cadastro feito a mais de três meses e o preço menor que 2.00.*/
DELETE FROM tb_produtos
WHERE (pro_categoria = 'Bebidas' OR pro_categoria = 'Papelaria') 
AND pro_data_cadastro < CURDATE() - INTERVAL 3 MONTH 
AND pro_preco < 2.00;

/*9. Defina a marca como 'Super Marca' e aumente o peso em 0.5 kg para produtos da categoria 'Utensílios Domésticos' que têm o preco maior que 50.00 e o peso menor que 2.00 kg.*/
UPDATE tb_produtos
SET pro_marca = 'Super Marca', pro_peso = pro_peso + 0.5
WHERE pro_categoria = 'Utensílios Domésticos' 
AND pro_preco > 50.00 
AND pro_peso < 2.00;

/*10. Exclua todos os produtos que têm preco menor que 2.00 e quantidade em estoque maior que 200.*/
DELETE FROM tb_produtos
WHERE pro_preco < 2.00 
AND pro_quantidade_estoque > 200;

/*11. Aumente o preço dos produtos da categoria 'Chocolates' em 25% onde validade é maior que a data atual e quantidade em estoque é maior que 50.*/
UPDATE tb_produtos
SET pro_preco = pro_preco * 1.25
WHERE pro_categoria = 'Chocolates' 
AND pro_data_validade > CURDATE() 
AND pro_quantidade_estoque > 50;

/*12. Exclua todos os produtos que têm peso maior que 5.00 kg e preco maior que 10.00.*/
DELETE FROM tb_produtos
WHERE pro_peso > 5.00 
AND pro_preco > 10.00;
```
