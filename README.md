
# Plataforma Utilitas



------------

    ├── README.md          
    ├── Informações
    │   ├── Objetivo do Projeto    <- Plataforma criada  para demontrar o estudo realizado pela equipe de IC para o cliente Utilitas.
    │   ├── Estudo Técnico do Setor de Resíduos Sólidos Industriais:  S:\05 Projetos Tranversais\Projeto Utilitas\Módulo 2 - Estudo Setorial Resíduos Sólidos\06. Apresentação
    │   ├── Caminho em Rede        V:\02 - Projetos de BI\Dashboard Utilitas
    ├── Bases do Projeto      
    ├── Tecnologias 

### Bases utilizadas neste projeto

Uma vez que criamos o processo de ingestão dos dados, foram ingeridas as seguintes bases dentro de produção

- INDICE_UTILITAS_FINAL_F [Manual]
- CAT_MUNICIPIOS_D [Dimensão]
- UTILITAS_GEO_F [Manual]
- EMPRESAS_RECEITA_FEDERAL_SOCIOS_F [Receita Federal]
- EMPRESAS_RECEITA_FEDERAL_F [Receita Federal]


### Tecnologia
A plataforma foi criada em Power BI utilizando o visual especifico externo Mapbox.
dentre o visual que mais podemos destacar está o visual do mapbox que exige uma documentação especifica para implementação.
- Mapbox
- MS Power BI 


##### Mapbox e como utilizar
Documentação da API: https://docs.mapbox.com/

- Os dados para gerar as informações georreferenciadas: dentro do projeto através da base_geo que não está habilitada para carga , foi exportado esta base de dados que será utilizada como base de endereços para o script em python contido neste projeto.
- O Script em python rodará, utilizando da API do google e acess token utilizando uma conta de gmail.
- Após rodar o script, as geolocalizações poderão serem refinados pois alguns endereços podem não conter da forma mais atual possível.

#Map Box Studio 

https://studio.mapbox.com/
https://studio.mapbox.com/tilesets/
https://studio.mapbox.com/datasets/

- Datasets
O dataset georreferenciado será utilizado para criar o style, após a geração via script python e possíveis correções
Como no exemplo: https://docs.google.com/spreadsheets/d/1yE4gVua6LJB02AQQHsxB9F5dP3Z9Wi5jMU-7RomNbGQ/edit?usp=sharing

- Tilesets
 O tileset é a forma que o mapbox gera os shapes através do dataset onde será utilizado para criar o style do mapa
 É nessa etapa que carregamos os dados georreferenciados para geração de pontos personalizados, ao carregar será criado um tileset que será referenciado pelo style.

Dentro do Mapbox Studio:

###Para criar um novo tileset
    - New TyleSet -> Carregar o arquivo em csv contendo as colunas georreferenciadas.
    - O arquivo esperado pode ser em CSV, Shapefile, dentre outros, neste caso utilizamos .csv
###Para criar um style: 
- https://studio.mapbox.com/
    - New style:
    - Classic Template
    - Selecionar o tipo de mapa, onde será utilizado como background para a visualização dos mapas.
    - Customizar o mapa selecionado
    - Dentro da visualização, à esquerda terá os layers, ao clicar no + poderemos adicionar uma nova layer que fará a plotagem dos dados.
    - Custom Layer : Utilizando uma layer customizada criada previamente
    - Filtrar pelo nome da layer, que deverá aparecer o tileset anteriormente criado, ou referenciar pelo ID, após importar, irão surgir os pontos no globo.
    - As layers podem ser personalizadas conforme situações.
    - Styles
     Criando o tileset, poderemos utilizar a informação contida nele para criarmos o style do projeto, estilizando, plotando circulos ou símbolos.
    - Após o carregamento, dentro do PBI a configuração segue local referenciando utilizando o visual externo mapbox, utilizando das credenciais de usuário criadas para o projeto, no caso estarei utilizando o do desenvolvedor.

Para plotagem do mapa, ele solicita credenciais
    - Access Token
    - Style URL (Criado através do mapbox studio no passo anterior)

Tileset: wcrfernandes.cloi42wxu18912ho7xiqqzc9t-7ymd3
Style: mapbox://styles/wcrfernandes/cl9j9ye67000m14qdlkpi0ubj

