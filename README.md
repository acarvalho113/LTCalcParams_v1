# Calculadora de Parâmetros de Linha de Transmissão - v1

- Solução para receber dados de uma LT trifásica e montar as matrizes de capacitância e de impedância.

## Entradas pelo usuário:
- Quantidade de fases;
- Quantidade de neutros;
- Quantidade de para-raios;
- Extensão da LT (km);
- Flechas de cada grupo de condutores (m);
- Temperatura ambiente (°C);
- Resistividade do solo (Ohm.m);
- Condutor utilizado na fase e nos neutros [Fonte: Cabos de Alumínio Nu com Alma de Aço - CAA (Série KCMIL)];
- Dados do condutor utilizado no para-raios;
- Posições baseadas em coordenadas cartesianas de cada grupo de condutores (fase, neutros e para-raios), onde x=0 é o condutor mais à esquerda e y=0 é o solo;

## Saídas para o usuário:
- Matrizes M1, M2, M3 e M4 (componentes da matriz de impedância);
- Matriz de impedância, reduzida a 3x3, quando houver para-raios ou neutros e sua média, caso necessário;
- Matriz de coeficientes de potencial, reduzida a 3x3, quando houver para-raios ou neutros e sua média, caso necessário;
- Matriz de capacitância e sua média, caso necessário.

## Fluxo do sistema:
Basicamente o sistema funciona em loop até a etapa de entrada das posições do condutores, pois ao final da identificação dos pontos correspondentes, o sistema vai plotar um gráfico com a representação das distâncias e disposições dos condutores, para que assim o usuário possa validar se os dados foram corretamente preenchidos. Caso queira, o usuário pode refutar a LT representada graficamente, interagindo com um questionamento do sistema e refazer o preenchimento das posições de cada grupo de condutores, podendo fazer esse processo até que alcance a distribuição desejada. Ao confirmar a disposição da LT que o usuário deseja, o sistema vai plotar os resultados e também a representação gráfica da LT para conferência.

## Dependências:
- numpy
- math
- cmath (log, sqrt)
- enum (Enum)
- matplotlib (pyplot)
- networkx
- os
