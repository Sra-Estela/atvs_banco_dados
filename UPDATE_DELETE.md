# UPDATE + DELETE

```MySQL
create database db_escola;
use db_escola;

CREATE TABLE tb_professores (
    pro_id INT AUTO_INCREMENT PRIMARY KEY,
    pro_nome VARCHAR(100) NOT NULL,
    pro_data_nascimento DATE NOT NULL,
    pro_genero ENUM('M', 'F', 'Outro') NOT NULL,
    pro_rua VARCHAR(100),
    pro_numero INT,
    pro_complemento VARCHAR(100),
    pro_bairro VARCHAR(100),
    pro_cidade VARCHAR(100),
    pro_estado VARCHAR(50),
    pro_cep VARCHAR(10),
    pro_email VARCHAR(100),
    pro_telefone VARCHAR(20),
    pro_data_contratacao DATE NOT NULL,
    pro_departamento VARCHAR(100)
);

INSERT INTO tb_professores (pro_nome, pro_data_nascimento, pro_genero, pro_rua, pro_numero, pro_complemento, pro_bairro, pro_cidade, pro_estado, pro_cep, pro_email, pro_telefone, pro_data_contratacao, pro_departamento) VALUES
('Anitta', '1993-03-30', 'F', 'Rua das Celebridades', 123, 'Apto 45', 'Centro', 'Rio de Janeiro', 'RJ', '20000-000', 'anitta@example.com', '555-1234', '2023-08-01', 'Música'),
('Neymar Jr.', '1992-02-05', 'M', 'Avenida dos Atletas', 456, '', 'Jardim Paulista', 'São Paulo', 'SP', '01000-000', 'neymar@example.com', '555-5678', '2023-08-02', 'Educação Física'),
('Ivete Sangalo', '1972-05-27', 'F', 'Rua dos Cantores', 789, 'Bloco B', 'Barra', 'Salvador', 'BA', '40000-000', 'ivete@example.com', '555-9101', '2023-08-03', 'Música'),
('Caetano Veloso', '1942-08-07', 'M', 'Rua da Música', 101, '', 'Pelourinho', 'Salvador', 'BA', '40000-000', 'caetano@example.com', '555-1122', '2023-08-04', 'Música'),
('Gisele Bündchen', '1980-07-20', 'F', 'Avenida das Modelos', 202, 'Cobertura 10', 'Centro', 'Horizontina', 'RS', '90000-000', 'gisele@example.com', '555-1314', '2023-08-05', 'Moda'),
('Pelé', '1940-10-23', 'M', 'Rua dos Esportes', 303, '', 'Canal 6', 'Santos', 'SP', '11000-000', 'pele@example.com', '555-1516', '2023-08-06', 'Educação Física'),
('Xuxa Meneghel', '1963-03-27', 'F', 'Rua das Rainhas', 404, 'Casa 12', 'Jardim Botânico', 'Rio de Janeiro', 'RJ', '20000-000', 'xuxa@example.com', '555-1718', '2023-08-07', 'Entretenimento Infantil'),
('Wagner Moura', '1976-06-27', 'M', 'Rua dos Atores', 505, '', 'Centro', 'Salvador', 'BA', '40000-000', 'wagner@example.com', '555-1920', '2023-08-08', 'Artes Cênicas'),
('Marília Mendonça', '1995-07-22', 'F', 'Rua dos Cantores', 606, '', 'Setor Oeste', 'Goiânia', 'GO', '74000-000', 'marilia@example.com', '555-2122', '2023-08-09', 'Música'),
('Rodrigo Santoro', '1975-08-22', 'M', 'Avenida dos Atores', 707, 'Apto 7B', 'Copacabana', 'Rio de Janeiro', 'RJ', '22000-000', 'rodrigo@example.com', '555-2324', '2023-08-10', 'Artes Cênicas'),
('Luis Fonsi', '1978-04-15', 'M', 'Avenida de la Música', 101, '', 'San Juan', 'Puerto Rico', '', '00901', 'luis@example.com', '555-1234', '2023-08-01', 'Música'),
('J Balvin', '1985-05-07', 'M', 'Calle del Reggaeton', 202, '', 'Medellín', 'Antioquia', '', '050001', 'jbalvin@example.com', '555-5678', '2023-08-02', 'Música'),
('Maluma', '1994-01-28', 'M', 'Carrera del Pop', 303, '', 'Medellín', 'Antioquia', '', '050001', 'maluma@example.com', '555-9101', '2023-08-03', 'Música'),
('Enrique Iglesias', '1975-05-08', 'M', 'Boulevard de la Fama', 404, '', 'Madrid', '', '', '28001', 'enrique@example.com', '555-1122', '2023-08-04', 'Música'),
('Daddy Yankee', '1977-02-03', 'M', 'Calle del Reggaeton', 505, '', 'San Juan', 'Puerto Rico', '', '00901', 'daddy@example.com', '555-1314', '2023-08-05', 'Música'),
('Marc Anthony', '1968-09-16', 'M', 'Avenida Tropical', 606, '', 'Nueva York', 'New York', 'NY', '10001', 'marc@example.com', '555-1516', '2023-08-06', 'Música'),
('Carlos Vives', '1961-08-07', 'M', 'Calle de la Salsa', 707, '', 'Santa Marta', 'Magdalena', '', '470001', 'carlos@example.com', '555-1718', '2023-08-07', 'Música'),
('Alejandro Sanz', '1968-12-18', 'M', 'Avenida del Pop', 808, '', 'Madrid', '', '', '28001', 'alejandro@example.com', '555-1920', '2023-08-08', 'Música'),
('Rosalía', '1992-09-25', 'F', 'Calle Flamenca', 909, '', 'Barcelona', '', '', '08001', 'rosalia@example.com', '555-2122', '2023-08-09', 'Música'),
('Juanes', '1972-08-09', 'M', 'Avenida del Rock', 1010, '', 'Medellín', 'Antioquia', '', '050001', 'juanes@example.com', '555-2324', '2023-08-10', 'Música'),
('Bad Bunny', '1994-03-10', 'M', 'Calle del Trap', 1111, '', 'San Juan', 'Puerto Rico', '', '00901', 'badbunny@example.com', '555-2526', '2023-08-11', 'Música'),
('Natalia Lafourcade', '1984-02-26', 'F', 'Calle de la Música', 1212, '', 'Ciudad de México', 'CDMX', '', '01000', 'natalia@example.com', '555-2728', '2023-08-12', 'Música'),
('Gente de Zona', '2000-01-01', 'M', 'Avenida de la Salsa', 1313, '', 'La Habana', '', '', '10400', 'gentedelzona@example.com', '555-2930', '2023-08-13', 'Música'),
('Paulina Rubio', '1971-06-17', 'F', 'Boulevard de la Pop', 1414, '', 'Ciudad de México', 'CDMX', '', '01000', 'paulina@example.com', '555-3132', '2023-08-14', 'Música'),
('Ricky Martin', '1971-12-24', 'M', 'Calle del Latin Pop', 1515, '', 'San Juan', 'Puerto Rico', '', '00901', 'ricky@example.com', '555-3334', '2023-08-15', 'Música'),
('Thalía', '1971-08-26', 'F', 'Avenida de la Música', 1616, '', 'Ciudad de México', 'CDMX', '', '01000', 'thalia@example.com', '555-3536', '2023-08-16', 'Música'),
('Camila Cabello', '1997-03-03', 'F', 'Calle del Pop', 1717, '', 'Cojímar', 'La Habana', '', '10400', 'camila@example.com', '555-3738', '2023-08-17', 'Música'),
('Sergio Mendes', '1941-02-11', 'M', 'Avenida Brasileira', 1818, '', 'Rio de Janeiro', 'RJ', '', '22000-000', 'sergio@example.com', '555-3940', '2023-08-18', 'Música'),
('Manuel Turizo', '2000-04-12', 'M', 'Calle del Reggaeton', 1919, '', 'Montería', 'Córdoba', '', '230001', 'manuel@example.com', '555-4142', '2023-08-19', 'Música'),
('Tini Stoessel', '1997-03-21', 'F', 'Avenida de la Música', 2020, '', 'Buenos Aires', '', '', 'C1001', 'tini@example.com', '555-4344', '2023-08-20', 'Música'),
('Pablo Alborán', '1989-05-25', 'M', 'Calle del Pop', 2121, '', 'Málaga', '', '', '29001', 'pablo@example.com', '555-4546', '2023-08-21', 'Música'),
('Ozuna', '1992-03-13', 'M', 'Calle del Trap', 2222, '', 'San Juan', 'Puerto Rico', '', '00901', 'ozuna@example.com', '555-4748', '2023-08-22', 'Música'),
('Mon Laferte', '1983-05-02', 'F', 'Avenida de la Música', 2323, '', 'Viña del Mar', '', '', '2570000', 'mon@example.com', '555-4950', '2023-08-23', 'Música'),
('Eladio Carrión', '1994-11-14', 'M', 'Calle del Trap', 2424, '', 'San Juan', 'Puerto Rico', '', '00901', 'eladio@example.com', '555-5152', '2023-08-24', 'Música'),
('Anuel AA', '1992-11-26', 'M', 'Calle del Reggaeton', 2525, '', 'San Juan', 'Puerto Rico', '', '00901', 'anuel@example.com', '555-5354', '2023-08-25', 'Música'),
('CNCO', '2015-01-01', 'M', 'Calle del Pop', 2626, '', 'Miami', 'Florida', 'FL', '33101', 'cnco@example.com', '555-5556', '2023-08-26', 'Música'),
('Ha-Ash', '2002-01-01', 'F', 'Avenida de la Música', 2727, '', 'Ciudad de México', 'CDMX', '', '01000', 'haash@example.com', '555-5758', '2023-08-27', 'Música'),
('Juan Luis Guerra', '1957-06-07', 'M', 'Calle del Merengue', 2828, '', 'Santo Domingo', '', '', '10101', 'juanluis@example.com', '555-5960', '2023-08-28', 'Música'),
('Ricardo Arjona', '1964-01-19', 'M', 'Calle del Romanticismo', 2929, '', 'Ciudad de Guatemala', '', '', '01001', 'ricardo@example.com', '555-6162', '2023-08-29','Música');

/*
UPDATE nome_da_tabela
SET coluna1 = valor1, coluna2 = valor2, ...
WHERE condição;
*/
/*
DELETE FROM nome_da_tabela
WHERE condição;
*/

/*1. **Atualização de E-mail:**  */
   /*Altere o e-mail do professor "Anitta" para "anitta.silva@exemplo.com".*/
SELECT * FROM tb_professores;
UPDATE tb_professores SET pro_email = "anitta.silva@exemplo.com" WHERE pro_id = 1;

/*2. **Mudança de Departamento:**  */
   /*Atualize o departamento dos professores que lecionam "Música" para "Moda".*/
SELECT * FROM tb_professores;
UPDATE tb_professores SET pro_departamento = "Moda" WHERE pro_departamento = "Música";

/*3. **Correção de Telefone:**  */
   /*Corrija o número de telefone do professor cujo ID é 3 para "(11) 99999-8888".*/
SELECT * FROM tb_professores; 
UPDATE tb_professores SET pro_telefone = "(11) 99999-8888" WHERE pro_id = 3;

/*4. **Ajuste de Salário:**  */
   /*Reduza em 5% o salário dos professores que trabalham no departamento de "Moda".*/
SELECT * FROM tb_professores;
UPDATE tb_professores SET pro_numero = 749.55 WHERE pro_departamento = 'Moda';

/*5. **Atualização de Endereço:**  */
   /*Atualize o endereço dos professores que moram na cidade "São Paulo" para "Rua Nova, 123".*/
SELECT * FROM tb_professores;  
UPDATE tb_professores SET pro_rua = 'Rua Nova', pro_numero = 123 WHERE pro_cidade = 'São Paulo';

/*6. **Exclusão por Departamento:**  */
   /*Delete todos os professores do departamento "Educação Física".*/
SELECT * FROM tb_professores;
DELETE FROM tb_professores WHERE pro_departamento = 'Educação Física';

/*7. **Remoção de Professores Recém-Contratados:**  */
   /*Remova todos os professores contratados após o ano de 2024.*/
SELECT * FROM tb_professores;
DELETE FROM tb_professores WHERE YEAR(pro_data_contratacao) > 2024;

/*12. **Alteração de Data de Contratação:**  */
    /*Corrija a data de contratação de "Marília Mendonça" para 2022-01-15.*/
SELECT * FROM tb_professores;    
UPDATE tb_professores SET pro_data_contratacao = '2022-01-15' WHERE pro_nome = 'Marília Mendonça';

/*13. **Correção de Cidade:**  */
    /*Atualize a cidade de todos os professores que moram no estado de "SP" para "São Paulo".*/
SELECT * FROM tb_professores;    
UPDATE tb_professores SET pro_cidade = 'São Paulo' WHERE pro_estado = 'SP';

/*15. **Exclusão por Estado:**  */
    /*Delete todos os professores que residem no estado de "RJ".*/
SELECT * FROM tb_professores;    
DELETE FROM tb_professores WHERE pro_estado = 'RJ';

/*18. **Remoção por Gênero:**  */
    /*Delete todos os professores cujo gênero é "Outro" para fins de simplificação do banco de dados.*/
SELECT * FROM tb_professores;    
DELETE FROM tb_professores WHERE pro_genero = 'Outro';

/*24. **Exclusão por Departamento e Data de Contratação:**  */
   /*Delete todos os professores do departamento "Música" contratados antes de 2020.*/
SELECT * FROM tb_professores; 
DELETE FROM tb_professores WHERE YEAR(pro_data_contratacao) > 2020 AND pro_departamento = 'Música';

/*26. **Exclusão por Cidade e Data de Contratação:**  */
   /*Delete todos os professores da cidade "Salvador" contratados após 2022.*/
SELECT * FROM tb_professores; 
DELETE FROM tb_professores WHERE YEAR(pro_data_contratacao) > 2022 AND pro_cidade = 'Salvador';

/*27. **Remoção por Gênero e Departamento:**  */
   /*Delete todos os professores do departamento "Biologia" cujo gênero é "Masculino".*/
SELECT * FROM tb_professores; 
DELETE FROM tb_professores WHERE pro_departamento = 'Biologia' AND pro_genero = 'M';

/*28. **Exclusão por ID e Faixa Etária:**  */
   /*Delete todos os professores com ID maior que 50 e mais de 55 anos de idade.*/
SELECT * FROM tb_professores;
DELETE FROM tb_professores WHERE pro_id > 50 AND (YEAR('2024-09-01') - YEAR(pro_data_nascimento)) > 55;
```
