# Power BI Analyst dio - Desafio 2

<h3>Descrição do desafio módulo 3 – Processamento de Dados Simplificado com Power BI</h3>
<p>1. Criação de uma instância na Azure para MySQL
  <p> <i> Foi utilizado um container docker do MySQL instalado em uma VM localmente.</i>
    
<p>2. Criar o Banco de dados com base disponível no github
  <p> <i> Foi criado o Banco de dados com base nos arquivos script_bd_company.sql e insercao_de_dados_e_queries_sql.sql utilizando o software DBeaver.</i>
    
<p>3. Integração do Power BI com MySQL no Azure
  <p> <i> Foi integrado o Power BI com a instância do MySQL em um container docker.</i>
    
<p>4. Verificar problemas na base a fim de realizar a transformação dos dados
  <p> <i> Não houve problemas.</i>

<h3>Diretrizes para transformação dos dados</h3>

<p>1. Verifique os cabeçalhos e tipos de dados
  <p> <i> Tantos os cabeçalhos quantos os tipos de dados estavam consistentes</i> 

<p>2. Modifique os valores monetários para o tipo double preciso
  <p> <i> Foi modificado o tipo da coluna Salary da tabela Employee para Número decimal fixo.</i>
    
<p>3. Verifique a existência dos nulos e analise a remoção
  <p> <i> Não haviam nulos para serem tratados.</i>
    
<p>4. Os employees com nulos em Super_ssn podem ser os gerentes. Verifique se há algum colaborador sem gerente
  <p> <i> Somente havia um colaborador com Super_ssn como nulo.</i>
    
<p>5. Verifique se há algum departamento sem gerente
  <p> <i> Todos os departamentos estavam com gerentes definidos.</i>
    
<p>6. Se houver departamento sem gerente, suponha que você possui os dados e preenchaas lacunas
  <p> <i> Todos os departamentos estavam com gerentes definidos.</i>
    
<p>7. Verifique o número de horas dos projetos
  <p> <i>Todos os campos estavam preenchidos.</i>
    
<p>8. Separar colunas complexas
  <p> <i>Na tabela Employee, a coluna Address, foi separada em Cidade, Estado e Número.</i>
    
<p>9. Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. Fique atento, essa informação influencia no tipo de junção
  <p> <i>Foi selecionado a tabela Employee, mesclada com a tabela Departament e selecionado o Tipo de Junção "Externa esquerda". Após a criação da nova tabela, foi expandido somente a coluna Dname, para exibir o nome do departamento.</i>
    
<p>10. Neste processo elimine as colunas desnecessárias
  <p> <i> Foram removidas todas as outras colunas, deixando apenas a coluna Nome e Dname.</i>
    
<p>11. Realize a junção dos colaboradores e respectivos nomes dos gerentes. Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. Caso utilize SQL, especifique no README a query utilizada no processo
  <p> <i>Foi selecionado a tabela Employee, mesclada com a tabela Employee, foram utilizados como chaves as colunas Super_ssn na primeira e Ssn na segunda, e selecionado o Tipo de Junção "Externa esquerda". Após a criação da nova tabela, foi expandido somente a coluna Name, para exibir o nome do Gerente. Foram eliminadas as colunas que não eram o nome do colaborador ou nome do gerente.</i>
    
<p>12. Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores
  <p> <i>Foram selecionadas as colunas de Nome e Sobrenome e mescladas com separador Espaço.</i>
    
<p>13. Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro
  <p> <i>Foi selecionado a tabela Departament, mesclada com a tabela dept_locations, foram utilizados como chaves as colunas Dnumber na primeira e Dnumber na segunda, e selecionado o Tipo de Junção "Externa esquerda". Após a criação da nova tabela, foi expandido somente a coluna Dlocation, para exibir o nome da localização. Foram removidas colunas desnecessárias. E foram mescladas as colunas Dlocation e Dname com separador Espaço.</i>
    
<p>14. Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir
  <p> <i>Porque as tabelas tem referências entre si e precisão se corresponder.</i>
    
<p>15. Agrupe os dados a fim de saber quantos colaboradores existem por gerente
  <p> <i>Sobre a coluna Gerente foi selecionado "Agrupar por", foi mantida a configuração padrão e OK.</i>
    
<p>16. Elimine as colunas desnecessárias, que não serão usadas no relatório, de cada tabela
  <p> <i>Colunas desnecessárias já haviam sido eliminadas.</i>
