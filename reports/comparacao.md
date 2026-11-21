# Comparação r1 vs. r2

## 1. Versões comparadas
- **Versão `r1`:** etiqueta `modelo-r1`, *commit* `5808a296cbe0199165a91fae76bd34d02aea4517`.
- **Versão `r2` (revisada):** etiqueta `modelo-r2` e alterações mescladas a partir do *branch* `correcao-rotulo` para a `main`.

## 2. Critério e resultado da revisão
- **Critério de revisão:** revisão de rótulos e dados da rodada `r2`.
- **Resultado da revisão:** comparação entre `r1` e `r2` registada na revisão.
- **Rastreabilidade por etiquetas:** as etiquetas `modelo-r1` e `modelo-r2` permitem selecionar os artefactos exatos de cada rodada.

## 3. Evidência de restauração (`modelo-r1`)
- **Procedimento:** restauração da versão `r1` via Git e DVC com estado limpo (`md5: 8fead0c04eb5043fe59ff5a8d6db4a1c`, `325` bytes), dispensando novo treino.
- **SHA do *commit* (`git rev-parse HEAD`):** `5808a296cbe0199165a91fae76bd34d02aea4517`.
- **Conferência de *hashes* SHA-256 face a `reports/modelo.json`:**
  - `data/split.csv` (`split_sha256`): confere com o manifesto.
  - `models/model.json` (`artifact_sha256`): `72a3a67936139a3473838a6dcfa7aae1acb4c23467be1ef1056d51d485b94840` (confere com o manifesto).
  - `data/chamados.csv` (`dataset_sha256`): o ficheiro restaurado (`325` bytes, `md5: 8fead0c04eb5043fe59ff5a8d6db4a1c`) tem SHA-256 `d03630a90bd7fc7cb1b6dfb7d8381d05e13f9669bf1146a5c3474941afb6238c`, enquanto `reports/modelo.json` no *commit* `5808a296cbe0199165a91fae76bd34d02aea4517` contém `590bbe63f34ea4fdd0e1cb1df9000c24c733714a14f78e5efb9938ea77123445` porque o manifesto foi gerado antes da configuração final de *bytes*/quebra de linha/BOM do CSV.
