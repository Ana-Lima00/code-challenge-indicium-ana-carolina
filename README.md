Relatório desafio de Código:
Por Ana Carolina de Lima Macedo

Resolução do desafio de código Indicium para Desenvolvedor de Software:

Na criação de um pipeline de dados, optei pelo Airflow, uma ferramenta eficaz para descrever, executar e monitorar fluxos de trabalho.
O pipeline aborda três tarefas essenciais:
1. Extração de Dados do PostgreSQL para o Disco Local:
   - Estabelece conexão com o PostgreSQL, extrai dados e os armazena em arquivos CSV locais.
   - Cada tabela gera um arquivo próprio, organizado em uma estrutura de diretórios por fonte, tabela e data de execução.
2. Cópia do Arquivo CSV para o Disco Local:
   - A organização do arquivo segue uma estrutura de diretórios baseada na data de execução.
3. Extração, Transformação e Carregamento no MongoDB:
   - Extrai dados dos arquivos CSV locais representando pedidos, produtos, clientes e detalhes do pedido.
   - Transforma os dados, unindo tabelas e organizando em formato JSON compatível com o MongoDB.
   - Carrega os dados transformados no MongoDB, facilitando recuperação e análise.

O pipeline é configurado em um DAG, e agendado para execução diária. 

A solução é containerizada usando o Docker para simplificar implantação e gestão, enquanto o Docker Compose configura o ambiente de forma direta.

Oferecendo uma abordagem eficaz escolhi implementar as tarefas em Python. A Tarefa 3 adota o formato JSON para facilitar a apresentação de detalhes do pedido com a lista de produtos aos desenvolvedores front-end.
