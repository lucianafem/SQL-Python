# How create table in SQL

	CREATE TABLE Dados1(
	Id int IDENTITY(1, 1) PRIMARY KEY,    
	Nome varchar(200) NOT NULL,
	Idade INT NOT NULL); 

	INSERT INTO Dados1(Nome,Idade)
	VALUES
	('Ana Maria Delgado',23),
	('Ricardo Ferreira',33),
	('Fabio Souza',25),
	('Washigton Martins', 45),
	('Patricia Morgado',34),
	('Joana Gouveia',56),
	('Laura Nunes Duarte',78),
	('Fernanda Faria Araújo',45),
	('Maurício José Marcolino',34),
	('Alex Vilela', 32),
	('Diogo Siqueira Cruz',55),
	('Sérgio Aureliano',65),
	('Alessandro Barroso',14),
	('Carlos Amadeu dos Santos',57),
	('Vanessa Machado', 25);

	CREATE TABLE Dados2(
	Id int IDENTITY(1, 1) PRIMARY KEY,    
	Nome varchar(200) NOT NULL,
	Idade INT NOT NULL); 

	INSERT INTO Dados2(Nome,Idade)
	VALUES
	('Durvalina Joana Rego',67),
	('Priscila Bernardes',38),
	('Eliana Jurema',33),
	('Ana Mariana Riana',45),
	('Aparecida Risoli',55),
	('Carina Sueli Morgado',14),
	('André Richtofen',67),
	('Daniele Sobrinha',45),
	('Stéphane Pacheco',22),
	('Célia de Jesus Cruz',41),
	('Regina Papua',34),
	('Francisco Constantino',37),
	('Pedro Araújo',39),
	('Regiane Pereira',50),
	('Alessandro Barroso',14),
	('Carlos Amadeu dos Santos',57),
	('Carina Sueli Morgado',14);
	
	SELECT * 
	FROM Dados1
	SELECT * 
	FROM Dados2

	SELECT Nome,Idade
	INTO Dados3
	FROM ( 
	SELECT Nome,Idade
	FROM Dados1
	UNION
	SELECT Nome,Idade
	FROM Dados2) AS Dados33

	SELECT Nome,Idade
    	INTO Dados4
	FROM Dados3
	WHERE Idade NOT IN(             
	SELECT Idade
	FROM Dados3
	GROUP BY Idade
	HAVING COUNT(*) =1)  
	
	SELECT * 
	FROM Dados4
	ORDER BY Idade
