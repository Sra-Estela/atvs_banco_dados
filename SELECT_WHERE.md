# SELECT + WHERE:

```MySQL
create database db_jogos;
use db_jogos;

CREATE TABLE atletismo_resultados (
modalidade VARCHAR(50),
prova VARCHAR(100),
posicao INT,
atleta_nome VARCHAR(100),
pais VARCHAR(50),
tempo TIME,
ano INT
);

-- Resultados das provas de atletismo nas Olimpíadas do Rio 2016
INSERT INTO atletismo_resultados (modalidade, prova, posicao, atleta_nome, pais, tempo, ano) VALUES
-- 100 Metros Rasos
('Feminino', '100 metros rasos', 1, 'Elaine Thompson', 'Jamaica', '00:10:71', 2016),
('Feminino', '100 metros rasos', 2, 'Shelly-Ann Fraser-Pryce', 'Jamaica', '00:10:86', 2016),
('Feminino', '100 metros rasos', 3, 'Tori Bowie', 'Estados Unidos', '00:10:86', 2016),
('Feminino', '100 metros rasos', 4, 'Dafne Schippers', 'Países Baixos', '00:10:89', 2016),
('Feminino', '100 metros rasos', 5, 'Marie-Josée Ta Lou', 'Costa do Marfim', '00:10:90', 2016),
('Feminino', '100 metros rasos', 6, 'Brittney Reese', 'Estados Unidos', '00:10:92', 2016),
('Feminino', '100 metros rasos', 7, 'Yarisley Silva', 'Cuba', '00:10:93', 2016),
('Feminino', '100 metros rasos', 8, 'Jodie Williams', 'Grã-Bretanha', '00:10:94', 2016),

('Masculino', '100 metros rasos', 1, 'Usain Bolt', 'Jamaica', '00:09:81', 2016),
('Masculino', '100 metros rasos', 2, 'Justin Gatlin', 'Estados Unidos', '00:09:89', 2016),
('Masculino', '100 metros rasos', 3, 'Andre De Grasse', 'Canadá', '00:09:91', 2016),
('Masculino', '100 metros rasos', 4, 'Yohan Blake', 'Jamaica', '00:09:92', 2016),
('Masculino', '100 metros rasos', 5, 'Akani Simbine', 'África do Sul', '00:09:93', 2016),
('Masculino', '100 metros rasos', 6, 'Ben Youssef Meité', 'Costa do Marfim', '00:09:94', 2016),
('Masculino', '100 metros rasos', 7, 'Asafa Powell', 'Jamaica', '00:09:95', 2016),
('Masculino', '100 metros rasos', 8, 'Jimmy Vicaut', 'França', '00:09:96', 2016),

-- 200 Metros
('Feminino', '200 metros rasos', 1, 'Elaine Thompson', 'Jamaica', '00:21:78', 2016),
('Feminino', '200 metros rasos', 2, 'Dafne Schippers', 'Países Baixos', '00:21:88', 2016),
('Feminino', '200 metros rasos', 3, 'Tori Bowie', 'Estados Unidos', '00:21:98', 2016),
('Feminino', '200 metros rasos', 4, 'Shelly-Ann Fraser-Pryce', 'Jamaica', '00:22:13', 2016),
('Feminino', '200 metros rasos', 5, 'Marie-Josée Ta Lou', 'Costa do Marfim', '00:22:15', 2016),
('Feminino', '200 metros rasos', 6, 'Jodie Williams', 'Grã-Bretanha', '00:22:20', 2016),
('Feminino', '200 metros rasos', 7, 'Asha Philip', 'Grã-Bretanha', '00:22:24', 2016),
('Feminino', '200 metros rasos', 8, 'Jenna Prandini', 'Estados Unidos', '00:22:30', 2016),

('Masculino', '200 metros rasos', 1, 'Usain Bolt', 'Jamaica', '00:19:78', 2016),
('Masculino', '200 metros rasos', 2, 'Justin Gatlin', 'Estados Unidos', '00:19:87', 2016),
('Masculino', '200 metros rasos', 3, 'Andre De Grasse', 'Canadá', '00:19:88', 2016),
('Masculino', '200 metros rasos', 4, 'Yohan Blake', 'Jamaica', '00:19:89', 2016),
('Masculino', '200 metros rasos', 5, 'Ramil Guliyev', 'Turquia', '00:19:92', 2016),
('Masculino', '200 metros rasos', 6, 'Isaac Makwala', 'Botswana', '00:19:95', 2016),
('Masculino', '200 metros rasos', 7, 'Lashawn Merritt', 'Estados Unidos', '00:19:96', 2016),
('Masculino', '200 metros rasos', 8, 'Chris Lemaitre', 'França', '00:19:98', 2016),

-- Revezamento 4x100 metros
('Feminino', 'Revezamento 4x100 metros', 1, 'Equipe Jamaica', 'Jamaica', '00:41:36', 2016),
('Feminino', 'Revezamento 4x100 metros', 2, 'Equipe Estados Unidos', 'Estados Unidos', '00:41:68', 2016),
('Feminino', 'Revezamento 4x100 metros', 3, 'Equipe Grã-Bretanha', 'Grã-Bretanha', '00:41:77', 2016),
('Feminino', 'Revezamento 4x100 metros', 4, 'Equipe Alemanha', 'Alemanha', '00:41:88', 2016),
('Feminino', 'Revezamento 4x100 metros', 5, 'Equipe França', 'França', '00:41:93', 2016),
('Feminino', 'Revezamento 4x100 metros', 6, 'Equipe Japão', 'Japão', '00:42:10', 2016),
('Feminino', 'Revezamento 4x100 metros', 7, 'Equipe Canadá', 'Canadá', '00:42:16', 2016),
('Feminino', 'Revezamento 4x100 metros', 8, 'Equipe Austrália', 'Austrália', '00:42:37', 2016),

('Masculino', 'Revezamento 4x100 metros', 1, 'Equipe Jamaica', 'Jamaica', '00:37:27', 2016),
('Masculino', 'Revezamento 4x100 metros', 2, 'Equipe Estados Unidos', 'Estados Unidos', '00:37:38', 2016),
('Masculino', 'Revezamento 4x100 metros', 3, 'Equipe Grã-Bretanha', 'Grã-Bretanha', '00:37:68', 2016),
('Masculino', 'Revezamento 4x100 metros', 4, 'Equipe Japão', 'Japão', '00:37:68', 2016),
('Masculino', 'Revezamento 4x100 metros', 5, 'Equipe Canadá', 'Canadá', '00:37:64', 2016),
('Masculino', 'Revezamento 4x100 metros', 6, 'Equipe França', 'França', '00:37:83', 2016),
('Masculino', 'Revezamento 4x100 metros', 7, 'Equipe China', 'China', '00:37:84', 2016),
('Masculino', 'Revezamento 4x100 metros', 8, 'Equipe Brasil', 'Brasil', '00:37:90', 2016),

-- Heptatlo e Decatlo
('Feminino', 'Heptatlo', 1, 'Nafissatou Thiam', 'Bélgica', '68:10:00', 2016),
('Feminino', 'Heptatlo', 2, 'Jessica Ennis-Hill', 'Grã-Bretanha', '67:40:00', 2016),
('Feminino', 'Heptatlo', 3, 'Eilidh Doyle', 'Grã-Bretanha', '67:00:00', 2016),
('Feminino', 'Heptatlo', 4, 'Anouk Vetter', 'Países Baixos', '66:70:00', 2016),
('Feminino', 'Heptatlo', 5, 'Brianne Theisen-Eaton', 'Canadá', '66:20:00', 2016),
('Feminino', 'Heptatlo', 6, 'Katarina Johnson-Thompson', 'Grã-Bretanha', '66:00:00', 2016),
('Feminino', 'Heptatlo', 7, 'Jennifer Oeser', 'Alemanha', '65:50:00', 2016),
('Feminino', 'Heptatlo', 8, 'Nadine Debois', 'França', '65:00:00', 2016),

('Masculino', 'Decatlo', 1, 'Ashton Eaton', 'Estados Unidos', '88:93:00', 2016),
('Masculino', 'Decatlo', 2, 'Kevin Mayer', 'França', '87:68:00', 2016),
('Masculino', 'Decatlo', 3, 'Damian Warner', 'Canadá', '86:00:00', 2016),
('Masculino', 'Decatlo', 4, 'Lamarcus Aldridge', 'Estados Unidos', '85:25:00', 2016),
('Masculino', 'Decatlo', 5, 'Nils Schumann', 'Alemanha', '84:99:00', 2016),
('Masculino', 'Decatlo', 6, 'Mathieu Gosselin', 'França', '84:70:00', 2016),
('Masculino', 'Decatlo', 7, 'Javier Culson', 'Puerto Rico', '84:60:00', 2016),
('Masculino', 'Decatlo', 8, 'Galen Rupp', 'Estados Unidos', '84:45:00', 2016),

-- Maratona
('Feminino', 'Maratona', 1, 'Jemima Sumgong', 'Quênia', '02:24:04', 2016),
('Feminino', 'Maratona', 2, 'Eunice Kirwa', 'Bahrain', '02:24:13', 2016),
('Feminino', 'Maratona', 3, 'Mare Dibaba', 'Etiópia', '02:24:30', 2016),
('Feminino', 'Maratona', 4, 'Tigist Tufa', 'Etiópia', '02:24:40', 2016),
('Feminino', 'Maratona', 5, 'Feyse Tadese', 'Etiópia', '02:24:50', 2016),
('Feminino', 'Maratona', 6, 'Shalane Flanagan', 'Estados Unidos', '02:25:26', 2016),
('Feminino', 'Maratona', 7, 'Amy Cragg', 'Estados Unidos', '02:27:05', 2016),
('Feminino', 'Maratona', 8, 'Jessica Trengove', 'Austrália', '02:28:59', 2016),

('Masculino', 'Maratona', 1, 'Eliud Kipchoge', 'Quênia', '02:08:44', 2016),
('Masculino', 'Maratona', 2, 'Feyisa Lilesa', 'Etiópia', '02:09:54', 2016),
('Masculino', 'Maratona', 3, 'Galen Rupp', 'Estados Unidos', '02:10:05', 2016),
('Masculino', 'Maratona', 4, 'Ghirmay Ghebreslassie', 'Eritreia', '02:11:04', 2016),
('Masculino', 'Maratona', 5, 'Alphonce Simbu', 'Tanzânia', '02:11:15', 2016),
('Masculino', 'Maratona', 6, 'Jared Ward', 'Estados Unidos', '02:11:30', 2016),
('Masculino', 'Maratona', 7, 'Cuthbert Nyasango', 'Zimbábue', '02:11:55', 2016),
('Masculino', 'Maratona', 8, 'Satoru Sasaki', 'Japão', '02:12:17', 2016),
-- 100 Metros Rasos
('Feminino', '100 metros rasos', 1, 'Elaine Thompson-Herah', 'Jamaica', '00:10:61', 2020),
('Feminino', '100 metros rasos', 2, 'Shelly-Ann Fraser-Pryce', 'Jamaica', '00:10:74', 2020),
('Feminino', '100 metros rasos', 3, 'Shericka Jackson', 'Jamaica', '00:10:76', 2020),
('Feminino', '100 metros rasos', 4, 'Marie-Josée Ta Lou', 'Costa do Marfim', '00:10:78', 2020),
('Feminino', '100 metros rasos', 5, 'Ajla Del Ponte', 'Suíça', '00:10:89', 2020),
('Feminino', '100 metros rasos', 6, 'Dina Asher-Smith', 'Grã-Bretanha', '00:10:91', 2020),
('Feminino', '100 metros rasos', 7, 'Teahna Daniels', 'Estados Unidos', '00:10:94', 2020),
('Feminino', '100 metros rasos', 8, 'Blessing Okagbare', 'Nigéria', '00:11:00', 2020),

('Masculino', '100 metros rasos', 1, 'Lamont Marcell Jacobs', 'Itália', '00:09:80', 2020),
('Masculino', '100 metros rasos', 2, 'Fred Kerley', 'Estados Unidos', '00:09:84', 2020),
('Masculino', '100 metros rasos', 3, 'Andre De Grasse', 'Canadá', '00:09:89', 2020),
('Masculino', '100 metros rasos', 4, 'Akani Simbine', 'África do Sul', '00:09:93', 2020),
('Masculino', '100 metros rasos', 5, 'Ronnie Baker', 'Estados Unidos', '00:09:95', 2020),
('Masculino', '100 metros rasos', 6, 'Zharnel Hughes', 'Grã-Bretanha', '00:10:00', 2020),
('Masculino', '100 metros rasos', 7, 'Bingtian Su', 'China', '00:10:03', 2020),
('Masculino', '100 metros rasos', 8, 'Ezechiel Kemboi', 'Quênia', '00:10:10', 2020),

-- 200 Metros
('Feminino', '200 metros rasos', 1, 'Elaine Thompson-Herah', 'Jamaica', '00:21:53', 2020),
('Feminino', '200 metros rasos', 2, 'Christine Mboma', 'Namíbia', '00:21:81', 2020),
('Feminino', '200 metros rasos', 3, 'Gabrielle Thomas', 'Estados Unidos', '00:21:87', 2020),
('Feminino', '200 metros rasos', 4, 'Shelly-Ann Fraser-Pryce', 'Jamaica', '00:21:94', 2020),
('Feminino', '200 metros rasos', 5, 'Marie-Josée Ta Lou', 'Costa do Marfim', '00:21:97', 2020),
('Feminino', '200 metros rasos', 6, 'Shaunae Miller-Uibo', 'Bahamas', '00:22:05', 2020),
('Feminino', '200 metros rasos', 7, 'Jenna Prandini', 'Estados Unidos', '00:22:30', 2020),
('Feminino', '200 metros rasos', 8, 'Dina Asher-Smith', 'Grã-Bretanha', '00:22:40', 2020),

('Masculino', '200 metros rasos', 1, 'Andre De Grasse', 'Canadá', '00:19:62', 2020),
('Masculino', '200 metros rasos', 2, 'Kenneth Bednarek', 'Estados Unidos', '00:19:68', 2020),
('Masculino', '200 metros rasos', 3, 'Noah Lyles', 'Estados Unidos', '00:19:74', 2020),
('Masculino', '200 metros rasos', 4, 'Joseph Fahnbulleh', 'Libéria', '00:19:98', 2020),
('Masculino', '200 metros rasos', 5, 'Aaron Brown', 'Canadá', '00:20:10', 2020),
('Masculino', '200 metros rasos', 6, 'Rasheed Dwyer', 'Jamaica', '00:20:21', 2020),
('Masculino', '200 metros rasos', 7, 'Azael Rodríguez', 'República Dominicana', '00:20:30', 2020),
('Masculino', '200 metros rasos', 8, 'Shawn Crawford', 'Estados Unidos', '00:20:40', 2020),

-- Revezamento 4x100 metros
('Feminino', 'Revezamento 4x100 metros', 1, 'Equipe Jamaica', 'Jamaica', '00:41:02', 2020),
('Feminino', 'Revezamento 4x100 metros', 2, 'Equipe Estados Unidos', 'Estados Unidos', '00:41:45', 2020),
('Feminino', 'Revezamento 4x100 metros', 3, 'Equipe Grã-Bretanha', 'Grã-Bretanha', '00:41:88', 2020),
('Feminino', 'Revezamento 4x100 metros', 4, 'Equipe Suíça', 'Suíça', '00:42:05', 2020),
('Feminino', 'Revezamento 4x100 metros', 5, 'Equipe Alemanha', 'Alemanha', '00:42:20', 2020),
('Feminino', 'Revezamento 4x100 metros', 6, 'Equipe Brasil', 'Brasil', '00:42:30', 2020),
('Feminino', 'Revezamento 4x100 metros', 7, 'Equipe Nigéria', 'Nigéria', '00:42:50', 2020),
('Feminino', 'Revezamento 4x100 metros', 8, 'Equipe Japão', 'Japão', '00:42:60', 2020),

('Masculino', 'Revezamento 4x100 metros', 1, 'Equipe Itália', 'Itália', '00:37:50', 2020),
('Masculino', 'Revezamento 4x100 metros', 2, 'Equipe Grã-Bretanha', 'Grã-Bretanha', '00:37:51', 2020),
('Masculino', 'Revezamento 4x100 metros', 3, 'Equipe Canadá', 'Canadá', '00:37:70', 2020),
('Masculino', 'Revezamento 4x100 metros', 4, 'Equipe Jamaica', 'Jamaica', '00:37:80', 2020),
('Masculino', 'Revezamento 4x100 metros', 5, 'Equipe China', 'China', '00:37:90', 2020),
('Masculino', 'Revezamento 4x100 metros', 6, 'Equipe Alemanha', 'Alemanha', '00:38:10', 2020),
('Masculino', 'Revezamento 4x100 metros', 7, 'Equipe Brasil', 'Brasil', '00:38:20', 2020),
('Masculino', 'Revezamento 4x100 metros', 8, 'Equipe Japão', 'Japão', '00:38:30', 2020),

-- Heptatlo e Decatlo
('Feminino', 'Heptatlo', 1, 'Nafi Thiam', 'Bélgica', '67:50:00', 2020),
('Feminino', 'Heptatlo', 2, 'Anouk Vetter', 'Países Baixos', '66:30:00', 2020),
('Feminino', 'Heptatlo', 3, 'Emma Oosterwegel', 'Países Baixos', '65:20:00', 2020);

/*Selecione todos os resultados de atletas do 'Brasil'.*/
select * from atletismo_resultados where pais='Brasil';

/*Encontre os resultados dos eventos ocorridos após 2016.*/
select * from atletismo_resultados where ano>2016;

/*Busque os resultados onde o atleta tem o gênero 'F' e a prova é '100m'.*/
select * from atletismo_resultados where modalidade='Feminino' and prova='100 metros rasos';

/*Encontre os resultados onde o atleta tem o gênero 'M' ou a prova é 'Maratona'.*/
select * from atletismo_resultados where modalidade='Masculino' or (prova='Maratona');

/*Liste os resultados onde a posição é menor que 4 e a prova é 'Maratona' ou '100 metros rasos'.*/
select * from atletismo_resultados where posicao<4 and (prova='Maratona' or prova='100 metros rasos');

/*Encontre os resultados dos eventos ocorridos em 2020 e onde o país do atleta é 'Jamaica' ou 'Canadá'.*/
select * from atletismo_resultados where ano=2020 and (pais='Jamaica' or pais='Canadá');

/*Encontre os resultados onde o tempo é menor que 10 segundos e a prova é '100 metros rasos '.*/
select * from atletismo_resultados where tempo<'00:00:10' and prova='100 metros rasos ';

/*Liste os resultados de atletas do país 'França' que competiram em 2020 e cuja posição é menor que 8.*/
select * from atletismo_resultados where pais='França' and ano=2020 and posicao<8;

/*Busque todos os resultados onde o atleta tem o gênero 'Feminino' ou a prova é 'Revezamento 4x100 metros', e a posição é menor que 4.*/
select * from atletismo_resultados where (modalidade='Feminino' or prova='Revezamento 4x100 metros') and posicao<4;

/*Encontre os resultados onde o país do atleta é diferente de 'China' ou 'Brasil', e a posição é entre 1 e 3.*/
select * from atletismo_resultados where (pais!='China' or pais!='Brasil') and posicao between 1 and 3;

/*Selecione todos os resultados onde o atleta é 'Nadine Debois' ou 'Usain Bolt', que competiram em eventos diferentes de '200 metros rasos' e 'Revezamento 4x100 metros'.*/
select * from atletismo_resultados where (atleta_nome='Nadine Debois' or atleta_nome='Usain Bolt') and (prova!='200 metros rasos' and prova!='Revezamento 4x100 metros');

/*Liste todos os resultados onde a prova é 'Decatlo'  e o atleta tem o gênero 'Masculino', e a posição é menor que 8.*/
select * from atletismo_resultados where prova='Decatlo' and  modalidade='Masculino' and posicao<8;

/*Encontre resultados de atletas com o tempo menor que 10 segundos na prova '100 metros rasos', que competiram em 2020.*/
select * from atletismo_resultados where (tempo<'00:00:10' and prova='100 metros rasos') and ano=2020;

/*Busque os resultados onde o atleta é 'Elaine Thompson' ou 'Shelly-Ann Fraser-Pryce', que competiram em provas diferentes de  '100 metros rasos ' e '200 metros rasos ',  e a posição é menor que 5.*/
select * from atletismo_resultados where (atleta_nome='Elaine Thompson' or atleta_nome='Shelly-Ann Fraser-Pryce') and (prova!='100 metros rasos' and prova!='200 metros rasos') and posicao<5;
```
