### Relatório sobre o Código de Criptografia e Decriptografia com Matrizes

O código em questão implementa um método de criptografia e decriptografia utilizando conceitos de álgebra linear, mais especificamente a multiplicação de matrizes e vetores, combinada com a lógica de uma cifra do tipo Enigma.

#### Estrutura do Código

1. **Alfabeto em Vetores**: O alfabeto é representado como vetores de 26 dimensões, onde cada letra corresponde a um vetor esparso com um único elemento igual a 1 na posição da letra (ex.: 'A' é representado por `[1, 0, 0, ..., 0]`). Isso permite a manipulação algébrica das letras como vetores em um espaço de 26 dimensões.

2. **Matrizes de Codificação**: Duas matrizes quadradas `P` e `Q`, de ordem 26, são usadas como chaves para criptografar e decriptografar a mensagem. Essas matrizes devem ser invertíveis para que a decriptografia seja possível.

3. **Criptografia**:
    - Cada letra da mensagem é convertida em seu vetor correspondente.
    - Esse vetor é multiplicado pela matriz `P` e, em seguida, pela matriz `Q`, resultando em um novo vetor codificado.
    - O vetor resultante é então mapeado de volta para uma letra utilizando a estrutura inversa do alfabeto.

4. **Decriptografia**:
    - O processo inverso é realizado na decriptografia. O vetor codificado é multiplicado pela inversa da matriz `Q` e depois pela inversa da matriz `P`.
    - O vetor resultante dessa multiplicação é convertido de volta na letra original.

#### Matemática Utilizada

A base matemática do código é a multiplicação de matrizes e vetores. No processo de criptografia, a ideia é transformar o vetor original, que representa uma letra, em um novo vetor que é difícil de associar ao original sem conhecer as matrizes `P` e `Q`.

- **Multiplicação de Matriz por Vetor**: Dada uma matriz `M` e um vetor `v`, a multiplicação `M @ v` produz um novo vetor. Essa operação é a base da transformação das letras.

- **Inversa de Matriz**: Para recuperar a mensagem original, precisamos das matrizes inversas de `P` e `Q`. A matriz inversa de uma matriz `M` é tal que `M @ M^(-1) = I`, onde `I` é a matriz identidade. Isso garante que a operação de criptografia possa ser revertida.

- **Espaço Vetorial de Dimensão 26**: As letras são tratadas como vetores em um espaço de 26 dimensões, permitindo a aplicação de transformações lineares (multiplicações por matrizes) de forma direta.

#### Considerações

O método é uma versão simplificada de técnicas mais complexas usadas em criptografia. O uso de matrizes adiciona uma camada de segurança, uma vez que a transformação das letras depende de operações que são difíceis de reverter sem o conhecimento das chaves (as matrizes `P` e `Q`). A eficácia desse método depende da complexidade das matrizes utilizadas, onde a aleatoriedade e a invertibilidade são fundamentais.

O código serve como um exemplo didático para mostrar como conceitos de álgebra linear podem ser aplicados em criptografia, ilustrando a importância de matrizes e vetores na codificação de informações.