# BancoDeDadosMySQL
## Descrição
Atividades solicitadas em sala de aula para avaliaçao.
## ETAPA 1:
 Crie uma tabela Produtos com os seguintes itens id_produto, nome, preço,
 estoque, perecível, marca, nacionalidade.
 Atribua a cada campo seu respectivo tipo;
 Os itens: nome; preço; estoque; perecível não poderão receber valores nulos;
 O id_produto deve ser utilizado como chave-primaria.


 ![exer1]()
 
/*Após a criação insira cinco produtos, todos devem ter seus respectivos campos
preenchidos;
Verifique se todos os dados foram inseridos;
Ao término inicie a segunda etapa.*/

INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('sabonete', 5.00, 8, 'N','Jhonson','Brasileira');

INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('shampoo', 9.00, 14, 'N','Jhonson','Brasileira');
	
INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('leite', 4.90, 32, 'S','Hercules','Brasileira');

INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('refrigerante', 3.50, 4, 'S','coca-cola','Brasileira');

INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('esponja de aco', 1.50, 22, 'N','Bombril','Brasileira');

![exer2]()

![exer3]()

## ETAPA 2:
/*Gere um relatório informando quantos produtos estão cadastrados*/

SELECT COUNT(*) FROM Produtos;

![exer4]()

/*Gere um relatório informando o preço médio dos produtos*/

	SELECT AVG(preco) as "preco_media" FROM Produtos;

![exer5]()

/*Selecione a média dos preços dos produtos em 2 grupos: perecíveis e não
perecíveis*/
	
	SELECT perecivel, AVG(preco) AS "media_precos"
	FROM Produtos
	GROUP BY perecivel;

![exer6]()

/*Selecione a média dos preços dos produtos agrupados pelo nome do produto*/

	SELECT nome, AVG(preco) AS "media_precos"
	FROM Produtos
	GROUP BY nome;

![exer7]()

/*Selecione a média dos preços e total em estoque dos produtos*/

	SELECT AVG(preco) AS media_precos, SUM(estoque) AS "total_estoque"
	FROM Produtos;

![exer8]()

/*Selecione o nome, marca e quantidade em estoque do produto mais caro*/

	SELECT nome, marca, estoque, MAX(preco) AS "produto_mais_caro"
	FROM Produtos; 

![exer9]()
 
/*Selecione os produtos com preço acima da média*/

	SELECT nome, preco FROM Produtos
	WHERE preco > (SELECT AVG(preco) FROM Produtos);

![exer10]()

/*Selecione a quantidade de produtos de cada nacionalidade*/

	SELECT COUNT(nacionalidade) AS "quantidade_produto_cada_nacionalidade"
	FROM Produtos;	

 ![exer11]()

 
