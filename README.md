# Análise de Campanhas de Marketing com Power BI

Painel em Power BI que analisa se as campanhas de marketing atraem clientes mais valiosos. Projeto feito a partir do mini-projeto do capítulo 4 do curso de Power BI da Data Science Academy, com perguntas, medidas e mudanças de layout próprias.

## Problema de negócio

Um gestor de marketing quer saber se vale a pena investir em campanhas. Para isso, defini 3 perguntas:

1. Clientes que aceitaram alguma campanha têm ticket médio maior que os que nunca aceitaram?
2. Quais campanhas atraíram clientes com mais compras, em comparação aos orgânicos (que não aceitaram nenhuma campanha)?
3. Quantos clientes responderam à última campanha, e a taxa foi maior ou menor que a das anteriores?

## Dados

Base de 1.999 clientes (27 colunas) fornecida no curso: perfil (escolaridade, estado civil, salário, filhos, país), gastos por categoria, compras por canal (web, catálogo, loja) e resposta a 6 campanhas.

A coluna `Comprou` indica a resposta à última campanha (1 = comprou, 0 = não comprou). Confirmei isso pelos próprios dados: quase todos os clientes têm compras, mas só 16% têm `Comprou` = 1.

## Limpeza e preparação

- Corrigi o tipo da coluna `Comprou` de texto para número inteiro no Power Query, para que a etapa fique registrada e rode de novo a cada atualização.
- Mantive a coluna numérica para os cálculos e criei uma versão em texto (Sim/Não) para exibição nos gráficos.
- Na análise exploratória, encontrei problemas de qualidade que ainda não tratei: 44 clientes repetidos com ID diferente, 19 salários vazios, 6 clientes sem nenhuma compra e datas de cadastro em formato misto.

## O que eu fiz

- **Colunas calculadas:** `Total Compras` (web + catálogo + loja) e `Aceitou Campanha` (Sim se aceitou pelo menos uma das campanhas 1 a 5).
- **Medidas DAX:** `Ticket Médio` (total gasto ÷ total de compras) e `% Conversão` (clientes que responderam à última campanha ÷ total de clientes).
- **Layout:** na Visão das Campanhas, troquei o gráfico de "comprou × não comprou" por um que responde à pergunta 1, adicionei um cartão com a taxa de resposta e padronizei cores (Sim = azul, Não = cinza) e títulos.

## Principais achados

- Quem aceitou alguma campanha gasta **R$ 65,74 por compra**, contra **R$ 41,58** de quem nunca aceitou: **58% a mais**.
- **16%** dos clientes responderam à última campanha.

## Próximos passos

- Montar os gráficos das perguntas 2 e 3 (compras por campanha × orgânicos e taxa de resposta de cada campanha).
- Tratar os problemas de qualidade: remover os clientes repetidos e preencher os salários vazios com a mediana.

## Ferramentas

Power BI Desktop · Power Query · DAX
