# trabalhoCD1
Instruções de Execução
Upload de Dados: Certifique-se de que os arquivos incidents_master.csv, financial_impact.csv e market_impact.csv estão na raiz do diretório /content/.
Setup: Execute a primeira célula para importar o pandas.
Ingestão & Bronze: Execute as células de carga e a função create_bronze_layer. Isso criará arquivos .parquet com metadados de auditoria em /content/datalake/bronze.
Qualidade (DQ): Execute o run_bronze_data_quality_report para validar a integridade dos dados brutos.
Refino & Silver: Execute o build_silver_layer. Esta etapa realiza a limpeza, imputação de valores financeiros e criação de labels para modelos preditivos em /content/datalake/silver.
Exploração: Utilize as células de EDA para visualizar distribuições e correlações financeiras.
