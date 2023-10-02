# BancoDeDadosMySQL
## Descrição
Atividades solicitadas em sala de aula para avaliaçao.
## ETAPA 1:
 Crie uma tabela Produtos com os seguintes itens id_produto, nome, preço,
 estoque, perecível, marca, nacionalidade.
 Atribua a cada campo seu respectivo tipo;
 Os itens: nome; preço; estoque; perecível não poderão receber valores nulos;
 O id_produto deve ser utilizado como chave-primaria.

 ![exer1](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2%20Tabela.png)
 
/*Após a criação insira cinco produtos, todos devem ter seus respectivos campos
preenchidos;

![exer2](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2%20ProdutosAtributos.png)

Verifique se todos os dados foram inseridos;

![exer3](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2%20ProdutosDescricaoBusca.png)

## ETAPA 2:
/*Gere um relatório informando quantos produtos estão cadastrados*/

SELECT COUNT(*) FROM Produtos;

![exer4](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2%20ProdutosRelatorio.png)

/*Gere um relatório informando o preço médio dos produtos*/

	SELECT AVG(preco) as "preco_media" FROM Produtos;

![exer5](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2%20ProdutosPMedio.png)

/*Selecione a média dos preços dos produtos em 2 grupos: perecíveis e não
perecíveis*/
	
	SELECT perecivel, AVG(preco) AS "media_precos"
	FROM Produtos
	GROUP BY perecivel;

![exer6](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2ProdutosPereciveis.png)

/*Selecione a média dos preços dos produtos agrupados pelo nome do produto*/

	SELECT nome, AVG(preco) AS "media_precos"
	FROM Produtos
	GROUP BY nome;

![exer7](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2ProdutosNomeMedia.png)

/*Selecione a média dos preços e total em estoque dos produtos*/

	SELECT AVG(preco) AS media_precos, SUM(estoque) AS "total_estoque"
	FROM Produtos;

![exer8](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2ProdutosMediaTotal.png)

/*Selecione o nome, marca e quantidade em estoque do produto mais caro*/

	SELECT nome, marca, estoque, MAX(preco) AS "produto_mais_caro"
	FROM Produtos; 

![exer9]()
 
/*Selecione os produtos com preço acima da média*/

	SELECT nome, preco FROM Produtos
	WHERE preco > (SELECT AVG(preco) FROM Produtos);

![exer10](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2ProdutosAcimaMedia.png)

/*Selecione a quantidade de produtos de cada nacionalidade*/

	SELECT COUNT(nacionalidade) AS "quantidade_produto_cada_nacionalidade"
	FROM Produtos;	

 ![exer11](https://github.com/Ig0rFA/BancoDeDadosMySQL/blob/main/AC2%20Print/AC2ProdutosPNacionalidade.png)

 
