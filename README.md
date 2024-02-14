Relatório desafio de Código:
Por Ana Carolina de Lima Macedo

Resolução do desafio de código Indicium para Desenvolvedor de Software:

Para atingir o objetivo do desafio, optei por utilizar o Airflow, uma ferramenta projetada para descrever, executar e monitorar fluxos de trabalho.

O pipeline em questão possui três tarefas principais:
1. Extrair dados do banco de dados Postgres e armazená-los no disco local.
2. Extrair dados de um arquivo CSV e gravá-los no disco local.
3. Extrair dados do sistema de arquivos local, transformá-los e carregá-los no banco de dados final.

Cada uma dessas tarefas foi implementada por meio de scripts em Python:
- Tarefa 1: Estabelece conexão com o Banco de Dados Postgres, obtém os nomes de todas as tabelas e escreve os dados em um arquivo local, indicando o caminho para cada fonte, tabela e dia de execução.
- Tarefa 2: Copia o conteúdo do arquivo CSV e o escreve em um arquivo local, especificando o caminho para cada fonte, tabela e dia de execução.
- Tarefa 3: Extrai dados locais, realiza junções entre tabelas e salva o resultado em formato JSON no banco de dados Mongo. A escolha pelo formato JSON foi feita devido à possibilidade de listar produtos do mesmo pedido no mesmo JSON, facilitando para um desenvolvedor front-end caso deseje apresentar os detalhes do pedido com a lista de produtos.

Além disso, optei por containerizar minha solução utilizando o Docker. Após configurar o código, é viável testar tarefas isoladas ou o pipeline completo em datas passadas.