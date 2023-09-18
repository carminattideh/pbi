## **editor avançado**

```DAX
let
    Fonte = MySQL.Database("sig.viaaroma.com.br", "via_aroma_operacional", [ReturnSingleDatabase=true, Query="SELECT#(lf)v.filial_id,#(lf)v.finalidade_pedido,#(lf)v.data,#(lf)v.status,#(lf)v.cliente_id,#(lf)v.cliente_codigo,#(lf)v.icms_base,#(lf)v.icms_valor,#(lf)v.total_produtos AS total_faturado,#(lf)v.valor_frete,#(lf)v.valor_outras_despesas,#(lf)v.ipi_valor,#(lf)v.valor_acrescimo,#(lf)v.valor_desconto,#(lf)v.total_pedido AS total_nf,#(lf)v.vendedor_id,#(lf)v.vendedor_nome,#(lf)v.pedido_venda_forma_id,#(lf)v.contas_portador_id,#(lf)v.nf_gerada,#(lf)v.nf_data_hora AS data_nf,#(lf)v.nf_numero#(lf)FROM#(lf)pedidos_vendas v#(lf)WHERE#(lf)v.nf_data_hora <= CURDATE()#(lf)AND v.nf_gerada = 's'#(lf)AND v.pedido_venda_forma_id <> '1'#(lf)UNION#(lf)#(lf)SELECT#(lf)v.filial_id,#(lf)v.finalidade_pedido,#(lf)v.data,#(lf)v.status,#(lf)v.cliente_id,#(lf)v.cliente_codigo,#(lf)v.icms_base,#(lf)v.icms_valor,#(lf)v.total_produtos AS total_faturado,#(lf)v.valor_frete,#(lf)v.valor_outras_despesas,#(lf)v.ipi_valor,#(lf)v.valor_acrescimo,#(lf)v.valor_desconto,#(lf)v.total_pedido AS total_nf,#(lf)v.vendedor_id,#(lf)v.vendedor_nome,#(lf)v.pedido_venda_forma_id,#(lf)v.contas_portador_id,#(lf)v.nf_gerada,#(lf)v.nf_data_hora AS data_nf,#(lf)v.nf_numero#(lf)FROM#(lf)pedidos_vendas_finalizados_2022 v#(lf)WHERE#(lf)v.nf_data_hora <= CURDATE()#(lf)AND v.nf_gerada = 's'#(lf)AND v.pedido_venda_forma_id <> '1'"]),
    #"Tipo Alterado" = Table.TransformColumnTypes(Fonte,{{"data", type date}, {"data_nf", type date}})
in
    #"Tipo Alterado"

```
