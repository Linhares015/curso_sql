# SQL na Master: Do Básico ao Avançado 🧙‍♂️


<p align="center">
  <img src="imagens/capa.jpeg" width="500" height="300">
</p>

- Apresentação Pessoal: 

    - Nome: Tiago Linhares;
    - Cargo: Analytics Engineer;
    - Experiência: 2 anos de TI, focado em Dados;
    - [Meu Blog](https://linhares015.github.io/);
    - [Meu Linkedin](https://www.linkedin.com/in/tiago-linhares/);
    - [Meu Github](https://github.com/Linhares015);
    - [Meu Livro - Guia para se Tornar um Analista de Dados](https://www.amazon.com.br/dp/B0CDDFZMLD?ref_=cm_sw_r_mwn_dp_VT4QMG06XS904M6EEQ3A);
    - [30 Dias de Desafio SQL](https://github.com/Linhares015/desafio_sql_30_dias).

## Material usado no Curso de SQL

[Dbeaver](https://dbeaver.io/)

### Opção 1 - Docker
[Docker](https://www.docker.com/)

[Imagem Docker AdventureWorks](https://hub.docker.com/r/chriseaton/adventureworks)

[Portainer](https://linhares015.github.io/linux/2023/09/08/37.html)

### Opção 2 - SQLServer Local

[SQLServer](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads)

[Backup Adventure](https://learn.microsoft.com/pt-br/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms)

### Comandos para subir a Imagem Docker AdventureWorks

- Microsoft SQL Server: 
```bash
docker run -p 1433:1433 -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=my_password' -d chriseaton/adventureworks:latest
```
Lembrando que o user é `sa` e a senha pode mudar em `my_password`

- PostgreSQL: 
```bash
docker run -p 5432:5432 -e 'POSTGRES_PASSWORD=my_password' -d chriseaton/adventureworks:postgres
```
Lembrando que o user é `postgres` e a senha pode mudar em `my_password`


### Comandos úteis Docker

Listar as imagens:
```bash
docker images
```

Listar os containers:
```bash
docker ps -a
```

Parar um container:
```bash
docker stop <container_id>
```

Remover um container:
```bash
docker rm <container_id>
```

Remover uma imagem:
```bash
docker rmi <image_id>
```
# Tópicos do Curso

## menu
- [Introdução ao SQL](#introdução-ao-sql)
    - [O que é SQL e por que é importante?](#o-que-é-sql-e-por-que-é-importante)
        - [Definição](#definição)
        - [História Breve](#história-breve)
        - [Análise de Dados](#análise-de-dados)
        - [Desenvolvimento de Aplicações](#desenvolvimento-de-aplicações)
        - [Integração de Sistemas](#integração-de-sistemas)
    - [Visão geral dos sistemas de gerenciamento de banco de dados (DBMS)](#visão-geral-dos-sistemas-de-gerenciamento-de-banco-de-dados-dbms)
        - [Definição DBMS](#definição-dbms)
        - [Tipos de DBMS](#tipos-de-dbms)
        - [Componentes Principais de um DBMS](#componentes-principais-de-um-dbms)
    - [Principais DBMS e suas características](#principais-dbms-e-suas-características)
        - [SQL Server](#sql-server)
        - [SQLite](#sqlite)
        - [MySQL](#mysql)
        - [PostgreSQL](#postgresql)
        - [Oracle](#oracle)
        - [BigQuery](#bigquery)
        - [Redshift](#redshift)
    - [Diferença entre Cloud e On-Premises](#diferença-entre-cloud-e-on-premises)
        - [Cloud (Nuvem)](#cloud-nuvem)
        - [On-Premises](#on-premises)
- [Fundamentos do SQL](#fundamentos-do-sql)
    - [Entendendo tabelas, registros e campos](#entendendo-tabelas-registros-e-campos)
        - [Tabelas](#tabelas)
        - [Registros (ou Linhas)](#registros-ou-linhas)
        - [Campos (ou Colunas)](#campos-ou-colunas)
    - [Tipos de dados](#tipos-de-dados)
        - [Tipos Numéricos](#tipos-numéricos)
        - [Tipos de Caracteres](#tipos-de-caracteres)
        - [Tipos de Data e Hora](#tipos-de-data-e-hora)
        - [Tipos Lógicos](#tipos-lógicos)
        - [Tipos de Dados Binários](#tipos-de-dados-binários)
        - [Tipos de Dados Espaciais (para bancos de dados que suportam GIS)](#tipos-de-dados-espaciais-para-bancos-de-dados-que-suportam-gis)
        - [Tipos de Dados JSON (em DBMSs modernos)](#tipos-de-dados-json-em-dbmss-modernos)
        - [Tipos de Dados XML (em alguns DBMSs)](#tipos-de-dados-xml-em-alguns-dbmss)
        - [Outros Tipos](#outros-tipos)
    - [Comandos básicos](#comandos-básicos)
        - [SELECT](#select)
        - [FROM](#from)
        - [WHERE](#where)
        - [ORDER BY](#order-by)
        - [GROUP BY](#group-by)
    - [Filtragem](#filtragem)
        - [Operadores de Comparação](#operadores-de-comparação)
        - [Operadores Lógicos](#operadores-lógicos)
        - [Operadores de Existência](#operadores-de-existência)
        - [Operadores de Conjunto (usados em subconsultas)](#operadores-de-conjunto-usados-em-subconsultas)
    - [Ordenação](#ordenação)
        - [ORDER BY](#order-by-1)
        - [Ordenação Múltipla](#ordenação-múltipla)
    - [Agrupamento](#agrupamento)
        - [Técnicas e Segredos](#técnicas-e-segredos)
- [Funções e Agregações](#funções-e-agregações)
    - [Funções de String](#funções-de-string)
        - [UPPER()](#UPPER())
        - [LOWER()](#LOWER())
        - [LENGTH()](#LENGTH())
        - [CONCAT()](#CONCAT())
        - [TRIM()](#TRIM())
        - [SUBSTRING()](#SUBSTRING())
        - [REPLACE()](#REPLACE())
        - [CHAR_LENGTH()](#CHAR_LENGTH())
        - [POSITION()](#POSITION())
        - [LTRIM()_e_RTRIM()](#LTRIM()_e_RTRIM())
        - [INITCAP()](#INITCAP())
        - [REPEAT()](#REPEAT())
        - [REVERSE()](#REVERSE())
        - [LEFT()_e_RIGHT()](#LEFT()_e_RIGHT())
        - [PADLEFT()_e_PADRIGHT()](#PADLEFT()_e_PADRIGHT())
        - [SOUNDEX()](#SOUNDEX())
        - [LTRIM(R)](#LTRIM(R))
        - [FORMAT()](#FORMAT())
        - [ASCII()](#ASCII())
        - [CHAR()](#CHAR())
    - [Funções de Data](#funções-de-data)
        - [CURRENT_DATE](#CURRENT_DATE)
        - [CURRENT_TIMESTAMP](#CURRENT_TIMESTAMP)
        - [DATEADD()](#DATEADD())
        - [DATEDIFF()](#DATEDIFF())
        - [DAY()_MONTH()_YEAR()](#DAY()_MONTH()_YEAR())
        - [GETDATE()](#GETDATE())
        - [DATEPART()](#DATEPART())
        - [LAST_DAY()](#LAST_DAY())
        - [TO_DATE()](#TO_DATE())
        - [EXTRACT()](#EXTRACT())
        - [NOW()](#NOW())
        - [AGE()](#AGE())
        - [INTERVAL](#INTERVAL)
        - [TRUNC()](#TRUNC())
        - [SYSDATE](#SYSDATE)
        - [EOMONTH()](#EOMONTH())
        - [ISDATE()](#ISDATE())
        - [CAST()](#CAST())
        - [DATE_FORMAT()](#DATE_FORMAT())
        - [TIMESTAMPDIFF()](#TIMESTAMPDIFF())
    - [Funções Numéricas](#funções-numéricas)
        - [ABS()](#ABS())
        - [ROUND()](#ROUND())
        - [CEIL()_ou_CEILING()](#CEIL()_ou_CEILING())
        - [FLOOR()](#FLOOR())
        - [MOD()](#MOD())
        - [POWER()](#POWER())
        - [SQRT()](#SQRT())
        - [RAND()](#RAND())
        - [LOG()](#LOG())
        - [EXP()](#EXP())
        - [SIN()_COS()_TAN()](#SIN()_COS()_TAN())
        - [PI()](#PI())
        - [DEGREES()](#DEGREES())
        - [RADIANS()](#RADIANS())
        - [SIGN()](#SIGN())
        - [TRUNCATE()](#TRUNCATE())
        - [GREATEST()](#GREATEST())
        - [LEAST()](#LEAST())
        - [ATAN2()](#ATAN2())
        - [LOG10()](#LOG10())
    - [Funções de Agregação](#funções-de-agregação)
        - [SUM()](#SUM())
        - [AVG()](#AVG())
        - [COUNT()](#COUNT())
        - [MIN()](#MIN())
        - [MAX()](#MAX())
        - [GROUP_CONCAT()](#GROUP_CONCAT())
        - [STDDEV()](#STDDEV())
        - [VARIANCE()](#VARIANCE())
        - [FIRST_VALUE()](#FIRST_VALUE())
        - [LAST_VALUE()](#LAST_VALUE())
        - [PERCENTILE_CONT()](#PERCENTILE_CONT())
        - [PERCENTILE_DISC()](#PERCENTILE_DISC())
        - [MODE()](#MODE())
        - [ARRAY_AGG()](#ARRAY_AGG())
        - [COVAR_POP()_COVAR_SAMP()](#COVAR_POP()_COVAR_SAMP())
    - [Funções de Conversão](#funções-de-conversão)
        - [CAST()](#CAST())
        - [CONVERT()](#CONVERT())
        - [TO_DATE()](#TO_DATE())
        - [TO_CHAR()](#TO_CHAR())
        - [TO_NUMBER()](#TO_NUMBER())
        - [STR()](#STR())
        - [FORMAT()](#FORMAT())
        - [PARSE()](#PARSE())
        - [TRY_CAST()](#TRY_CAST())
        - [TRY_CONVERT()](#TRY_CONVERT())
        - [TRY_PARSE()](#TRY_PARSE())
    - [Funções de Sistema](#funções-de-sistema)
        - [DATABASE()](#DATABASE())
        - [USER()](#USER())
        - [VERSION()](#VERSION())
        - [NOW()](#NOW())
        - [CURDATE()](#CURDATE())
        - [CURTIME()](#CURTIME())
        - [LAST_INSERT_ID()](#LAST_INSERT_ID())
        - [SESSION_USER()](#SESSION_USER())
        - [SYSTEM_USER()](#SYSTEM_USER())
        - [UUID()](#UUID())
    - [Funções de Controle de Fluxo](#funções-de-controle-de-fluxo)
        - [CASE](#CASE)
        - [IF()](#IF())
        - [NULLIF()](#NULLIF())
        - [COALESCE()](#COALESCE())
        - [IIF()](#IIF())
    - [Funções de Janela](#funções-de-janela)
        - [ROW_NUMBER()](#ROW_NUMBER())
        - [DENSE_RANK()](#DENSE_RANK())
        - [NTILE(n)](#NTILE(n))
        - [LAG()](#LAG())
        - [LEAD()](#LEAD())
        - [FIRST_VALUE()](#FIRST_VALUE())
        - [LAST_VALUE()](#LAST_VALUE())
    - [Funções de Json](#funções-de-json)
        - [JSON_VALUE](#JSON_VALUE)
        - [JSON_QUERY](#JSON_QUERY)
        - [JSON_OBJECT](#JSON_OBJECT)
        - [JSON_ARRAY](#JSON_ARRAY)
        - [JSON_EXISTS](#JSON_EXISTS)
        - [JSON_LENGTH](#JSON_LENGTH)
        - [JSON_KEYS](#JSON_KEYS)
        - [JSON_REMOVE](#JSON_REMOVE)
    - [Funções de Xml](#funções-de-xml)
        - [XML_VALUE](#XML_VALUE)
        - [XML_QUERY](#XML_QUERY)
        - [XML_ELEMENT](#XML_ELEMENT)
        - [XML_ATTRIBUTES](#XML_ATTRIBUTES)
        - [XML_EXISTS](#XML_EXISTS)
        - [XMLTABLE](#XMLTABLE)
        - [XMLSERIALIZE](#XMLSERIALIZE)
        - [XMLPARSE](#XMLPARSE)
- [Junções e Relações](#junções-e-relações)
    - [Chaves Primárias e Estrangeiras](#chaves-primárias-e-estrangeiras)
        - [Chave Primária (PK)](#chave-primária-pk)
        - [Chave Estrangeira (FK)](#chave-estrangeira-fk)
    - [Junções](#junções)
        - [INNER_JOIN](#INNER_JOIN)
        - [LEFT_JOIN](#LEFT_JOIN)
        - [RIGHT_JOIN](#RIGHT_JOIN)
        - [FULL_JOIN](#FULL_JOIN)
    - [Subconsultas](#subconsultas)
        - [Subconsultas_Correlacionadas](#subconsultas-correlacionadas)
        - [Subconsultas_Não_Correlacionada](#subconsultas-não-correlacionada)
- [Manipulação de Dados](#manipulação-de-dados)
    - [Inserindo Dados](#inserindo-dados)
        - [INSERT](#insert)
    - [Atualizando Dados](#atualizando-dados)
        - [UPDATE](#update)
    - [Excluindo Dados](#excluindo-dados)
        - [DELETE](#delete)
    - [Transações](#transações)
- [Tópicos Avançados](#tópicos-avançados)
    - [Indexação e Performance](#indexação-e-performance)
    - [Views](#views)
    - [Triggers e Procedimentos Armazenados](#triggers-e-procedimentos-armazenados)
    - [Normalização](#normalização)
- [Maiores Erros em SQL: Explicação e Soluções](#maiores-erros-em-sql-explicação-e-soluções)
    - [Subqueries Ineficientes](#subqueries-ineficientes)
    - [Uso Excessivo de Wildcards](#uso-excessivo-de-wildcards)
    - [Não Utilizar Índices Adequadamente](#não-utilizar-índices-adequadamente)
    - [Consultas N+1](#consultas-n1)
    - [Não Considerar a Distribuição de Dados](#não-considerar-a-distribuição-de-dados)
    - [Injeção de SQL](#injeção-de-sql)
    - [Não Utilizar Transações Quando Necessário](#não-utilizar-transações-quando-necessário)
- [Estilo de Código SQL e Boas Práticas](#estilo-de-código-sql-e-boas-práticas)
    - [Estilo de Código SQL](#estilo-de-código-sql)
    - [Common Table Expressions (CTEs)](#common-table-expressions-ctes)
    - [Ferramentas e Extensões para VSCode](#ferramentas-e-extensões-para-vscode)
- [Recursos Avançados em SQL](#recursos-avançados-em-sql)
    - [Tabelas Temporárias](#tabelas-temporárias)
    - [Variáveis](#variáveis)
    - [Loops](#loops)
    - [Defaults](#defaults)
    - [Identity](#identity)
- [SQL para Análise de Dados](#sql-para-análise-de-dados)
    - [Técnicas de Limpeza de Dados](#técnicas-de-limpeza-de-dados)
    - [Análise Exploratória com SQL](#análise-exploratória-com-sql)
    - [Funções Analíticas e Janelas](#funções-analíticas-e-janelas)
- [Diferenças entre DBMSs](#diferenças-entre-dbmss)
    - [Modelo ANSI](#modelo-ansi)
    - [Sintaxes Específicas de Diferentes DBMSs](#sintaxes-específicas-de-diferentes-dbmss)
    - [Funções e Características Exclusivas](#funções-e-características-exclusivas)
    - [Casos de Uso e Quando Escolher Cada DBMS](#casos-de-uso-e-quando-escolher-cada-dbms)
- [Prática e Projetos Reais](#prática-e-projetos-reais)
    - [Análise de um Conjunto de Dados do Mundo Real](#análise-de-um-conjunto-de-dados-do-mundo-real)
    - [Resolução de Problemas Comuns do Dia a Dia](#resolução-de-problemas-comuns-do-dia-a-dia)
    - [Construção de um Mini-Projeto](#construção-de-um-mini-projeto)
- [Recursos para Aprendizado Contínuo](#recursos-para-aprendizado-contínuo)
- [Conclusão e Próximos Passos](#conclusão-e-próximos-passos)
- [Projeto Final](#projeto-final)
- [Recomendações para Aprendizado Avançado](#recomendações-para-aprendizado-avançado)
    - [Integração SQL com Outras Ferramentas](#integração-sql-com-outras-ferramentas)
    - [Aprendizado de Outras Linguagens Relacionadas a Banco de Dados](#aprendizado-de-outras-linguagens-relacionadas-a-banco-de-dados)
    - [DBT (Data Build Tool)](#dbt-data-build-tool)
- [Conclusão](#conclusão)


## introdução-ao-sql
[Voltar ao Topo](#menu)


### o-que-é-sql-e-por-que-é-importante
[Voltar ao Topo](#menu)


#### Definição 
SQL (Structured Query Language) é uma linguagem padrão para armazenar, manipular e recuperar dados em bancos de dados.

#### História Breve 
O SQL, que significa "Structured Query Language" (Linguagem de Consulta Estruturada), é uma linguagem de programação usada para gerenciar e manipular bancos de dados relacionais. Aqui está uma breve visão da sua origem e evolução:

- Anos 1970: A história do SQL começa nos laboratórios da IBM em San Jose, Califórnia. Em 1970, o Dr. Edgar F. Codd publicou um artigo intitulado "A Relational Model of Data for Large Shared Data Banks", introduzindo o conceito de modelo relacional para bancos de dados. Este modelo tornou-se a base para o desenvolvimento do SQL.

- 1974: A primeira versão do SQL foi desenvolvida pela IBM e foi originalmente chamada de SEQUEL (Structured English Query Language). No entanto, devido a problemas de marca registrada, o nome foi posteriormente alterado para SQL.

- Anos 1980: A popularidade do SQL cresceu rapidamente durante esta década. Em 1986, o American National Standards Institute (ANSI) padronizou o SQL como uma linguagem oficial para bancos de dados relacionais. Durante este período, empresas como Oracle, Microsoft e Sybase começaram a desenvolver seus próprios sistemas de gerenciamento de banco de dados (RDBMS) baseados em SQL.

- Anos 1990: Com a crescente adoção da internet e do comércio eletrônico, a demanda por bancos de dados robustos e escaláveis aumentou. O SQL se adaptou a essas mudanças, com melhorias na linguagem e novos recursos, como triggers, stored procedures e suporte para XML.

- Anos 2000 e além: A era do "Big Data" trouxe novos desafios e oportunidades para o mundo dos bancos de dados. Enquanto bancos de dados NoSQL começaram a ganhar popularidade para certos casos de uso, o SQL continuou a ser a linguagem padrão para bancos de dados relacionais. Além disso, surgiram extensões e variações da linguagem SQL para atender a bancos de dados específicos em nuvem, como o BigQuery da Google e o Redshift da Amazon.

Hoje, o SQL continua a ser uma das linguagens de programação mais populares e amplamente utilizadas no mundo, com uma rica história e um futuro promissor à medida que os bancos de dados e as tecnologias de dados continuam a evoluir.
    
#### Análise de Dados 
SQL permite que analistas e cientistas de dados consultem grandes conjuntos de dados de maneira eficiente.
    
#### Desenvolvimento de Aplicações
Muitos aplicativos modernos dependem de bancos de dados para armazenar informações do usuário, e SQL é a ponte para acessar e manipular esses dados.
    
#### Integração de Sistemas
SQL serve como uma linguagem comum entre diferentes sistemas para troca de dados.

### visão-geral-dos-sistemas-de-gerenciamento-de-banco-de-dados-dbms
[Voltar ao Topo](#menu)


#### Definição DBMS  
Um DBMS é um software que permite criar, definir e manipular bancos de dados para vários aplicativos.
    
#### Tipos de DBMS
- RDBMS (Relational Database Management System): Baseia-se no modelo relacional onde os dados são armazenados em tabelas. Exemplos: MySQL, PostgreSQL, Oracle.
    
- NoSQL: Não usa o modelo relacional tradicional. Exemplos: MongoDB (baseado em documentos), Cassandra (baseado em colunas), Redis (armazenamento de valor-chave).

#### Componentes Principais de um DBMS 
    
- Motor de Banco de Dados: 
    Realiza funções de armazenamento, recuperação e atualização de dados.
    
- Linguagem de Consulta de Dados: 
    Permite que os usuários interajam com o banco de dados (por exemplo, SQL).
    
- Ferramentas de Administração: 
    Auxiliam na manutenção e monitoramento do banco de dados. Usaremos nesse curso o um banco SQLServer, e o Dbeaver como ferramenta de administração.
    
### principais-dbms-e-suas-características
[Voltar ao Topo](#menu)



#### SQL Server
- Visão Geral: Desenvolvido pela Microsoft, o SQL Server é um RDBMS poderoso e versátil que suporta uma ampla variedade de cargas de trabalho de transação e análise.
    
- Pontos Fortes: Integração com outras ferramentas da Microsoft, recursos avançados de BI, segurança robusta.
    
- Pontos Fracos: Licenciamento pode ser caro, embora exista uma versão Express gratuita com limitações.
    
- Instalação: A Microsoft fornece uma imagem [Docker oficial para SQL Server](https://hub.docker.com/_/microsoft-mssql-server) que pode ser usada para instalação e configuração em ambientes de desenvolvimento.

#### SQLite
- Visão Geral: SQLite é um banco de dados relacional embutido que é leve e não requer um servidor separado para operar. É ideal para aplicações móveis, desktop e pequenas aplicações web.
    
- Pontos Fortes: Portabilidade, sem necessidade de configuração, adequado para prototipagem rápida.
    
- Pontos Fracos: Não é adequado para aplicações de alto desempenho ou com muitos usuários simultâneos.
    
- Instalação: Docker Image para [SQLite](https://hub.docker.com/r/nouchka/sqlite3)

#### MySQL
- Visão Geral: Um dos RDBMS mais populares do mundo, adequado para pequenas e grandes aplicações.
    
- Pontos Fortes: Comunidade ativa, muitos recursos, ampla adoção na indústria.
    
- Pontos Fracos: Pode ter problemas de desempenho em cargas de trabalho muito grandes.
    
- Instalação: Docker Image para [MySQL](https://hub.docker.com/_/mysql)

#### PostgreSQL
- Visão Geral: RDBMS avançado com muitos recursos e extensões, como PostGIS para geoespacial.
    
- Pontos Fortes: Extensível, suporte a JSON, desempenho robusto.

- Pontos Fracos: Curva de aprendizado mais íngreme em comparação com MySQL ou SQLite.
    
- Instalação: Docker Image para [PostgreSQL](https://hub.docker.com/_/postgres)

#### Oracle
- Visão Geral: Um dos RDBMS mais antigos e robustos, amplamente utilizado em grandes corporações.
    
- Pontos Fortes: Recursos avançados, alta disponibilidade, segurança.
    
- Pontos Fracos: Licenciamento caro, complexidade na configuração e manutenção.
    
- Instalação: Oracle não fornece uma imagem Docker oficial. No entanto, existem imagens não oficiais disponíveis no Docker Hub.

#### BigQuery
- Visão Geral: Serviço de análise de dados em nuvem do Google, sem servidor e totalmente gerenciado.
    
- Pontos Fortes: Escalabilidade, capacidade de lidar com petabytes de dados, modelo de pagamento pelo uso.
    
- Pontos Fracos: Pode ser caro para consultas frequentes, não é um RDBMS tradicional.
    
- Configuração: BigQuery é um serviço em nuvem, portanto, não requer instalação tradicional.

#### Redshift
- Visão Geral: Serviço de armazenamento de dados em nuvem da Amazon, otimizado para análise.
    
- Pontos Fortes: Integração com o ecossistema AWS, escalabilidade, desempenho.
    
- Pontos Fracos: Custo pode ser alto dependendo do uso, complexidade na otimização de consultas.
    
- Configuração: Redshift é um serviço em nuvem, portanto, não requer instalação tradicional.


### diferença-entre-cloud-e-on-premises
[Voltar ao Topo](#menu)



#### Cloud (Nuvem)

##### Definição:

- Modelos de computação em que os recursos de TI são fornecidos como um serviço através da internet.
    
##### Vantagens:

- Escalabilidade: Capacidade de aumentar ou diminuir recursos conforme a necessidade.
        
- Custo: Pagamento conforme o uso, sem necessidade de grandes investimentos iniciais.
        
- Manutenção: Os provedores de nuvem gerenciam e atualizam a infraestrutura.
        
- Acessibilidade: Acesso aos recursos de qualquer lugar com uma conexão à internet.
    
##### Desvantagens:
        
- Latência: Pode haver atrasos na transferência de dados dependendo da localização.
        
- Segurança: Dependência de terceiros para garantir a segurança dos dados.

#### On-Premises

##### Definição: 

- Modelos de computação em que os recursos de TI são hospedados e gerenciados localmente, geralmente nas instalações da própria organização.
    
##### Vantagens:

- Controle: Controle total sobre a infraestrutura e os dados.
        
- Personalização: Capacidade de personalizar completamente o ambiente de TI.
        
- Segurança: Os dados permanecem no local, reduzindo o risco de exposição.
    
##### Desvantagens:

- Custo: Grandes investimentos iniciais em hardware e software.
        
- Manutenção: A organização é responsável pela manutenção e atualizações.
        
- Escalabilidade: Aumentar a capacidade pode exigir novos investimentos e tempo.

## fundamentos-do-sql
[Voltar ao Topo](#menu)


O SQL é uma linguagem poderosa e versátil, mas, como qualquer linguagem, é essencial entender seus fundamentos para usá-la efetivamente. Aqui, exploraremos os conceitos básicos que formam a base da linguagem SQL.

### entendendo-tabelas-registros-e-campos
[Voltar ao Topo](#menu)


#### Tabelas: 

Em um banco de dados relacional, as tabelas são estruturas que armazenam dados em formato tabular. Pense nelas como equivalentes a planilhas em uma aplicação de planilha eletrônica. Cada tabela tem um nome único e consiste em linhas e colunas.
        
#### Registros (ou Linhas): 

Cada linha em uma tabela representa um registro. Um registro é um conjunto único de dados relacionados que são armazenados juntos.
        
#### Campos (ou Colunas): 

As colunas em uma tabela representam campos. Cada campo tem um nome e armazena um tipo específico de informação. Por exemplo, em uma tabela de "Clientes", você pode ter campos como "Nome", "Endereço" e "Número de Telefone".

### tipos-de-dados
[Voltar ao Topo](#menu)

        
Os tipos de dados em SQL definem o tipo de valor que uma coluna pode conter. É crucial escolher o tipo de dado correto para uma coluna, pois isso afeta não apenas o tipo de informação que você pode armazenar, mas também o desempenho do banco de dados e a quantidade de espaço de armazenamento usado. Aqui está uma lista dos tipos de dados mais comuns em SQL, agrupados por categorias:

#### Tipos Numéricos:
- `INT`: Um número inteiro.
- `SMALLINT`: Um número inteiro menor que INT.
- `TINYINT`: Um número inteiro ainda menor que SMALLINT.
- `BIGINT`: Um número inteiro maior que INT.
- `FLOAT`: Número de ponto flutuante.
- `REAL`: Número de ponto flutuante menor que FLOAT.
- `DECIMAL(p, s)`: Número decimal fixo. Onde p é a precisão total e s é a escala.
- `NUMERIC(p, s)`: Semelhante ao DECIMAL.

#### Tipos de Caracteres:
- `CHAR(n)`: String de tamanho fixo.
- `VARCHAR(n)`: String de tamanho variável.
- `TEXT`: Uma string de tamanho variável longa.

#### Tipos de Data e Hora:
- `DATE`: Data no formato YYYY-MM-DD.
- `TIME`: Hora no formato HH:MI:SS.
- `DATETIME`: Combinação de data e hora.
- `TIMESTAMP`: Marca de data/hora que inclui a data e a hora até a fração de segundo.

#### Tipos Lógicos:
- `BIT`: Valor binário (0 ou 1).
- `BOOLEAN`: Verdadeiro ou falso.

#### Tipos de Dados Binários:
- `BINARY(n)`: Dados binários de tamanho fixo.
- `VARBINARY(n)`: Dados binários de tamanho variável.
- `BLOB`: Dados binários de tamanho variável longo.

#### Tipos de Dados Espaciais (para bancos de dados que suportam GIS):
- `GEOMETRY`: Tipo de dado base para todos os tipos espaciais.
- `POINT`: Representa um ponto em um plano.
- `LINESTRING`: Representa uma linha.
- `POLYGON`: Representa um polígono.

#### Tipos de Dados JSON (em DBMSs modernos):
- `JSON`: Armazena valores JSON.
- `JSONB`: Armazena valores JSON em formato binário (específico do PostgreSQL).

#### Tipos de Dados XML (em alguns DBMSs):
- `XML`: Armazena valores XML.

#### Outros Tipos:
- `UUID`: Identificador único universal.
- `ENUM`: Um tipo que consiste em uma lista estática de strings.

Lembre-se de que a disponibilidade, a sintaxe e o comportamento exatos desses tipos de dados podem variar dependendo do sistema de gerenciamento de banco de dados (DBMS) que você está usando. Além disso, muitos DBMSs oferecem tipos de dados adicionais ou variações dos tipos listados acima. Sempre consulte a documentação oficial do seu DBMS ao projetar sua base de dados.

### comandos-básicos
[Voltar ao Topo](#menu)
        
#### SELECT: 

Usado para selecionar dados de uma ou mais tabelas. Por exemplo, SELECT nome FROM clientes; retornaria todos os nomes da tabela de clientes.
        
#### FROM: 

Especifica de qual tabela você deseja selecionar ou recuperar dados.
        
#### WHERE: 

Permite filtrar os resultados com base em uma condição. Por exemplo, SELECT nome FROM clientes WHERE idade > 21; retornaria os nomes de todos os clientes com mais de 21 anos.

#### ORDER BY: 

Ordena os resultados com base em uma ou mais colunas. Por exemplo, SELECT nome FROM clientes ORDER BY nome; retornaria os nomes de todos os clientes em ordem alfabética.

#### GROUP BY: 

Agrupa os resultados com base em uma ou mais colunas. Por exemplo, SELECT departamento, COUNT(*) FROM funcionários GROUP BY departamento; retornaria o número de funcionários em cada departamento.

- Lembre-se sempre:

```sql
select -- Selecione
    * -- Colunas
from tabela --Aonde
where condicao -- Quando
```

### filtragem: 
[Voltar ao Topo](#menu)


Os operadores lógicos são fundamentais em SQL, especialmente quando se trabalha com a cláusula WHERE para filtrar resultados. Eles permitem combinar ou modificar condições para tornar uma consulta mais específica ou flexível. Aqui estão os operadores lógicos mais comuns usados em SQL:

#### Operadores de Comparação:
- `=` : Igual a.
- `<>` ou `!=` : Diferente de.
- `>` : Maior que.
- `<` : Menor que.
- `>=` : Maior ou igual a.
- `<=` : Menor ou igual a.
- `BETWEEN` : Entre um intervalo (inclusive).
- `LIKE` : Pesquisa por um padrão específico.
- `IN` : Verifica se o valor está em uma lista de valores.

#### Operadores Lógicos:
- `AND` : Retorna verdadeiro se ambas as condições especificadas forem verdadeiras.
- `OR` : Retorna verdadeiro se pelo menos uma das condições especificadas for verdadeira.
- `NOT` : Retorna verdadeiro se a condição especificada for falsa.

#### Operadores de Existência:
- `IS NULL` : Retorna verdadeiro se o valor é nulo.
- `IS NOT NULL` : Retorna verdadeiro se o valor não é nulo.
- `EXISTS` : Retorna verdadeiro se a subconsulta retornar pelo menos um registro.

#### Operadores de Conjunto (usados em subconsultas):
- `ALL` : Compara um valor a todos os valores em outra lista ou conjunto de resultados.
- `ANY` : Compara um valor a pelo menos um dos valores em outra lista ou conjunto de resultados.
- `SOME` : Funciona da mesma forma que ANY.

Ao usar esses operadores, é crucial entender a ordem das operações para garantir que sua consulta retorne os resultados esperados. Por exemplo, o operador AND tem precedência sobre o OR, o que significa que, em uma expressão com ambos, as condições ligadas por AND serão avaliadas primeiro. Se necessário, você pode usar parênteses para alterar a ordem de avaliação e tornar sua intenção mais clara.

Exemplo:

```sql
SELECT 
    * 
FROM employees
WHERE department = 'Sales' 
AND (years_of_experience > 5 
OR manager = 'Yes');
```

Neste exemplo, a consulta retornará todos os registros de empregados no departamento de vendas que têm mais de 5 anos de experiência ou que são gerentes. Graças aos parênteses, a consulta não se limita a retornar gerentes com mais de 5 anos de experiência.
        
### ordenação: 
[Voltar ao Topo](#menu)


A ordenação é uma parte crucial das consultas SQL, permitindo que os usuários apresentem os resultados de uma maneira específica e legível. A cláusula ORDER BY é usada para classificar os registros em ordem crescente ou decrescente com base em uma ou mais colunas. Aqui estão os principais componentes e conceitos relacionados à ordenação em SQL:

#### ORDER BY: 
- É a cláusula usada para especificar a ordem dos registros retornados.
- Pode ser aplicada a qualquer tipo de coluna: numérica, string, data, etc.
- Por padrão, a ordenação é em ordem ascendente.

Exemplo:

```sql
SELECT 
    * 
FROM employees
ORDER BY last_name;
```

Este exemplo retornará todos os registros da tabela employees, ordenados alfabeticamente pelo sobrenome.

- ASC: 
    - Significa "ascendente" e é usado para ordenar os registros de forma ascendente.
    - Embora seja o comportamento padrão, pode ser útil especificá-lo para tornar a intenção clara.

Exemplo:

```sql
SELECT 
    * 
FROM products
ORDER BY price ASC;
```

Este exemplo retornará todos os produtos da tabela products, ordenados pelo preço do mais baixo para o mais alto.

- DESC:
    - Significa "descendente" e é usado para ordenar os registros de forma descendente.

Exemplo:

```sql
SELECT 
    * 
FROM sales
ORDER BY sale_date DESC;
```

Este exemplo retornará todos os registros da tabela sales, ordenados pela data de venda do mais recente para o mais antigo.

#### Ordenação Múltipla:
- É possível ordenar os resultados por mais de uma coluna.
- A ordenação é aplicada da esquerda para a direita, ou seja, a primeira coluna especificada tem prioridade sobre as subsequentes.

Exemplo:

```sql
SELECT 
    * 
FROM employees
ORDER BY department ASC
    , last_name DESC;
```

Neste exemplo, os registros serão primeiro ordenados pelo departamento em ordem ascendente. Dentro de cada departamento, os registros serão ordenados pelo sobrenome em ordem descendente.

A cláusula `ORDER BY` é extremamente útil para apresentar dados de uma maneira que faça sentido para os usuários finais, seja para relatórios, análises ou qualquer outra finalidade. Ao compreender e utilizar eficazmente as opções de ordenação, você pode garantir que seus resultados sejam não apenas precisos, mas também facilmente interpretáveis.

### agrupamento:
[Voltar ao Topo](#menu)


A cláusula `GROUP BY` é usada para agrupar linhas que têm os mesmos valores em colunas específicas em resumo, como somatório, média, contagem, etc. É frequentemente usada com funções de agregação para realizar operações em cada grupo de linhas.

Como Funciona:

- Agrupamento: As linhas da tabela são agrupadas com base em uma ou mais colunas especificadas na cláusula GROUP BY. Cada grupo representa um conjunto de linhas que têm os mesmos valores nas colunas de agrupamento.

- Agregação: Para cada grupo formado, são calculados valores agregados usando funções de agregação, como `SUM()`, `AVG()`, `COUNT()`, `MIN()`, `MAX()`, etc. O resultado final consiste em uma linha para cada grupo, com as colunas de agrupamento e os valores agregados calculados.

- Filtragem de Grupo: A cláusula `HAVING` é usada para filtrar grupos após a agregação. Diferentemente da cláusula `WHERE`, que filtra linhas antes da agregação, `HAVING` filtra os grupos formados.

Exemplo Básico:

```sql
SELECT 
    departamento
    , COUNT(*) as numero_funcionarios
FROM funcionarios
GROUP BY departamento;
```

Neste exemplo, os funcionários são agrupados pelo departamento, e é contado o número de funcionários em cada departamento.

#### Técnicas e Segredos:

- Uso de HAVING: Filtra os grupos após a agregação.

```sql
SELECT 
    departamento
    , AVG(salario) as salario_medio
FROM funcionarios
GROUP BY departamento
HAVING salario_medio > 5000;
```

Lista os departamentos onde o salário médio é maior que 5000.

- Agrupamento por Múltiplas Colunas: Você pode agrupar por mais de uma coluna.

```sql
SELECT 
    departamento
    , cargo
    , COUNT(*) as numero_funcionarios
FROM funcionarios
GROUP BY departamento, cargo;
```

Agrupa os funcionários por departamento e cargo.

- Uso com ORDER BY: Ordena os resultados após o agrupamento e agregação.

```sql
SELECT 
    departamento
    , SUM(salario) as total_salarios
FROM funcionarios
GROUP BY departamento
ORDER BY total_salarios DESC;
```

Lista os departamentos pela soma total dos salários em ordem decrescente.

- Agrupamento por Expressões: Você pode agrupar por expressões ou funções.

```sql
SELECT 
    YEAR(data_contratacao) as ano_contratacao
    , COUNT(*) as numero_contratacoes
FROM funcionarios
GROUP BY YEAR(data_contratacao);
```
Conta o número de contratações por ano.

Estas são algumas técnicas e segredos do GROUP BY que podem ajudá-lo a manipular e analisar dados de forma eficiente em SQL.

## funções-e-agregações
[Voltar ao Topo](#menu)


O SQL não é apenas sobre a recuperação de dados brutos; é também sobre a transformação e análise desses dados para obter insights valiosos. As funções e agregações são ferramentas essenciais nesse processo, permitindo que você manipule e resuma dados de maneiras significativas.

### funções-de-string 
[Voltar ao Topo](#menu)

Permitem manipular e formatar strings.

#### UPPER():
- Descrição: Converte todos os caracteres de uma string para maiúsculas.
    
    Exemplo:

    ```sql
    SELECT 
        UPPER('banana') AS Result;
    ```
    Resultado: `BANANA`

#### LOWER():

- Descrição: Converte todos os caracteres de uma string para minúsculas.
    
    Exemplo:

    ```sql
    SELECT 
        LOWER('APPLE') AS Result;
    ```
    Resultado: `apple`

#### LENGTH():

- Descrição: Retorna o número de caracteres em uma string.
    
    Exemplo:

    ```sql
    SELECT 
        LENGTH('grape') AS Result;
    ```
    Resultado: `5`

#### CONCAT():

- Descrição: Combina duas ou mais strings.
    
    Exemplo:

    ```sql
    SELECT 
        CONCAT('pine', 'apple') AS Result;
    ```
    Resultado: `pineapple`

#### TRIM():

- Descrição: Remove espaços do início e do final de uma string.
    
    Exemplo:

    ```sql
    SELECT 
        TRIM('   mango   ') AS Result;
    ```
    Resultado: `mango`

#### SUBSTRING():

- Descrição: Extrai uma parte da string.
    
    Exemplo:

    ```sql
    SELECT 
        SUBSTRING('strawberry', 1, 5) AS Result;
    ```
    Resultado: `straw`

#### REPLACE():

- Descrição: Substitui uma substring por outra.
    
    Exemplo:

    ```sql
    SELECT 
        REPLACE('blueberry is blue', 'blue', 'red') AS Result;
    ```
    Resultado: `redberry is red`

#### CHAR_LENGTH():

- Descrição: Retorna o número de caracteres em uma string.
    
    Exemplo:

    ```sql
    SELECT 
        CHAR_LENGTH('kiwi') AS Result;
    ```
    Resultado: `4`

#### POSITION():

- Descrição: Retorna a posição da primeira ocorrência de uma substring.
    
    Exemplo:

    ```sql
    SELECT 
        POSITION('nut' IN 'coconut') AS Result;
    ```
    Resultado: `5`

#### LTRIM()_e_RTRIM():

- Descrição: Remove espaços do início ou final.
    
    Exemplo:

    ```sql
    SELECT 
        LTRIM('   raspberry') AS LeftTrimResult
        , RTRIM('blackberry   ') AS RightTrimResult;
    ```
    Resultado: `raspberry` e `blackberry`

#### INITCAP():

- Descrição: Converte a primeira letra de cada palavra para maiúscula.
    
    Exemplo:

    ```sql
    SELECT 
        INITCAP('hello world') AS Result;
    ```
    Resultado: `Hello World`

#### REPEAT():

- Descrição: Repete uma string um número específico de vezes.
    
    Exemplo:

    ```sql
    SELECT 
        REPEAT('ha', 3) AS Result;
    ```
    Resultado: `hahaha`

#### REVERSE():

- Descrição: Inverte uma string.
    
    Exemplo:

    ```sql
    SELECT 
        REVERSE('melon') AS Result;
    ```
    Resultado: `nolem`

#### LEFT()_e_RIGHT():

- Descrição: Retorna um número específico de caracteres do início ou final da string.
    
    Exemplo:

    ```sql
    SELECT 
        LEFT('cherry', 3) AS LeftResult
        , RIGHT('cherry', 3) AS RightResult;
    ```
    Resultado: `che` e `rry`

#### PADLEFT()_e_PADRIGHT():

- Descrição: Adiciona caracteres à esquerda ou à direita de uma string até atingir um comprimento especificado.
    
    Exemplo:

    ```sql
    SELECT 
        PADLEFT('fruit', 8, '0') AS LeftPadResult
        , PADRIGHT('fruit', 8, '0') AS RightPadResult;
    ```
    Resultado: `000fruit` e `fruit000`

#### SOUNDEX():

- Descrição: Retorna um código que representa a string, útil para encontrar palavras que soam de forma semelhante.
    
    Exemplo:

    ```sql
    SELECT 
        SOUNDEX('pear') AS Result;
    ```
    Resultado: `Um código específico para "pear".`

#### LTRIM(R):

- Descrição: Remove caracteres específicos do início ou final da string.
    
    Exemplo:

    ```sql
    SELECT 
        LTRIM('000123', '0') AS Result;
    ```
    Resultado: `123`

#### FORMAT():

- Descrição: Formata uma string de acordo com um padrão especificado.
    
    Exemplo:

    ```sql
    SELECT 
        FORMAT(12345.6789, '#,##0.00') AS Result;
    ```
    Resultado: `12,345.68`

#### ASCII():

- Descrição: Retorna o valor ASCII do primeiro caractere da string.
    
    Exemplo:

    ```sql
    SELECT 
        ASCII('A') AS Result;
    ```
    Resultado: `65`

#### CHAR():

- Descrição: Retorna o caractere correspondente a um valor ASCII.
    
    Exemplo:

    ```sql
    SELECT 
        CHAR(65) AS Result;
    ```
    Resultado: `A`

Estas são apenas algumas das muitas funções de manipulação de strings disponíveis em SQL. A disponibilidade e a sintaxe exata podem variar dependendo do sistema de gerenciamento de banco de dados que você está usando.
    
### funções-de-data 
[Voltar ao Topo](#menu)


Estas são cruciais para trabalhar com campos de data e hora. 

#### CURRENT_DATE:

- Descrição: Retorna a data atual.
    
    Exemplo:

    ```sql
    SELECT 
        CURRENT_DATE AS Today;
    ```
    Resultado: `2023-07-10` (por exemplo)

#### CURRENT_TIMESTAMP:

- Descrição: Retorna a data e hora atuais.
    
    Exemplo:

    ```sql
    SELECT 
        CURRENT_TIMESTAMP AS Now;
    ```
    Resultado: `2023-07-10 12:00:00` (por exemplo)

#### DATEADD():

- Descrição: Adiciona um intervalo específico a uma data.
    
    Exemplo:

    ```sql
    SELECT 
        DATEADD(DAY, 7, '2023-07-10') AS OneWeekLater;
    ```
    Resultado: `2023-07-17`

#### DATEDIFF():

- Descrição: Retorna a diferença entre duas datas.
    
    Exemplo:

    ```sql
    SELECT 
        DATEDIFF(DAY, '2023-07-01', '2023-07-10') AS DaysDifference;
    ```
    Resultado: `9`

#### DAY()_MONTH()_YEAR():

- Descrição: Extraem o dia, mês ou ano de uma data, respectivamente.
    
    Exemplo:

    ```sql
    SELECT 
        DAY('2023-07-10') AS DayPart
        , MONTH('2023-07-10') AS MonthPart
        , YEAR('2023-07-10') AS YearPart;
    ```
    Resultado: `10`, `7`, `2023`

#### GETDATE():

- Descrição: Retorna a data e hora atuais (específico do SQL Server).
    
    Exemplo:

    ```sql
    SELECT 
        GETDATE() AS Now;
    ```
    Resultado: `2023-07-10 12:00:00` (por exemplo)

#### DATEPART():

- Descrição: Retorna uma parte específica de uma data, como o dia da semana.
    
    Exemplo:

    ```sql
    SELECT 
        DATEPART(WEEKDAY, '2023-07-10') AS DayOfWeek;
    ```
    Resultado: `2`

#### LAST_DAY():

- Descrição: Retorna o último dia do mês para a data fornecida.
    
    Exemplo:

    ```sql
    SELECT 
        LAST_DAY('2023-07-10') AS LastDayOfMonth;
    ```
    Resultado: `2023-07-31`

#### TO_DATE():

- Descrição: Converte uma string para uma data.
    
    Exemplo:

    ```sql
    SELECT 
        TO_DATE('10-JUL-2023', 'DD-MON-YYYY') AS DateConversion;
    ```
    Resultado: `2023-07-10`

#### EXTRACT():

- Descrição: Extrai uma parte específica de uma data, como o trimestre.
    
    Exemplo:

    ```sql
    SELECT 
        EXTRACT(QUARTER FROM '2023-07-10') AS QuarterPart;
    ```
    Resultado: `3`

#### NOW():

- Descrição: Retorna a data e hora atuais.
    
    Exemplo:

    ```sql
    SELECT 
        NOW() AS CurrentDateTime;
    ```
    Resultado: `2023-07-10 12:00:00` (por exemplo)

#### AGE():

- Descrição: Retorna a idade entre duas datas.
    
    Exemplo:

    ```sql
    SELECT 
        AGE('2023-07-10', '2000-01-01') AS AgeDifference;
    ```
    Resultado: `23 years 6 mons 9 days`

#### INTERVAL:

- Descrição: Usado para adicionar ou subtrair um intervalo específico de uma data.
    
    Exemplo:

    ```sql
    SELECT 
        '2023-07-10' + INTERVAL '1 YEAR' AS OneYearLater;
    ```
    Resultado: `2024-07-10`

#### TRUNC():

- Descrição: Trunca uma data para o início do dia, mês ou ano.
    
    Exemplo:

    ```sql
    SELECT 
        TRUNC('2023-07-10', 'MONTH') AS StartOfMonth;
    ```
    Resultado: `2023-07-01`

#### SYSDATE:

- Descrição: Retorna a data e hora atuais do sistema (específico do Oracle).
    
    Exemplo:

    ```sql
    SELECT 
        SYSDATE FROM DUAL;
    ```

#### EOMONTH():

- Descrição: Retorna o último dia do mês da data fornecida.
    
    Exemplo:

    ```sql
    SELECT 
        EOMONTH('2023-07-10') AS EndOfMonth;
    ```
    Resultado: `2023-07-31`

#### ISDATE():

- Descrição: Verifica se uma expressão é uma data válida.
    
    Exemplo:

    ```sql
    SELECT 
        ISDATE('2023-07-10') AS IsValid;
    ```
    Resultado: `1` (verdadeiro)

#### CAST():

- Descrição: Converte um tipo de dado em outro, como uma string em uma data.
    
    Exemplo:

    ```sql
    SELECT 
        CAST('2023-07-10' AS DATE) AS DateConversion;
    ```
    Resultado: `2023-07-10`

#### DATE_FORMAT():

- Descrição: Formata uma data de acordo com um padrão especificado.
    
    Exemplo:

    ```sql
    SELECT 
        DATE_FORMAT('2023-07-10', '%W %D %M %Y') AS FormattedDate;
    ```
    Resultado: `Tuesday 10th July 2023`

#### TIMESTAMPDIFF():

- Descrição: Retorna a diferença entre duas datas em um intervalo específico, como dias ou meses.
    
    Exemplo:

    ```sql
    SELECT 
        TIMESTAMPDIFF(MONTH, '2023-01-01', '2023-07-10') AS MonthsDifference;
    ```
    Resultado: `6`

Estas são algumas das funções relacionadas a datas em SQL. A disponibilidade e a sintaxe exata podem variar dependendo do sistema de gerenciamento de banco de dados que você está usando.

### funções-numéricas
[Voltar ao Topo](#menu)


Estas são usadas para realizar operações matemáticas. 

#### ABS():

- Descrição: Retorna o valor absoluto de um número.
    
    Exemplo:

    ```sql
    SELECT 
        ABS(-123) AS AbsoluteValue;
    ```
    Resultado: `123`

#### ROUND():

- Descrição: Arredonda um número para um número especificado de casas decimais.
    
    Exemplo:

    ```sql
    SELECT 
        ROUND(123.4567, 2) AS RoundedValue;
    ```
    Resultado: `123.46`

#### CEIL()_ou_CEILING():

- Descrição: Arredonda um número para o menor inteiro maior ou igual ao número.
    
    Exemplo:

    ```sql
    SELECT 
        CEIL(123.4567) AS CeilingValue;
    ```
    Resultado: `124`

#### FLOOR():

- Descrição: Arredonda um número para o maior inteiro menor ou igual ao número.
    
    Exemplo:

    ```sql
    SELECT 
        FLOOR(123.4567) AS FloorValue;
    ```
    Resultado: `123`

#### MOD():

- Descrição: Retorna o resto da divisão de dois números.
    
    Exemplo:

    ```sql
    SELECT 
        MOD(7, 3) AS ModulusValue;
    ```
    Resultado: `1`

#### POWER():

- Descrição: Retorna o valor de um número elevado à potência de outro número.
    
    Exemplo:

    ```sql
    SELECT 
        POWER(2, 3) AS PowerValue;
    ```
    Resultado: `8`

#### SQRT():

- Descrição: Retorna a raiz quadrada de um número.
    
    Exemplo:

    ```sql
    SELECT 
        SQRT(16) AS SqrtValue;
    ```
    Resultado: `4`

#### RAND():

- Descrição: Retorna um número aleatório entre 0 e 1.
    
    Exemplo:

    ```sql
    SELECT 
        RAND() AS RandomValue;
    ```
    Resultado: `0.123456789`

#### LOG():

- Descrição: Retorna o logaritmo natural de um número.
    
    Exemplo:

    ```sql
    SELECT 
        LOG(10) AS LogValue;
    ```
    Resultado: `2.302585092994046`

#### EXP():

- Descrição: Retorna e (número de Euler) elevado à potência de um número dado.
    
    Exemplo:

    ```sql
    SELECT 
        EXP(1) AS ExpValue;
    ```
    Resultado: Aproximadamente `2.71828`

#### SIN()_COS()_TAN():

- Descrição: Funções trigonométricas que retornam o seno, cosseno e tangente de um número, respectivamente.
    
    Exemplo:

    ```sql
    SELECT 
        SIN(PI()/2) AS SinValue
        , COS(PI()) AS CosValue
        , TAN(PI()/4) AS TanValue;
    ```
    Resultado: `1`, `-1`, `1`

#### PI():

- Descrição: Retorna o valor de π (pi).
    
    Exemplo:

    ```sql
    SELECT 
        PI() AS PiValue;
    ```
    Resultado: Aproximadamente `3.14159`

#### DEGREES():

- Descrição: Converte um valor em radianos para graus.
    
    Exemplo:

    ```sql
    SELECT 
        DEGREES(PI()) AS DegreesValue;
    ```
    Resultado: `180`

#### RADIANS():

- Descrição: Converte um valor em graus para radianos.
    
    Exemplo:

    ```sql
    SELECT 
        RADIANS(180) AS RadiansValue;
    ```
    Resultado: Aproximadamente `3.14159`

#### SIGN():

- Descrição: Retorna o sinal de um número (-1, 0, 1 para números negativos, zero e positivos, respectivamente).
    
    Exemplo:

    ```sql
    SELECT 
        SIGN(-5) AS SignValue;
    ```
    Resultado: `-1`

#### TRUNCATE():

- Descrição: Trunca um número para um número especificado de casas decimais, sem arredondamento.
    
    Exemplo:

    ```sql
    SELECT 
        TRUNCATE(123.4567, 2) AS TruncatedValue;
    ```
    Resultado: `123.45`

####  GREATEST():

- Descrição: Retorna o maior valor em uma lista de expressões.
    
    Exemplo:

    ```sql
    SELECT 
        GREATEST(1, 2, 3, 4, 5) AS GreatestValue;
    ```
    Resultado: `5`

#### LEAST():

- Descrição: Retorna o menor valor em uma lista de expressões.
    
    Exemplo:

    ```sql
    SELECT 
        LEAST(1, 2, 3, 4, 5) AS LeastValue;
    ```
    Resultado: `1`

#### ATAN2():

- Descrição: Retorna a arco tangente do quociente de seus argumentos.
    
    Exemplo:

    ```sql
    SELECT 
        ATAN2(1, 1) AS Atan2Value;
    ```
    Resultado: `0.7853981633974483`

#### LOG10():

- Descrição: Retorna o logaritmo base 10 de um número.
    
    Exemplo:

    ```sql
    SELECT 
        LOG10(100) AS Log10Value;
    ```
    Resultado: `2`

Estas são algumas das funções numéricas mais comuns em SQL. A disponibilidade e a sintaxe exata podem variar dependendo do sistema de gerenciamento de banco de dados que você está usando.
### funções-de-agregação
[Voltar ao Topo](#menu)

Estas funções são usadas para resumir e analisar conjuntos de dados.

#### SUM():

- Descrição: Retorna a soma total de uma coluna numérica.
    
    Exemplo:

    ```sql
    SELECT 
        SUM(salary) AS TotalSalary FROM employees;
    ```
    Resultado: `100000`

#### AVG():

- Descrição: Retorna a média dos valores em uma coluna numérica.
    
    Exemplo:

    ```sql
    SELECT 
        AVG(salary) AS AverageSalary FROM employees;
    ```
    Resultado: `50000`

#### COUNT():

- Descrição: Retorna o número de linhas que correspondem a um critério especificado.
    
    Exemplo:

    ```sql
    SELECT 
        COUNT(*) AS TotalEmployees FROM employees;
    ```
    Resultado: `2`

#### MIN():

- Descrição: Retorna o menor valor em uma coluna.
    
    Exemplo:

    ```sql
    SELECT 
        MIN(salary) AS LowestSalary FROM employees;
    ```
    Resultado: `25000`

#### MAX():

- Descrição: Retorna o maior valor em uma coluna.
    
    Exemplo:

    ```sql
    SELECT 
        MAX(salary) AS HighestSalary FROM employees;
    ```
    Resultado: `75000`

#### GROUP_CONCAT() (em alguns DBMS, como MySQL) ou STRING_AGG() (em SQL Server):

- Descrição: Agrega valores de várias linhas em uma única string.
    
    Exemplo (usando GROUP_CONCAT):

    ```sql
    SELECT 
        department
        , GROUP_CONCAT(employee_name) AS EmployeeList 
    FROM employees 
    GROUP BY department;
    ```
    Resultado: `engineering` e `John, Jane`

#### STDDEV():

- Descrição: Retorna o desvio padrão de um conjunto de números.
    
    Exemplo:

    ```sql
    SELECT 
        STDDEV(salary) AS SalaryStandardDeviation 
    FROM employees;
    ```
    Resultado: `25000`

#### VARIANCE():

- Descrição: Retorna a variância de um conjunto de números.
    
    Exemplo:

    ```sql
    SELECT 
        VARIANCE(salary) AS SalaryVariance 
    FROM employees;
    ```
    Resultado: `625000000`

#### FIRST_VALUE():

- Descrição: Retorna o primeiro valor em um conjunto ordenado de valores.
    
    Exemplo:

    ```sql
    SELECT 
        FIRST_VALUE(employee_name) OVER (ORDER BY hire_date) AS FirstHired 
    FROM employees;
    ```
    Resultado: `John`

#### LAST_VALUE():

- Descrição: Retorna o último valor em um conjunto ordenado de valores.
    
    Exemplo:

    ```sql
    SELECT 
        LAST_VALUE(employee_name) OVER (ORDER BY hire_date) AS LastHired
    FROM employees;
    ```
    Resultado: `Jane`

#### PERCENTILE_CONT():

- Descrição: Calcula o valor do percentil contínuo para um conjunto ordenado de valores.
    
    Exemplo:

    ```sql
    SELECT 
        PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY salary) AS MedianSalary 
    FROM employees;
    ```
    Resultado: `50000`

#### PERCENTILE_DISC():

- Descrição: Calcula o valor do percentil discreto para um conjunto ordenado de valores.
    
    Exemplo:

    ```sql
    SELECT 
        PERCENTILE_DISC(0.5) WITHIN GROUP (ORDER BY salary) AS MedianSalary 
    FROM employees;
    ```
    Resultado: `50000`

#### MODE():

- Descrição: Retorna o valor que aparece com mais frequência em um conjunto de valores.
    
    Exemplo:

    ```sql
    SELECT 
        MODE() WITHIN GROUP (ORDER BY department) AS MostCommonDepartment 
    FROM employees;
    ```
    Resultado: `engineering`

#### ARRAY_AGG():

- Descrição: Agrega valores de várias linhas em uma matriz.
    
    Exemplo:

    ```sql
    SELECT 
        department
        , ARRAY_AGG(employee_name) AS EmployeeArray 
    FROM employees 
    GROUP BY department;
    ```
    Resultado: `engineering` e `John, Jane`

#### COVAR_POP()_COVAR_SAMP():

- Descrição: Calcula a covariância de um conjunto de números.
    
    Exemplo:

    ```sql
    SELECT 
        COVAR_POP(salary, age) AS PopulationCovariance 
    FROM employees;
    ```
    Resultado: `125000000`

### funções-de-conversão
[Voltar ao Topo](#menu)


Estas são algumas das funções de agregação mais comuns em SQL. A disponibilidade e a sintaxe exata podem variar dependendo do sistema de gerenciamento de banco de dados que você está usando.

#### CAST():
        
- Descrição: Converte um tipo de dado em outro.
    
    Exemplo: 
    
    ```sql
    SELECT 
        CAST('1234' AS INT) AS Result;
    ```
    Resultado: `1234`

#### CONVERT():
        
- Descrição: Semelhante ao CAST(), mas com uma sintaxe diferente e, em alguns DBMSs, oferece mais opções.
        
    Exemplo: 
    
    ```sql
    SELECT 
        CONVERT(INT, '1234') AS Result;
    ```
    Resultado: `1234`

    [Mais Opções de CAST e CONVERT](https://learn.microsoft.com/pt-br/sql/t-sql/functions/cast-and-convert-transact-sql?view=sql-server-ver16)

#### TO_DATE():

- Descrição: Converte uma string em uma data.
    
    Exemplo: 
    
    ```sql
    SELECT 
        TO_DATE('2023-01-01', 'YYYY-MM-DD') AS ResultDate;
    ```
    Resultado: `2023-01-01`

#### TO_CHAR():

- Descrição: Converte um número ou data em uma string.
    
    Exemplo: 
    
    ```sql
    SELECT 
        TO_CHAR(1234, '9999') AS ResultString;
    ```
    Resultado: `1234`

#### TO_NUMBER():
    
- Descrição: Converte uma string em um número.

    Exemplo: 
    
    ```sql
    SELECT 
        TO_NUMBER('1234.56', '9999.99') AS ResultNumber;
    ```
    Resultado: `1234.56`
#### STR():
    
- Descrição: Converte um número em uma string.
    
    Exemplo: 
    
    ```sql
    SELECT 
        STR(1234) AS ResultString;
    ```
    Resultado: `1234`

#### FORMAT():
    
- Descrição: Formata um valor usando um padrão específico. Muito útil para formatar números e datas.
    
    Exemplo: 
    
    ```sql
    SELECT 
        FORMAT(1234.5678, 'N2') AS FormattedNumber;
    ```
    Resultado: `1,234.57`

#### PARSE():
    
- Descrição: Analisa uma string usando um formato específico e a converte em um tipo de dado específico.
    
    Exemplo: 
    
    ```sql
    SELECT 
        PARSE('2023-01-01' AS DATE USING 'en-US') AS ResultDate;
    ```
    Resultado: `2023-01-01` 

#### TRY_CAST():

- Descrição: Semelhante ao CAST(), mas retorna NULL se a conversão falhar.
    
    Exemplo: 
    
    ```sql
    SELECT 
        TRY_CAST('ABC' AS INT) AS Result;
    ```
    Resultado: `NULL` 

#### TRY_CONVERT():
    
- Descrição: Semelhante ao CONVERT(), mas retorna NULL se a conversão falhar.
    
    Exemplo: 
    
    ```sql
    SELECT 
        TRY_CONVERT(INT, 'ABC') AS Result;
    ```
    Resultado: `NULL`

#### TRY_PARSE():
    
- Descrição: Semelhante ao PARSE(), mas retorna NULL se a análise falhar.

    Exemplo: 
    
    ```sql
    SELECT 
        TRY_PARSE('ABC' AS INT USING 'en-US') AS Result;
    ```
    Resultado: `NULL`

Estes são algumas das principais funções de conversão em SQL. A disponibilidade e a sintaxe exata podem variar dependendo do sistema de gerenciamento de banco de dados (DBMS) que você está usando. Além disso, é importante lembrar que a conversão inadequada de tipos de dados pode levar a erros ou resultados inesperados, então sempre é bom testar e entender completamente as conversões antes de aplicá-las em situações reais.

### funções-de-sistema
[Voltar ao Topo](#menu)



Estas são funções específicas do sistema que retornam informações sobre o sistema de banco de dados.

#### DATABASE():
        
- Descrição: Retorna o nome do banco de dados atual.
        
    Exemplo: 
    
    ```sql
    SELECT 
        DATABASE() AS CurrentDatabase;
    ```

#### USER():
        
- Descrição: Retorna o nome do usuário atual.
        
    Exemplo: 
    
    ```sql
    SELECT 
        USER() AS CurrentUser;
    ```

#### VERSION():
    
- Descrição: Retorna a versão atual do sistema de gerenciamento de banco de dados.
        
    Exemplo: 
    
    ```sql
    SELECT 
        VERSION() AS DBVersion;
    ```
    
#### NOW():
    
- Descrição: Retorna a data e hora atuais.
        
    Exemplo:

    ```sql 
    SELECT 
        NOW() AS CurrentDateTime;
    ```

#### CURDATE():
    
- Descrição: Retorna a data atual.
        
    Exemplo: 
    
    ```sql
    SELECT 
        CURDATE() AS CurrentDate;
    ```

#### CURTIME():

- Descrição: Retorna a hora atual.
        
    Exemplo: 
    
    ```sql
    SELECT 
        CURTIME() AS CurrentTime;
    ```

#### LAST_INSERT_ID():
        
- Descrição: Retorna o último ID inserido em uma tabela com uma coluna de autoincremento.
        
    Exemplo: 
    
    ```sql
    INSERT INTO table_name (column1) VALUES ('value1'); 
    SELECT LAST_INSERT_ID();
    ```
    
#### SESSION_USER():
        
- Descrição: Retorna o nome do usuário da sessão atual.
        
    Exemplo: 
    
    ```sql
    SELECT 
        SESSION_USER() AS SessionUser;
    ```

#### SYSTEM_USER():
        
- Descrição: Retorna o nome do usuário do sistema.
        
    Exemplo: 
    
    ```sql
    SELECT 
        SYSTEM_USER() AS SystemUser;
    ```

#### UUID():
        
- Descrição: Gera um valor UUID (Universal Unique Identifier) único.
        
    Exemplo: 
    
    ```sql
    SELECT 
        UUID() AS UniqueID;
    ```

Estas são algumas das principais funções de sistema em SQL. A disponibilidade e a sintaxe exata podem variar dependendo do sistema de gerenciamento de banco de dados (DBMS) que você está usando. Funções de sistema são extremamente úteis para obter informações sobre o ambiente do banco de dados, gerar valores únicos ou aleatórios e muito mais.

### funções-de-controle-de-fluxo
[Voltar ao Topo](#menu)


Estas são funções que controlam o fluxo de execução de uma consulta.

#### CASE:

- Descrição: Permite condições em consultas SQL. Pode ser usado em instruções ou expressões.
    
    Exemplo:

    ```sql
    SELECT 
        name
        , CASE 
            WHEN age < 18 THEN 'Menor'
            WHEN age BETWEEN 18 AND 64 THEN 'Adulto'
            ELSE 'Sênior'
        END AS age_group
    FROM people;
    ```
    Classifica pessoas em grupos de idade.

#### IF():

- Descrição: Retorna um valor se a condição for verdadeira e outro se for falsa.
    
    Exemplo:

    ```sql
    SELECT 
        name
        , IF(is_student = 1, 'Estudante', 'Não-Estudante') AS status
    FROM people;
    ```
    Classifica pessoas como estudante ou não-estudante.

#### NULLIF():

- Descrição: Retorna NULL se dois valores forem iguais, caso contrário, retorna o primeiro valor.
    
    Exemplo:

    ```sql
    SELECT 
        name
        , NULLIF(age, 0) AS age
    FROM people;
    ```
    Retorna NULL para idade se o valor for 0.

#### COALESCE():

- Descrição: Retorna o primeiro valor não nulo na lista.
    
    Exemplo:

    ```sql
    SELECT 
        name
        , COALESCE(phone, email, 'N/A') AS contact
    FROM people;
    ```
    Retorna o primeiro método de contato disponível ou 'N/A' se ambos forem nulos.

#### IIF():

- Descrição: Função similar ao IF(), mas mais concisa. Retorna um valor se a condição for verdadeira e outro se for falsa.
    
    Exemplo:

    ```sql
    SELECT 
        name
        , IIF(is_employee = 1, 'Empregado', 'Freelancer') AS job_status
    FROM people;
    ```
    Classifica pessoas como empregado ou freelancer.

Estas são algumas das principais funções de controle de fluxo em SQL. Elas permitem que os desenvolvedores criem lógica condicional em suas consultas, tornando-as mais dinâmicas e adaptáveis às necessidades de análise de dados. A disponibilidade e a sintaxe exata podem variar dependendo do sistema de gerenciamento de banco de dados (DBMS) que você está usando. Utilizar funções de controle de fluxo corretamente pode melhorar significativamente a eficiência e a clareza de suas consultas SQL.

### funções-de-janela
[Voltar ao Topo](#menu)


Estas são funções que operam em um conjunto de linhas que estão relacionadas a uma linha atual.

#### ROW_NUMBER():

- Descrição: Atribui um número único a cada linha de um conjunto de resultados.
    
    Exemplo:

    ```sql
    SELECT 
        name
        , age
        , ROW_NUMBER() OVER (ORDER BY age) AS row_num
    FROM people;
    ```
    Numera as pessoas por ordem crescente de idade.

    - Você também pode usar o PARTITION para particionar os resultados por uma coluna específica.

    Exemplo:

    ```sql
    SELECT 
        name
        , age
        , ROW_NUMBER() OVER (PARTITION BY name ORDER BY age) AS row_num
    FROM people;
    ```
    

#### RANK():

- Descrição: Atribui um rank a cada linha, com valores idênticos recebendo o mesmo rank.
    
    Exemplo:

    ```sql
    SELECT 
        name
        , score
        , RANK() OVER (ORDER BY score DESC) AS ranking
    FROM exam_results;
    ```
    Classifica os resultados do exame por pontuação, do maior para o menor.

#### DENSE_RANK():

- Descrição: Semelhante ao RANK(), mas sem lacunas entre os ranks quando há valores idênticos.
    
    Exemplo:

    ```sql
    SELECT 
        name
        , score
        , DENSE_RANK() OVER (ORDER BY score DESC) AS dense_ranking
    FROM exam_results;
    ```
    Classifica os resultados do exame por pontuação, sem lacunas no ranking.

#### NTILE(n):

- Descrição: Divide o conjunto de resultados em 'n' número de aproximadamente tamanhos iguais.
    Exemplo:

    ```sql
    SELECT 
        name
        , score
        , NTILE(4) OVER (ORDER BY score) AS quartile
    FROM exam_results;
    ```
    Divide os resultados do exame em quartis.

#### LAG():

- Descrição: Acessa dados da linha anterior no conjunto de resultados.
    
    Exemplo:

    ```sql
    SELECT 
        month
        , sales
        , LAG(sales) OVER (ORDER BY month) AS previous_month_sales
    FROM monthly_sales;
    ```
    Compara as vendas de um mês com o mês anterior.

#### LEAD():

- Descrição: Acessa dados da próxima linha no conjunto de resultados.
    
    Exemplo:

    ```sql
    SELECT 
        month
        , sales
        , LEAD(sales) OVER (ORDER BY month) AS next_month_sales
    FROM monthly_sales;
    ```
    Compara as vendas de um mês com o próximo mês.

#### FIRST_VALUE():

- Descrição: Retorna o primeiro valor em uma janela ordenada.
    
    Exemplo:

    ```sql
    SELECT 
        date
        , temperature
        , FIRST_VALUE(temperature) OVER (ORDER BY date) AS first_temp
    FROM daily_temperatures;
    ```
    Mostra a primeira temperatura registrada no conjunto de dados.

#### LAST_VALUE():

- Descrição: Retorna o último valor em uma janela ordenada.
    
    Exemplo:

    ```sql
    SELECT 
        date
        , temperature
        , LAST_VALUE(temperature) OVER (ORDER BY date) AS last_temp
    FROM daily_temperatures;
    ```
    Mostra a última temperatura registrada no conjunto de dados.

Estas são algumas das principais funções de janela em SQL. Elas oferecem uma maneira poderosa de realizar análises complexas diretamente no banco de dados, sem a necessidade de extrair dados ou usar ferramentas adicionais. A capacidade de entender e usar funções de janela é uma habilidade valiosa para qualquer profissional que trabalhe com análise de dados. A disponibilidade e a sintaxe exata podem variar dependendo do sistema de gerenciamento de banco de dados (DBMS) que você está usando.


### funções-de-json
[Voltar ao Topo](#menu)


Estas são funções que operam em dados JSON.

#### JSON_VALUE:

- Descrição: Extrai um valor escalar de um objeto JSON.
    
    Exemplo:

    ```sql
    SELECT 
        JSON_VALUE('{"name": "Alice"}', '$.name') AS UserName;
    ```
    Retorna `Alice`.

#### JSON_QUERY:

- Descrição: Extrai um objeto ou array do JSON.
    
    Exemplo:

    ```sql
    SELECT 
        JSON_QUERY('{"skills": ["SQL", "Python"]}', '$.skills') AS UserSkills;
    ```
    Retorna [`SQL`, `Python`].

#### JSON_OBJECT:

- Descrição: Cria um objeto JSON a partir de pares chave-valor.
    
    Exemplo:

    ```sql
    SELECT 
        JSON_OBJECT('name', 'Alice', 'age', 30) AS UserObject;
    ```
    Retorna {`name`: `Alice`, `age`: `30`}.

#### JSON_ARRAY:

- Descrição: Cria um array JSON a partir de uma lista de valores.
    
    Exemplo:

    ```sql
    SELECT 
        JSON_ARRAY('SQL', 'Python') AS SkillsArray;
    ```
    Retorna [`SQL`, `Python`].

#### JSON_EXISTS:

- Descrição: Verifica se um caminho específico existe dentro de um objeto JSON.
    
    Exemplo:

    ```sql
    SELECT 
        JSON_EXISTS('{"name": "Alice"}', '$.name') AS NameExists;
    ```
    Retorna true se o caminho existir, caso contrário, retorna false.

#### JSON_LENGTH:

- Descrição: Retorna o número de elementos em um array JSON ou o número de pares chave-valor em um objeto JSON.
    
    Exemplo:

    ```sql
    SELECT 
        JSON_LENGTH('{"skills": ["SQL", "Python"]}', '$.skills') AS SkillsCount;
    ```
    Retorna `2`.

#### JSON_KEYS:

- Descrição: Retorna um array contendo as chaves de um objeto JSON.
    
    Exemplo:

    ```sql
    SELECT 
        JSON_KEYS('{"name": "Alice", "age": 30}') AS ObjectKeys;
    ```
    Retorna [`name`, `age`].

#### JSON_REMOVE:

    - Descrição: Remove um ou mais caminhos de um objeto JSON.
    
    Exemplo:

    ```sql
    SELECT 
        JSON_REMOVE('{"name": "Alice", "age": 30}', '$.age') AS UpdatedObject;
    ```
    Retorna {`name`: `Alice`}.

Estas são algumas das principais funções JSON em SQL. Elas são cruciais para trabalhar com dados semi-estruturados em um ambiente relacional. A capacidade de manipular e consultar dados JSON diretamente no SQL oferece uma grande flexibilidade e poder aos desenvolvedores. Assim como outras funções, a disponibilidade e a sintaxe exata dessas funções podem variar dependendo do sistema de gerenciamento de banco de dados (DBMS) que você está usando.

### funções-de-xml
[Voltar ao Topo](#menu)


Estas são funções que operam em dados XML.

#### XML_VALUE:

- Descrição: Extrai um valor de um elemento ou atributo XML.
    
    Exemplo:

    ```sql
    SELECT 
        XML_VALUE('<user><name>Alice</name></user>', '/user/name') AS UserName;
    ```
    Retorna `Alice`.

#### XML_QUERY:

- Descrição: Extrai um fragmento XML usando uma expressão XQuery.
    
    Exemplo:

    ```sql
    SELECT 
        XML_QUERY('<skills><skill>SQL</skill><skill>Python</skill></skills>', '/skills/skill') AS UserSkills;
    ```
    Retorna `<skill>SQL</skill><skill>Python</skill>`.

#### XML_ELEMENT:

- Descrição: Cria um elemento XML com um nome especificado e valor.
    
    Exemplo:

    ```sql
    SELECT 
        XML_ELEMENT(NAME "name", 'Alice') AS UserElement;
    ```
    Retorna `<name>Alice</name>`.

#### XML_ATTRIBUTES:

- Descrição: Cria atributos XML para um elemento.
    
    Exemplo:

    ```sql
    SELECT 
        XML_ELEMENT(NAME "user", XML_ATTRIBUTES('Alice' AS "name")) AS UserAttribute;
    ```
    Retorna `<user name="Alice"/>`.

#### XML_EXISTS:

- Descrição: Verifica se uma expressão XQuery retorna um resultado.
    
    Exemplo:

    ```sql
    SELECT 
        XML_EXISTS('<user><name>Alice</name></user>', '/user/name') AS NameExists;
    ```
    Retorna true se a expressão XQuery retornar um resultado, caso contrário, retorna false.

#### XMLTABLE:

- Descrição: Transforma XML em uma tabela relacional.
    
    Exemplo:

    ```sql
    SELECT 
        name 
    FROM XMLTABLE('/users/user' PASSING '<users><user>Alice</user><user>Bob</user></users>' COLUMNS name VARCHAR(50) PATH '.') AS UserDetails;
    ```
    Retorna uma tabela com nomes `Alice` e `Bob`.

#### XMLSERIALIZE:

- Descrição: Converte um valor XML em uma string.
    
    Exemplo:

    ```sql
    SELECT 
        XMLSERIALIZE('<name>Alice</name>' AS VARCHAR(50)) AS UserName;
    ```
    Retorna a string `Alice`.

#### XMLPARSE:

- Descrição: Converte uma string em um valor XML.
    
    Exemplo:

    ```sql
    SELECT 
        XMLPARSE(CONTENT '<name>Alice</name>') AS UserXML;
    ```
    Retorna o valor XML `<name>Alice</name>`.

Estas são algumas das principais funções XML em SQL. Elas são essenciais para trabalhar com dados estruturados em formato XML em um ambiente relacional. A capacidade de manipular, consultar e transformar dados XML diretamente no SQL oferece uma grande flexibilidade aos desenvolvedores. Assim como outras funções, a disponibilidade e a sintaxe exata dessas funções podem variar dependendo do sistema de gerenciamento de banco de dados (DBMS) que você está usando.

## junções-e-relações
[Voltar ao Topo](#menu)


A capacidade de relacionar tabelas é uma das características mais poderosas dos sistemas de banco de dados relacional. Isso permite que os dados sejam organizados de forma eficiente, evitando redundâncias e facilitando a recuperação de informações de várias tabelas de forma coesa. Vamos mergulhar profundamente neste tópico.

### chaves-primárias-e-estrangeiras
[Voltar ao Topo](#menu)

#### Chave Primária (PK): 

É uma coluna ou conjunto de colunas em uma tabela que identifica exclusivamente cada linha da tabela. Uma PK garante que não haja duas linhas com o mesmo valor e que nenhum valor na coluna da chave primária seja NULL.
        
#### Chave Estrangeira (FK): 

É uma coluna ou conjunto de colunas em uma tabela que é usada para estabelecer e impor um link entre os dados em duas tabelas. Ela estabelece uma relação entre duas tabelas ao referenciar a chave primária de outra tabela. A principal utilidade da FK é garantir a integridade referencial dos dados.

### junções
[Voltar ao Topo](#menu)



#### INNER_JOIN:
    
- Descrição:

O `INNER JOIN` é o tipo de junção mais comum em SQL. Ele retorna as linhas que têm correspondência em ambas as tabelas envolvidas na junção. Se uma linha em uma tabela não tem correspondência na outra, ela não aparece no conjunto de resultados.

- Exemplo:

```sql
SELECT 
    Clientes.Nome
    , Pedidos.PedidoID
FROM Clientes
INNER JOIN Pedidos ON Clientes.ClienteID = Pedidos.ClienteID;
```

Neste exemplo, estamos buscando os nomes dos clientes e os `IDs` dos pedidos, retornando apenas os clientes que possuem pedidos.

- Considerações Avançadas:
        
    - Performance: O uso eficiente de índices nas colunas envolvidas na junção pode melhorar significativamente a performance do `INNER JOIN`.
        
    - Filtragem: O `INNER JOIN` pode ser usado em conjunto com cláusulas `WHERE` para filtrar ainda mais os resultados.

#### LEFT_JOIN

- Descrição:

O `LEFT JOIN` retorna todas as linhas da tabela à esquerda e as linhas correspondentes da tabela à direita. Se não existe correspondência para uma linha da tabela à esquerda, a saída exibe `NULL` para cada coluna da tabela à direita.

- Exemplo:

```sql
SELECT 
    Clientes.Nome
    , Pedidos.PedidoID
FROM Clientes
LEFT JOIN Pedidos ON Clientes.ClienteID = Pedidos.ClienteID;
```

Aqui, todos os clientes serão listados, independentemente de terem feito pedidos.

- Considerações Avançadas:
        
    - Uso com Agregação: `LEFT JOIN` é útil em consultas agregadas para incluir itens que não têm correspondência na tabela à direita.
        
    - Tratamento de NULL: É importante tratar valores `NULL` ao usar `LEFT JOIN`, especialmente ao realizar operações em colunas que podem conter `NULL`.

#### RIGHT_JOIN

- Descrição:

O `RIGHT JOIN` é o inverso do `LEFT JOIN`. Retorna todas as linhas da tabela à direita e as linhas correspondentes da tabela à esquerda. Se não existe correspondência para uma linha da tabela à direita, a saída exibe NULL para cada coluna da tabela à esquerda.

- Exemplo:

```sql
SELECT 
    Clientes.Nome
    , Pedidos.PedidoID
FROM Clientes
RIGHT JOIN Pedidos ON Clientes.ClienteID = Pedidos.ClienteID;
```

Neste caso, todos os pedidos serão listados, mesmo que não tenham um cliente associado.

- Considerações Avançadas:
        
    - Substituição por LEFT JOIN: Em muitos casos, `RIGHT JOIN` pode ser substituído por `LEFT JOIN` reordenando as tabelas na consulta.
        
    - Raridade de Uso: `RIGHT JOIN` é menos comum que `LEFT JOIN`, mas pode ser útil dependendo da estrutura da consulta.

#### FULL_JOIN

- Descrição:

O `FULL JOIN` retorna linhas quando há uma correspondência em pelo menos uma das tabelas. Portanto, ele retorna todas as linhas da tabela à esquerda e todas as linhas da tabela à direita, com as linhas correspondentes de ambos os lados quando disponíveis. Se não houver correspondência, a parte não correspondente exibe `NULL`.

- Exemplo:

```sql
SELECT 
    Clientes.Nome
    , Pedidos.PedidoID
FROM Clientes
FULL JOIN Pedidos ON Clientes.ClienteID = Pedidos.ClienteID;
```

Este exemplo lista todos os clientes e todos os pedidos, correspondentes ou não.

- Considerações Avançadas:
        
    - Uso Específico: `FULL JOIN` é menos comum que `INNER JOIN` e `LEFT JOIN`, mas é muito útil para comparar registros entre tabelas.

    - Tratamento de NULL: Assim como com `LEFT JOIN` e `RIGHT JOIN`, o tratamento de valores NULL é crucial ao usar `FULL JOIN`.

- Conclusão:

Entender as diferenças e usos de cada tipo de junção em SQL é fundamental para a construção de consultas eficientes e precisas. O domínio desses conceitos permite ao desenvolvedor manipular e analisar dados de maneira mais flexível e profunda, atendendo a uma variedade de necessidades e cenários.
### subconsultas
[Voltar ao Topo](#menu)



Uma subconsulta é uma consulta dentro de outra consulta. Ela pode retornar um ou mais valores e é usada em várias situações, como para comparar com um valor ou lista de valores, verificar a existência de dados, entre outros.
        
#### Subconsultas Correlacionadas: 

São subconsultas que são executadas uma vez para cada linha processada pela consulta externa. Elas são chamadas "correlacionadas" porque a subconsulta depende da consulta externa.
        
#### Subconsultas Não Correlacionadas: 

São subconsultas que são executadas apenas uma vez e o resultado é entregue à consulta principal.

Entender junções e relações é fundamental para trabalhar com bancos de dados relacionais. Elas permitem que os analistas de dados explorem e analisem dados de várias tabelas simultaneamente, proporcionando uma visão mais completa e integrada dos dados. Ao dominar esses conceitos, você pode combinar, comparar e analisar dados de várias fontes com facilidade e precisão.

## manipulação-de-dados
[Voltar ao Topo](#menu)


A manipulação de dados é uma parte essencial do trabalho com bancos de dados. Ela se refere ao processo de inserção, atualização, exclusão e gerenciamento de dados armazenados em um banco de dados. Vamos explorar cada um desses aspectos em detalhes:

### inserindo-dados
[Voltar ao Topo](#menu)


#### INSERT
    
- Objetivo:

O comando `INSERT` em SQL é utilizado para adicionar novos registros a uma tabela, permitindo assim a expansão do conjunto de dados armazenados no banco de dados. Este comando é fundamental para a operação de qualquer sistema de gerenciamento de banco de dados, pois possibilita a inclusão de novas informações.

- Sintaxe Básica:

```sql
INSERT INTO nome_tabela (coluna1, coluna2, coluna3, ...)
VALUES (valor1, valor2, valor3, ...);
```

#### Considerações Avançadas:

- `Tipos de Dados`: É essencial garantir que os valores fornecidos correspondam aos tipos de dados das colunas. A tentativa de inserir um tipo de dado incompatível resultará em um erro.

- Exemplo:

```sql
-- Inserir um registro com tipos de dados correspondentes
INSERT INTO Clientes (ClienteID, Nome, Email)
VALUES (1, 'João Silva', 'joao.silva@email.com');
```

- `Inserção Completa`: Se estiver inserindo valores para todas as colunas da tabela, não é necessário especificar os nomes das colunas. No entanto, a ordem dos valores deve corresponder à ordem das colunas na tabela.

- Exemplo:

```sql
-- Inserir um registro sem especificar os nomes das colunas
INSERT INTO Clientes
VALUES (2, 'Maria Oliveira', 'maria.oliveira@email.com');
```

- `Inserção com SELECT`: É possível utilizar o comando `INSERT` juntamente com `SELECT` para inserir registros baseados em resultados de uma consulta.

- Exemplo:

```sql
-- Inserir registros em uma tabela com base em registros de outra tabela
INSERT INTO ClientesVIP (ClienteID, Nome)
SELECT 
    ClienteID
    , Nome
FROM Clientes
WHERE Saldo > 1000;
```

- `Inserção de Múltiplos Registros`: Alguns SGBDs permitem a inserção de múltiplos registros em uma única consulta, o que pode melhorar a eficiência.

- Exemplo:

```sql
-- Inserir múltiplos registros em uma única consulta
INSERT INTO Clientes (Nome, Email)
VALUES ('Carlos Pereira', 'carlos.pereira@email.com'),
       ('Fernanda Costa', 'fernanda.costa@email.com');
```

- `Retorno de IDs Gerados`: Ao inserir registros em tabelas com colunas auto-incrementadas, é útil obter o ID gerado para uso em operações subsequentes.

- Exemplo:

```sql
-- Inserir um registro e retornar o ID gerado
INSERT INTO Clientes (Nome, Email)
VALUES ('Roberto Almeida', 'roberto.almeida@email.com');
SELECT SCOPE_IDENTITY() AS NovoClienteID;
```

- Conclusão:

O comando `INSERT` é uma ferramenta versátil e essencial em SQL, permitindo a inclusão de novos dados no banco de forma variada e eficiente. O entendimento de suas funcionalidades avançadas, como inserção com `SELECT` e retorno de `IDs` gerados, é fundamental para o desenvolvimento de soluções robustas e otimizadas em sistemas de banco de dados.

### atualizando-dados
[Voltar ao Topo](#menu)



#### UPDATE

- Objetivo:

O comando `UPDATE` em SQL tem como objetivo principal modificar registros existentes em uma tabela, permitindo a atualização de um ou mais campos com novos valores. Esse comando é essencial para manter a integridade e a relevância dos dados armazenados em um banco de dados.

- Sintaxe Básica:

```sql
UPDATE nome_tabela
    SET coluna1 = valor1
    , coluna2 = valor2
    , ...
WHERE condição;
```

#### Considerações Avançadas:

- `Cláusula WHERE`: A cláusula `WHERE` é crucial ao utilizar o comando `UPDATE`, pois ela define quais registros serão afetados pela operação. **A ausência dessa cláusula resultará na atualização de todos os registros da tabela, o que pode ter consequências indesejadas.**

- Exemplo:

```sql
-- Atualiza apenas o registro onde o ID é igual a 1
UPDATE Clientes
    SET Nome = 'João Silva'
WHERE ID = 1;
```

- `Testar com SELECT`: Antes de executar um `UPDATE`, é altamente recomendado testar a condição `WHERE` com uma consulta `SELECT` para garantir que apenas os registros desejados sejam selecionados e modificados.

- Exemplo:

```sql
-- Verifica quais registros serão afetados
SELECT 
    * 
FROM Clientes
WHERE Nome LIKE 'João%';
```

- `Atualização com JOIN`: O comando `UPDATE` pode ser combinado com `JOIN` para atualizar registros em uma tabela com base em condições relacionadas a outra tabela.

- Exemplo:

```sql
-- Atualiza os preços dos produtos com base em uma tabela de descontos
UPDATE Produtos p
JOIN Descontos d ON p.ProdutoID = d.ProdutoID
    SET p.Preco = p.Preco - (p.Preco * d.Desconto);
```
ou
```sql
UPDATE p
    SET p.Preco = p.Preco - (p.Preco * d.Desconto)
from Produtos p
JOIN Descontos d ON p.ProdutoID = d.ProdutoID
```

- `Backup e Transações`: Ao realizar atualizações significativas, é prudente fazer backup dos dados e utilizar transações para garantir que as alterações possam ser revertidas em caso de erro.

- Exemplo:

```sql
BEGIN TRANSACTION;

UPDATE Clientes
    SET Cidade = 'São Paulo'
WHERE Estado = 'SP';

-- Se tudo estiver correto, commit, senão rollback
COMMIT;
```

- `Limitar Atualizações`: Dependendo do SGBD, é possível limitar o número de registros atualizados usando cláusulas como `LIMIT` ou `TOP`.

- Exemplo:

```sql
-- Atualiza apenas os 10 primeiros registros que atendem à condição
UPDATE TOP (10) Clientes
    SET Status = 'Inativo'
WHERE Saldo < 0;
```

- Conclusão:

O comando `UPDATE` é uma ferramenta poderosa e essencial em SQL, mas requer cuidado e atenção para evitar a modificação indesejada de dados. O uso de práticas como testar com `SELECT`, utilizar transações e fazer backups são essenciais para operações seguras e eficientes.

### excluindo-dados
[Voltar ao Topo](#menu)

##### DELETE

- Objetivo:

O comando `DELETE` em SQL é utilizado para remover registros existentes de uma tabela. Este comando é vital para a manutenção da integridade e relevância dos dados em um banco de dados, permitindo a remoção de informações obsoletas ou incorretas.

- Sintaxe Básica:

```sql
DELETE FROM nome_tabela WHERE condição;
```

###### Considerações Avançadas:

- `Cláusula WHERE`: A cláusula `WHERE` é indispensável ao utilizar o comando `DELETE`, pois determina quais registros serão removidos. **A ausência dessa cláusula resultará na exclusão de todos os registros da tabela, o que pode ter consequências graves e irreversíveis.**

- Exemplo:

```sql
-- Deletar o registro onde o ID é igual a 1
DELETE FROM Clientes WHERE ClienteID = 1;
```

- `Backup de Dados`: É imperativo realizar backup dos dados antes de executar comandos `DELETE`, especialmente em ambientes de produção, para evitar a perda irreparável de informações importantes.

- `Transações`: Utilizar transações ao executar comandos `DELETE` permite que você reverta a operação caso algo dê errado, garantindo assim a segurança dos dados.

- Exemplo:

```sql
BEGIN TRANSACTION;

DELETE FROM Pedidos WHERE DataPedido < '2022-01-01';

-- Se tudo estiver correto, commit, senão rollback
COMMIT;
```

- `DELETE vs TRUNCATE`: Enquanto `DELETE` remove registros com base em uma condição, o comando `TRUNCATE` remove todos os registros de uma tabela de forma mais eficiente, mas não pode ser usado com uma cláusula `WHERE`.

- Exemplo:

```sql
-- Deletar todos os registros de uma tabela
TRUNCATE TABLE TabelaTemporaria;
```

- `Restrições de Chave Estrangeira`: Ao tentar deletar registros que são referenciados por chaves estrangeiras em outras tabelas, você pode encontrar erros de restrição. É necessário considerar as dependências entre as tabelas e, se necessário, deletar os registros relacionados primeiro.

- Exemplo:

```sql
-- Deletar registros relacionados antes de deletar o registro principal
DELETE FROM Pedidos WHERE ClienteID = 1;
DELETE FROM Clientes WHERE ClienteID = 1;
```

- `Limitar Exclusões`: Dependendo do SGBD, é possível limitar o número de registros deletados usando cláusulas como `LIMIT` ou `TOP`.

- Exemplo:

```sql

-- Deletar apenas os 10 primeiros registros que atendem à condição
DELETE TOP (10) FROM Clientes WHERE Status = 'Inativo';
```

- Conclusão:

O comando `DELETE` é uma ferramenta poderosa em SQL para a manutenção da integridade dos dados, mas requer cuidado e atenção para evitar a exclusão indesejada de informações. O uso de práticas como realização de backups, utilização de transações e consideração de restrições de chave estrangeira são essenciais para operações seguras e eficientes.
### transações
[Voltar ao Topo](#menu)

- Objetivo: 

O principal objetivo das transações em SQL é assegurar a integridade e a consistência dos dados ao agrupar várias operações como uma única unidade de trabalho. Isso é crucial quando se realizam operações complexas que envolvem múltiplas tabelas ou registros, garantindo que, em caso de falha em uma das operações, todas as alterações possam ser revertidas, evitando assim a corrupção dos dados.

- Conceitos Principais:
        
    - `BEGIN TRANSACTION`: Este comando é utilizado para iniciar uma transação. A partir deste ponto, todas as operações realizadas serão parte de uma única unidade de trabalho.
        
    - `COMMIT`: Ao executar este comando, todas as operações realizadas durante a transação são salvas permanentemente no banco de dados.
        
    - `ROLLBACK`: Este comando é utilizado para desfazer todas as operações realizadas durante a transação, revertendo o banco de dados ao seu estado anterior ao início da transação.

- Considerações:


Transações são fundamentais para manter a integridade dos dados em qualquer sistema de banco de dados relacional. Elas garantem que o banco de dados permaneça em um estado consistente, mesmo quando ocorrem erros ou falhas durante a execução das operações.

Utilizar o comando `ROLLBACK` permite que, se algo der errado durante uma transação, o banco de dados seja revertido ao seu estado original, evitando assim a persistência de dados incorretos ou inconsistentes.

É uma prática recomendada sempre utilizar transações ao realizar operações que alteram múltiplos registros ou tabelas, pois isso assegura que o banco de dados mantenha sua integridade e consistência.

Dominar a manipulação de transações é essencial para qualquer profissional que trabalhe com bancos de dados, pois permite interagir efetivamente com os dados, assegurando que as informações sejam precisas, atualizadas e relevantes para as necessidades analíticas ou operacionais.

- Exemplo Prático: 

Suponha que você esteja gerenciando um sistema bancário e queira transferir dinheiro entre duas contas. Isso envolve duas operações: debitar uma conta e creditar outra. Aqui está um exemplo de como você poderia usar transações em SQL para realizar essa tarefa:

```sql
BEGIN TRANSACTION;

UPDATE Contas
    SET Saldo = Saldo - 100
WHERE NumeroConta = 1;

UPDATE Contas
    SET Saldo = Saldo + 100
WHERE NumeroConta = 2;

IF @@ERROR = 0
    COMMIT;
ELSE
    ROLLBACK;
```

Neste exemplo, iniciamos uma transação com `BEGIN TRANSACTION`, realizamos as operações de débito e crédito e, em seguida, verificamos se ocorreu algum erro usando `@@ERROR`. Se não houver erros, confirmamos a transação com COMMIT, caso contrário, revertemos as alterações com ROLLBACK.


## tópicos-avançados
[Voltar ao Topo](#menu)


À medida que nos aprofundamos no mundo do SQL, encontramos tópicos que são essenciais para profissionais que desejam otimizar, proteger e expandir a funcionalidade de seus bancos de dados. Estes tópicos avançados são a espinha dorsal de muitos sistemas de banco de dados em produção e são cruciais para garantir a eficiência, segurança e escalabilidade.

### indexação-e-performance
[Voltar ao Topo](#menu)
        
- Objetivo: 

O principal objetivo da utilização de índices em um banco de dados é otimizar a velocidade e eficiência das consultas, permitindo que os dados sejam recuperados de forma mais rápida e eficaz, melhorando assim o desempenho geral do sistema de banco de dados.
    
- Descrição: 

Um índice é uma estrutura de dados especial que armazena um subconjunto de dados de uma tabela de banco de dados de forma organizada, proporcionando um caminho mais rápido para localização de registros. Sem a presença de índices, o sistema de banco de dados teria que realizar uma varredura completa em cada linha da tabela para encontrar os registros desejados, processo conhecido como "full table scan", que é altamente ineficiente, especialmente para grandes volumes de dados.

A utilização de índices é análoga ao uso de um índice em um livro, onde, ao invés de percorrer todas as páginas para encontrar um tópico, você consulta o índice para localizar a página certa, economizando tempo e esforço.
    
A indexação permite que o banco de dados encontre os dados desejados sem ter que pesquisar cada linha, semelhante a um índice em um livro.
    
- Considerações:
        
É importante notar que, embora os índices sejam extremamente úteis para acelerar as operações de consulta, eles têm um custo. Cada vez que um registro é inserido, atualizado ou excluído, os índices associados também precisam ser atualizados. Isso pode resultar em uma sobrecarga adicional e afetar o desempenho das operações de escrita no banco de dados.

A decisão de quais colunas indexar e como estruturar os índices é uma tarefa complexa e requer uma análise cuidadosa das consultas que serão frequentemente executadas no sistema. Uma compreensão profunda do modelo de dados e das necessidades de negócio é essencial para projetar índices eficientes e otimizar o desempenho do banco de dados.

- Exemplo Prático:

Suponha que temos uma tabela Clientes com milhares de registros e frequentemente realizamos consultas para buscar clientes por nome. Nesse caso, criar um índice na coluna Nome pode significativamente acelerar essas consultas:

```sql
CREATE INDEX idx_nome
ON Clientes (Nome);
```

Com esse índice, as consultas que filtram clientes por nome serão mais rápidas, pois o banco de dados utilizará o índice idx_nome para localizar os registros de forma eficiente, evitando a necessidade de percorrer toda a tabela.

### views
[Voltar ao Topo](#menu)

- Objetivo: 
        
Criar uma representação virtual de uma tabela ou combinação de tabelas.
    
- Descrição:
        
Uma view é uma consulta SQL armazenada que é executada quando a view é chamada. Ela não armazena dados por si só, mas fornece uma maneira de encapsular consultas complexas.
    
- Considerações:

Views são úteis para simplificar consultas complexas, restringir o acesso a partes específicas dos dados ou transformar os dados de uma forma particular para análise.
        
Como as views não armazenam dados, elas sempre refletem os dados atuais das tabelas subjacentes.

- Exemplos Práticos:

```sql
CREATE VIEW vw_ProdutosMaisVendidos AS
SELECT 
    product.ProductID
    , product.Name AS Produto
    , SUM(sales.OrderQty) AS QuantidadeVendida
    , customer.CustomerID
    , CONCAT(person.FirstName, ' ', person.LastName) AS NomeCliente
FROM 
    Sales.SalesOrderDetail sales
JOIN Production.Product product ON sales.ProductID = product.ProductID
JOIN Sales.SalesOrderHeader salesh ON sales.SalesOrderID = salesh.SalesOrderID
JOIN Sales.Customer customer ON salesh.CustomerID = customer.CustomerID
JOIN Person.Person person ON customer.PersonID = person.BusinessEntityID
GROUP BY 
    product.ProductID,
    product.Name,
    customer.CustomerID,
    person.FirstName,
    person.LastName
ORDER BY 
    QuantidadeVendida DESC;
```

Neste exemplo, estamos criando uma VIEW chamada vw_ProdutosMaisVendidos. Estamos juntando várias tabelas:

`SalesOrderDetail`, `Product`, `SalesOrderHeader`, `Customer`, e `Person` para obter as informações necessárias.

A `VIEW` irá listar o ID do produto, o nome do produto, a quantidade total vendida desse produto, o ID do cliente e o nome do cliente. Os resultados serão agrupados por produto e cliente e ordenados pela quantidade vendida em ordem decrescente.

Depois de criar a `VIEW`, você pode consultá-la como faria com qualquer outra tabela:

```sql
SELECT 
    * 
FROM vw_ProdutosMaisVendidos;
```

Isso retornará a lista de produtos mais vendidos, juntamente com as informações do cliente e a quantidade vendida.

Lembre-se de verificar as permissões do banco de dados e ajustar o código conforme necessário, dependendo da versão específica do AdventureWorks que você está usando.

### triggers-e-procedimentos-armazenados
[Voltar ao Topo](#menu)


- Objetivo: 
        
Automatizar e encapsular operações lógicas no nível do banco de dados.
    
- Descrição:
        
Triggers são scripts que são automaticamente executados em resposta a eventos específicos no banco de dados, como inserções, atualizações ou exclusões.
        
Procedimentos armazenados são conjuntos de instruções SQL que podem ser executadas como uma única unidade, permitindo a reutilização de lógica complexa.
    
- Considerações:
        
Triggers podem ser úteis para manter a integridade dos dados, registrar alterações ou automatizar tarefas repetitivas.
        
Procedimentos armazenados podem melhorar a performance ao reduzir o tráfego de rede, pois múltiplas instruções podem ser executadas em uma única chamada.

- Exemplos Práticos:

```sql
CREATE PROCEDURE sp_DetalhesPedidosCliente
    @ClienteID INT
AS
BEGIN
    SELECT 
        salesh.SalesOrderID AS PedidoID
        , salesh.OrderDate AS DataPedido
        , produto.ProductID
        , produto.Name AS NomeProduto
        , salesdetail.OrderQty AS Quantidade
        , salesdetail.UnitPrice AS PrecoUnitario
        , (salesdetail.OrderQty * salesdetail.UnitPrice) AS TotalItem
    FROM 
        Sales.SalesOrderHeader salesh
        JOIN Sales.SalesOrderDetail salesdetail ON salesh.SalesOrderID = salesdetail.SalesOrderID
        JOIN Production.Product produto ON salesdetail.ProductID = produto.ProductID
    WHERE 
        salesh.CustomerID = @ClienteID
    ORDER BY 
        salesh.OrderDate DESC, 
        produto.Name;
END
```

Neste exemplo, estamos criando uma `Stored Procedure` chamada `sp_DetalhesPedidosCliente` que aceita um parâmetro `@ClienteID`. A Procedure irá retornar uma lista de pedidos do cliente especificado, juntamente com os detalhes de cada item do pedido, como ID do produto, nome do produto, quantidade, preço unitário e total do item.

Os resultados serão ordenados pela data do pedido em ordem decrescente e pelo nome do produto.

Depois de criar a Stored Procedure, você pode executá-la passando o ID do cliente como parâmetro:

```sql
EXEC sp_DetalhesPedidosCliente @ClienteID = 1;
```

Isso retornará os detalhes dos pedidos do cliente com ID 1.

Lembre-se de verificar as permissões do banco de dados e ajustar o código conforme necessário, dependendo da versão específica do AdventureWorks que você está usando.

### normalização
[Voltar ao Topo](#menu)



- Objetivo:

A normalização tem como principal objetivo organizar o esquema de um banco de dados relacional de forma a reduzir a redundância de dados e melhorar a integridade dos mesmos, proporcionando uma estrutura de dados mais eficiente e confiável.

- Descrição:

A normalização é um processo sistemático que envolve a decomposição de tabelas em componentes menores e mais manejáveis, enquanto mantém as relações lógicas entre elas. Este processo é realizado através de uma série de regras ou normas, conhecidas como formas normais (1NF, 2NF, 3NF, BCNF, etc.), cada uma delas abordando diferentes aspectos da estrutura e relações das tabelas.

#### Considerações Avançadas:

- Formas Normais: Existem várias formas normais, cada uma com regras específicas. A aplicação sucessiva destas formas normais elimina diferentes tipos de anomalias e redundâncias.

- Exemplo:
    - 1NF: Garante que cada coluna contém valores atômicos, eliminando grupos de valores.
        
    - 2NF: Remove dependências parciais, garantindo que cada atributo não-chave depende totalmente da chave primária.
        
    - 3NF: Elimina dependências transitivas entre atributos não-chave.

- Desnormalização: Em alguns casos, para otimizar a performance de consultas, pode-se optar pela desnormalização, que é o processo inverso da normalização. A desnormalização pode envolver a introdução de redundância controlada e a combinação de tabelas através do uso de técnicas como pré-agregação.

- Exemplo:

```sql
-- Tabela desnormalizada para armazenar informações de pedidos e clientes
CREATE TABLE PedidosClientes (
  PedidoID INT PRIMARY KEY,
  DataPedido DATE,
  ClienteID INT,
  NomeCliente VARCHAR(255),
  Total DECIMAL(10, 2)
);
```

- Integridade Referencial: A normalização frequentemente resulta na criação de relações entre tabelas através de chaves estrangeiras, o que ajuda a manter a integridade referencial dos dados.

- Exemplo:

```sql

 -- Definindo uma chave estrangeira para garantir a integridade referencial
ALTER TABLE Pedidos
ADD FOREIGN KEY (ClienteID) REFERENCES Clientes(ClienteID);
```

- Impacto na Performance: Embora a normalização ofereça benefícios significativos em termos de integridade dos dados e eficiência de armazenamento, ela pode, em alguns casos, levar a um aumento na complexidade das consultas e potencialmente afetar a performance, especialmente em bancos de dados muito grandes.

- Balanceamento: É essencial encontrar um equilíbrio entre a normalização e as necessidades de performance do sistema. O nível ideal de normalização depende dos requisitos específicos de cada aplicação e do volume e natureza dos dados.

- Conclusão:

A normalização é um conceito fundamental em design de banco de dados, proporcionando uma estrutura de dados robusta e consistente. Dominar as técnicas de normalização e entender quando e como aplicá-las ou, em alguns casos, optar pela desnormalização, são habilidades essenciais para profissionais que desejam projetar, otimizar e manter bancos de dados eficientes e confiáveis.


## maiores-erros-em-sql-explicação-e-soluções
[Voltar ao Topo](#menu)

O SQL, apesar de ser uma linguagem poderosa para manipulação e consulta de dados, também é suscetível a erros comuns que podem afetar a performance, a integridade dos dados e a segurança. Vamos explorar alguns dos erros mais comuns, entender por que eles ocorrem e aprender como resolvê-los.

### subqueries-ineficientes
[Voltar ao Topo](#menu)

- Descrição: 
        
Subqueries, quando usadas inadequadamente, podem resultar em operações repetidas e ineficientes, tornando a consulta global muito mais lenta.
    
- Solução:
        
Avalie se uma subquery é realmente necessária. Muitas vezes, uma junção (JOIN) pode ser mais eficiente.
        
Se possível, limite a quantidade de dados retornados pela subquery usando cláusulas como WHERE ou LIMIT.
        
Considere a utilização de CTEs (Common Table Expressions) para tornar as subqueries mais legíveis e otimizáveis.
    
### uso-excessivo-de-wildcards
[Voltar ao Topo](#menu)


- Descrição: 
        
Usar SELECT * retorna todas as colunas de uma tabela, o que pode ser ineficiente, especialmente se a tabela tiver muitas colunas ou se apenas algumas colunas forem realmente necessárias.
    
- Solução:

Especifique explicitamente as colunas que você precisa em sua consulta.
        
Isso não apenas melhora a performance, mas também torna o código mais legível e menos propenso a erros.

### não-utilizar-índices-adequadamente
[Voltar ao Topo](#menu)



- Descrição: 

Índices são cruciais para acelerar consultas, mas se não forem usados ou projetados corretamente, podem resultar em desempenho subótimo.
    
- Solução:

Certifique-se de que as colunas frequentemente consultadas ou filtradas estejam indexadas.
        
Evite índices desnecessários, pois eles podem desacelerar operações de inserção e atualização.

### consultas-n1
[Voltar ao Topo](#menu)

- Descrição: 

Este é um problema comum onde, para cada registro em um conjunto de resultados, é feita uma nova consulta ao banco de dados.
    
- Solução:
        
Use junções para buscar todos os dados relacionados de uma vez, em vez de fazer múltiplas consultas individuais.
    
### não-considerar-a-distribuição-de-dados
[Voltar ao Topo](#menu)

- Descrição: 
        
A performance pode ser afetada se a distribuição de dados em uma coluna não for considerada ao criar índices ou ao escrever consultas.
    
- Solução:
        
Use estatísticas e histogramas para entender a distribuição de dados e otimize suas consultas e índices de acordo.
    
### injeção-de-sql
[Voltar ao Topo](#menu)
        
- Descrição: 
        
Um dos maiores riscos de segurança, onde entradas mal-intencionadas são inseridas em consultas SQL, potencialmente dando acesso não autorizado ou causando danos ao banco de dados.
    
- Solução:
        
Nunca construa consultas SQL concatenando strings diretamente com entradas do usuário.
        
Use consultas parametrizadas ou prepared statements para garantir que as entradas sejam tratadas como dados e não como código SQL.
    
### não-utilizar-transações-quando-necessário
[Voltar ao Topo](#menu)
    
- Descrição: 
        
As transações garantem que um conjunto de operações seja concluído com sucesso antes de ser confirmado. Ignorar transações pode levar a estados inconsistentes.
    
- Solução:
        
Use transações sempre que estiver realizando múltiplas operações que dependam umas das outras.

Estes são apenas alguns dos erros mais comuns em SQL. A chave para escrever SQL eficiente e seguro é entender profundamente a linguagem, o esquema do banco de dados e os dados subjacentes. Com prática e experiência, você pode evitar esses erros e escrever consultas que são rápidas, precisas e seguras.


## estilo-de-código-sql-e-boas-práticas
[Voltar ao Topo](#menu)

A legibilidade e a manutenção do código SQL são tão importantes quanto a eficiência das consultas. Adotar um estilo de código consistente e seguir boas práticas não apenas torna o código mais compreensível, mas também facilita a colaboração entre desenvolvedores e analistas. Vamos explorar o estilo de código, o modelo de escrita CTE e as ferramentas que podem ajudar a manter a qualidade do código.

### estilo-de-código-sql
[Voltar ao Topo](#menu)

- Indentação: Use espaços (geralmente dois ou quatro) para indentar o código e mostrar a estrutura da consulta.
    
- Nomenclatura: Use nomes descritivos para tabelas, colunas e aliases. Evite abreviações obscuras.
    
- Maiúsculas e Minúsculas: Embora o SQL seja insensível a maiúsculas e minúsculas, é comum usar maiúsculas para palavras-chave SQL (por exemplo, SELECT, FROM) e minúsculas para nomes de tabelas e colunas.
    
- Comentários: Use comentários para explicar a lógica complexa, decisões de design ou qualquer aspecto que possa não ser imediatamente óbvio para outros desenvolvedores.

### common-table-expressions-ctes
[Voltar ao Topo](#menu)

- O que são: 
        
CTEs são consultas temporárias que você pode referenciar dentro de uma instrução SELECT, INSERT, UPDATE ou DELETE. Eles são definidos usando a cláusula WITH.
    
#### Benefícios do Uso de CTEs:

- Legibilidade: 
    
CTEs podem dividir consultas complexas em partes menores e mais gerenciáveis, tornando o código mais fácil de entender.
    
- Manutenção: 
        
Ao dividir uma consulta em várias CTEs, é mais fácil modificar ou depurar partes específicas da consulta.
    
- Reutilização: 
        
Uma CTE pode ser referenciada várias vezes na mesma consulta, evitando a repetição de subconsultas.

### ferramentas-e-extensões-para-vscode
[Voltar ao Topo](#menu)



#### SQLFluff:
        
- Descrição: 
        
SQLFluff é um linter para SQL que ajuda a identificar problemas de estilo e potenciais erros no código.
    
- Benefícios: 
        
Além de verificar o estilo, o SQLFluff pode formatar automaticamente o código SQL para seguir um estilo consistente.

#### VSCode SQL Server (mssql)

- Descrição: 
        
Esta extensão permite conectar-se a servidores SQL, executar consultas e visualizar resultados diretamente no VSCode.
    
- Benefícios: 
        
Facilita a escrita e teste de consultas sem sair do ambiente de desenvolvimento.
    
#### SQLTools

- Descrição: 
        
Uma extensão VSCode que oferece suporte a vários bancos de dados, incluindo execução de consultas, visualização de tabelas e muito mais.
    
- Benefícios: 
       
Uma ferramenta versátil que pode se conectar a vários bancos de dados, tornando-a útil para equipes que trabalham com múltiplos sistemas de gerenciamento de banco de dados.

Adotar um estilo de código consistente e usar ferramentas que promovam a qualidade do código são práticas essenciais para qualquer desenvolvedor ou analista SQL. Elas não apenas melhoram a legibilidade e manutenção do código, mas também promovem uma colaboração mais eficaz entre membros da equipe.

## recursos-avançados-em-sql
[Voltar ao Topo](#menu)


O SQL, como linguagem de consulta estruturada, oferece uma variedade de recursos avançados que permitem aos desenvolvedores e analistas de dados manipular e gerenciar dados de maneira mais eficiente e flexível. Vamos explorar alguns desses recursos em detalhes:

### tabelas-temporárias
[Voltar ao Topo](#menu)

- O que são:

Tabelas temporárias são estruturas de armazenamento temporário no SQL Server, que existem apenas durante a duração da sessão ou da consulta que as criou. São úteis para armazenar e manipular um conjunto de resultados temporários. Existem três tipos principais de tabelas temporárias: locais `#`, globais `##` e variáveis de tabela `@`.

- Tipos de Tabelas Temporárias:

    - `Tabelas Temporárias Locais (#)`:
        - Prefixo: `#`
        - Exemplo: `#MinhaTabelaTemp`
        - Escopo: São visíveis apenas na sessão que as criou e são automaticamente descartadas ao final da sessão.
        - Uso: São úteis para armazenar resultados temporários em procedimentos armazenados e blocos de código.

    - `Tabelas Temporárias Globais (##)`:
        - Prefixo: `##`
        - Exemplo: `##MinhaTabelaTempGlobal`
        - Escopo: São visíveis para todas as sessões e são descartadas quando a última sessão que as referencia é encerrada.
        - Uso: São úteis quando múltiplas sessões precisam acessar os mesmos dados temporários.

    - `Variáveis de Tabela (@)`:
        - Prefixo: @
        - Exemplo: `DECLARE @MinhaTabelaTemp AS TABLE (ID INT, Nome NVARCHAR(255))`
        - Escopo: São visíveis apenas na sessão que as criou e têm um escopo ainda mais restrito que as tabelas temporárias locais, geralmente dentro do batch, stored procedure ou função que as criou.
        - Uso: São úteis para armazenar pequenos volumes de dados e quando o escopo restrito é desejável.

- Uso e Benefícios:

Tabelas temporárias são extremamente úteis em diversas situações, como:
- Armazenamento de Resultados Intermediários: Facilitam o processamento de consultas complexas ao armazenar resultados intermediários, evitando a necessidade de subconsultas repetitivas.

- Melhoria de Performance: Podem melhorar significativamente a performance de consultas ao reduzir o tempo de execução e o uso de recursos, especialmente com grandes volumes de dados.

- Divisão de Consultas Complexas: Ajudam a tornar o código mais legível e manutenível ao dividir consultas complexas em etapas lógicas.

- Exemplo Prático:

```sql
-- Criando uma tabela temporária local para armazenar resultados intermediários
CREATE TABLE #ClientesComPedidos
(
    ClienteID INT,
    NomeCliente NVARCHAR(255)
);

-- Inserindo dados na tabela temporária
INSERT INTO #ClientesComPedidos (ClienteID, NomeCliente)
SELECT ClienteID, Nome
FROM Clientes
WHERE EXISTS (SELECT 1 FROM Pedidos WHERE Pedidos.ClienteID = Clientes.ClienteID);

-- Consultando a tabela temporária
SELECT * FROM #ClientesComPedidos;
```

- Considerações Adicionais:
    - Índices: Assim como tabelas permanentes, tabelas temporárias podem ter índices, o que pode otimizar consultas.
        
    - Restrições e Triggers: Tabelas temporárias suportam a definição de restrições e a criação de triggers.
        
    - Limpeza: Embora tabelas temporárias sejam automaticamente descartadas, é uma boa prática excluí-las explicitamente quando não forem mais necessárias, utilizando o comando `DROP TABLE` ou `DROP TABLE IF EXISTS`.

- Conclusão:

O entendimento e a utilização eficiente de tabelas temporárias são essenciais para desenvolvedores SQL, pois oferecem flexibilidade, otimização de performance e organização de código. Conhecer as diferenças e os usos apropriados dos diferentes tipos de tabelas temporárias permite a criação de soluções mais robustas e eficientes em ambientes de banco de dados.

### variáveis
[Voltar ao Topo](#menu)
    
- O que são:

Variáveis em SQL são objetos que armazenam valores temporários, permitindo a manipulação e referência desses valores em consultas, procedimentos armazenados, funções e outros objetos do banco de dados. Elas proporcionam flexibilidade e dinamismo na construção de scripts SQL.

- Declaração e Atribuição:

Variáveis são geralmente declaradas usando a palavra-chave DECLARE e podem ser atribuídas valores usando `SET` ou `SELECT`.

```sql
-- Declaração de variável
DECLARE @MeuNumero INT;

-- Atribuição usando SET
SET @MeuNumero = 10;

-- Atribuição usando SELECT
SELECT @MeuNumero = 20;
```

- Uso e Aplicações Práticas:

Variáveis são extremamente úteis em diversas situações, tais como:
- Armazenamento de Valores Temporários: Permitem armazenar resultados intermediários ou valores que serão referenciados várias vezes em uma consulta ou procedimento.
    
- Parametrização de Consultas: Facilitam a criação de consultas dinâmicas e parametrizadas, especialmente em procedimentos armazenados.
    
- Controle de Fluxo: São utilizadas em estruturas de controle de fluxo, como loops e condicionais, para manipular a lógica de execução de scripts.

```sql
-- Exemplo de uso de variável para parametrização de consulta
DECLARE @ClienteID INT;
SET @ClienteID = 1;

SELECT * FROM Clientes WHERE ClienteID = @ClienteID;
```

- Considerações Avançadas:
        
    - Escopo: O escopo de uma variável refere-se à extensão do código onde ela pode ser referenciada. Variáveis declaradas em um bloco de código, procedimento ou função são locais a esse escopo e não podem ser acessadas fora dele.
        
    - Tipos de Dados: Variáveis podem ser de qualquer tipo de dado disponível no SQL Server, incluindo tipos de dados personalizados e tipos de tabela.
        
    - Inicialização: Variáveis devem ser inicializadas antes de serem utilizadas, caso contrário, o SQL Server retornará um erro.
        
    - Variáveis de Sistema: O SQL Server possui variáveis de sistema predefinidas (por exemplo, `@@ROWCOUNT`), que armazenam valores específicos do sistema e podem ser referenciadas em consultas e procedimentos.

```sql
-- Exemplo de uso de variável de sistema
SELECT 
    * 
FROM Clientes;
PRINT 'Número de linhas afetadas: ' + CAST(@@ROWCOUNT AS NVARCHAR);
```
    
- Conclusão:

O entendimento e a utilização eficiente de variáveis são fundamentais para desenvolvedores SQL, proporcionando a capacidade de criar scripts e consultas mais dinâmicos, flexíveis e reutilizáveis. Através do uso adequado de variáveis, é possível otimizar a performance, melhorar a legibilidade do código e implementar soluções mais robustas e adaptáveis a diferentes necessidades.

### loops
[Voltar ao Topo](#menu)
    
- O que são:

Loops são estruturas de controle de fluxo que permitem a execução repetida de um bloco de código enquanto uma condição especificada é verdadeira. Eles são fundamentais para realizar tarefas repetitivas e iterativas, especialmente em procedimentos armazenados e scripts de manipulação de dados.

- Tipos Comuns:

O tipo mais comum de loop em SQL é o `WHILE`. Este loop continua executando um blobo de código enquanto a condição especificada for verdadeira.

```sql
-- Exemplo de uso do WHILE loop
DECLARE @Contador INT = 0;

WHILE @Contador < 5
BEGIN
    PRINT 'Número: ' + CAST(@Contador AS NVARCHAR);
    SET @Contador = @Contador + 1;
END
```

- Uso e Aplicações Práticas: Embora SQL seja uma linguagem projetada principalmente para operações de conjunto, os loops são particularmente úteis nas seguintes situações:

    - Procedimentos Armazenados e Funções: Loops são frequentemente utilizados em procedimentos armazenados e funções para realizar operações repetitivas, como processamento de linhas de uma tabela.
    
    - Manipulação de Dados: São úteis para tarefas de manipulação de dados, como atualizações em lote, inserções condicionais e exclusões controladas.
    
    - Controle de Fluxo: Permitem a implementação de lógicas complexas de controle de fluxo, especialmente quando combinados com estruturas condicionais como IF.

```sql
-- Exemplo de uso do WHILE loop para atualização em lote
DECLARE @BatchSize INT = 100;
DECLARE @RowsAffected INT = 1;

WHILE @RowsAffected > 0
BEGIN
    UPDATE TOP (@BatchSize) MinhaTabela
    SET Coluna1 = 'NovoValor'
    WHERE Coluna1 IS NULL;

    SET @RowsAffected = @@ROWCOUNT;
END
```
    
- Considerações Avançadas:
        
    - Performance: Loops podem ser menos eficientes que operações de conjunto para grandes volumes de dados. É importante avaliar a performance e considerar alternativas quando apropriado.
        
    - Controle de Transações: Em loops que realizam modificações de dados, é prudente implementar controle de transações para garantir a integridade dos dados.
        
    - Evitar Loops Infinitos: É crucial garantir que a condição de saída do loop seja alcançável, para evitar loops infinitos que podem consumir recursos do servidor.
        
    - Variáveis de Controle: O uso de variáveis para controlar a execução e a condição de saída do loop é uma prática comum e recomendada.

```sql
-- Exemplo de uso do WHILE loop com controle de transações
DECLARE @Contador INT = 0;

BEGIN TRANSACTION;

WHILE @Contador < 5
BEGIN
    -- Código de manipulação de dados
    
    IF @@ERROR <> 0
    BEGIN
        ROLLBACK TRANSACTION;
        PRINT 'Erro detectado. Transação desfeita.';
        RETURN;
    END
    
    SET @Contador = @Contador + 1;
END

COMMIT TRANSACTION;
```

- Conclusão:

O domínio das estruturas de loop é essencial para desenvolvedores SQL, permitindo a criação de soluções mais dinâmicas e adaptáveis. Embora o SQL seja orientado a conjuntos, o uso inteligente de loops pode resolver problemas complexos, otimizar a manipulação de dados e enriquecer a lógica de negócios em procedimentos armazenados e funções.

### defaults
[Voltar ao Topo](#menu)

- O que são:

Defaults são valores predefinidos atribuídos automaticamente a uma coluna no caso de uma operação de `INSERT` não especificar um valor para essa coluna. Eles servem como um mecanismo de segurança para garantir que os registros mantenham a integridade, preenchendo campos que, de outra forma, seriam deixados em branco.

- Uso e Aplicações Práticas: Defaults são extremamente úteis em diversas situações, como:
    - Garantir Valores Não Nulos: São utilizados para assegurar que uma coluna sempre tenha um valor, evitando a inserção de nulos onde não são permitidos.
    
    - Simplificar Inserções: Facilitam operações de inserção, uma vez que o usuário não precisa fornecer um valor para cada coluna.
    
    - Valores de Auditoria: Frequentemente usados para atribuir automaticamente timestamps de criação e modificação de registros.

```sql
-- Exemplo de criação de tabela com valor default
CREATE TABLE Produtos (
    ProdutoID INT PRIMARY KEY,
    Nome NVARCHAR(255) NOT NULL,
    Preco DECIMAL(10, 2) NOT NULL,
    DataCriacao DATETIME DEFAULT GETDATE() -- Atribui a data e hora atual como valor default
);

-- Inserindo um registro sem especificar DataCriacao
INSERT INTO Produtos (ProdutoID, Nome, Preco) VALUES (1, 'Produto A', 100.00);

-- Consultando a tabela
SELECT * FROM Produtos;
```
- Considerações Avançadas:

    - Tipos de Defaults:
        - Valores Constantes: Podem ser valores fixos, como números, strings ou datas.
            
        - Funções de Sistema: Como `GETDATE()` para timestamps ou `NEWID()` para GUIDs.
            
        - Expressões: Expressões que calculam um valor baseado em outras colunas ou funções.

        - Constraints DEFAULT: Defaults podem ser definidos como constraints, permitindo nomeação e gerenciamento mais fácil.
            
Podem ser alterados ou removidos posteriormente usando `ALTER TABLE`.

```sql
-- Exemplo de criação de constraint DEFAULT
ALTER TABLE Produtos
ADD CONSTRAINT DF_Produtos_DataCriacao DEFAULT GETDATE() FOR DataCriacao;

    Defaults e NULLs:
        Se um valor default é definido para uma coluna, mas um NULL é explicitamente inserido, o NULL sobrescreverá o valor default.
        Para garantir um valor não nulo, a coluna deve ser definida como NOT NULL.
```
    
- Conclusão:

O entendimento e a aplicação adequada de valores default são essenciais para manter a integridade dos dados e simplificar operações de inserção. Eles oferecem uma maneira eficiente de gerenciar valores não fornecidos, automatizar a atribuição de valores e garantir a consistência dos dados em um banco de dados relacional. O uso estratégico de defaults, aliado ao conhecimento de suas nuances, permite aos desenvolvedores SQL criar soluções mais robustas e eficientes.

### identity
[Voltar ao Topo](#menu)

- O que é:

A propriedade `Identity` no SQL é uma propriedade de coluna que gera automaticamente valores numéricos sequenciais. Cada novo registro inserido na tabela recebe um valor único e incremental na coluna Identity, geralmente utilizada como chave primária para garantir a unicidade dos registros.

```sql
-- Exemplo de criação de tabela com coluna Identity
CREATE TABLE Clientes (
    ClienteID INT IDENTITY(1,1) PRIMARY KEY,
    Nome NVARCHAR(255) NOT NULL
);
```
- Uso e Aplicações Práticas: A propriedade Identity é amplamente utilizada em cenários onde:

    - Identificador Único: É necessário um identificador único para cada linha, e o valor exato desse identificador não é crucial.
    
    - Autoincremento: É preciso evitar a geração manual de identificadores, garantindo que cada novo registro seja automaticamente numerado de forma sequencial.
    
    - Chave Primária: Serve como uma solução prática para a criação de chaves primárias em tabelas, assegurando a integridade referencial.

```sql
-- Inserindo registros em uma tabela com coluna Identity
INSERT INTO Clientes (Nome) VALUES ('Carlos'), ('Ana');

-- Consultando a tabela
SELECT * FROM Clientes;
```

- Benefícios e Considerações Avançadas:
        
    - Unicidade e Integridade: A propriedade Identity assegura a unicidade dos registros e contribui para a integridade dos dados, eliminando a possibilidade de conflitos de identificadores.
        
    - Performance: Contribui para a eficiência das operações de inserção e consulta, especialmente em tabelas com grande volume de dados.
        
    - SEED e INCREMENT: Ao definir uma coluna Identity, é possível especificar o valor inicial (SEED) e o incremento, controlando assim a geração de valores.
        
    - RESET: É possível redefinir o valor Identity utilizando comandos como DBCC CHECKIDENT.
        
    - SCOPE_IDENTITY(): A função `SCOPE_IDENTITY()` pode ser utilizada para recuperar o último valor Identity inserido na sessão atual.

```sql
-- Exemplo de uso da função SCOPE_IDENTITY()
INSERT INTO Clientes (Nome) VALUES ('Julia');
SELECT SCOPE_IDENTITY() AS NovoClienteID;
```
    
IDENTITY_INSERT: O SQL Server permite a inserção explícita de valores em colunas Identity através do comando SET IDENTITY_INSERT Tabela ON, mas seu uso deve ser feito com cautela.

```sql
-- Exemplo de uso de IDENTITY_INSERT
SET IDENTITY_INSERT Clientes ON;
INSERT INTO Clientes (ClienteID, Nome) VALUES (10, 'Roberto');
SET IDENTITY_INSERT Clientes OFF;
```

- Conclusão:

A compreensão e utilização eficaz da propriedade Identity são fundamentais para desenvolvedores SQL, proporcionando maior flexibilidade, eficiência e integridade na manipulação de dados. Este recurso, juntamente com suas funcionalidades associadas, permite a otimização de consultas, a simplificação de tarefas complexas e a garantia de unicidade e integridade dos registros em bancos de dados relacionais.

## sql-para-análise-de-dados
[Voltar ao Topo](#menu)


A linguagem SQL, embora tradicionalmente associada à gestão de bancos de dados, é uma ferramenta poderosa para análise de dados. Ela permite que analistas e cientistas de dados acessem, transformem e analisem grandes volumes de dados diretamente na fonte. Vamos explorar como o SQL pode ser usado para esses propósitos:

### técnicas-de-limpeza-de-dados
[Voltar ao Topo](#menu)

- O que é: 
        
A limpeza de dados envolve a identificação e correção (ou remoção) de erros e inconsistências em dados para melhorar sua qualidade. É um passo crucial antes de qualquer análise.
    
- Técnicas comuns em SQL:
        
Remoção de duplicatas: Utilizando DISTINCT ou combinando GROUP BY e funções de agregação.
        
Tratamento de valores nulos: Usando funções como IS NULL, COALESCE ou NULLIF.
        
Padronização de strings: Funções como UPPER(), LOWER(), TRIM() e REPLACE() ajudam a manter a consistência.
        
Conversão de tipos de dados: Funções como CAST() ou CONVERT().
    
- Benefícios: 
        
Dados limpos e de alta qualidade são essenciais para análises precisas e tomada de decisões informadas.

### análise-exploratória-com-sql
[Voltar ao Topo](#menu)

- O que é: 
        
A análise exploratória é o processo de examinar conjuntos de dados para resumir suas características, frequentemente com métodos visuais.
    
- Técnicas comuns em SQL:
        
Estatísticas descritivas: Usando funções como AVG(), MIN(), MAX(), STDEV().
        
Distribuição de valores: GROUP BY combinado com funções de agregação.
        
Identificação de outliers: Combinando funções de janela com lógica condicional.
    
- Benefícios: 
        
Fornece uma compreensão inicial dos dados, identifica tendências, padrões e anomalias.

### funções-analíticas-e-janelas
[Voltar ao Topo](#menu)

- O que são: 
        
As funções analíticas operam sobre um grupo de linhas, possivelmente particionando o conjunto de linhas em "janelas" baseadas em valores de colunas.
    
- Exemplos comuns:
        
    ROW_NUMBER(): Atribui um número único a cada linha.
    LAG() e LEAD(): Acessa dados de linhas anteriores ou subsequentes.
    FIRST_VALUE() e LAST_VALUE(): Retorna o primeiro ou último valor em uma janela.
    RANK() e DENSE_RANK(): Atribui um rank a cada linha, com DENSE_RANK() não deixando lacunas em rankings quando há empates.
    
- Uso: 

Essas funções são extremamente úteis para análises que exigem comparação entre linhas, cálculos cumulativos ou análises de séries temporais.
    
- Benefícios: 
        
Permitem análises mais complexas e detalhadas sem a necessidade de subconsultas ou tabelas temporárias.

O SQL, quando usado para análise de dados, oferece uma maneira eficiente e direta de obter insights a partir de grandes conjuntos de dados. Ao dominar essas técnicas, os analistas podem extrair valor dos dados de maneira mais rápida e informada, diretamente na fonte.

## diferenças-entre-dbmss
[Voltar ao Topo](#menu)

A variedade de Sistemas de Gerenciamento de Banco de Dados (DBMS) disponíveis no mercado oferece uma ampla gama de funcionalidades, desempenho e características específicas. Embora todos sigam os princípios fundamentais do SQL, cada um tem suas peculiaridades. Vamos explorar as diferenças mais notáveis:

### modelo-ansi
[Voltar ao Topo](#menu)

O SQL ANSI (American National Standards Institute) é um padrão que define a linguagem SQL (Structured Query Language) para manipulação e consulta de dados em sistemas de gerenciamento de banco de dados relacionais (RDBMS). O SQL ANSI estabelece as regras e convenções para a linguagem SQL, garantindo que os comandos SQL sejam consistentes entre diferentes sistemas de banco de dados, como MySQL, PostgreSQL, SQL Server, Oracle, etc.
Instâncias do SQL ANSI:

O SQL ANSI é composto por várias "instâncias" ou partes, cada uma abordando diferentes aspectos da linguagem SQL. Algumas das principais instâncias incluem:

- SQL/Framework: Define a estrutura geral da linguagem SQL e estabelece as bases para outras instâncias.

- SQL/Foundation:Define a sintaxe básica e os elementos fundamentais da linguagem SQL, como tipos de dados, operadores, funções de agregação, etc.
    
- SQL/CLI (Call-Level Interface): Define a interface de chamada de procedimento para comunicação entre aplicações cliente e servidores de banco de dados.
    
- SQL/PSM (Persistent Stored Modules): Define a sintaxe e a semântica para rotinas armazenadas, como procedimentos armazenados e funções, triggers, etc.

- Principais Comandos SQL ANSI:

    - DDL (Data Definition Language):
        
        - CREATE: Utilizado para criar objetos no banco de dados, como tabelas, índices, etc.
        
        - ALTER: Utilizado para modificar a estrutura de objetos existentes no banco de dados.
        
        - DROP: Utilizado para excluir objetos do banco de dados.

    - DML (Data Manipulation Language):
        
        - SELECT: Utilizado para consultar e recuperar dados de uma ou mais tabelas.
        
        - INSERT: Utilizado para inserir novas linhas em uma tabela.
        
        - UPDATE: Utilizado para modificar dados existentes em uma tabela.
        
        - DELETE: Utilizado para excluir linhas de uma tabela.

    - DCL (Data Control Language):
        
        - GRANT: Utilizado para conceder privilégios de acesso a objetos do banco de dados a usuários ou roles.
        
        - REVOKE: Utilizado para remover privilégios de acesso concedidos anteriormente.

    - TCL (Transaction Control Language):
        
        - COMMIT: Utilizado para salvar permanentemente as alterações feitas por uma transação.
        
        - ROLLBACK: Utilizado para desfazer as alterações feitas por uma transação.
        
        - SAVEPOINT: Define um ponto na transação ao qual você pode posteriormente fazer um ROLLBACK.
        
        - SET TRANSACTION: Configura as propriedades da transação.

    - Cláusulas e Operadores:
        
        - WHERE: Utilizado para filtrar os resultados de uma consulta.
        
        - GROUP BY: Utilizado para agrupar linhas que têm os mesmos valores em colunas específicas.
        
        - HAVING: Utilizado para filtrar grupos após a agregação.
        
        - ORDER BY: Utilizado para ordenar os resultados de uma consulta.
        
        - JOIN: Utilizado para combinar linhas de duas ou mais tabelas com base em uma condição relacionada.

O SQL ANSI serve como base para a implementação de SQL em diferentes sistemas de gerenciamento de banco de dados, embora cada sistema possa ter suas próprias extensões e variações da linguagem padrão.
### sintaxes-específicas-de-diferentes-dbmss
[Voltar ao Topo](#menu)

- O que são: 
        
Enquanto a linguagem SQL tem um padrão definido pelo ANSI, cada DBMS pode ter variações em sua sintaxe ou oferecer extensões à linguagem.
    
- Exemplos comuns:
        
Limitação de resultados: Enquanto o MySQL usa LIMIT, o SQL Server utiliza TOP, e o Oracle emprega ROWNUM ou FETCH FIRST.
        
- Concatenação de strings: 
        
O SQL Server usa +, o Oracle utiliza ||, e o PostgreSQL oferece a função CONCAT().
    
- Benefícios: 
    
Conhecer essas diferenças permite que os desenvolvedores escrevam consultas otimizadas e compatíveis para cada DBMS.

### funções-e-características-exclusivas
[Voltar ao Topo](#menu)
    
- O que são: 
        
Além das funções padrão do SQL, muitos DBMSs introduzem funções e características que são exclusivas ou implementadas de maneira única.
    
- Exemplos comuns:
        
- Funções de janela: 
    
Embora muitos DBMSs modernos suportem funções de janela, a implementação e as funções disponíveis podem variar.
        
- Extensões geoespaciais: 
        
PostGIS para PostgreSQL e Spatial Extensions para MySQL são exemplos de extensões que fornecem capacidades geoespaciais avançadas.
    
- Benefícios: 
        
Essas características exclusivas podem ser decisivas ao escolher um DBMS para necessidades específicas, como análise geoespacial ou processamento de séries temporais.

### casos-de-uso-e-quando-escolher-cada-dbms
[Voltar ao Topo](#menu)

- O que são: 
        
Cada DBMS foi projetado com certos casos de uso em mente, seja para lidar com grandes volumes de dados, alta concorrência, análise em tempo real, entre outros.
    
- Exemplos comuns:
        
- MySQL: 

Ideal para aplicações web devido à sua simplicidade e desempenho.
        
- Oracle: 
            
Preferido por grandes corporações que precisam de robustez e uma ampla gama de recursos.
        
- PostgreSQL: 
            
Conhecido por sua extensibilidade e conformidade com padrões.
        
- SQL Server: 
            
Integrado ao ecossistema Microsoft, é frequentemente escolhido por empresas que utilizam outras soluções da Microsoft.
    
- Benefícios: 
        
Entender os pontos fortes e fracos de cada DBMS ajuda a tomar decisões informadas ao iniciar um novo projeto ou ao migrar dados existentes.

Ao explorar as diferenças entre os DBMSs, é crucial lembrar que não existe uma solução única para todos. A escolha do DBMS certo depende das necessidades específicas do projeto, do orçamento, da experiência da equipe e de outros fatores. Conhecer as nuances de cada sistema permite uma implementação mais eficiente e eficaz.

## prática-e-projetos-reais
[Voltar ao Topo](#menu)

A teoria é fundamental, mas a prática é o que solidifica o conhecimento. Ao trabalhar com dados do mundo real, os alunos enfrentam desafios e situações que não são comuns em exemplos de livros didáticos. O banco de dados AdventureWorks da Microsoft é um excelente exemplo de um conjunto de dados do mundo real que simula uma empresa fictícia e seus processos de negócios.

### análise-de-um-conjunto-de-dados-do-mundo-real
[Voltar ao Topo](#menu)

- O que é o AdventureWorks: 
        
O AdventureWorks é um banco de dados de exemplo da Microsoft que simula uma empresa de venda de bicicletas e acessórios. Ele contém uma variedade de tabelas, vistas e procedimentos que representam diferentes aspectos dos negócios, como vendas, produtos, funcionários e mais.
    
- Benefícios: 
        
Trabalhar com o AdventureWorks permite que os alunos se familiarizem com uma estrutura de banco de dados complexa, entendam relações entre tabelas e pratiquem consultas em um ambiente semelhante ao que encontrariam em muitas empresas.

### resolução-de-problemas-comuns-do-dia-a-dia
[Voltar ao Topo](#menu)

- Desafios típicos: 
        
Com o AdventureWorks, os alunos podem enfrentar desafios como determinar os produtos mais vendidos, analisar tendências de vendas ao longo do tempo, identificar os funcionários de melhor desempenho e muito mais.
    
- Soluções práticas: 
        
Ao resolver esses problemas, os alunos aplicarão conceitos aprendidos no curso, como junções, funções agregadas e subconsultas, para obter insights valiosos dos dados.

### construção-de-um-mini-projeto
[Voltar ao Topo](#menu)

- Sistema de Gerenciamento de Pedidos: 
        
Os alunos podem criar um sistema simplificado que permite inserir, atualizar e excluir pedidos, bem como visualizar detalhes do pedido e históricos de clientes.
    
- Dashboard Analítico: 
        
Utilizando as informações de vendas e produtos, os alunos podem construir um dashboard que mostra métricas-chave, como vendas mensais, categorias de produtos mais populares e tendências de vendas.
    
- Benefícios: 
        
Ao construir um projeto prático, os alunos não apenas aplicam seus conhecimentos de SQL, mas também aprendem a pensar criticamente sobre os dados, a tomar decisões baseadas em insights e a apresentar suas descobertas de forma clara e concisa.

Ao final deste módulo, os alunos terão uma compreensão profunda de como o SQL é usado no mundo real e estarão bem preparados para enfrentar desafios semelhantes em suas carreiras.

## recursos-para-aprendizado-contínuo
[Voltar ao Topo](#menu)

- Documentação Oficial: 
        
Sempre uma fonte confiável para entender funções e características específicas de um DBMS.
    
- Cursos Online e Workshops: 
        
Plataformas como Coursera, Udemy e edX oferecem cursos avançados que podem ajudar a aprofundar conhecimentos específicos.
    
- Comunidades e Fóruns: 
        
Sites como Stack Overflow e Reddit têm comunidades ativas onde os profissionais de SQL discutem problemas, compartilham soluções e oferecem conselhos.

Ao adotar essas melhores práticas e utilizar os recursos certos, os profissionais de SQL não apenas melhoram sua eficiência, mas também garantem que suas consultas sejam robustas, escaláveis e fáceis de manter.

## conclusão-e-próximos-passos
[Voltar ao Topo](#menu)


Ao chegar ao final deste curso, os alunos terão adquirido uma compreensão profunda e prática do SQL, desde os fundamentos até os tópicos mais avançados. No entanto, o aprendizado é um processo contínuo, e é essencial refletir sobre o que foi aprendido e considerar os próximos passos na jornada de aprimoramento profissional.

## projeto-final
[Voltar ao Topo](#menu)

- Exame Abrangente: 
        
Um teste final que abrange todos os tópicos discutidos ao longo do curso, garantindo que os alunos tenham assimilado os conceitos essenciais.

- Feedback do Curso: 
        
Uma oportunidade para os alunos avaliarem o curso, fornecendo feedback sobre os conteúdos, metodologia e áreas de melhoria. Isso é vital para aprimorar futuras edições do curso.

## recomendações-para-aprendizado-avançado
[Voltar ao Topo](#menu)

### integração-sql-com-outras-ferramentas
[Voltar ao Topo](#menu)


Explorar como o SQL pode ser integrado a ferramentas de visualização de dados, como Tableau ou Power BI, para criar dashboards interativos e relatórios.
    
### aprendizado-de-outras-linguagens-relacionadas-a-banco-de-dados
[Voltar ao Topo](#menu)


Considerar a aprendizagem de linguagens como PL/SQL (Oracle) ou T-SQL (SQL Server) para aprimorar ainda mais as habilidades em banco de dados.
    
### dbt-data-build-tool
[Voltar ao Topo](#menu)

Explorar ferramentas como DBT, que permitem que os desenvolvedores apliquem práticas de engenharia de software ao desenvolvimento de pipelines de dados.

## conclusão
[Voltar ao Topo](#menu)

O SQL é uma linguagem poderosa e versátil que permite aos desenvolvedores e analistas de dados acessar, manipular e analisar dados de maneira eficiente e eficaz. Ao dominar o SQL, você pode se tornar um profissional mais eficiente, produtivo e valioso para sua organização.




Selo:

[<img src="image.png" width="100" height="100">](https://github.com/Linhares015)

