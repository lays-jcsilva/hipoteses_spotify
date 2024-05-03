# 📊 🎧 Análise de Dados para Teste de Hipóteses Spotify

Olá, seja bem-vindo(a) à análise de dados do Spotify!

Neste projeto, mergulhamos em uma análise detalhada do conjunto de dados do Spotify, que oferece informações sobre as músicas mais ouvidas em 2023. Utilizando uma abordagem baseada em ferramentas como BigQuery, Google Colab e Power BI, buscamos extrair insights valiosos e validar hipóteses sobre os fatores que contribuem para o sucesso de uma música.

Estou animada para compartilhar as descobertas desta análise e contribuir para uma melhor compreensão do ecossistema musical do Spotify. Vamos explorar juntos as tendências e insights que moldam o sucesso das músicas na plataforma.


**Título do Projeto**
Validação de hipóteses Spotify


<details>
<summary><b>Objetivo</b></summary>
  
O objetivo principal deste projeto foi aplicar testes estatísticos, como correlação, teste de significância e regressão linear, para validar ou refutar hipóteses relevantes. Essas análises visam fornecer descobertas valiosas para uma gravadora que busca entender o contexto da indústria musical para lançar um novo artista

**Contexto**


A indústria musical faz parte de um ambiente que está em constante evolução e é altamente competitivo, a chave para o triunfo reside na capacidade de tomar decisões estratégicas guiadas por dados.

Nesse cenário desafiador uma gravadora visionária se depara com a missão extraordinária de lançar um novo artista no firmamento musical global , ela dispõe um tesouro em sua mãos que são os dados do spotify, repleto de insights valiosos sobre as músicas que dominaram as paradas em 2023.
</details>


<details>
<summary><b>Equipe</b></summary>



  Lays Silva e Nicole Machado Corrêa

</details>


<details>
<summary><b>Ferramentas e Tecnologia</b></summary>



**BigQuery:** O BigQuery é um serviço de armazenamento e análise de dados na nuvem fornecido pelo Google Cloud Platform. Ele oferece capacidade escalável para armazenar grandes volumes de dados e realizar consultas SQL de forma rápida e eficiente. No contexto deste projeto, o BigQuery foi utilizado para importar as bases de dados, limpar e tratar os dados iniciais, realizar manipulações e alterações os tipos de dados, além de criar variáveis adicionais conforme necessário.

**Google Colab:** Uma plataforma de desenvolvimento baseada em nuvem, foram conduzidos os testes de significância estatística. Esta ferramenta permite escrever e executar código Python de forma colaborativa e eficiente, aproveitando recursos computacionais como GPU e TPU. Os testes de significância foram realizados para avaliar a validade estatística das hipóteses levantadas durante a análise de dados. O ambiente interativo do Google Colab proporcionou uma experiência flexível e acessível para conduzir esses testes, permitindo uma análise robusta dos resultados.

**Python:** Uma linguagem de programação versátil e poderosa, foi empregado neste projeto para conduzir uma análise de regressão linear. Além disso, Python foi utilizado para criar gráficos de dispersão.

**Power BI:** Uma ferramenta de visualização de dados da Microsoft, desempenhou um papel fundamental neste projeto ao criar um dashboard abrangente e informativo. Este dashboard integrava diversos dados da base de dados, proporcionando uma visão holística e detalhada do cenário da indústria musical em 2023.A capacidade de conectar e consolidar dados de diferentes fontes, a ampla variedade de opções de visualização e a facilidade de compartilhamento foram aspectos essenciais que contribuíram para a criação de um painel.


</details>


<details>
<summary><b>Processamento de dados</b></summary>


<details>
<summary><b>Obtenção de dados</b></summary>
  
Os dados foram obtidos através arquivos CVS nomeados como "track_in_spotify", "track_in_competition" e "track,technical_info".


**Importação da base de dados**

A primeira fase deste projeto consistiu na importação das bases de dados para o ambiente do BigQuery no Google Cloud. Dentro da opção "BigQuery", foi criada uma pasta denominada "projeto-2-hipoteses". Para isso, foram importadas as tabelas diretamente através do upload de arquivos, adicionando os três arquivos CSV correspondentes a  "track_in_spotify", "track_in_competition" e "track_technical_info" dentro de uma subpasta denominada "dados_spotify". Essa abordagem permitiu uma organização estruturada e acessível dos dados, facilitando sua manipulação e análise subsequentes.

* Descrição das tabelas:

**track_in_spotify:** A tabela "track_in_spotify" contém informações sobre as músicas disponíveis no Spotify. Ela inclui o identificador exclusivo da música (track_id), o nome da música (track_name), o nome do(s) artista(s) (artist(s)_name), o número de artistas que contribuíram na música (artist_count), o ano, mês e dia em que a música foi lançada (released_year, released_month, released_day), o número de listas de reprodução do Spotify em que a música está incluída (in_spotify_playlists), a presença e posição da música nas paradas do Spotify (in_spotify_charts) e o número total de streams, representando o número de vezes que a música foi ouvida pelos usuários do Spotify (streams). Essa tabela fornece uma visão abrangente das características e do desempenho das músicas na plataforma de streaming.

**track_in_competition:** A tabela "track_in_competition" oferece insights sobre a competição das músicas em outras plataformas de streaming, além do Spotify. Ela inclui o identificador exclusivo da música (track_id) e informações sobre sua presença e desempenho em serviços como Apple Music, Deezer e Shazam. Para cada plataforma, são registrados o número de listas de reprodução em que a música está incluída (in_apple_playlists, in_deezer_playlists), bem como sua posição e classificação nas respectivas paradas de sucesso (in_apple_charts, in_deezer_charts, in_shazam_charts). Essa tabela permite uma análise comparativa do desempenho das músicas em diferentes plataformas de streaming, fornecendo uma visão abrangente da sua popularidade e alcance entre os usuários.

**track_technical_info:** A tabela "track_technical_info" contém informações técnicas detalhadas sobre as músicas. Ela inclui o identificador exclusivo da música (track_id) e uma série de métricas que descrevem características musicais específicas. Estas métricas incluem o número de batidas por minuto (bpm), indicando o ritmo da música, a porcentagem de danceability, que representa o quão adequada a música é para dançar, o valence, indicando a positividade do conteúdo musical, a energia (energy) percebida da música, a acústica(acusticness), representando a quantidade de som acústico presente, a instrumentabilidade (instrumentality_),  indicando a quantidade de conteúdo instrumental, a porcentagem de liveness, que reflete a presença de elementos de performance ao vivo, e a speechiness, que representa a quantidade de palavras faladas na música. Essas informações fornecem uma compreensão detalhada das características musicais de cada faixa, possibilitando análises mais profundas sobre seu estilo, apelo emocional e potencial de engajamento com o público.

</details>

<details>
<summary><b> Limpeza dos dados</b></summary>

**Dados Nulos:**
Para identificar e tratar valores nulos no BigQuery, foram empregados comandos SQL, incluindo SELECT, FROM, WHERE e IS NULL, para localizar os valores nulos dentro de cada uma das variáveis das tabelas. Durante a análise, constatou-se a presença de 50 valores nulos na variável "in_shazam_charts" e 95 valores nulos na variável "key". Para abordar os valores nulos na variável "in_shazam_charts", optou-se por utilizar o valor da mediana para preenchê-los, uma vez que esse método resultou em uma variação mínima na média dos dados. Essa estratégia de tratamento foi escolhida para preservar a integridade e a representatividade dos dados, garantindo a qualidade da análise subsequente.

**Dados Duplicados:**
Para identificar e tratar valores duplicados no BigQuery, foram utilizados os comandos SQL COUNT, GROUP BY e HAVING. Durante a análise, foram identificados 10 valores duplicados para a variável "track_name". Para lidar com essa duplicidade, foram removidos 5 valores duplicados, garantindo a integridade e a consistência dos dados. Essa abordagem foi adotada para assegurar a precisão e a confiabilidade da análise subsequente, evitando distorções nos resultados devido a entradas duplicadas.
</details>

<details>
<summary><b> Transformação dos dados</b></summary>

**Dados fora do escopo da análise e discrepantes:**
Através de comandos SQL, como SELECT EXCEPT, foi decidido remover as variáveis "key" (tom musical da música) e "mode" (modo de música -maior ou menor), pois foram consideradas irrelevantes para o propósito da análise. Em relação aos dados discrepantes, foi utilizado o comando REGEXP REPLACE para manipulação de strings, corrigindo caracteres nas variáveis "track_name" e "artist_s__name". Para identificar discrepâncias em variáveis numéricas, como "streams", originalmente armazenada como string, empregaram-se os comandos MAX, MIN e AVG. Essa abordagem permitiu a identificação e correção de valores discrepantes, garantindo a qualidade e a confiabilidade dos dados.


**Conversão do tipo de dados da variável 'streams':**
A variável "streams", que originalmente estava no formato de string, foi convertida para um formato numérico utilizando o comando SAFE_CAST. Essa conversão permite que os dados sejam tratados e analisados de forma mais eficiente, possibilitando a realização de cálculos e análises estatísticas relevantes,proporcionando uma compreensão mais precisa do número total de streams de cada música no Spotify.


**Criação de novas variáveis:** 
Através dos comandos CONCAT, CAST e JOIN, foram criadas as seguintes variáveis:


* "release_date_concat": Esta variável foi criada com o propósito de combinar três variáveis: *"released_year", "released_month" e "released_day", formando uma única data que representa o ano, mês e dia de lançamento de uma música.

* "soma_playlists": Esta variável representa a soma de uma música em playlists do Spotify, Deezer e Apple, sendo criada através da concatenação das variáveis "in_spotify_playlists", "in_apple_playlists" e "in_deezer_playlists".

Obs: Não consideramos o Shazam, pois se trata de um aplicativo que identifica o nome da música que está tocando no ambiente, ele é útil para quem não conhece ou se esqueceu do nome da canção reproduzida.

* "count_music_artosolo": Esta variável foi criada para representar a quantidade de músicas por artista solo. Para sua criação, foram utilizados os comandos SQL WITH, COUNT e GROUP BY.

Essas variáveis foram criadas utilizando uma combinação de funções e comandos SQL para agregar e manipular os dados de forma significativa, proporcionando insights valiosos para análises posteriores.


**Consolidação dos dados:**
Ao término do processo, foi realizada a integração das tabelas 'track_in_competition', 'track_in_spotify' e 'track_technical_info' por meio dos comandos CREATE TABLE, LEFT JOIN e JOIN, resultando na criação da tabela 'dados_spotify_final'."

</details>


<details>
<summary><b> Análise Exploratória dos dados </b></summary>



</details>
