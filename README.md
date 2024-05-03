# 📊 🎧 Análise de dados para teste de hipoteses spotify

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

**BigQuery:** O BigQuery é um serviço de armazenamento e análise de dados na nuvem fornecido pelo Google Cloud Platform. Ele oferece capacidade escalável para armazenar grandes volumes de dados e realizar consultas SQL de forma rápida e eficiente. No contexto deste projeto, o BigQuery foi utilizado para importar as bases de dados, limpar e tratar os dados iniciais, realizar manipulações e alterações nos tipos de dados, além de criar variáveis adicionais conforme necessário.

**Google Colab:** Uma plataforma de desenvolvimento baseada em nuvem, foram conduzidos os testes de significância estatística. Esta ferramenta permite escrever e executar código Python de forma colaborativa e eficiente, aproveitando recursos computacionais como GPU e TPU. Os testes de significância foram realizados para avaliar a validade estatística das hipóteses levantadas durante a análise de dados. O ambiente interativo do Google Colab proporcionou uma experiência flexível e acessível para conduzir esses testes, permitindo uma análise robusta dos resultados.

**Python:** Uma linguagem de programação versátil e poderosa, foi empregado neste projeto para conduzir uma análise de regressão linear. Além disso, Python foi utilizado para criar gráficos de dispersão.

**Power BI:** Uma ferramenta de visualização de dados da Microsoft, desempenhou um papel fundamental neste projeto ao criar um dashboard abrangente e informativo. Este dashboard integrava diversos dados da base de dados, proporcionando uma visão holística e detalhada do cenário da indústria musical em 2023.A capacidade de conectar e consolidar dados de diferentes fontes, a ampla variedade de opções de visualização e a facilidade de compartilhamento foram aspectos essenciais que contribuíram para a criação de um painel.


</details>

<details>
<summary><b>Processamento de dados</b></summary>

<details>
<summary><b>Obtenção de dados</b></summary>
Os dados foram obtidos através de três CVS nomeados como "track_in_spotify", "track_in_competition","track,technical_info"


**Importação da base de dados**


A primeira fase deste projeto consistiu na importação das bases de dados para o ambiente do BigQuery no Google Cloud. Dentro da opção "BigQuery", foi criada uma pasta denominada "projeto-2-hipoteses". Para isso, foram importadas as tabelas diretamente através do upload de arquivos, adicionando os três arquivos CSV correspondentes a "track_in_competition", "track_in_spotify" e "track_technical_info" dentro de uma subpasta denominada "dados_spotify". Essa abordagem permitiu uma organização estruturada e acessível dos dados, facilitando sua manipulação e análise subsequentes.


</details>
