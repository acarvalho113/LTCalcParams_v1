# Calculadora de Parâmetros de Linha de Transmissão - v1

- Solução para receber dados de uma LT trifásica e montar as matrizes de capacitância e de impedância.

## Entradas pelo usuário:
- Quantidade de fases;
- Quantidade de neutros;
- Quantidade de para-raios;
- Extensão da LT (km);
- Condutor utilizado na fase e nos neutros [Fonte: Cabos de Alumínio Nu com Alma de Aço - CAA (Série KCMIL)];
- Posições baseadas em coordenadas cartesianas de cada grupo de condutores (fase, neutros e para-raios), onde x=0 é o condutor mais à esquerda e y=0 é o solo;

## Saídas para o usuário:
- Matrizes M1, M2, M3 e M4 (componentes da matriz de impedância);
- Matriz de impedância e sua média, caso necessário;
- Matriz reduzida, para casos onde sejam indicados neutros e/ou para-raios e sua média, caso necessário;
- Matriz de coeficientes de potencial;
- Matriz de capacitância e sua média, caso necessário.

## Fluxo do sistema:
Basicamente o sistema funciona em loop até a etapa de entrada das posições do condutores, pois ao final da identificação dos pontos correspondentes, o sistema vai plotar um gráfico com a representação das distâncias de disposições dos condutores, para que assim o usuário possa validar se os dados foram corretamente preenchidos nessa etapa de suma importância. Caso queira, o usuário pode refutar a LT representada graficamente e refazer o preenchimento das posições de cada grupo de condutores, podendo fazer esse processo até que alcance a distribuição desejada.

## Dependências:
- numpy
- math
- cmath (log, sqrt)
- enum (Enum)
- matplotlib (pyplot)
- networkx
- os
