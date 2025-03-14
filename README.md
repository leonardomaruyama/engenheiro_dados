# Projeto de Movimentação de Dados

Este projeto realiza a movimentação e processamento de dados em um pipeline entre os diretórios `data`, `raw`, `curated` e `modeled`. O objetivo é organizar e transformar os dados para que fiquem prontos para uso em ferramentas de análise de dados, como o Power BI.

## Estrutura de Diretórios

- **data**: Contém os arquivos JSON brutos, que são lidos e processados.
- **raw**: Contém os dados no formato **Parquet** em lotes (chunked), após a leitura dos arquivos JSON.
- **curated**: Contém os dados processados e limpos, prontos para análises e agregações.
- **modeled**: Contém os dados finais organizados para serem utilizados em ferramentas de análise como o Power BI.

## Fluxo de Movimentação de Dados

1. **Leitura dos Arquivos Brutos (data)**:
   Os dados originais estão armazenados no formato **JSON** no diretório `data`. Esses arquivos são lidos e processados para o formato **Parquet**.

2. **Processamento para Raw**:
   Após a leitura dos arquivos JSON, os dados são transformados em **Parquet** e organizados em lotes. Esses dados são armazenados no diretório `raw`.

3. **Limpeza e Agregação para Curated**:
   Os dados do diretório `raw` são então processados para remover informações irrelevantes e agregar os dados de forma que fiquem prontos para análise. Os dados processados são armazenados no diretório `curated`.

4. **Modelagem e Preparação para Análise**:
   Finalmente, os dados no diretório `curated` são preparados para uso em ferramentas como o **Power BI**. As agregações e transformações necessárias são realizadas e os dados finais são salvos no diretório `modeled`.

## Script de cargas
Na pasta src contém os scripts usado para transferência dos dados

- **raw_pipeline.ipynb**: transfere os dados do diretório `data` (origem), para diretório `raw`.
- **curated_*.ipynb**: transfere os dados do diretório `raw` para diretório `curated`.
- **modeled_*.ipynb**: transfere os dados do diretório `curated` para diretório `modeled`, gravados em arquivo excel para serem utilizado no Power BI.

## Objetivo Final

Os dados no diretório `modeled` são prontos para uso em ferramentas de análise como **Power BI**. Essas ferramentas são usadas para gerar relatórios, dashboards e outras visualizações de dados.

## Dependências

As bibliotecas necessárias para rodar este projeto podem ser instaladas a partir do arquivo `requirements.txt` com o seguinte comando:

```bash
pip install -r requirements.txt
