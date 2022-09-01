# PD-Mice tutorial

###### Steps done so far:

#### PD Mice: Sample metadata - Detalhes sobre como/quando/onde usar metadata, incluindo os comandos.

1) Download tsv
2) Transformar artefato para visualização .qzv
3) Visualizar no QIIME2 View
**OBS:** QIIME2 suporta dois tipos de metadata: categórico e numérico - ele deduz que colunas com apenas números são numéricas e as demais são categóricas, sendo *missing data* suportado por ambos os tipos.
4) Para mostrar ao QIIME qual é o tipo da coluna, usar **#q2:types**
**OBS:** usar Keemei para validar metadata


#### PD Mice: Importing demultiplexed sequences - Como importar com manifest file, usar `demux summarize` e visualizar os dados

- Os dados do tutorial têm 150 bp reads, curto demais para usar paired end, porque não são suficientes para sobreposição. Por isso, será usado single end.
- Manifest file: duas colunas (**sample id** e **absolute filepath**). No caso de paired end, teria uma terceira coluna para o filepath das reverse reads.
- `qiime demux summarize` - gera o arquivo .qzv para visualização no QIIME2 View. No tutorial é explicada a visualização dos gráficos. 
- **Provenance** mostra todo o caminho do que foi feito até ser gerado o arquivo.


#### PD Mice: Denoising

- Seguindo o tutorial, fiz o denoising, como já havia feito com os dados de bovinos.
- O próximo passo pós DADA2 é `qiime metadata tabulate`, que gera um .qzv como output e permite visualizar o que acontecer durante o denoising. Rodei com os dados do tutorial e com os dados de bovinos.
- A visualização mostra quantas sequências por amostra foram inseridas como input, quantas restaram após filtro etc
- O resultado ao rodar com os dados de bovinos foi muito diferente, foram eliminadas muitas sequências - vou fazer toda a análise desde o começo novamente, talvez com manifest file.
- `feature table summary` - depois do denoising, permite verificar os resultados olhando o resumo da feature table. Isso fornece as contagens associadas a cada sequência e cada feature, além de outros gráficos e métricas.

