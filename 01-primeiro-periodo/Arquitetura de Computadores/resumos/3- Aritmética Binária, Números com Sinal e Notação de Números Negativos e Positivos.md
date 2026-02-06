
---
# Resumo: Aritmética Binária e Números com Sinal

Este resumo abrange as operações matemáticas fundamentais no sistema binário e as diferentes notações utilizadas para representar números positivos e negativos em sistemas digitais.

## 1. Aritmética Binária (Arquivo 004)

Este módulo foca na realização de operações aritméticas (soma, subtração e multiplicação) diretamente na base 2, essencial para a arquitetura de computadores.

### 1.1. Motivação

Embora seja possível converter números binários para decimal, operar e converter de volta, esse processo é ineficiente. Os computadores modernos operam diretamente sobre números na base 2, portanto, é necessário compreender os algoritmos nativos dessa base.

### 1.2. Operações Básicas

#### Adição

A soma binária segue a mesma lógica posicional do sistema decimal, somando-se algarismo a algarismo da direita para a esquerda.

- **Regra principal:** $1 + 1 = 0$ e transporta 1 (_carry_) para a coluna da esquerda.
- Exemplo: $11_{(2)} + 10_{(2)} = 101_{(2)}$.

#### Subtração

A subtração também alinha as casas e opera da direita para a esquerda.

- **Empréstimo:** Quando o subtraendo é maior que o minuendo (ex: $0 - 1$), realiza-se um "empréstimo" (_borrow_) da coluna à esquerda.
- O algarismo que empresta é decrementado, e o que recebe o empréstimo ganha o valor da base (2).
- Exemplo: $10010_{(2)} - 10001_{(2)} = 1_{(2)}$.

#### Multiplicação

Utiliza-se o algoritmo da "multiplicação longa", análogo ao decimal.

- Multiplica-se o primeiro operando por cada bit do segundo operando, alinhando os resultados parciais.
- Como os bits são apenas 0 ou 1, as multiplicações parciais são simples: ou o resultado é zero, ou é a cópia do primeiro operando.
- Ao final, somam-se os resultados parciais.

#### Divisão

A divisão é considerada a operação mais complexa, envolvendo subtrações e multiplicações, e não é abordada profundamente neste material.

---

## 2. Notação de Números Negativos e Positivos 

Este módulo trata de como codificar sinais (+ e -) utilizando apenas bits (0 e 1) e como os sistemas digitais padronizam essas representações.

### 2.1. Tipos de Representação

Existem três formas principais de representar números com sinal em binário:

1. **Sinal-Módulo:**
    
    - Acrescenta-se um bit de sinal à esquerda do número.
    - Convenção: **0** indica positivo e **1** indica negativo.
    - O restante dos bits representa a magnitude (valor absoluto) do número.
2. **Complemento a 1 (C1):**
    
    - Obtido pela inversão de todos os bits do número original (0 vira 1, 1 vira 0).
    - É usado principalmente como passo intermediário para calcular o Complemento a 2.
3. **Complemento a 2 (C2):**
    
    - É a notação padrão para números negativos em sistemas digitais.
    - **Cálculo:** Obtém-se calculando o Complemento a 1 e somando 1 ao resultado ($C2 = C1 + 1$).

### 2.2. Notação em Sistemas Digitais

Nos sistemas digitais, o bit mais à esquerda (MSB) funciona como indicador de sinal e definição de codificação:

- **Bit 0:** O número é positivo e sua representação é em binário normal.
- **Bit 1:** O número é negativo e está representado em **Complemento a 2**.

### 2.3. Faixa de Representação e Bits Necessários

A quantidade de bits ($N$) define o intervalo de números que podem ser representados.

- **Fórmula da Faixa:** De $-2^{(N-1)}$ até $+2^{(N-1)} - 1$.
- **Exemplo (4 bits):** Representa de -8 até +7.
- **Adequação:** É crucial usar um número de bits suficiente para incluir o sinal e a magnitude. Por exemplo, para representar o número -9, 4 bits não são suficientes (o intervalo vai apenas até -8); seriam necessários 5 bits.

### 2.4. Aritmética com Complemento a 2

A grande vantagem do Complemento a 2 é a simplificação do hardware:

- Para realizar uma subtração ou soma com números negativos, basta converter o número negativo para C2 e realizar uma **soma** normal.
- Isso permite que o mesmo circuito somador realize tanto adições quanto subtrações.
- Para descobrir o valor decimal de um número negativo em C2, basta aplicar o processo de complemento a 2 novamente sobre ele.