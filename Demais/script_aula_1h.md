# Aula: SQL para Analistas de Negócios e BI usando SQL Server 🧙‍♂️

## Introdução:

- Apresentação Pessoal: 

    - Nome: Tiago Linhares;
    - Cargo: Analytics Engineer;
    - Experiência: 2 anos de TI, focado em Dados;
    - [Meu Linkedin](https://www.linkedin.com/in/tiago-linhares/)
    - [Meu Github](https://github.com/Linhares015)
    - [Meu Livro - Guia para se Tornar um Analista de Dados](https://www.amazon.com.br/dp/B0CDDFZMLD?ref_=cm_sw_r_mwn_dp_VT4QMG06XS904M6EEQ3A)
    - [Material Curso Completo](https://github.com/Linhares015/curso_sql)

## Módulo 1: Conceitos Básicos de Banco de Dados

<p align="center">
  <img src="https://horadecodar.com.br/wp-content/uploads/2023/06/banco-de-dados.png" width="400" height="280">
</p>

- O que é um Banco de Dados?
    - `Definição`: Um banco de dados é um conjunto organizado de dados, armazenados e acessados eletronicamente a partir de um sistema de computador. Os bancos de dados permitem que os usuários armazenem, recuperem, atualizem e gerenciem uma grande quantidade de informações de maneira eficiente e segura.

    - `Importância`: Em um mundo cada vez mais orientado por dados, os bancos de dados desempenham um papel crucial em quase todos os aspectos dos negócios e da tecnologia. Eles são a espinha dorsal de muitos sistemas, desde sites e aplicativos móveis até sistemas de gerenciamento de recursos empresariais e plataformas de comércio eletrônico.

- Como os dados são armazenados e organizados?
    - Os dados em um banco de dados são armazenados em `tabelas`. Cada tabela é composta por `linhas (registros)` e `colunas (campos)`. As tabelas são `inter-relacionadas`, o que permite que os dados sejam acessados e organizados de várias maneiras. Além disso, os bancos de dados modernos usam sistemas de gerenciamento de banco de dados `(SGBD)` para garantir a integridade, segurança e eficiência dos dados armazenados.

- DBMS:
    - `Definição DBMS`: Um DBMS é um software que permite criar, definir e manipular bancos de dados para vários aplicativos.
    
- Tipos de DBMS
    - `RDBMS (Relational Database Management System)`: Baseia-se no modelo relacional onde os dados são armazenados em tabelas. Exemplos: MySQL, PostgreSQL, Oracle.
    
    - `NoSQL`: Não usa o modelo relacional tradicional. Exemplos: MongoDB (baseado em documentos), Cassandra (baseado em colunas), Redis (armazenamento de valor-chave).

- Cloud X On-Premises
    - `Cloud`: Modelos de computação em que os recursos de TI são fornecidos como um serviço através da internet.
        - `Vantagens`: Escalabilidade, Custo, Manutenção, Acessibilidade.
        - `Desvantagens`: Latência, Segurança.
    
    - `On-Premises`: Modelos de computação em que os recursos de TI são hospedados e gerenciados localmente, geralmente nas instalações da própria organização.
        - `Vantagens`: Controle, Personalização, Segurança.
        - `Desvantagens`: Custo, Manutenção, Escalabilidade.

## Módulo 2: Consultas Básicas em SQL

- SELECT: A Base de Tudo:
    - A instrução `SELECT` é usada para selecionar dados de uma ou mais tabelas. A estrutura básica consiste em especificar as colunas desejadas, seguidas pela cláusula `FROM` e o nome da tabela.
    
    Exemplo Prático:
    ```sql
    SELECT --Selecione 
        coluna1  --O que
        , coluna2
    FROM nome_da_tabela; --De onde
    ```
    - Filtrando Dados: A cláusula `WHERE` é usada para filtrar registros com base em uma ou mais condições.

    Exemplo Prático:
    ```sql
    SELECT --Selecione
        coluna1 --O que
        , coluna2
    FROM nome_da_tabela --De onde
    WHERE coluna1 = 'valor'; --Quando
    ```

- Funções Úteis para Analistas:
    - `COUNT`: Conta o número de registros em uma coluna.
    
    Exemplo Prático:
    ```sql
    SELECT 
        COUNT(coluna1) --Conte
    FROM nome_da_tabela; --De onde
    ```        
    
    - `SUM`: Soma os valores em uma coluna.

    Exemplo Prático:
    ```sql
    SELECT 
        SUM(coluna1) --Some
    FROM nome_da_tabela; --De onde
    ```
    
    - `AVG`: Calcula a média dos valores em uma coluna.

    Exemplo Prático:
    ```sql
    SELECT 
        AVG(coluna1) --Calcule a média
    FROM nome_da_tabela; --De onde
    ```

    - `MIN`: Retorna o menor valor de uma coluna.

    Exemplo Prático:
    ```sql
    SELECT 
        MIN(coluna1) --Retorne o menor valor
    FROM nome_da_tabela; --De onde
    ```

    - `MAX`: Retorna o maior valor de uma coluna.

    Exemplo Prático:
    ```sql
    SELECT 
        MAX(coluna1) --Retorne o maior valor
    FROM nome_da_tabela; --De onde
    ```

- Ordenação e Agrupamento de Dados
    - `ORDER BY`: Ordena os registros com base em uma ou mais colunas. Pode ser ascendente (ASC) ou descendente (DESC).

    Exemplo Prático:
    ```sql
    SELECT
        coluna1
        , coluna2
    FROM nome_da_tabela
    ORDER BY coluna1 ASC; --Ordene
    ```
    
    - `GROUP BY`: Agrupa registros com base em uma ou mais colunas, geralmente usado com funções agregadas.

    Exemplo Prático:
    ```sql
    SELECT
        coluna1
        , coluna2
    FROM nome_da_tabela
    GROUP BY coluna1; --Agrupe
    ```

## Módulo 3: Joins e Relacionamentos
- Chaves Primárias:
    - `Conceito`: Uma chave primária é uma coluna ou conjunto de colunas em uma tabela que identifica exclusivamente cada linha da tabela. Ela garante que cada registro na tabela seja único.
    
    - `Importância`: As chaves primárias são essenciais para a integridade dos dados, pois evitam a duplicação de registros e permitem referências rápidas e eficientes.

- Chaves Estrangeiras:
    - `Conceito`: Uma chave estrangeira é uma coluna ou conjunto de colunas em uma tabela que é usada para estabelecer e impor um link entre os dados em duas tabelas. Ela estabelece uma relação entre duas tabelas ao referenciar a chave primária de outra tabela.
    
    - `Importância`: As chaves estrangeiras são cruciais para manter a integridade referencial dos dados, garantindo que as relações entre as tabelas sejam mantidas corretamente.

- Como identificar e usar em joins:
    Ao projetar ou analisar um banco de dados, as chaves primárias geralmente são indicadas com um ícone de chave ou `PK`, enquanto as chaves estrangeiras podem ser indicadas com `FK`.
    Ao realizar joins entre tabelas, as chaves estrangeiras de uma tabela são frequentemente usadas para se juntar à chave primária da tabela relacionada.

- Joins:
    - `Definição`: Joins são operações que permitem combinar registros de duas ou mais tabelas em um banco de dados relacional com base em colunas relacionadas entre elas.

    - `Importância`: Em bancos de dados relacionais, os dados são frequentemente distribuídos em várias tabelas para evitar redundâncias e melhorar a eficiência. No entanto, para análises e relatórios, muitas vezes é necessário combinar informações de diferentes tabelas. Joins facilitam essa combinação, permitindo que analistas e desenvolvedores obtenham uma visão unificada dos dados.

- Tipos de Joins:
    - `INNER JOIN`: Retorna registros que têm valores correspondentes em ambas as tabelas.

    Exemplo Prático:
    ```sql
    SELECT
        coluna1
        , coluna2
    FROM tabela1
    INNER JOIN tabela2 --Retorne registros que tenham valores correspondentes
        ON tabela1.coluna1 = tabela2.coluna1; --em ambas as tabelas
    ```

    - `LEFT JOIN`: Retorna todos os registros da tabela à esquerda e os registros correspondentes da tabela à direita. Se não houver correspondência, o resultado é `NULL` na tabela à direita.

    Exemplo Prático:
    ```sql
    SELECT
        coluna1
        , coluna2
    FROM tabela1
    LEFT JOIN tabela2 --Retorne todos os registros da tabela à esquerda
        ON tabela1.coluna1 = tabela2.coluna1; --e os registros correspondentes da tabela à direita
    ```
    
    - `RIGHT JOIN`: Retorna todos os registros da tabela à direita e os registros correspondentes da tabela à esquerda. Se não houver correspondência, o resultado é `NULL` na tabela à esquerda.

## Módulo 4: Dicas e Sacadas do Dia a Dia

- Uso de Views
    - `O que são`: Views são consultas armazenadas que agem como tabelas virtuais. Elas permitem que você salve uma consulta específica e a reutilize como se fosse uma tabela.

    - Por que são úteis:
        - `Simplificação`: Views podem simplificar consultas complexas, transformando-as em uma "tabela" única e fácil de usar.
        
        - `Segurança`: Ao criar uma view, você pode escolher quais colunas e registros são visíveis, protegendo dados sensíveis.
        
        - `Reutilização`: Uma vez criada, a view pode ser reutilizada em várias consultas, garantindo consistência e reduzindo a repetição.

        Exemplo Prático:
        
        Suponha que frequentemente você consulte os detalhes do cliente juntamente com seus pedidos mais recentes.

        ```sql
        CREATE VIEW vw_ClientesRecentes 
        AS
        
        SELECT 
            Clientes.Nome
            , Pedidos.Produto
            , Pedidos.DataPedido
        FROM Clientes
        INNER JOIN Pedidos ON Clientes.ClienteID = Pedidos.ClienteID
        WHERE Pedidos.DataPedido > DATEADD(MONTH, -1, GETDATE());
        ```

- Tabelas Temporárias e Variáveis
    - `Tabelas Temporárias`: São tabelas que existem apenas durante a sessão ou consulta atual.

    Exemplo Prático:
    ```sql
    CREATE TABLE #TempClientes (ClienteID INT, Nome NVARCHAR(100));
    INSERT INTO #TempClientes 
    SELECT 
    ClienteID
    , Nome 
    FROM Clientes WHERE Ativo = 1;
    ```    
    - `Variáveis`: Permitem armazenar valores temporários para uso em uma consulta ou procedimento.

    Exemplo Prático:
    ```sql
    DECLARE @DataRecente DATE;
    SET @DataRecente = GETDATE();
    SELECT 
        * 
    FROM Pedidos WHERE DataPedido > @DataRecente;
    ```
    - Quando e por que usar:
        - `Análise Intermediária`: Tabelas temporárias são úteis quando você precisa de um lugar para armazenar dados intermediários.
        
        - `Consultas Complexas`: Ao dividir uma consulta complexa em partes, você pode armazenar resultados intermediários em tabelas temporárias ou variáveis.
        
        - `Performance`: Em algumas situações, usar tabelas temporárias pode melhorar a performance ao reduzir a quantidade de leituras do disco.

- Funções de Data e Hora
    - `GETDATE()`: Retorna a data e hora atual do sistema.

    Exemplo Prático:
    ```sql
    SELECT GETDATE();
    ```

    - `DATEPART()`: Retorna uma parte específica de uma data, como dia, mês ou ano.

    Exemplo Prático:
    ```sql
    SELECT DATEPART(MONTH, GETDATE());
    ```

    - `DATEDIFF()`: Retorna a diferença entre duas datas.

    Exemplo Prático:
    ```sql
    DECLARE @DataInicio DATE = '2022-01-01';
    DECLARE @DataFim DATE = '2022-12-31';
    SELECT 
        DATEDIFF(DAY, @DataInicio, @DataFim) AS 'Diferença em Dias';
    ```

## Módulo 5: Boas Práticas e Considerações Finais

- Importância do Backup
    - `Definição`: Backup é o processo de criar uma cópia dos dados para restauração em caso de perda de dados.

    **Mensagem Principal**:
        
    Sempre faça backup antes de alterações importantes. Seja uma atualização em massa, exclusão de registros ou qualquer outra operação que possa afetar significativamente os dados. O backup garante que você possa restaurar o banco de dados ao seu estado anterior em caso de erros ou problemas inesperados.

- Evite Consultas `Pesadas` em Horários de Pico 
    - `Definição`: Consultas `pesadas` são aquelas que consomem muitos recursos, seja em termos de CPU, memória ou I/O.

    **Mensagem Principal**:

    Durante horários de pico, quando muitos usuários estão acessando o banco de dados, é crucial evitar consultas que possam sobrecarregar o sistema. Isso garante uma experiência suave para todos os usuários e evita lentidão ou falhas.
        
- Considerações sobre performance: 

Ao projetar consultas, especialmente aquelas que serão executadas regularmente, é importante otimizá-las para eficiência. Utilize ferramentas de análise de plano de execução e monitore o desempenho para identificar e resolver gargalos.

- Conclusão e Q&A

    - Resumo dos Tópicos Abordados
    - Abertura para Perguntas e Esclarecimentos

Obrigado pela presença e até a próxima!🧙‍♂️