
Este material complementa o estudo das bases numéricas, focando em duas bases essenciais para a computação que servem como formas compactas de representar sequências binárias: a base 8 (Octal) e a base 16 (Hexadecimal).

## 1. Sistema Octal de Numeração
### Definição

- **Base:** 8.
- **Algarismos:** 0, 1, 2, 3, 4, 5, 6, 7.
- **Representação de Quantidade:** A quantidade "oito" não possui um símbolo único; ela é representada como $10_{(8)}$ (análogo ao dez no sistema decimal).

### Conversões no Sistema Octal

#### 1.1. Octal para Decimal

Utiliza-se o conceito posicional (soma das potências da base 8). Multiplica-se cada algarismo por $8^n$, onde $n$ é a posição do dígito (começando de 0 na direita).

- **Exemplo ($144_8$):** $1 \cdot 8^2 + 4 \cdot 8^1 + 4 \cdot 8^0 = 64 + 32 + 4 = 100_{(10)}$.

#### 1.2. Decimal para Octal

Utiliza-se o **Método das Divisões Sucessivas** pela base 8.

- Divide-se o número decimal por 8 repetidamente até que o quociente seja indivisível.
- O resultado é lido do último quociente seguido pelos restos na ordem inversa (baixo para cima).
- **Exemplo ($92_{10}$):**
    - $92 \div 8 = 11$ (resto 4)
    - $11 \div 8 = 1$ (resto 3)
    - Resultado: $134_{(8)}$.

#### 1.3. Octal para Binário

A conversão é direta, baseada na propriedade de que $2^3 = 8$. Portanto, **cada algarismo octal equivale a 3 bits**.

- **Método:** Substituir cada dígito octal pelo seu correspondente binário de 3 bits.
- **Exemplo ($34_8$):**
    - $3 \to 011$
    - $4 \to 100$
    - Resultado: $11100_2$ (ou $011100$).

#### 1.4. Binário para Octal

Realiza-se o processo inverso.

- **Método:** Agrupa-se os bits de **3 em 3**, começando da direita para a esquerda. Se o último grupo não tiver 3 bits, completa-se com zeros à esquerda.
- **Exemplo ($110010_2$):**
    - Separação: $110$ | $010$
    - Conversão: $6$ | $2$
    - Resultado: $62_{(8)}$.

---

## 2. Sistema Hexadecimal de Numeração

### Definição

- **Base:** 16.
- **Algarismos:** Possui 16 símbolos: 0 a 9 e as letras de A a F.
    - A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.
- **Representação de Quantidade:** A quantidade "dezesseis" é representada como $10_{(16)}$.

### Conversões no Sistema Hexadecimal

#### 2.1. Hexadecimal para Decimal

Utiliza-se a soma das potências da base 16. As letras devem ser substituídas pelos seus valores decimais correspondentes durante o cálculo.

- **Exemplo ($3F_{16}$):**
    - $F = 15$
    - $3 \cdot 16^1 + 15 \cdot 16^0 = 48 + 15 = 63_{(10)}$.
- **Exemplo ($1C3_{16}$):**
    - $C = 12$
    - $1 \cdot 16^2 + 12 \cdot 16^1 + 3 \cdot 16^0 = 256 + 192 + 3 = 451_{(10)}$.

#### 2.2. Decimal para Hexadecimal

Utiliza-se o **Método das Divisões Sucessivas** pela base 16.

- Divide-se o número por 16 e coletam-se os restos. Se um resto for maior que 9, deve-se substituí-lo pela letra correspondente (ex: resto 14 vira E).
- **Exemplo ($1000_{10}$):**
    - $1000 \div 16 = 62$ (resto 8)
    - $62 \div 16 = 3$ (resto 14 $\to$ E)
    - Último quociente: 3.
    - Resultado: $3E8_{(16)}$.

#### 2.3. Hexadecimal para Binário

A conversão baseia-se na propriedade de que $2^4 = 16$. Logo, **cada algarismo hexadecimal equivale a 4 bits**.

- **Exemplo ($1ED_{16}$):**
    - $1 \to 0001$
    - $E (14) \to 1110$
    - $D (13) \to 1101$
    - Resultado: $111101101_2$ (zeros à esquerda podem ser omitidos).

#### 2.4. Binário para Hexadecimal

Agrupam-se os bits de **4 em 4**, da direita para a esquerda.

- **Exemplo ($1100011_2$):**
    - Separação: $0110$ (completado com zero) | $0011$
    - Conversão: $6$ | $3$
    - Resultado: $63_{(16)}$.

---

## Resumo Comparativo das Conversões Binárias

Ambos os arquivos destacam a facilidade de conversão entre Binário e estas bases (Octal/Hexadecimal) devido à relação de potências de 2:

|Sistema|Base|Potência de 2|Bits por Grupo|
|:--|:--|:--|:--|
|**Octal**|8|$2^3$|3 bits|
|**Hexadecimal**|16|$2^4$|4 bits|
