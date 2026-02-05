
Este material aborda os conceitos fundamentais de sistemas de numeração, com foco na arquitetura de computadores, especificamente a transição entre a base decimal e a base binária, incluindo números inteiros e fracionários.

## 1. Introdução aos Sistemas de Numeração

Um sistema de numeração é um sistema de escrita para expressar números através de símbolos. O valor de um símbolo depende não apenas do símbolo em si, mas também de sua posição (sistema posicional).

### O Sistema Decimal (Base 10)

- É o sistema utilizado no dia a dia.
- Possui 10 símbolos (algarismos): 0 a 9.
- Cada posição representa uma potência de 10 ($10^0, 10^1, 10^2, \dots$).
- O valor total é a soma de cada algarismo multiplicado pela potência de 10 correspondente à sua posição.

## 2. Bases Numéricas

Podemos utilizar qualquer base $k$ para representar números.

- Uma base $k$ possui $k$ símbolos possíveis (de $0$ a $k-1$).
- Cada posição corresponde a um multiplicador que é uma potência de $k$.

### Por que Base Binária (Base 2)?

Enquanto computadores antigos usavam base 10, os computadores modernos têm como unidade básica de informação o **bit**, que assume dois estados (0 ou 1). Portanto, é mais eficiente representar dados na base 2.

- **Outras Bases:** O material cita as bases **Octal (8)** e **Hexadecimal (16)** como formas de agrupar bits e prover representações mais compactas utilizadas em programação.

### Notação

Para distinguir números iguais em bases diferentes (ex: 1010 existe na base 2 e na 10), utiliza-se a notação com a base subscrita entre parênteses:

- Exemplo: $1010_{(2)}$ (binário) vs $10_{(10)}$ (decimal).

## 3. Conversões Numéricas

### 3.1. Binário para Decimal (Inteiros)

A regra de formação consiste no somatório de cada bit multiplicado pela base (2) elevada à potência de sua posição (começando de 0 na direita).

- **Método:** Multiplicar cada bit por $2^n$ (onde $n$ é a posição do bit) e somar os resultados.
- **Exemplo:** $110101_{(2)} = 32 + 16 + 0 + 4 + 0 + 1 = 53_{(10)}$.

### 3.2. Decimal para Binário (Inteiros)

Utiliza-se o **Método das Divisões Sucessivas**.

1. Divide-se o número decimal por 2 repetidamente.
2. O processo para quando o quociente for indivisível.
3. O número binário é formado pelo **último quociente** seguido de todos os **restos** na ordem inversa (do último para o primeiro).

- **Nota:** O último resto/quociente corresponde ao MSB (Bit Mais Significativo) e o primeiro resto ao LSB (Bit Menos Significativo).

### 3.3. Números Fracionários

#### Binário Fracionário para Decimal

Aplica-se a mesma regra da soma das potências, porém as posições após a vírgula utilizam potências negativas ($2^{-1}, 2^{-2}, 2^{-3}, \dots$).

- Exemplo: $101,101_{(2)}$
    - Parte inteira: $1 \cdot 4 + 0 \cdot 2 + 1 \cdot 1 = 5$
    - Parte fracionária: $1 \cdot 0,5 + 0 \cdot 0,25 + 1 \cdot 0,125 = 0,625$
    - Resultado: $5,625_{(10)}$.

#### Decimal Fracionário para Binário

O processo é dividido em duas partes:

1. **Parte Inteira:** Converte-se usando o método das divisões sucessivas.
2. **Parte Fracionária:** Utiliza-se o **Método da Multiplicação Sucessiva**.
    - Multiplica-se a parte fracionária por 2.
    - O algarismo inteiro resultante (0 ou 1) torna-se parte do número binário.
    - Repete-se o processo apenas com a parte fracionária restante.
    - O processo para quando a parte fracionária for nula ou atingir a precisão desejada.

- **Exemplo:** $0,375_{(10)} = 0,011_{(2)}$.
