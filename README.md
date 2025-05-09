# monitoramento_queimadas_brasil

# ETL e Análise de Dados
## Monitoramento de Queimadas no Brasil


<div align="center">
  <img src="" width="500">
</div>

## Sobre este Projeto 
Os conjuntos de arquivos _shafiles_ aqui utilizados foram obtidos em: <a href='https://www.ide.df.gov.br/geoportal/' target="_blank">GeoPortal-DF</a>

## Contextualização
Este projeto é constituído de duas etapas:

#### 1 - ETL dos _Shapefiles_ para o Google BigQuery
Nesta etapa do projeto, foi realizada a leitura de uma pasta contendo diversos conjuntos de arquivos <a href='https://desktop.arcgis.com/en/arcmap/latest/manage-data/shapefiles/what-is-a-shapefile.htm' target="_blank">_shapefile_</a>. A pasta apresentava uma organização hierárquica, que foi preservada no processo de ingestão dos dados no <a href='https://cloud.google.com/bigquery/docs/introduction?hl=pt-br' target="_blank">_Google BigQuery_</a>, a fim manter a categorização temática dos _shapefiles_. A seguir, apresenta-se uma breve descrição de cada etapa do processo de ETL:

- **_Extract_**: Leitura dos arquivos _shapefile_.
- **_Transform_**: Organização dos dados, adequando-os para o carregamento.
- **_Load_**: Inserção dos dados no _Google BigQuery_, com a criação de uma única tabela para armazenamento dos dados.

Segue a tabela criada no _Google BigQuery_ após o processo de ETL:
<div align="center">
  <img src="https://drive.google.com/uc?export=view&id=13SNtO5hh8YAuIGXHwtXkaGe5e1ZHFKxl" width="800">
</div>



#### 2 - Gerador de Relatório Automático 
Na segunda etapa do projeto, foi desenvolvido um sistema para geração automática de relatórios. Em suma, o sistema realiza a sobreposição dos dados geoespaciais armazenados no _Google BigQuery_ com as informações contidas em um _shapefile_ fornecido pelo usuário. A partir desse processo, é gerado um relatório (em formato HTML) que identifica as interferências existentes nas áreas delimitadas pelo _shapefile_.

* **Informações do Sistema:**
<div align="center">
  <img src="https://drive.google.com/uc?export=view&id=1cGcoa5cPPJCMp-JquWTNpIGVPjrw0V_Z" width="800">
</div>

1 - Campo para selecionar o arquivo _shapefile_ (.shp) que será utilizado como base para a geração do relatório automático.

2 - Campo para selecionar onde será salvo o relatório em formato HTML (.html).

3 - Botão para gerar o relatório.

<div align="center">
  <img src="https://drive.google.com/uc?export=view&id=1SB8QKZO28uz2LlqFkskuW3DERuIK6NFo" width="800">
</div>

4 - Campo para selecionar o arquivo _json_ que contêm as credenciais de acesso do _Google BigQuery_.

5 - Campo para informar o nome do projeto no _Google BigQuery_.

6 - Campo para informar o nome do dataset no _Google BigQuery_.

3 - Campo para informar o nome do tabela no _Google BigQuery_.


* **Sistema em operação:**
<div align="center">
  <img src="https://drive.google.com/uc?export=view&id=17oddV7w475KfTUOxVoVim8P8EgkYgVAM" width="800">
</div>

* **Relatório gerado:**
<div align="center">
  <img src="https://drive.google.com/uc?export=view&id=11ZHkBbAY_tJB6ZP7957hVfIZTSKlGf4b" width="800">
</div>


## Tecnologias utilizadas
- Python
- Tableau
