# Desafio_SQL_DNC

1 - Construa um card no metabase informando a idade média dos leads

<table align="center">
  <tr>
   <td>Pergunta</td>
   <td>Funções</td>
   <td>Tabelas</td>
   <td>Query</td>
  </tr>
  
  <tr>
   <td>Construa um gráfico de pizza no metabase informando a quantidade de pessoas por generos/td>
   <td>Operação Matemática | Agrupamento</td>
   <td>leads_basic_details</td>
   <td>select gender as Generos, count(gender) as Quantidade
    from leads_basic_details
    group by gender </td>
  </tr>
  
  
  <tr>
   <td>Construa um card no metabase informando a idade média dos leads</td>
   <td>Operação Matemática</td>
   <td>leads_basic_details</td>
   <td>select avg(age) from leads_basic_details</td>
  </tr>
  
  <tr>
   <td>Construa uma carta que mostre a quantidade de leads por grau de escolaridade em ordem crescente</td>
   <td>Operação Matemática | Agrupamento | Ordenação</td>
   <td>leads_basic_details</td>
   <td>select current_education, count(current_education) as Quantidade from leads_basic_details
    group by current_education
    order by count(current_education)</td>
  </tr>
  
  <tr>
   <td>Construa uma tabela de médias de watched que possuam watched_percentage maior que 0.5 e agrupe por language</td>
   <td>Operação Matemática | Agrupamento | Where</td>
   <td>leads_demo_watched_details</td>
   <td>select language, avg(watched_percentage) as Porcentagem from leads_demo_watched_details
    where watched_percentage > 0.5
    group by language</td>
  </tr>
  
  <tr>
   <td>Construa um gráfico de linhas que mostre a quantidade de ligações atendidas por plataforma</td>
   <td>Operação Matemática | Agrupamento | União | Where</td>
   <td>leads_basic_details | leads_basic_details</td>
   <td>select A.jnr_sm_id, count(A.call_status), A.call_done_date, B.current_city from leads_interaction_details A
    left join leads_basic_details B
    on A.lead_id = B.lead_id
    WHERE A.call_status = "successful"
    group by A.jnr_sm_id, B.current_city, A.call_done_date</td>
  </tr>
</table>
