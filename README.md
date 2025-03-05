# Desafio de Engenharia de dados da PEV

[Link do arquivo para rodar no colab](https://colab.research.google.com/drive/1YwJURtuzFSZomAnMlkEvcCjwgXBlEqcf?usp=sharing)

[Link do repositório no GitHub](https://github.com/ryguigas0/desafio-pev)

## Desenvolvimento

### Planejamento
Primeiramente li [os requisitos do projeto](https://docs.google.com/document/d/1TziXLKoH70efao7-VQbiRzhAyuKtKQ68PPqtkPXML5I/edit?tab=t.0) e montei a lista de tarefas abaixo:

1. [ ] Criar o arquivo do colab
2. [ ] Usar o apache mais recente ([link](https://spark.apache.org/downloads.html))
3. [ ] Raspagem de dados por web scrapping
	1. [ ] Acesse a página https://www.worldometers.info/world-population/population-by-country/
	2. [ ] Extraia os dados
		1. [ ] País
		2. [ ] População 2024
		3. [ ] Variação populacional (%) - Yearly Exchange
	3. [ ] Armazene os dados em dataframe pandas
	4. [ ] Salve o dataframe em um arquivo csv com nome `populacao_paises.csv`
4. [ ] Processamento de dados com spark, o código deve ser executado em ambiente local sem necessidade de cluster distribuído
	1. [ ] Carregue o csv pra um spark dataframe
	2. [ ] Remova países com populacao inferior a 1 milhão de habitantes
	3. [ ] Crie uma nova coluna chamada "População em 2030", estimando o crescimento populacional com base na variação percentual, considerando a taxa de crescimento constante
	4. [ ] Salve o resultado final em um arquivo parquet, com o nome `populacao_paises_processado.parquet`
5. [ ] Explique sua abordagem e quais desafios enfrentou no arquivo `README.md`
6. [ ] Envio do projeto
	1. [ ] Zipe o repositório e nomeie como `resolucao_case_ed[seu-nome].zip`
	2. [ ] Envie o arquivo zip para o e-mail derek.sanches@yahoo.com até as 23h59min do dia 07/03/2025 com o título "Resolucao Case Engenharia de Dados" junto com o meu currículo, a ausência do currículo caracterizara desclassificação do candidato

Em seguida busquei em projetos anteriores o que já tinha pronto
- [Dataton na ESPM](https://colab.research.google.com/drive/1rnwvcvRZWcDWp3kTzB6kB0VjdJkSoTJu), onde fiz uma raspagem de dados de uma tabela
- [Prova da matéria de Data Lake na ESPM](https://colab.research.google.com/drive/1GyRpUScqdNNq0Hg6JcE__6oH65Rt-n9u?usp=sharing), onde fiz a leitura de dados e transformações

### Desafios durante a execução
Utilizei o Google Colab para ter maior simplicidade e unicidade de ambiente e juntei o código que já tinha e alterei informações que faltavam

Para aprender funções que eu não desconhecia, busquei na documentação oficial do Apache Spark e do Pandas:
- [Função de elevação](https://spark.apache.org/docs/latest/api/python/reference/pyspark.sql/api/pyspark.sql.functions.pow.html)
- [Split de string](https://spark.apache.org/docs/latest/api/python/reference/pyspark.sql/api/pyspark.sql.functions.split.html)
- [Cheat Sheet oficial do Pandas](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)

Para garantir que estava fazendo o cálculo corretamente, fiz a fórmula completa do crescimento de população

Eu não arredondei o dado da população de 2030 porque não estava descrito nos requisitos, logo critério vai ser de quem for utilizar essas informações

Adicionei timestamps nos arquivos para fazer o versionamento de dados da camada de ingestão (`2025-03-05_populacao_paises.csv`) e da camada de management (`2025-03-05_populacao_paises_processado.parquet`)

## Agradecimentos
Muito obrigado pela oportunidade e pela atenção!

Gostaria de podermos nos conectar no [LinkedIn](https://www.linkedin.com/in/guigadev/) e no [GitHub](https://github.com/ryguigas0)