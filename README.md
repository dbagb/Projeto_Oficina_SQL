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
A criação do modelo conceitual é o segundo processo para a criação do banco de dados, utilizaremos como base o Modelo Entidade-Relacionamento. Nessa etapa, será definida a estrutura do banco de dados de forma independente do SGBD utilizado. Definiremos os atributos das entidades e seus relacionamentos e modelo de cardinalidade entre as tabelas, tendo como objetivo visualizar, definir e gerar o entendimento da regra de negócio aplicada a criação do banco de dados.
</p>

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
</p>


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
ID_FUNC			       INT IDENTITY (1,1) PRIMARY KEY,
NOME				       VARCHAR (50) NOT NULL, 
CARGO				       VARCHAR (30) NOT NULL,
SEXO				       VARCHAR (20) NOT NULL,
TELEFONE			     VARCHAR (11) NOT NULL,
ENDERECO			     VARCHAR (40) NOT NULL,
BAIRRO				     VARCHAR (30) NOT NULL,
DATA_NASC			     DATE NOT NULL,
DATA_ADMISSAO			 DATE NOT NULL,
SALARIO			       FLOAT NOT NULL,
OBSERVACAO			   VARCHAR (100)
);
  

CREATE TABLE SETORES_TESTE
(
ID_SETOR			     INT IDENTITY (100,1) PRIMARY KEY,
NOME_SETOR			   VARCHAR (30) NOT NULL,
QNT_FUNC			     INT, 
);

CREATE TABLE SERVICO_PRESTADO_TESTE
(
ID_SERVICO			     INT IDENTITY (1,1) PRIMARY KEY,
TIPO_SERVICO			   VARCHAR (30),
HORA_INICIO			     DATETIME,
HORA_TERMINO			   DATETIME,
VALOR_PECA			     FLOAT,
VALOR_MO			       FLOAT,
DESCONTOS			       FLOAT,
FORMA_PG			       VARCHAR(20),
VALOR_TOTAL			     FLOAT,
DESC_SERVICO			   VARCHAR (100)
);

CREATE TABLE VEICULOS 
(
ID_VEICULO			  INT IDENTITY (100,1) PRIMARY KEY,
NOME_VEICULO			VARCHAR (50) NOT NULL,
COR_VEICULO			  VARCHAR (10) NOT NULL,
DATA_ENTRADA			DATE NOT NULL,
DATA_SAIDA			  DATE NOT NULL,
PLACA				      VARCHAR (10) NOT NULL,
OBSERVACAO			  VARCHAR (100),
);

CREATE TABLE CLIENTES_TESTE
(
ID_CLIENTE			  INT IDENTITY (1,1) PRIMARY KEY,
NOME_CLIENTE			VARCHAR (50) NOT NULL,
ENDERECO			    VARCHAR (40),
BAIRRO				    VARCHAR (30),
DATA_NASC			    DATE,
CPF				        CHAR (14),
TELEFONE			    VARCHAR (11) NOT NULL,
);

CREATE TABLE TIPO_PG_TESTE
(
ID_TIPOPG			    INT IDENTITY(1,1) PRIMARY KEY,
TIPO_PAGAMENTO		VARCHAR(40)
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
Para ver as definições dos usuários
