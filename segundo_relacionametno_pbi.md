## **Ativando segundo relacionamento da tabela**

```DAX
nome_medida = calculate(
  [medida],
userrelationship(tabela1[campo], tabela2[campo]))
```

```Exemplo
relacionamento ativo = dim_calendario[data] > fat_funcionarios[data_contratacao]
relacionmento inativo = dim_calendario[data] > fat_funcionarios[data_demissao]

- Para esses casos o padrão PBI é criar visuais baseados na data de contratação, para que ele também considere a
data de demissão de cada funcionário é necessário forçar a ativação do segundo relacionamento

demissoes na data = calculate(
  [total_demissoes],
userrelationship(dim_calendario[data], fat_funcionarios[data_demissao]))

```
