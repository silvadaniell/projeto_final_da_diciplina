# Meta-DR: Meta-Learning for Dimensionality Reduction Recommendation

Meta-DR é um framework de meta-aprendizagem para recomendação de técnicas de redução de dimensionalidade com base nas características dos conjuntos de dados.

O projeto investiga como metafeatures podem ser utilizadas para modelar a relação entre as propriedades dos dados e o desempenho de diferentes técnicas de redução de dimensionalidade. Em vez de avaliar todas as técnicas disponíveis para cada novo conjunto de dados, o Meta-DR aprende a partir de experimentos anteriores e recomenda as técnicas com maior potencial de desempenho.

A metodologia utiliza conjuntos de dados da plataforma OpenML, extrai metafeatures por meio da biblioteca PyMFE, aplica um processo de seleção de metafeatures e treina um meta-modelo baseado em Random Forest para predizer rankings de técnicas de redução de dimensionalidade.

Os experimentos foram realizados em 94 conjuntos de dados de classificação e avaliados por meio do coeficiente de correlação de Spearman e da métrica F1-score. Os resultados mostram que foi possível reduzir o conjunto inicial de 1.146 metafeatures para apenas 25 atributos selecionados, mantendo a capacidade do sistema em recomendar técnicas de redução de dimensionalidade de forma competitiva.

Este repositório contém a implementação completa do framework Meta-DR, incluindo extração de metafeatures, seleção de atributos, avaliação de técnicas de redução de dimensionalidade, construção do meta-conjunto de dados, treinamento do meta-modelo e análise experimental.


## Repository structure and usage

- **`Meta_DR.ipynb`**: Notebook principal contendo todo o fluxo do projeto, incluindo extração de metafeatures, avaliação das técnicas de redução de dimensionalidade, construção do meta-conjunto de dados, treinamento do meta-modelo e análise dos resultados.
- **`data/`**: Diretório contendo os dados processados utilizados durante os experimentos, incluindo resultados das técnicas de redução de dimensionalidade, metafeatures extraídas, rankings, previsões e demais artefatos gerados.
- 
### Executando o Projeto

1. **Clone o repositório.**
2. **Opcional, mas recomendado:** Crie um ambiente virtual:
```bash
   python -m venv .venv
   source .venv/bin/activate   # Linux/macOS
   # ou:  .venv\Scripts\activate   # Windows
```
   No **Debian/Ubuntu**, se você receber o erro *ensurepip is not available*, instale primeiro o pacote venv:
```bash
   sudo apt install python3.12-venv   # ou python3-venv
```
   Em seguida, execute `python -m venv .venv` novamente.
3. **Instale as dependências:**
```bash
   pip install -r requirements.txt
```
4. **Abra e execute o notebook** a partir da **raiz do projeto** (para que caminhos como `data/...` funcionem corretamente). Use o Jupyter, VS Code ou qualquer ambiente que execute arquivos `.ipynb`.

O primeiro cell instala `openml`, `pymfe` e `mlxtend` caso você esteja no Google Colab; ao executar localmente, esses pacotes já são fornecidos pelo `requirements.txt`. O notebook detecta execuções locais e pula a montagem do Google Drive, portanto nenhum `.venv` ou Colab é necessário — mas usar um `.venv` é recomendado para evitar conflitos com outros projetos Python.
