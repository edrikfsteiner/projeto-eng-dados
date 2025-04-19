# Operações com Apache Iceberg

Este documento apresenta exemplos práticos de como realizar operações básicas em tabelas Apache Iceberg utilizando PySpark e Spark SQL.

---

## INSERT

A operação de **INSERT** insere novos registros em uma tabela Iceberg.

```python
spark.sql("INSERT INTO local.carro_iceberg VALUES (1, 'XYZ1J34'), (2, 'RLC5B93'), (3, 'ABV1V23')")
```

Esse comando insere três registros na tabela `carro_iceberg`.

---

## UPDATE

A operação de **UPDATE** permite modificar registros existentes com base em uma condição.

```python
spark.sql(
    """
    update local.carro_iceberg set marca = 'Renault', modelo = 'Sandero', ano = 2021 where id = 1
    """
)

spark.sql('update local.carro_iceberg set marca="GM", modelo="tracker", ano=2020 where id = 2')
spark.sql('update local.carro_iceberg set marca="Ford", modelo="EcoSport", ano=2022 where id = 3')
```

Esses comandos atualizam os campos `marca`, `modelo` e `ano` dos registros com base no `id`.

---

## DELETE

A operação de **DELETE** remove registros de uma tabela Iceberg com base em uma condição.

```python
spark.sql('delete from local.carro_iceberg where id = 3')
```

Esse comando remove o registro com `id = 3` da tabela `carro_iceberg`.

> **Observação:** O Apache Iceberg também oferece suporte a operações de remoção com filtros mais complexos, desde que o engine utilizado suporte a sintaxe SQL compatível.

