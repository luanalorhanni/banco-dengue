# banco-dengue

Unificação das bases de notificação de dengue do **SINAN/DATASUS** (2016–2022) num único banco SQLite, feita durante pesquisa de Iniciação Científica financiada pelo **CNPq**.

## O problema

O DATASUS publica os registros de dengue em arquivos anuais separados, e o esquema muda de ano para ano — colunas aparecem, somem e trocam de tipo. Comparar séries históricas exige antes reconciliar tudo num esquema único.

## O que tem aqui

| arquivo | o que faz |
|---|---|
| `db-bases-dengue/conexao.py` | esquema da tabela unificada e carga no SQLite |
| `db-bases-dengue/tratamento/tratamento.ipynb` | normalização das bases anuais até o esquema comum |

## Os dados não estão neste repositório

Os microdados do SINAN são registros individuais de notificação de saúde. Mesmo pseudonimizados — sem nome, sem CPF, sem endereço — eles carregam data de nascimento, sexo, raça, ocupação, município de residência, sintomas e evolução do caso. Por isso não são versionados aqui.

Para reproduzir, baixe as bases DENGBR do DATASUS e coloque em `db-bases-dengue/tratamento/`:

- <https://datasus.saude.gov.br/transferencia-de-arquivos/> → SINAN → Dengue
- arquivos esperados: `dengbr16.csv`, `dengbr17.csv`, `dengbr18.csv`, `dengbr19.csv`, `dengbr21.csv`, `dengbr22.csv`

## Licença

[MIT](LICENSE) — aplica-se ao código. Os dados do SINAN são do Ministério da Saúde e seguem os termos do DATASUS.
