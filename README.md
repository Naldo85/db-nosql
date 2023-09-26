# db-nosql
## O que é NoSQL e para que serve?
- NoSQL (Not Only SQL) é um termo usado para bancos de dados não relacionais de alto desempenho, onde o SQL geralmente não é usado como linguagem de consulta. 
O NoSQL foi criado para ter melhor desempenho e maior escalabilidade horizontal para a ineficácia dos bancos de dados relacionais.

## Terminologias no MongoDB
#### Base de dados
- O banco de dados é um contêiner físico para coleções.

#### Coleção
- Coleção é um grupo de documentos do MongoDB. É o equivalente a uma tabela RDBMS.

#### Documento
- Um documento é um conjunto de pares de valores-chave. Os documentos têm esquema dinâmico

## Comparação com os nomes usados em SQL
| SQL  | NoSQL(MongoDB) |
| ------------- | ------------- |
| RDBMS  | MongoDB |
| Banco de Dados | Banco de Dados |
| Tabela | Coleção |
| Linha | Documento |
| Coluna | Campo |
| Junção de tabela | Documentos incorporados |
| Chave Primária | Chave Primária (chave padrão _id fornecida pelo próprio mongodb) |
| mysqld/oracle | mongod |
| mysql/sqlplus | mongo |

## Principais comandos NoSQL
### bancos de dados (databases)
```
show dbs - lista todos os bancos de dados, o alias desse comando é show databases;

use [nome-do-banco] - selecionar um banco de dados, ex.: use admin;

db - verifica qual o banco de dados em uso no momento;

use terminalroot - cria um banco de dados, mas só passa a existir efetivamente quando você 
cria uma collection e insere algum dado nela, se não o mesmo não estará disponível quando você listar os bancos, deixará de existir;

db.dropdatabase() - apaga um banco de dados, usar após selecionar use nome-do-banco que deseja;
```

### collections (tabelas)
```
show collections - Mostra as collections;

createcollection() - Cria uma collection, protótipo dela é createcollection("nomedatabela", 
opções), exemplo: db.createcollection("minhacolecao").

db.nome_da_colecao.find().pretty() - Ler todos os dados de uma coleção, ex.: db.system.users.find().pretty() , ler todos os dados da coleção system.users, equivalente à 
select * from tabela. essa saída sairá formatada, se quiser os dados numa única linha, use sem o método .pretty(): db.system.users.find();

db.nome_da_colecao.insert() - Insere dados numa coleção, ex.: db.minhacolecao.insert( { "_id" : 0, "site" : "terminal root", "url" : "terminalroot.com.br", "content" : "sobre mongodb" } );

db.nome_da_colecao.update(consulta, o_que_atualizar, opções) - Atualiza(update) dados em um documento(campo), ex.: db.minhacolecao.update({'content':'sobre mongodb'},{$set:{'content':'mongodb definitivo'}}), altera o documento de nome content que tem o valor: sobre mongodb por mongodb definitivo;

db.nome_da_colecao.drop() - Deleta uma coleção, ex.: db.minhacolecao.drop(), deleta a coleção minhacolecao.

db.dados.remove({"mail": "scleinaldo@yahoo.com"}) - Remove um documento( linha em SQL ) que possui uma coluna( campo em SQL ) mail igual à scleinaldo@yahoo.com.
```
