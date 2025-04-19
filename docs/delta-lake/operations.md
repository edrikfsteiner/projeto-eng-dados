# Operações com Delta Lake

Este documento apresenta exemplos práticos de como realizar operações básicas em tabelas Delta Lake utilizando PySpark e Spark SQL.

---

## INSERT

A operação de **INSERT** insere novos registros em uma tabela Delta Lake.

```python
spark.sql("INSERT INTO carro_delta VALUES (1, 'XYZ1J34'), (2, 'RLC5B93'), (3, 'ABV1V23')")
```

Esse comando insere três registros na tabela `carro_delta`.

---

## UPDATE

A operação de **UPDATE** permite modificar registros existentes com base em uma condição.

```python
spark.sql(
    """
    update carro_delta set marca = 'Renault', modelo = 'Sandero', ano = 2021 where id = 1
    """
)

spark.sql('update carro_delta set marca="GM", modelo="tracker", ano=2020 where id = 2')
spark.sql('update carro_delta set marca="Ford", modelo="EcoSport", ano=2022 where id = 3')
```

Esses comandos atualizam os campos `marca`, `modelo` e `ano` dos registros com base no `id`.

---

## DELETE

A operação de **DELETE** remove registros de uma tabela Delta Lake com base em uma condição.

```python
spark.sql("DELETE FROM carro_delta WHERE id = 1")
```

Esse comando remove o registro com `id = 1` da tabela `carro_delta`.

> **Observação:** O suporte a comandos `DELETE` depende da versão do Delta Lake e da configuração do ambiente Spark.

