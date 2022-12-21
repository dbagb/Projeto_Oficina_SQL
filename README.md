<h1> Introdução </h1>

<p>
Esse projeto tem como objetivo demonstrar todo o processo de criação de um banco de dados de uma oficina de pequeno porte. Os processos documentados serão: 

  <strong>Análise de Requisitos</strong> – A primeira etapa e mais importante para a criação de um banco de dados. Consiste no conhecimento sobre a empresa e suas regras de negócio, nesta etapa são realizadas reuniões com o intuito de compreender o que faz a empresa , quais tipos de cliente a empresa possui, seu ramo de atuação e demais características que possam ser fundamentais para a criação de um banco de dados.

  <strong>Criação do Modelo Conceitual</strong> – Etapa onde serão definidas as entidades, atributos das entidades e como serão os relacionamentos com base no Modelo Entidade Relacionamento. A criação desse modelo tem como função captar os requisitos de informação e regras de negócio sob o ponto de vista da empresa, visando o entendimento da regra de negócio da empresa e utilizar como base para a criação do banco de dados.  

  <strong>Criação do Modelo Lógico</strong> – Etapa onde serão definidas as estruturas de armazenamento dos dados no banco e também seus relacionamentos. Serão definidos os registros, tipos de dados dos campos, tamanhos, chaves primárias e estrangeiras etc.

  <strong>Criação do Modelo Físico</strong> – Etapa onde será realizado o design do banco de dados de acordo com o modelo lógico definido. Nesta etapa também definimos o SGBD que será utilizado, nesse projeto utilizaremos o SGBD Microsoft SQL Server 2016.

Neste projeto será criado o modelo de banco de dados de uma Oficina Auto elétrica de pequeno porte, cenário o qual já tive experiência profissional durante dois anos antes de iniciar os estudos na área de tecnologia. Algumas informações serão simuladas afim de garantir um melhor desempenho nos processos criados para a conclusão do projeto.

</p>

<h1>
Análise de Requisitos
</h1>

<p>
O primeiro e mais importante processo a ser realizado durante a criação de um banco de dados, é a análise de requisitos. Etapa onde analisamos e conhecemos as regras de negócio da empresa, tendo como foco reuniões para conhecer melhor o mercado e público alvo da empresa, o tipo de serviço oferecido, tipos de cliente, seu ramo de atuação, suas características e demais informações que possam ser importantes para a criação do banco de dados.
Essa oficina será simulada como uma empresa de pequeno porte, a qual terá os seguintes setores:
  
•	<strong>Financeiro</strong> – Responsável pelo gerenciamento das contas gerais da empresa, pagamentos de funcionários e notas fiscais da empresa.

•	<strong>Produção</strong> – Responsável pela mão de obra principal da empresa, reparo de veículos e negociação direta com clientes. 
  
Para esses setores, serão listados os seguintes profissionais.
  
  •	<strong>Um assistente financeiro</strong>
  
  •	<strong>Três mecânicos eletricistas</strong>

  A partir das regras de negócio e entendendo a necessidade do cliente, a documentação das informações necessárias foram detalhadas abaixo.

  • <strong>Veículos</strong> – Identificação do veículo, Nome, Cor, Placa, Identificação do cliente (dono do veículo), Observações.

  •	<strong>Serviço Prestado</strong> – Identificação do serviço presto, Tipo de serviço, Data do serviço, Valor de peças, Valor de mão de obra, Descontos, Forma de Pagamento, Valor Total, Descrição do Serviço, Identificação do funcionário que realizou o serviço, identificação do veículo.

  •	<strong>Tipo de serviço</strong> – Identificação do tipo de serviço prestado, Tipo de serviço prestado, Descrição do tipo de serviço

  •	<strong>Funcionários</strong> – Identificação do funcionário, Nome, Cargo, Sexo, Telefone, Endereço, Bairro, Data de Nascimento, Data de Admissão, Salário, Observações.

  •	<strong>Clientes</strong> – Identificação do cliente, Nome, Endereço, Bairro, Data de Nascimento, CPF, Telefone

  •	<strong>Setores</strong> – Identificação do Setor, Nome do Setor, Quantidade de funcionários, identificação dos funcionários.

Tendo essas informações definidas, a próxima etapa será a criação do modelo conceitual.

</p>

<h1>
Modelo Conceitual
</h1>

<p>
A criação do modelo conceitual é o segundo processo para a criação do banco de dados, utilizaremos como base o Modelo Entidade-Relacionamento. Nessa etapa, será definida a estrutura do banco de dados de forma independente do SGBD utilizado. Definiremos os atributos das entidades e seus relacionamentos e modelo de cardinalidade entre as tabelas, tendo como objetivo visualizar, definir e gerar o entendimento da regra de negócio aplicada a criação do banco de dados. Segue abaixo exemplo do modelo conceitual desenvolvido para esse projeto.
</p>

![Modelo Conceitual Oficina](https://user-images.githubusercontent.com/119353539/208750436-ce80ee2c-e9eb-4a67-a824-aa97210cfd6e.png)


<h1>
Cardinalidade e Relacionamento
</h1>

<p>
A cardinalidade é caracterizada pelo número máximo e mínimo de ocorrências de uma entidade associada a ocorrências de outra entidade. Seguindo o modelo conceitual desenvolvido e regra de negócio apresentada na análise de requisitos, segue abaixo o modelo de cardinalidade desenvolvido para esse projeto.
<strong>
  
•	Veículos (1,N) <--> (1,1) Clientes 
Um veículo pertence a apenas um cliente, enquanto um cliente pode ter diversos veículos.

•	Veículos (1,N) <---> (1,1) Serviço Prestado
Um veículo gera apenas um serviço, enquanto os serviços são gerados por diversos veículos.

•	Funcionários (1,1) <--> (1,N) Serviço Prestado
Um funcionário pode fazer diversos serviços, porém cada serviço é vinculado a apenas um funcionário. 

•	Serviços Prestado (1,N) <--> (1,1) Tipo de pagamento
Um serviço pode ter apenas um tipo de pagamento, enquanto os tipos de pagamento podem ser vinculados a diversos serviços.

•	Serviços Prestados (1,N) <--> (1,1) Tipos de serviço
Um serviço pode ter apenas um tipo registrado, enquanto os tipos de serviços podem ser registrados em diversos serviços diferentes.

•	Funcionários (1,N) <--> (1,1) Setores
Um funcionário pode ser vinculado à apenas um setor, enquanto cada setor pode ter diversos funcionários.
  </strong>
  </p>

<h1>
Modelo Lógico
</h1>

<p>
Etapa onde será definida as estruturas de armazenamento dos dados e seus relacionamentos. Serão definidos os principais componentes como Entidades, Atributos, Relacionamentos, Chaves primárias e estrangeiras e afins. Neste projeto iremos adotar o SGBD Microsoft SQL Server 2016, o qual utiliza o modelo relacional.
Segue abaixo exemplo do modelo lógico definido para esse projeto.
</p>


![Modelo_Oficina_Lógico](https://user-images.githubusercontent.com/119353539/208750019-c12b7469-04c8-433b-9fed-89cc7e5aa7d8.png)


<h1>
Modelo Físico
</h1>

<p>
E por fim, chegamos à etapa onde será construída a modelagem física do banco de dados. Etapa onde será definido o design do banco de dados com base nos requisitos reunidos durante a modelagem lógica e conceitual. Tabelas, colunas, tipos de dados, restrições, índices e diversos procedimentos estruturais do banco de dados serão definidos nessa etapa.
Para esse projeto, utilizaremos o SGBD Microsoft SQL Server.
SGBD’s (Sistema de Gerenciamento de Banco de Dados) são softwares responsáveis pelo gerenciamento de uma base de dados. 

•	Criação do banco de dados – Para darmos início ao nosso projeto, o primeiro passo para a modelagem física é a criação do nosso banco de dados. 

Utilizaremos as configurações padrão do SQL Server 2016 para propriedades do banco de dados como Autogrowth, Recovery Model, Endpoint,  quantidade de arquivos de log e dados de linhas também serão padrão.

Comando utilizado:
```  
CREATE DATABASE OFICINA_TESTE;

USE OFICINA_TESTE;
```
•	Criação das tabelas – Após a criação do banco de dados, o próximo passo será a criação das tabelas. Definiremos os campos, tamanhos, tipos e restrições. Adicionando também a chave primária de cada tabela. 
Comando utilizado:
```
  
CREATE TABLE FUNCIONARIOS_TESTE
(
ID_FUNC			INT IDENTITY (1,1) PRIMARY KEY,
FK_ID_SETOR		INT,
NOME			VARCHAR (50) NOT NULL,
CARGO			VARCHAR (30) NOT NULL,
SEXO			VARCHAR (20) NOT NULL,
TELEFONE		VARCHAR (11) NOT NULL,
ENDERECO		VARCHAR (40) NOT NULL,
BAIRRO			VARCHAR (30) NOT NULL,
DATA_NASC		DATE NOT NULL,
DATA_ADMISSAO	        DATE NOT NULL,
SALARIO			FLOAT NOT NULL,
OBSERVACAO		VARCHAR (100),
);

CREATE TABLE SETORES_TESTE
(
ID_SETOR		INT IDENTITY (100,1) PRIMARY KEY,
NOME_SETOR		VARCHAR(30) NOT NULL,
QNT_FUNC		INT,
FK_ID_FUNC		INT,
);
  

CREATE TABLE SERVICO_PRESTADO_TESTE
(
ID_SERVICO		INT IDENTITY (1,1) PRIMARY KEY,
TIPO_SERVICO		INT,
HORA_INICIO		DATETIME,
HORA_TERMINO            DATETIME,
VALOR_PECA		DECIMAL (4,2),
VALOR_MO		DECIMAL (4,2),
DESCONTOS		DECIMAL (4,2),
FORMA_PG		VARCHAR(20),
VALOR_TOTAL		DECIMAL (10,2),
DESC_SERVICO	        VARCHAR (100),
FK2_ID_FUNC		INT,
FK2_ID_VEICULO		INT
);


CREATE TABLE VEICULOS_TESTE 
(
ID_VEICULO		INT IDENTITY (100,1) PRIMARY KEY,
NOME_VEICULO	        VARCHAR (50) NOT NULL,
COR_VEICULO		VARCHAR (10) NOT NULL,
PLACA			VARCHAR (10) NOT NULL,
OBSERVACAO              VARCHAR (100),
FK_ID_CLIENTE		INT
);

  
CREATE TABLE CLIENTES_TESTE
(
ID_CLIENTE              INT IDENTITY (1,1) PRIMARY KEY,
NOME_CLIENTE            VARCHAR (50) NOT NULL,
SEXO                    VARCHAR(20) NOT NULL,
ENDERECO                VARCHAR (40),
BAIRRO                  VARCHAR (30),
DATA_NASC               DATE,
CPF                     CHAR (14),
TELEFONE                VARCHAR (11)  NOT NULL,
);

CREATE TABLE TIPO_PG_TESTE
(ID_TIPOPG              INT PRIMARY KEY IDENTITY (1,1),
TIPO_PAGAMENTO          VARCHAR(40)
);
  
CREATE TABLE TIPO_SERVICO_TESTE
(
ID_TIPOSERVICO          INT PRIMARY KEY IDENTITY (1,1),
TIPO_SERVICO            VARCHAR (50),
DESC_SERVICO            VARCHAR (300)
);  
  
```
</p>

<h1>
Criando e adicionando chaves estrangeiras
</h1>

<p>
Após a criação das tabelas, precisamos criar as chaves estrangeiras para relacionar as tabelas entre si.
  
```
ALTER TABLE VEICULOS_TESTE
ADD CONSTRAINT FK_ID_CLIENTE 
FOREIGN KEY (FK_ID_CLIENTE)
REFERENCES CLIENTES_TESTE (ID_CLIENTE) 

ALTER TABLE SETORES_TESTE
ADD CONSTRAINT FK_ID_FUNC
FOREIGN KEY (FK_ID_FUNC)
REFERENCES FUNCIONARIOS_TESTE (ID_FUNC)

ALTER TABLE SERVICO_PRESTADO_TESTE
ADD CONSTRAINT FK2_ID_FUNC
FOREIGN KEY (FK2_ID_FUNC)
REFERENCES FUNCIONARIOS_TESTE (ID_FUNC)

ALTER TABLE SERVICO_PRESTADO_TESTE
ADD CONSTRAINT FK2_ID_VEICULO
FOREIGN KEY (FK2_ID_VEICULO)
REFERENCES VEICULOS_TESTE (ID_VEICULO)
```

</p>

<h1>
Criação de usuários e definição de permissões
</h1>

<p>
Para esse projeto, teremos dois usuários criados para acessar o banco de dados. Cada usuário terá suas limitações de permissões e privilégios de acessos ao banco.

<h5>
Usuários
</h5>

<p>

• Gerente - Usuário com permissões para alterar, inserir e deletar dados do banco. Este usuário terá privilégios de permissão a nível DB_DATAWRITER.

• Funcionário - Usuário com permissões e privilégios mais básicas dentro do banco de dados. Este usuário terá permissão e privilégio a nível DB_DATAREADER, onde será possível apenas visualizar os dados inseridos no banco através de SELECT's.

</p>

<h1>
Inserindo dados nas tabelas
</h1>

<p>
Nesta etapa iremos adicionar os registros nas tabelas para que possamos iniciar o projeto realizando algumas consultas mais específicas futuramente. 
Inicialmente serão inseridos uma quantidade exata de registros nas tabelas:

•	4 Registros na tabela funcionários

•	2 Registros na tabela setores

•	60 Registros na tabela Serviço Prestado

•	40 Registros na tabela Clientes

•	48 Registros na tabela Veículos

</p>

Para que esta etapa não tome muito espaço no projeto, o código gerado para toda a inserção poderá ser visto através deste link : INSERIR LINK AQUI

<p>
Serão descritos três registros em cada tabela aqui para que não fique muito extenso.
Código de inserção de dados para a tabela FUNCIONÁRIOS
-- ANTES DE INSERIR OS DADOS NA TABELA FUNCIONÁRIOS, DEVEMOS ATIVAR O IDENTITY_INSERT DA TABELA
-- QUE CONSISTE EM ATIVAR A INSERÇÃO DE DADOS DE FORMA QUE O ID SEJA INCREMENTADO AUTOMÁTICAMENTE 
</p>

```
SET IDENTITY_INSERT OFICINA_TESTE.DBO.FUNCIONARIOS_TESTE ON
GO

INSERT INTO FUNCIONARIOS_TESTE (ID_FUNC, NOME, CARGO, SEXO, TELEFONE, ENDERECO, BAIRRO, DATA_NASC, DATA_ADMISSAO, SALARIO, OBSERVACAO) VALUES 
(1, 'VALÉRIA PEREIRA SANTOS' ,'ASSISTENTE FINANCEIRA' ,'F' ,'21996854631' , 'RUA FERNANDO GUIMARÃES Nº 145', 'PADRE MIGUEL', '24/08/1990' , '03/02/2020' ,1850.64 ,'ASSISTENTE ADMINISTRATIVA GERAL'),
(2, 'VICTOR PAULO FERRIRA', 'SUPERVISOR MECÂNICO', 'M', '21977485221', 'AVENIDA TITUÍBA Nº 1015', 'BATAN', '11/09/1995', '09/01/2019',2750.31 ,'ELÉTRICA E MECÂNICA AVANÇADA'),
(3, 'JEREMIAS MOREIRA ALVES', 'GERENTE GERAL MECÂNICO', 'M', '21968953676', 'RUA SÃO CLEMENTE Nº 13', 'SULACAP', '15/12/1980', '23/06/2018', 3620.87, 'ELÉTRICA E INJEÇÃO ELETRÔNICA AVANÇADA');
```

<p>Código de inserção de dados na tabela setores</p>

```
INSERT INTO SETORES_TESTE (NOME_SETOR, QNT_FUNC, FK_ID_FUNC) VALUES
(1, 'FINANCEIRO', 1, 1),
(2, 'LOGÍSTICA', 1, 5),
(3,'REPARO AUTOMOTIVO', 3, 2),
(4,'REPARO AUTOMOTIVO', 3, 3),
(5,'REPARO AUTOMOTIVO', 3, 4);
```

<p>Código de inserção de dados na tabela Clientes</p>

```
INSERT INTO CLIENTES_TESTE (ID_CLIENTE, NOME_CLIENTE, ENDERECO, BAIRRO, DATA_NASC, CPF, TELEFONE) VALUES
(1, 'ANTÔNIO FREITAS', 'RUA BELGÁRIO GOMES Nº 35', 'REALENGO', '11/02/1975', '42715246935', '21963389214'),
(2, 'CLÁUDIO GOMES', 'AVENIDA SIQUEIRA CAMPOS Nº 1475', 'BANGU', '04/01/1980', '14236589782','21984522898'),
(3, 'FERNANDA MACEDO', 'TRAVESSA CAMPO BELO Nº 11', 'BANGU', '15/08/1985', '325504070', '21977658214');
```

<p>Código de inserção de dados na tabela Veículos</p>

```
INSERT INTO VEICULOS_TESTE (ID_VEICULO, NOME_VEICULO, COR_VEICULO, PLACA, OBSERVACAO, FK_ID_CLIENTE) VALUES
( 1, 'GOL', 'VERMELHO', 'RI02A18', 'VEÍCULO ARRANHADO NA LATERAL ESQUERDA, PINTURA DANIFICADA', '8'),
( 2, 'CORSA', 'VERDE', 'SR04B23', 'PORTA ESQUERDA TRAVADA, ABRE APENAS POR DENTRO', '26'),
( 3, 'PALIO', 'PRETO', 'LKO-0434', 'NENHUMA AVARIA', '2');
```


<p>Código de inserção de dados na tabela Serviço Prestado</p>

```
INSERT INTO SERVICO_PRESTADO_TESTE (ID_SERVICO, TIPO_SERVICO, HORA_INICIO, HORA_TERMINO, VALOR_PECA, VALOR_MO, DESCONTOS, FORMA_PG, VALOR_TOTAL, DESC_SERVICO, FK2_ID_FUNC, FK2_ID_VEICULO) VALUES
(1, 1, '01/04/2022 09:40', '01/04/2022 10:05', 00.00, 50.00, 00.00, 1, 60.00, 'SCANNER INJEÇÃO ELETRÔNICA - DIAGNÓSTICO DO PROBLEMA', 4, 14),
(2, 4, '01/04/2022 10:14'  , '01/04/2022 14:20', 280.00, 150.00, 10.00, 3, 420.00, 'LIMPEZA E TROCA DE BICOS DEFEITUOSOS, TROCA DE LÂMPADAS', 3, 21),
( 3, 6, ' 01/04/2022 12:13', '01/04/2022 12:55'  , 00.00, 180.00, 00, 3, 180, 'CARGA DE GÁS - AR CONDICIONADO'  , 2, 16);
```

<p>Código de inserção de dados na tabela Tipo de Serviço</p>

```
INSERT INTO TIPO_SERVICO_TESTE (ID_TIPOSERVICO, TIPO_SERVICO, DESC_SERVICO) VALUES
(1,'DIAGNÓSTICO ELETRÔNICO/ELÉTRICO','SCANNER INJEÇÃO ELETRÔNICA, DIAGNÓSTICO ELÉTRICO'),
(2, 'REVISÃO ELÉTRICA', 'TROCA DE CABOS, VELAS, ÓLEO DE MOTOR E FILTROS, LIMPEZA DE BICOS, REVISÃO GERAL EM LANTERNAS'),
(3, 'MANUTENÇÃO ELÉTRICA I', 'PROBLEMAS DE LANTERNAS, INSTALAÇÃO/PROBLEMAS DE ALARMES, INSTALAÇÃO/PROBLEMAS COM SEGREDOS, MULTIMÍDIA, INSTALAÇÃO/PROBLEMAS CÂMERA DE RÉ, PROBLEMAS COM LIMPADOR DE PARABRISA');
```

<p>Código de inserção na tabela Tipo de pagamento</p>

```
INSERT INTO TIPO_PG_TESTE (ID_TIPOPG, TIPO_PAGAMENTO) VALUES
(1,'DINHEIRO' ),
(2,'CARTÃO DÉBITO' ),
(3,'CARTÃO CRÉDITO' ),
(4,'DIVIDIDO CARTÃO E DINHEIRO' );
```

<h1>
Etapa de criação de relatórios
</h1>

<p>
Para a geração de relatórios gerenciais como por exemplo, relatórios diários sobre faturamento, relatórios analíticos mensais e demais relatórios com informações que possam ser importantes para gerenciar o negócio da empresa, optei por utilizar as views como recurso.

Seguem abaixo os relatórios gerados e seus códigos
</p>
