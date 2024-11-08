# IA_Odontoprev

# Integrantes do Grupo
- RM552648 - Diego Costa Silva
- RM553745 - Lucas Minozzo Bronzeri

# Desrcrição do Problema
Clínicas médicas fraudando consultas/exames/cirurgias. E, clientes que utilizam do plano de forma imprópria/desnecessária. Tudo isso gerando gastos para a Odontoprev.

# Descrição Solução
Um aplicativo que coloque a Odontoprev, o cliente, e a clínica no mesmo ambiente. Um aplicativo para que os clientes possam agendar e acompanhar suas consultas, contratar planos, e avaliar clínicas.  A clínica por sua vez, poderá lançar informações referentes as consultas dos clientes, e receber também.
Além disso, tanto no perfil da clínica e cliente, terão um histórico de consultas. Assim, podemos identificar padrões que indicam uma possível fraude, como: 
-	Consultas para o mesmo “problema” marcadas de forma recorrente;
-	Tempo de atendimento; 
-	Autorização prévia para procedimentos, consultas e exames mais caros;  

Uma funcionalidade que queremos implementar, é que só será possível começar um atendimento, se o cliente agendar e a clínica validar as informações. Por último, no momento do check-in, a consulta só irá ser iniciada, quando o cliente apresentar o código token para a recepcionista. Além disso, o sistema acompanhará um validador de IP, identificando possíveis compartilhamentos de login.

Atualizações para a entrega 2, adicionamos uma tabela ao nosso banco, que guarda sinistros, ou seja, caso haja alguma suspeita de algum usuário, a tabela ira guardar as informações do usuário, das consultas e dos Doutores que realizaram as consultas, fizemos também uma alteração na parte de IA, agora o nosso modelo prediz se o usuário é suspeito ou não, no caso de fraudes, os dados passados são: Total_Consultas, Idade,Renda_Anual, Score_Credito, Numero_Transacoes, Renda_por_Transacao e Idade_por_Consulta, para predizer a coluna: Chances_Fraude;

# Público-alvo
Clínicas, e pessoas físicas a partir dos 18 anos. De um lado, uma clínica buscando mais clientes e de outro lado o cliente, com acesso as melhores e mais indicadas clínicas que temos parceria. 

# Estudo de mercado
Amil Dental e Unimed Odonto, são duas das principais concorrentes da Odontoprev, as duas, assim como a Odontoprev, têm algumas opções de planos, a Amil tem menos opções que as demais, com preços perto da média, a Unimed tem uma grande gama de planos, os dois apresentam um diferencial, eles têm um plano empresarial, para que empresas, com um valor reduzido, possam assinar em grandes cargas e “distribuir” para seus funcionários. A Odontoprev contém planos mais completos que suas concorrentes, tendo como principais benefícios no plano “Bem-Estar Orto White”:

-	Aparelho Fixo e Móvel;
-	Manutenção de aparelhos;
-	Documentação ortodôntica completa;
-	Clareamento estético com Gel;

# Potencial de Mercado
Temos um foco de mercado direcionado a maiores de idade, temos um grande potencial, vendo que na nossa proposta, deixamos o atendimento bem mais dinâmico e seguro para o consumidor, tendo prevenções a usos indevidos de planos, também com o crescimento da odontologia no país, podemos afirmar que devemos alcançar números surpreendentes.

# Projeto IA

Trabalhando com o treinamento de um modelo de regressão, que tem como dados: Total_Consultas, Idade,Renda_Anual, Score_Credito, Numero_Transacoes, Renda_por_Transacao, Idade_por_Consulta e Chances_Fraude, a coluna "Chances_Fraude", tem os valores de 0 e 1, sendo 0 = sem chances de fraude e 1 = existem chances de fraude, o modelo irá predizer, com base nas outras informações(Total_Consultas, Idade,Renda_Anual, Score_Credito, Numero_Transacoes, Renda_por_Transacao e Idade_por_Consulta), se o cliente tem probabilidade de cometer alguma fraude, para isso estamos utilizando:
- Pandas: Com o foco em ler o arquivo CSV selecionado "dados_treinamento_fraude.csv";
- Matplotlib: Utilizado para a criação de gráficos, para a análise dos dados de Distribiução de Score de Crédito, Renda Anual vs Chances de Fraude e Número de Transações vs Chances de Fraude;
- Scikit-learn: Fazendo a separação dos dados em "X" e "y" depois fazemos a separação em X_train, X_test, y_train, y_test, utilizando "train_test_split", logo em seguida nós treinamos o modelo e utilizamos o accuracy_score, para vermos qual foi a Acurácia do modelo;  

Iremos fazer uma API para a coleta dos dados que serão utilizados no modelo de detecção de sinistros, o modelo, ainda na versão Beta, utiliza de dados ficticios, para que haja o funcionamento;

# Link Pitch
https://youtu.be/SBQ-_mBXdK0
