## Como Executar

Execultar a classe SpringBootApplicationConfig para iniciar a aplicação

[source,java,indent=0]
----
	package com.greenmile;

	import org.springframework.boot.SpringApplication;
	import org.springframework.boot.autoconfigure.SpringBootApplication;

	@SpringBootApplication
	public class SpringBootApplicationConfig {
	
		public static void main(String[] args) {
			SpringApplication.run(SpringBootApplicationConfig.class, args);
		}
	}
	
----


## Sobre o desafio

Especificação do desafio:

Criar uma aplicação que realize importação de arquivos.

Gerentes de projeto poderão importar dados do seu time de desenvolvimento, e a partir daí manipulá-los.

A API deve conter endpoints para realizar as seguintes ações:

1. Usuários
1.1 Cadastro de usuários

2. Projetos
2.1 Cadastro de Projetos
2.2 Listar projetos (Contendo os usuários envolvidos)
2.3 Arquivar projetos

3. Associação de usuários a projetos

4. Importação de projetos
4.1 Importação de projetos através de arquivos CSV

Segue em anexo, arquivo que poderá ser utilizado como exemplo para importação de projetos, todos os arquivos que serão testados seguem esse formato.

* Cada projeto só poderá ter um Gerente de projetos.
* Durante a atribuição de um usuário a um projeto é necessário informar a função que será exercida.

Considerações:

* Aplicação client-side não é um requisito, mas se quiser fazer, fique a vontade.
* Deverão ser utilizados: Spring Boot e Spring Batch.
* Você poderá definir a flexibilidade e as limitações dessa API de consulta.
* Você pode utilizar qualquer base de dados e qualquer solução de cache.
* Consistência eventual não é um problema.
* Testes são extremamente importantes.

## Solução do desafio

O desafio foi resolvida de acordo com as informações passadas, utilizando o Spring Boot e Spring Batch.
O Spring Batch foi utilizado como um job que é executado toda vez que a aplicação é executada.
O Spring Batch é responsavel por ler o arquivo .csv que está no resource da aplicação e grava os dados na base de dados da seguinte forma: para cada linha do csv é verificado se o projeto já existe na base de dados senão é criado um projeto e uma lista de usuários que faz parte daquele projeto
O banco de dados utilizado para aplicação foi o h2database que em tempo de execução cria as tabelas de acordo com as entidades mapiadas
