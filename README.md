# Projeto PySpark com Delta Lake e Apache Iceberg

Projeto desenvolvido para demonstração de funcionalidades do Apache Spark (PySpark) com integração aos formatos Delta Lake e Apache Iceberg em ambiente local.

Ambiente Python isolado criado com [UV](https://github.com/astral-sh/uv), utilizando o JupyterLab como interface para notebooks.

## 📌 Descrição

Este projeto demonstra:

- Criação e manipulação de tabelas Delta Lake e Iceberg.
- Execução de comandos **INSERT**, **UPDATE** e **DELETE** com suporte transacional.
- Visualização e documentação utilizando **MkDocs**.
- Utilização de dados públicos (IBGE ou NYC Open Data).

## ⚠️ Avisos

- Este projeto é destinado a fins educacionais.
- Pode exigir permissões específicas para manipulação de arquivos locais.
- Certifique-se de ter recursos suficientes para executar Spark localmente.

## ✅ Pré-requisitos

- Python 3.10+
- Git
- [UV](https://github.com/astral-sh/uv) instalado (`pip install uv` ou via `pipx`)
- Java 8 ou superior
- Instalar dependências conforme instruções abaixo

## 🛠️ Instalação

1. Clone o repositório:

```bash
git clone https://github.com/seu-usuario/pyspark-lake-engine.git
cd pyspark-lake-engine
```

2. Inicialize o projeto com UV:

```bash
uv init
uv venv
source .venv/bin/activate
```

3. Adicione as bibliotecas necessárias:

```bash
uv add pyspark==3.5.3 delta-spark==3.2.0 jupyterlab ipykernel pandas matplotlib seaborn
```

4. Inicie o JupyterLab:

```bash
jupyter lab
```

⚠️ Certifique-se de selecionar o kernel `.venv` no notebook.

---

## ▶️ HowTo

Acesse os notebooks em `notebooks/` para exemplos funcionais:

- `delta-lake-notebook.ipynb` – Criação, inserção, atualização e exclusão com Delta Lake.
- `iceberg-notebook.ipynb` – Operações equivalentes com Apache Iceberg.

### 📊 Imagens e Modelo ER

Modelos relacionais, imagens, diagramas e dados de exemplo estão embutidos nos notebooks.

Exemplo de código (Delta Lake):

```python
from delta import configure_spark_with_delta_pip
from pyspark.sql import SparkSession

builder = SparkSession.builder \
    .appName("DeltaLakeExample") \
    .config("spark.sql.extensions", "io.delta.sql.DeltaSparkSessionExtension") \
    .config("spark.sql.catalog.spark_catalog", "org.apache.spark.sql.delta.catalog.DeltaCatalog")

spark = configure_spark_with_delta_pip(builder).getOrCreate()
```

---

## 🧪 Testes

Os notebooks contêm células com assertions para validação. Basta executar as células em sequência.

Para testar o ambiente:

```bash
python -c "import pyspark; print(pyspark.__version__)"
```

---

## 📘 Documentação

A documentação do projeto foi criada com o [MkDocs](https://www.mkdocs.org/):

### Executar servidor local:

```bash
pip install mkdocs
mkdocs serve
```

### Estrutura esperada:

- `docs/index.md` – Página inicial.
- `docs/delta-lake.md` – Documentação com comandos, imagens, modelo ER para Delta Lake.
- `docs/iceberg.md` – Documentação similar para Iceberg.