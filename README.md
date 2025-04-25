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
git clone https://github.com/edrikfsteiner/projeto-eng-dados.git
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

## Referências

- https://www.youtube.com/watch?v=WwrX1YVmOyA&pp=ygUKZGF0YXdheSBictIHCQmECQGHKiGM7w%3D%3D
- https://datawaybr.medium.com/do-zero-ao-pyspark-em-1h-4185005771e5
- https://github.com/jlsilva01/spark-delta
- https://github.com/jlsilva01/spark-iceberg