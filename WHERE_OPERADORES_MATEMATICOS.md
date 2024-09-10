# WHERE+OPERADORES (LÓGICOS, MATEMÁTICOS, IN, NOT IN, LIKE) + ORDER BY:

```MySQL
CREATE DATABASE DB_ATIVIDADE6;
USE DB_ATIVIDADE6;
CREATE TABLE  tb_alunos  (
   alu_id  int(11) NOT NULL AUTO_INCREMENT,
   alu_nome  varchar(100) NOT NULL,
   alu_data_nascimento  date NOT NULL,
   alu_genero  enum('M','F','Outro') NOT NULL,
   alu_rua  varchar(100) DEFAULT NULL,
   alu_numero  int(11) DEFAULT NULL,
   alu_complemento  varchar(100) DEFAULT NULL,
   alu_bairro  varchar(100) DEFAULT NULL,
   alu_cidade  varchar(100) DEFAULT NULL,
   alu_estado  varchar(50) DEFAULT NULL,
   alu_cep  varchar(10) DEFAULT NULL,
   alu_email  varchar(100) DEFAULT NULL,
   alu_telefone  varchar(20) DEFAULT NULL,
   alu_data_matricula  date NOT NULL,
  PRIMARY KEY ( alu_id )
);
INSERT INTO  tb_alunos  VALUES 
(1,'Leonardo DiCaprio','1974-11-11','M','Hollywood Blvd',123,'Apt 45','Hollywood','Los Angeles','CA','90028','leonardo@example.com','555-1234','2023-08-01' ),
(2,'Beyoncé Knowles','1981-09-04','F','Main St',456,'','Downtown','Houston','TX','77002','beyonce@example.com','555-5678','2023-08-02' ),
(3,'Cristiano Ronaldo','1985-02-05','M','Rua da Bola',789,'Bloco B','Centro','Funchal','Madeira','9000-001','cristiano@example.com','555-9101','2023-08-03' ),
(4,'Scarlett Johansson','1984-11-22','F','Broadway',101,'','Manhattan','New York','NY','10001','scarlett@example.com','555-1122','2023-08-04' ),
(5,'Robert Downey Jr.','1965-04-04','M','Palm Dr',202,'Suite 10','Beverly Hills','Los Angeles','CA','90210','robert@example.com','555-1314','2023-08-05' ),
(6,'Taylor Swift','1989-12-13','F','Music Ave',303,'Floor 3','Nashville','Nashville','TN','37201','taylor@example.com','555-1516','2023-08-06' ),
(7,'Lionel Messi','1987-06-24','M','Calle Futbol',404,'','Rosario','Santa Fe','','2000','lionel@example.com','555-1718','2023-08-07' ),
(8,'Jennifer Lawrence','1990-08-15','F','Oak St',505,'','Indian Hills','Louisville','KY','40207','jennifer@example.com','555-1920','2023-08-08' ),
(9,'Will Smith','1968-09-25','M','Sunset Blvd',606,'Villa 12','Bel Air','Los Angeles','CA','90077','will@example.com','555-2122','2023-08-09' ),
(10,'Emma Watson','1990-04-15','F','Queen St',707,'Flat 7B','London','London','','W1','emma@example.com','555-2324','2023-08-10' ),
(11,'Angelina Jolie','1975-06-04','F','Sunset Blvd',123,'Apt 12','Hollywood','Los Angeles','CA','90028','angelina@example.com','555-1234','2023-08-01' ),
(12,'Brad Pitt','1963-12-18','M','Mulholland Dr',456,'','Hollywood','Los Angeles','CA','90068','brad@example.com','555-5678','2023-08-02' ),
(13,'Madonna','1958-08-16','F','5th Ave',789,'Penthouse','Manhattan','New York','NY','10001','madonna@example.com','555-9101','2023-08-03' ),
(14,'Tom Cruise','1962-07-03','M','Mission St',101,'','Beverly Hills','Los Angeles','CA','90210','tom@example.com','555-1122','2023-08-04' ),
(15,'Rihanna','1988-02-20','F','Ocean Dr',202,'','Bridgetown','Bridgetown','','BB','rihanna@example.com','555-1314','2023-08-05' ),
(16,'Ed Sheeran','1991-02-17','M','Castle St',303,'Flat 3','Framlingham','Suffolk','','IP13','ed@example.com','555-1516','2023-08-06' ),
(17,'Lady Gaga','1986-03-28','F','Broadway',404,'','Manhattan','New York','NY','10001','gaga@example.com','555-1718','2023-08-07' ),
(18,'Justin Bieber','1994-03-01','M','Maple St',505,'','Stratford','Ontario','','N5A','justin@example.com','555-1920','2023-08-08' ),
(19,'Katy Perry','1984-10-25','F','Hollywood Blvd',606,'','Hollywood','Los Angeles','CA','90028','katy@example.com','555-2122','2023-08-09' ),
(20,'Chris Hemsworth','1983-08-11','M','Bondi Beach',707,'House 7','Sydney','New South Wales','','2026','chris@example.com','555-2324','2023-08-10' ),
(21,'Jennifer Lopez','1969-07-24','F','Bronx St',808,'','Bronx','New York','NY','10453','jennifer@example.com','555-2526','2023-08-11' ),
(22,'Keanu Reeves','1964-09-02','M','Reeves Dr',909,'','Toronto','Ontario','','M4C','keanu@example.com','555-2728','2023-08-12' ),
(23,'Gal Gadot','1985-04-30','F','Wonder Woman Ave',1010,'','Rosh HaAyin','','','48805','gal@example.com','555-2930','2023-08-13' ),
(24,'Michael Jordan','1963-02-17','M','Champion St',1111,'','Charlotte','North Carolina','NC','28202','michael@example.com','555-3132','2023-08-14' ),
(25,'LeBron James','1984-12-30','M','King Blvd',1212,'','Akron','Ohio','OH','44301','lebron@example.com','555-3334','2023-08-15' ),
(26,'Adele','1988-05-05','F','Rolling St',1313,'','Tottenham','London','','N15','adele@example.com','555-3536','2023-08-16' ),
(27,'Johnny Depp','1963-06-09','M','Pirates Cove',1414,'','Owensboro','Kentucky','KY','42301','johnny@example.com','555-3738','2023-08-17' ),
(28,'Selena Gomez','1992-07-22','F','Selena St',1515,'','Grand Prairie','Texas','TX','75050','selena@example.com','555-3940','2023-08-18' ),
(29,'Hugh Jackman','1968-10-12','M','Wolverine Rd',1616,'','Sydney','New South Wales','','2000','hugh@example.com','555-4142','2023-08-19' ),
(30,'Dwayne Johnson','1972-05-02','M','Rock St',1717,'','Hayward','California','CA','94541','dwayne@example.com','555-4344','2023-08-20' ),
(31,'Shakira','1977-02-02','F','Hips St',1818,'','Barranquilla','Atlántico','','080001','shakira@example.com','555-4546','2023-08-21' ),
(32,'Mark Zuckerberg','1984-05-14','M','Facebook Ave',1919,'','Palo Alto','California','CA','94301','mark@example.com','555-4748','2023-08-22' ),
(33,'Elon Musk','1971-06-28','M','SpaceX Rd',2020,'','Pretoria','Gauteng','','0002','elon@example.com','555-4950','2023-08-23' ),
(34,'Bill Gates','1955-10-28','M','Microsoft Way',2121,'','Seattle','Washington','WA','98109','bill@example.com','555-5152','2023-08-24' ),
(35,'Oprah Winfrey','1954-01-29','F','Harpo St',2222,'','Kosciusko','Mississippi','MS','39090','oprah@example.com','555-5354','2023-08-25' ),
(36,'Meghan Markle','1981-08-04','F','Royal Ave',2323,'','Los Angeles','California','CA','90001','meghan@example.com','555-5556','2023-08-26' ),
(37,'Prince Harry','1984-09-15','M','Palace Rd',2424,'','London','','','SW1A','harry@example.com','555-5758','2023-08-27' ),
(38,'Serena Williams','1981-09-26','F','Tennis Ct',2525,'','Saginaw','Michigan','MI','48601','serena@example.com','555-5960','2023-08-28' ),
(39,'Novak Djokovic','1987-05-22','M','Ace Blvd',2626,'','Belgrade','','','11000','novak@example.com','555-6162','2023-08-29' ),
(40,'Usain Bolt','1986-08-21','M','Sprint St',2727,'','Sherwood Content','Trelawny','','','usain@example.com','555-6364','2023-08-30');

/*1. Liste todos os alunos do estado da Califórnia (CA).*/
select * from tb_alunos where alu_cidade='California';

/*2. Liste todos os alunos que moram em Los Angeles e são do gênero masculino.*/
select * from tb_alunos where alu_cidade='Los Angeles' and alu_genero='M';

/*3. Liste todos os alunos cujo número da residência seja maior que 500.*/
select * from tb_alunos where alu_numero>500;

/*4. Liste todos os alunos que moram em Nova York, Los Angeles ou Houston.*/
select * from tb_alunos where alu_cidade='Nova York' or alu_cidade='Los Angeles' or alu_cidade='Houston';

/*5. Liste todos os alunos que não moram em Nova York, Los Angeles ou Houston.*/
select * from tb_alunos where alu_cidade!='Nova York' and alu_cidade!='Los Angeles' and alu_cidade!='Houston';

/*6. Encontre todos os alunos cujos nomes começam com a letra 'J'.*/
select * from tb_alunos where alu_nome like 'J%';

/*7. Liste todos os alunos ordenados por data de matrícula em ordem decrescente.*/
select * from tb_alunos where alu_data_matricula order by alu_data_matricula desc;

/*8. Liste todos os alunos do gênero feminino cujo número de residência seja menor que 500.*/
select * from tb_alunos where alu_genero='F' and alu_numero<500;

/*9. Liste todos os alunos que moram em cidades que começam com "L" ou "B" e que estão nos estados de Califórnia ou Nova York.*/
select * from tb_alunos where (alu_cidade like 'L%' or alu_cidade like 'B%') and (alu_estado='CA' or alu_estado='NY');

/*10. Liste todos os alunos que não moram em Los Angeles ou Nova York, ordenados por nome em ordem alfabética.*/
select * from tb_alunos where alu_cidade!='Los Angeles' and alu_cidade!='Nova York' order by alu_nome;

/*11. Encontre todos os alunos do gênero masculino cujo email contém "example.com".*/
select * from tb_alunos where alu_genero='M' and alu_email like '%example.com';

/*12. Liste todos os alunos que moram em Los Angeles, Nova York ou Houston e cujo número de residência seja maior que 100.*/
select * from tb_alunos where (alu_cidade='Los Angeles' or alu_cidade='Nova York' or alu_cidade='Houston') and alu_numero>100;

/*13. Liste todos os alunos que se matricularam em 2023, ordenados pela data de nascimento.*/
select * from tb_alunos where alu_data_matricula like '2023%' order by alu_data_nascimento;

/*14. Liste todos os alunos do gênero feminino que não moram em Califórnia, Nova York ou Texas.*/
select * from tb_alunos where alu_genero='F' and (alu_cidade!='Califórnia' and alu_cidade!='Nova York' and alu_cidade!='Texas');

/*15. Liste todos os alunos do gênero masculino cujo nome começa com "L", o número da residência seja maior que 100, e moram na Califórnia.*/
select * from tb_alunos where alu_genero='M' and alu_nome like 'L%' and alu_numero>100 and alu_cidade='Califórnia';

/*16. Liste todos os alunos que moram em cidades que começam com "S" ou "H", estão nos estados da Califórnia ou Nova York, e ordene os resultados pelo nome em ordem decrescente.*/
select * from tb_alunos where alu_cidade like 'S%' and alu_cidade like 'H%' and (alu_estado='CA' or alu_estado='NY') order by alu_nome desc;

/*17. Liste todos os alunos do gênero feminino que moram em Nova York ou Los Angeles e cujo número de residência seja menor que 500.*/
select * from tb_alunos where alu_genero='F' and (alu_cidade='Nova York' or alu_cidade='Los Angeles') and alu_numero<500;

/*18. Liste todos os alunos que não moram em Texas, Califórnia ou Nova York, e que tenham se matriculado em 2023, ordenados pela data de matrícula em ordem crescente.*/
select * from tb_alunos where (alu_cidade!='Texas' and alu_cidade!='Califórnia' and alu_cidade!='Nova York') and alu_data_matricula like '2023%' order by alu_data_matricula;

/*19. Liste todos os alunos que moram na Califórnia ou Nova York, cujos nomes contêm "a", e que se matricularam após 1º de agosto de 2023.*/
select * from tb_alunos where (alu_cidade='Califórnia' or alu_cidade='Nova York') and alu_nome like '%a%' and alu_data_matricula>'2023-08-01';

/*20. Liste todos os alunos do gênero feminino que não moram em Nova York, mas cujo nome começa com "J" e possuem um complemento no endereço.*/
select * from tb_alunos where alu_genero='F' and alu_cidade!='Nova York' and alu_nome like 'J%' and alu_complemento like '%';

/*21. Liste todos os alunos do gênero masculino que se matricularam em 2023, cujo número de residência seja menor que 1000, e ordene os resultados pela data de nascimento em ordem crescente.*/
select * from tb_alunos where alu_genero='M' and alu_data_matricula like '2023%' and alu_numero<1000 order by alu_data_nascimento;
```
