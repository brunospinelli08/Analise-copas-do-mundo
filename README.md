Análise Exploratória — Copas do Mundo FIFA (1930–2022)

Projeto da disciplina Python para Data Science (Prof. Victor Lattari) do curso de Engenharia de Computação da ESEG.

Autores: Bruno Spinelli e Cauã Guerreiro

Sobre o projeto

O projeto é uma análise exploratória de 1.248 partidas de Copas do Mundo FIFA: 22 edições masculinas (1930–2022) e 8 femininas (1991–2019). O objetivo é transformar dados em informação. Para isso, o trabalho verifica a qualidade dos registros, formula perguntas, constrói tabelas e gráficos e interpreta os resultados, sempre indicando as limitações.

As competições masculina e feminina são analisadas separadamente, porque têm históricos, números de edições e períodos muito diferentes.

Perguntas investigadas
Como o número de partidas por edição evoluiu?
A média de gols por partida mudou ao longo das edições?
Jogos decisivos (mata-mata) têm menos gols que a fase de grupos?
Quais seleções mais venceram? Com que frequência há empates?
Como se comparam Brasil e Alemanha, as duas seleções com mais vitórias?
Principais resultados
Achado	Evidência
O torneio cresceu, mas os jogos têm menos gols	A Copa masculina passou de 18 para 64 partidas. A média caiu de 4–5 gols por jogo nas primeiras edições para 2,2–2,7 desde 1994.
A Copa feminina se aproximou da masculina	Começou com média próxima de 3,8 gols por jogo e está em 2,7–2,8 desde 2011.
As fases decisivas não têm menos gols	Médias da fase de grupos: 2,67; semifinal: 3,47; final: 3,81. A prorrogação e as poucas finais limitam a comparação.
Brasil e Alemanha dominam o histórico	Brasil: 76 vitórias (67% dos jogos). Alemanha: 68 vitórias. A Argentina, 3ª colocada, tem 47.
Empates são menos comuns na Copa feminina	13,7% na feminina, contra 22,2% na masculina.
Tratamento dos dados

O dataset não tem valores ausentes nem registros duplicados. Nenhuma linha foi removida. As correções foram feitas em colunas novas, e as originais foram mantidas.

Fases padronizadas: a mesma fase aparecia escrita de formas diferentes (ex.: quarter-final e quarter-finals).
Pênaltis como empate: nos 43 jogos decididos nos pênaltis, o placar estava empatado, mas a coluna original registrava vitória. Os jogos foram tratados como empate, seguindo a convenção da FIFA.
Valores extremos mantidos: goleadas como 13 × 0 (EUA × Tailândia, 2019) são resultados reais, não erros de registro.
Alemanhas unificadas: "West Germany" (até 1990) e "Germany" (desde 1994) foram tratadas como uma única seleção.
Visualizações
Gráfico	Tipo	O que mostra
Partidas por edição	Barras	Crescimento do torneio, masculino e feminino
Média de gols por edição	Linha	Evolução dos gols ao longo do tempo
Gols por fase	Boxplot	Distribuição de gols da fase de grupos à final
Ranking de seleções	Barras horizontais	As 10 seleções com mais vitórias
Brasil × Alemanha	Linha	Vitórias acumuladas edição a edição
Limitações
Os dados mostram tendências, não causas: mudanças táticas, de regras e de formato podem explicar os resultados, mas não foram testadas.
O formato do torneio mudou várias vezes, o que dificulta comparações diretas entre épocas.
A Copa feminina tem apenas 8 edições, e a de 2023 não consta no dataset.
Algumas análises dependem de decisões de interpretação (pênaltis, Alemanhas), justificadas no notebook.
Estrutura do repositório
├── Analise_Copas_do_Mundo.ipynb      # Notebook com código, gráficos e interpretações
├── Apresentacao_Copas_do_Mundo.pdf   # Slides da apresentação
└── README.md
Como executar
Abra o arquivo Analise_Copas_do_Mundo.ipynb no Google Colab (Arquivo → Abrir notebook → GitHub).
Vá em Ambiente de execução → Executar tudo.

Os dados são lidos diretamente do repositório de origem, então não é preciso baixar nenhum arquivo.

Para rodar localmente:

bash
pip install pandas matplotlib seaborn jupyter
jupyter notebook Analise_Copas_do_Mundo.ipynb
Tecnologias
Python
Pandas: leitura, limpeza e agrupamento dos dados
Matplotlib e Seaborn: visualizações
Google Colab
Fonte dos dados

Fjelstul, Joshua C. The Fjelstul World Cup Database. Repositório: https://github.com/jfjelstul/worldcup Arquivo utilizado: matches.csv
