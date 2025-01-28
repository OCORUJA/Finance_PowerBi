# README

Este readme descreve os passos realizados com parte integrante do desafio de Projeto do módulo Processamento de Dados com Power BI

**As ferramentas necessárias para a criação do projeto foram:**  
- Uso da plataforma Azure  
- SQL  
- Power BI

**Criar conta na Azure através do site:**  
https://portal.azure.com/

**Criar uma instância**

- Na barra pesquisar digitar **mysql**
- **Banco de dados do Azure para MySQL**
- **Criar**

**Item Grupo de Recursos:**  
- Selecionar opção **Teste**

**Nome do servidor:**  
- desafio-projeto-dio-rodrigo

**Região:**  
- Southeast Asia

**Versão MySQL:**  
- 8

**Nome do administrador:**  
- company

**Senha:**  
- Senha:         ***************  
- Confirmar senha: ****************

**Selecionar Avançar:**  
- **Rede**

**Método de Conectividade:**  
- Acesso público

**Selecionar Avançar:**  
- **Revisar + Criar**

**Criar banco de dados usando os comandos SQL via Cloud Shell**

- Selecionar o ícone cloud shell
- No prompt de comando digitar:  
  `mysql -h desafio-projeto-dio-rodrigo.mysql.database.azure.com -u company -p`
- Digitar a senha

A criação do Banco de dados foi feita utilizando o código disponivel atraves do arquivo  script_bd_company.sql disponível no site:

A inserção dos dados foi feita utilizando o conteúdo do arquivo insercao_de_dados_e_queries_sql.sql disponivel no site: 

**Transformação**

**Alteração no nome das tabelas:**

| anterior                  | atual                     |
|---------------------------|---------------------------|
| azure_company employee    | company_employee          |
| azure_company departamento| company_departament       |
| azure_company dept_locations | company_dept_locations |
| azure_company project     | company_project           |
| azure_company works_on    | company_works_on          |

- Tabela employee: Salary de inteiro para decimal fixo;
  - Selecionar coluna salary em seguida Tipo de Dados opção decimal fixo;

- Na tabela employees foi encontrado um null, o item não foi removido pois trata-se de gerente;
- Todos os departamentos têm gerente.

**Criação da coluna employe_departament:**

- Selecionar **Mesclar Consultas** em seguida **Mesclar Consultas como novas**, escolher a tabela **Company_employe** e selecionar coluna **Dnumber**.
- No campo abaixo selecionar a tabela **Company_departament** coluna **Dnumber**.
- Uma nova consulta foi criada e o nome foi modificado para **employee_departament**, a coluna foi **Company_departament** foi selecionada e o item expandir.
- Deixar selecionado o item **Dname**;

**Mescla do Nome e Sobrenome:**

- Item **Mesclar Consultas** **Mesclar Consultas** selecionar coluna **Fname**.
- Tabela **Company_employee** selecionar **Lname**.
- Nova coluna criada e o nome alterado para **Complet_name**.

**Junção de nome e sobrenome:**

- Tabela **Company_employee**:
  - Selecionar coluna **Fname**, manter pressionada a tecla **Ctrl**, **Mesclar Colunas**, o item **Separador Espaço**, **Nome da Coluna Full_name**.

- Selecionar **Company_departament**.