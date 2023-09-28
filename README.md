# ProjetoDio-TranformandoDados
Esse projeto tem como objetivo responder ao 2º desafio para os alunos do curso de Power BI Analyst, módulo 4.

## IMAGEM

![Captura de tela 2023-09-28 184005](https://github.com/LeviMarra/ProjetoDio-TranformandoDados/assets/137719953/bb98bc7c-0caa-4b6e-90dd-2bf3ad9843fe)

## Passo a Passo
A construção foi feita de acordo com as exigências do desafio, criei um star schema da sample financials utilizando a tabela VENDAS como tabela principal.
F_Vendas composta pelas colunas: SK_ID; Sales; Country; Date(Month Name, Year); Discount Band; Product; ID_Product; Segment; ID_Segment; Profit; Sale Price; Unit Sold.
E as tabelas dimensões: D_Produtos; D_ProdutosDetalhes; D_Detalhes; D_Descontos e Calendário.
As tabelas D_Produtos, D_Descontos e D_ProdutosDetalhes tiveram o relacionamento criado com a tabela fato a partir da coluna ID_Produto.
A tabela D_Detalhes que contém informações extras de detalhes que não se encontram nas outras tabelas teve o relacionamento criado com a tabela fato a partir da coluna Sales.
A tabela Calendário foi criada utilizando o DAX e teve seu relacionamento criado com a tabela fato a partir de Data.

## Utilizando o Dax 
A tabela Calendário foi criada utilizando as seguintes funções dax:
Criar nova tabela,
Calendário = CALENDARAUTO(12).
Criar nova coluna, ja dentro da tabela Calendário,
Year = YEAR('Calendário'[Date]).
Criar nova coluna, ja dentro da tabela Calendário novamente.
Month Name = MONTH('Calendário'[Date]).

Decidi por utilizar somente essas medidas por que era o padrão do resto do esquema.
