# Meta-DR: Meta-Learning for Dimensionality Reduction Recommendation

Meta-DR é um framework de meta-aprendizagem para recomendação de técnicas de redução de dimensionalidade com base nas características dos conjuntos de dados.

O projeto investiga como metafeatures podem ser utilizadas para modelar a relação entre as propriedades dos dados e o desempenho de diferentes técnicas de redução de dimensionalidade. Em vez de avaliar todas as técnicas disponíveis para cada novo conjunto de dados, o Meta-DR aprende a partir de experimentos anteriores e recomenda as técnicas com maior potencial de desempenho.

A metodologia utiliza conjuntos de dados da plataforma OpenML, extrai metafeatures por meio da biblioteca PyMFE, aplica um processo de seleção de metafeatures e treina um meta-modelo baseado em Random Forest para predizer rankings de técnicas de redução de dimensionalidade.

Os experimentos foram realizados em 94 conjuntos de dados de classificação e avaliados por meio do coeficiente de correlação de Spearman e da métrica F1-score. Os resultados mostram que foi possível reduzir o conjunto inicial de 1.146 metafeatures para apenas 25 atributos selecionados, mantendo a capacidade do sistema em recomendar técnicas de redução de dimensionalidade de forma competitiva.

Este repositório contém a implementação completa do framework Meta-DR, incluindo extração de metafeatures, seleção de atributos, avaliação de técnicas de redução de dimensionalidade, construção do meta-conjunto de dados, treinamento do meta-modelo e análise experimental.


## Repository structure and usage

- **`Meta_DR.ipynb`**: Main notebook with the full pipeline (meta-feature extraction, DR evaluation, meta-dataset construction, meta-learner training, and evaluation).
- **`data/`**: Processed data (baseline classification, DR results, meta-features, predictions)..

### Running on your PC

1. **Clone the repo** and open the project folder (e.g. `meta-dr/`).
2. **Optional but recommended:** create a virtual environment so dependencies stay isolated:
   ```bash
   python -m venv .venv
   source .venv/bin/activate   # Linux/macOS
   # or:  .venv\Scripts\activate   # Windows
   ```
   On **Debian/Ubuntu**, if you get *ensurepip is not available*, install the venv package first:
   ```bash
   sudo apt install python3.12-venv   # or python3-venv
   ```
   then run `python -m venv .venv` again.
3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Open and run the notebook** from the **project root** (so paths like `data/...` work). Use Jupyter, VS Code, or any environment that runs `.ipynb` files.

The first cell installs `openml`, `pymfe`, and `mlxtend` if you are on Google Colab; when running locally, those packages are provided by `requirements.txt`. The notebook detects local runs and skips Google Drive mount, so no `.venv` or Colab is required—but using a `.venv` is recommended to avoid conflicts with other Python projects.
