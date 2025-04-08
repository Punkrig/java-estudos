# java-estudos

# Anatomia de um programa em java
```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Olá, mundo!");
    }
}

```
1️⃣ **Declaração da classe**

```java
public class Main {
```

- Todo código em Java deve estar dentro de uma **classe**.
    
- O nome da classe **deve ser igual ao nome do arquivo** (`Main.java` → `class Main`).
    
- `public` significa que a classe pode ser acessada de qualquer lugar.
    

2️⃣ **Método principal (`main`)**

```java



public static void main(String[] args) {
```

- Esse método **é obrigatório** e é onde o programa começa a ser executado.
    
- `public` → Pode ser chamado de qualquer lugar.
    
- `static` → Permite chamar o método sem precisar criar um objeto da classe.
    
- `void` → Indica que o método não retorna nada.
    
- `String[] args` → Permite passar argumentos ao programa (pode ignorar por enquanto).
    

3️⃣ **Corpo do método (`main`)**

```java

System.out.println("Olá, mundo!");
```

- `System.out.println()` imprime algo na tela.
    
- Aqui, imprime `"Olá, mundo!"` no console.

# Variáveis
## **1. O que é uma variável?**

Uma variável é um **espaço na memória** do computador onde podemos armazenar um valor.  
No Java, para criar uma variável, precisamos definir **o tipo de dado** e **o nome** da variável.

### **Exemplo de variável:**

```java


`int idade = 25;`
```

Aqui, criamos uma variável chamada `idade`, que guarda o valor `25`.

---

## **2. Tipos de Variáveis em Java**

### ✅ **1. Variáveis Primitivas (Tipos Básicos)**

São os tipos mais simples e armazenam valores diretos.

|Tipo|Tamanho|Descrição|
|---|---|---|
|`byte`|8 bits|Guarda valores pequenos (-128 a 127).|
|`short`|16 bits|Pequenos inteiros (-32.768 a 32.767).|
|`int`|32 bits|Inteiros mais usados (-2 bilhões a 2 bilhões).|
|`long`|64 bits|Números inteiros muito grandes.|
|`float`|32 bits|Números decimais (precisão menor).|
|`double`|64 bits|Números decimais mais precisos.|
|`char`|16 bits|Armazena um único caractere (`'A'`, `'1'`).|
|`boolean`|1 bit|Armazena `true` ou `false`.|

### **Exemplos de uso:**

```java


`byte idade = 25; short ano = 2024; int populacao = 150000; long estrelas = 10000000000L; // Precisa do "L" no final float preco = 5.99f; // Precisa do "f" no final double pi = 3.14159; char letra = 'A'; boolean ativo = true;`
```

---

### ✅ **2. Variáveis de Referência (Objetos)**

- Ao contrário das variáveis primitivas, as **variáveis de referência** armazenam **endereços de objetos** na memória.
    
- Exemplos: **String, Arrays, Classes, Objetos.**
    

### **Exemplos de uso:**

```java

`String nome = "Igor"; // String é um objeto int[] numeros = {1, 2, 3, 4}; // Array de inteiros Scanner scanner = new Scanner(System.in); // Objeto Scanner`
```

---

## **3. Modificadores de Variáveis**

Em Java, podemos modificar o comportamento das variáveis usando palavras-chave:

|Modificador|Descrição|
|---|---|
|`final`|Torna a variável **constante** (não pode ser alterada).|
|`static`|Pertence à classe e não a um objeto específico.|
|`volatile`|Indica que a variável pode ser alterada por múltiplas threads.|

### **Exemplo de `final`:**

```java

`final double PI = 3.14159; // Agora, não pode ser alterado.`
```

---


## **4. Escopo das Variáveis**

O **escopo** define onde a variável pode ser usada:

|Tipo de Variável|Onde é Declarada|Duração|
|---|---|---|
|**Local**|Dentro de um método ou bloco|Só existe enquanto o método roda.|
|**De Instância**|Dentro de uma classe, mas fora de métodos|Existe enquanto o objeto existir.|
|**Estática**|Dentro da classe com `static`|Existe enquanto o programa roda.|

### **Exemplo:**

```java

`public class Pessoa {     int idade; // Variável de instância (cada objeto terá uma cópia)     static String planeta = "Terra"; // Variável estática (compartilhada)      public void definirIdade(int novaIdade) {         int anoAtual = 2024; // Variável local (existe apenas dentro do método)         this.idade = novaIdade;     } }`
```

## **1. Convenção para Nomes de Variáveis**

- ✅ **Usar camelCase** → Primeira palavra minúscula, próximas com maiúscula.
    
- ✅ **Ser descritivo** → O nome deve indicar o que a variável representa.
    
- ❌ **Evitar abreviações confusas** → `qtd` pode ser `quantidade`.
    

### **Exemplos corretos:**

```java

`int idade = 25; double precoProduto = 10.50; boolean estaLogado = true;`

```
### **Exemplos errados:**

```java

`int Idade = 25;        // ❌ Começando com maiúscula (parece classe). double precoproduto = 10.50; // ❌ Difícil de ler. boolean e = true;      // ❌ Nome muito curto e sem significado.`
```

---

## **2. Convenção para Nomes de Classes**

- ✅ **Usar PascalCase** → Todas as palavras começam com maiúscula.
    
- ✅ **Ser um substantivo** → Representa um objeto ou entidade.
    

### **Exemplos corretos:**

```java

`public class Carro { }  public class ContaBancaria { } public class UsuarioSistema { }`
```

### **Exemplos errados:**

```java

`public class carro { } // ❌ Deve começar com maiúscula. public class contabancaria { } // ❌ Sem PascalCase. public class usuario_sistema { } // ❌ Não usar underscore (_) em classes.`
```

---

## **3. Convenção para Nomes de Métodos**

- ✅ **Usar camelCase** → Primeira palavra minúscula, próximas com maiúscula.
    
- ✅ **Deve indicar uma ação** → Normalmente começa com um **verbo**.
    

### **Exemplos corretos:**

```java

`public void calcularDesconto() { } public int obterIdade() { } public boolean estaAtivo() { }`
```

### **Exemplos errados:**

```java

`public void CalcularDesconto() { } // ❌ Começando com maiúscula. public void obter_idade() { } // ❌ Não usar underscore (_) em métodos. public void DESCONTO() { } // ❌ Tudo em maiúsculas (parece constante).`
```

---

## **4. Convenção para Nomes de Constantes**

- ✅ **Usar letras maiúsculas**.
    
- ✅ **Separar palavras com underscore (`_`)**.
    
- ✅ **Usar `final`** para garantir que o valor não será alterado.
    

### **Exemplos corretos:**

```java


`public static final double PI = 3.14159; public static final int MAX_USUARIOS = 1000; public static final String MENSAGEM_ERRO = "Erro ao processar!";`
```

### **Exemplos errados:**

```java

`public static final double pi = 3.14159; // ❌ Constantes devem ser MAIÚSCULAS. public static final int MaxUsuarios = 1000; // ❌ Não usar PascalCase em constantes. public static final String mensagemErro = "Erro"; // ❌ Sem letras minúsculas.`
```

---

## **5. Convenção para Nomes de Pacotes**

- ✅ **Sempre em minúsculas**.
    
- ✅ **Usar domínio invertido** (evita conflitos de nomes).
    
- ✅ **Sem espaços ou caracteres especiais**.
    

### **Exemplos corretos:**

```java


`package com.empresa.sistema; package br.com.meuprojeto.util;`

```
### **Exemplos errados:**

```java

`package MeuProjeto; // ❌ Deve ser minúsculo. package sistema.Utilidades; // ❌ Sem maiúsculas. package br.com.meu projeto; // ❌ Sem espaços.`
```

### 🧠 **O que são Tipos de Referência?**

Em Java, os tipos de referência são **todos os tipos que não são primitivos**.

> 🔗 **Tipo de referência** é aquele que **aponta** para um **objeto na memória** (em vez de guardar diretamente um valor como os tipos primitivos fazem).

---

### ✅ **Exemplos de Tipos de Referência**

- `String`
    
- `Arrays` (`int[]`, `String[]`, etc.)
    
- Classes criadas por você (`Pessoa`, `Carro`, etc.)
    
- Classes da API do Java (`Scanner`, `ArrayList`, etc.)
    
- Interfaces e Enums
    

---

### 📦 **Como funcionam?**

Quando você cria um objeto, por exemplo:

```java

Pessoa pessoa = new Pessoa();
```

- `pessoa` **não guarda o objeto inteiro**.
    
- Ela guarda apenas um **endereço de memória** (referência) que aponta para onde o objeto `Pessoa` está na memória.
    

---

### 🎯 Diferença entre Primitivo e Referência

|Tipo|Armazena o quê?|Exemplo|
|---|---|---|
|Primitivo|Valor diretamente|`int idade = 20;`|
|Referência|Endereço de um objeto na memória|`Pessoa p = new Pessoa();`|

---

### 🛠️ **Exemplo prático:**

```java


public class Pessoa {
    String nome;
}

public class Main {
    public static void main(String[] args) {
        Pessoa p1 = new Pessoa();
        p1.nome = "Igor";

        Pessoa p2 = p1; // p2 aponta pro mesmo objeto que p1

        p2.nome = "Ana";

        System.out.println(p1.nome); // Vai imprimir "Ana"
    }
}
```

➡️ **Por quê?**  
Porque `p1` e `p2` são **referências** para o **mesmo objeto**. Quando `p2.nome` muda, `p1.nome` também muda, pois os dois apontam para o mesmo lugar.

---

### 💡 Cuidado com Comparações!

```java

String a = new String("Olá"); String b = new String("Olá");  System.out.println(a == b); // false 😱 System.out.println(a.equals(b)); // true ✅`

```
- `==` compara **referências** (endereços de memória)
    
- `.equals()` compara **conteúdo**
    

---

### 🔁 O que é **null**?

Se uma variável de referência **não aponta pra nada**, ela tem valor `null`.

```java

Pessoa pessoa = null; // Ainda não aponta para nenhum objeto
```

## 🔨 **Criação de Strings**

```java

 
String nome = "Igor";  // Forma mais comum
nome2 = new String("Igor");// Também funciona (usando o construtor da classe String) String

```
---

## 🔧 **Principais Métodos para Manipular Strings**

|Método|Descrição|Exemplo|
|---|---|---|
|`length()`|Retorna o comprimento da string|`"Igor".length()` → `4`|
|`charAt(int index)`|Retorna o caractere na posição indicada|`"Igor".charAt(1)` → `'g'`|
|`toUpperCase()`|Transforma tudo em maiúsculo|`"igor".toUpperCase()` → `"IGOR"`|
|`toLowerCase()`|Transforma tudo em minúsculo|`"IGOR".toLowerCase()` → `"igor"`|
|`substring(int start, int end)`|Pega parte da string|`"Igor".substring(1, 3)` → `"go"`|
|`contains(String)`|Verifica se contém certo texto|`"Java é legal".contains("legal")` → `true`|
|`equals(String)`|Compara se duas strings são iguais (case sensitive)|`"Igor".equals("igor")` → `false`|
|`equalsIgnoreCase(String)`|Compara ignorando maiúsculas/minúsculas|`"Igor".equalsIgnoreCase("IGOR")` → `true`|
|`replace(char, char)`|Substitui caracteres|`"bola".replace('a', 'o')` → `"bolo"`|
|`trim()`|Remove espaços no início e fim|`" teste ".trim()` → `"teste"`|
|`split(String regex)`|Divide a string em partes|`"a,b,c".split(",")` → `["a", "b", "c"]`|
|`startsWith(String)`|Verifica se começa com...|`"Java".startsWith("Ja")` → `true`|
|`endsWith(String)`|Verifica se termina com...|`"programa".endsWith("ma")` → `true`|

---

## 📌 Exemplo Prático

```java
public class TesteString {
    public static void main(String[] args) {
        String frase = "  Java é divertido!  ";

        System.out.println(frase.length()); // 22
        System.out.println(frase.trim()); // "Java é divertido!"
        System.out.println(frase.toUpperCase()); // "  JAVA É DIVERTIDO!  "
        System.out.println(frase.contains("divertido")); // true
        System.out.println(frase.substring(2, 6)); // "Java"
    }
}

```
---

## 🚫 Lembrete: String é imutável

```java

String nome = "Igor"; 
nome.toUpperCase(); 
System.out.println(nome); // Ainda é "Igor" ❌  
nome = nome.toUpperCase(); // Agora sim ✅ System.out.println(nome); // "IGOR"`
```
## ✨ O que são **Caracteres Especiais** em Strings?

Em Java, dentro de uma string (entre aspas `"`), alguns caracteres **não podem ser usados diretamente** ou têm significados especiais (como `\n` para nova linha). Por isso, usamos **sequências de escape** com uma **barra invertida** (`\`) pra representar eles.

---

## 🧩 **Principais Caracteres Especiais (Escape Sequences)**

|Sequência|Significado|Exemplo|
|---|---|---|
|`\n`|Quebra de linha (newline)|`"Olá\nMundo"` →  <br>Olá  <br>Mundo|
|`\t`|Tabulação (tab)|`"Nome:\tIgor"` → Nome: Igor|
|`\"`|Aspas duplas dentro de string|`"Ele disse: \"Oi!\""` → Ele disse: "Oi!"|
|`\'`|Aspas simples (quando precisa delas)|`'\'a\''` → `'a'` (menos comum em string, mais em `char`)|
|`\\`|Barra invertida (`\`)|`"C:\\Users\\Igor"`|
|`\r`|Retorno de carro (carriage return)|Raramente usado sozinho|
|`\b`|Backspace (apaga o último caractere)|Pouco usado também|
|`\f`|Avanço de formulário|Muito raro|

---

## 📌 Exemplos na prática:

```java
public class CaracteresEspeciais {
    public static void main(String[] args) {
        System.out.println("Olá,\nmeu nome é Igor."); // quebra de linha
        System.out.println("Caminho: C:\\Programas\\Java"); // barra invertida
        System.out.println("Ele disse: \"Java é legal!\""); // aspas duplas
        System.out.println("Tabulação:\t-> Aqui está"); // tabulação
    }
}
```





### Saída:

```makefile
Olá,
meu nome é Igor.
Caminho: C:\Programas\Java
Ele disse: "Java é legal!"
Tabulação:	-> Aqui está
```
## 🧠 Dica: Por que isso existe?

Porque alguns caracteres têm **significados especiais no código** e não podem aparecer diretamente, como `"` (delimitador de string) ou `\` (usado para sequências de escape). Então o Java precisa saber quando você quer dizer literalmente `"`, `\`, ou quando você quer dizer algo como uma **quebra de linha** (`\n`).


## 🔹 O que é um **Array** em Java?

- Um **array** é uma **estrutura de dados** que armazena **múltiplos valores do mesmo tipo**.
    
- O tamanho do array é **fixo** após ser criado.
    
- Os elementos são acessados por **índice**, começando em **0**.
    


### ✅ Exemplo de Array Simples (1D):

```java

int[] numeros = new int[5]; // array com 5 posições (valores default: 0)

// Atribuindo valores
numeros[0] = 10;
numeros[1] = 20;
numeros[2] = 30;
numeros[3] = 40;
numeros[4] = 50;

// Imprimindo
System.out.println(numeros[2]); // 30

```

---

## 🔁 Declarando e Inicializando com Valores Diretos:

```java
String[] nomes = { "Igor", "Ana", "Lucas" };  System.out.println(nomes[0]); // "Igor"`
```

---

## 🔄 Percorrendo com for:

```java

	for (int i = 0; i < nomes.length; i++) {
    System.out.println(nomes[i]);
	}

// Ou com for-each:
for (String nome : nomes) {
    System.out.println(nome);
}
```

---

## 🔷 Métodos úteis para manipulação (via utilitários):

Java não tem métodos diretos em arrays como em listas, mas você pode usar:

```java

`import java.util.Arrays;`
```

|Método|Descrição|
|---|---|
|`Arrays.sort(array)`|Ordena o array|
|`Arrays.toString(array)`|Converte array para string (para imprimir)|
|`Arrays.copyOf(array, novoTamanho)`|Copia e redimensiona|
|`Arrays.equals(a1, a2)`|Compara dois arrays|
|`Arrays.fill(array, valor)`|Preenche o array com um valor|

### Exemplo:

```java

int[] numeros = {5, 1, 3, 9}; 
Arrays.sort(numeros); // [1, 3, 5, 9] 
System.out.println(Arrays.toString(numeros));
```

---

## 🧩 Matriz em Java (Array Bidimensional)

Uma **matriz** é um **array de arrays**, ou seja, cada "linha" é um novo array.

```java

int[][] matriz = new int[2][3]; // 2 linhas, 3 colunas

matriz[0][0] = 1;
matriz[0][1] = 2;
matriz[0][2] = 3;

matriz[1][0] = 4;
matriz[1][1] = 5;
matriz[1][2] = 6;

// Percorrendo com dois for
for (int i = 0; i < matriz.length; i++) {
    for (int j = 0; j < matriz[i].length; j++) {
        System.out.print(matriz[i][j] + " ");
    }
    System.out.println();
}

```


### Saída:

`1 2 3   4 5 6`

## 🧱 O que é uma constante?

Uma **constante** em Java é uma **variável cujo valor não pode ser alterado** depois de ser definido. Para declarar uma constante, usamos a **palavra-chave `final`**.

```java

final int IDADE_MINIMA = 18;
```

> Uma vez que você define esse valor, **nunca mais pode mudar** no resto do programa!

---

## 🔐 Por que usar constantes?

- Evita **repetição de valores fixos** no código.
    
- Facilita a **manutenção** (você muda em um lugar só).
    
- Evita **erros** (alguém mudar sem querer um valor que deveria ser fixo).
    
- Deixa o código mais **legível e expressivo**.
    

---

## 🧠 Como declarar constantes

```java

final tipo NOME = valor;
```

Exemplos:

```java

final double PI = 3.14159; 
final int LIMITE_USUARIOS = 100; 
final String NOME_DO_SISTEMA = "MinhaApp";
```

---

## 🧾 Convenção de nomes para constantes

🔠 Em Java, a convenção para constantes é:

- **Nome em CAIXA ALTA** (letras maiúsculas)
    
- **Separadas por underscores** (`_`)
    
- Usa-se nomes descritivos
    

```java
`final int MAX_TENTATIVAS = 5; final double TAXA_JUROS = 0.1;`
```

---

## 🧪 Exemplo de uso:

```java

public class ExemploConstantes {
    public static void main(String[] args) {
        final double PI = 3.14159;
        final int MAX_VIDAS = 3;

        System.out.println("Valor de PI: " + PI);
        System.out.println("Máximo de vidas: " + MAX_VIDAS);

        // PI = 3.14; // ❌ Erro! Não pode mudar o valor de uma constante
    }
}
```

## ➕ Operadores Aritméticos em Java

|Operador|Símbolo|Exemplo|Significado|
|---|---|---|---|
|Soma|`+`|`a + b`|Soma dois valores|
|Subtração|`-`|`a - b`|Subtrai b de a|
|Multiplicação|`*`|`a * b`|Multiplica|
|Divisão|`/`|`a / b`|Divide (inteiros ou decimais)|
|Módulo|`%`|`a % b`|Resto da divisão|

---

## ⚠️ Observações importantes:

- Se **ambos os operandos** forem inteiros (`int`), o resultado da divisão será um **inteiro** (sem casas decimais):
    
    java
    
    CopiarEditar
    
    `int resultado = 7 / 2; // resultado = 3, não 3.5!`
    
- Para obter resultado com casas decimais, **use `double` ou `float`**:
    
    java
    
    CopiarEditar
    
    `double resultado = 7.0 / 2; // resultado = 3.5`
    

---

## 🔄 Exemplo completo:

```java

public class Operadores {
    public static void main(String[] args) {
        int a = 10;
        int b = 3;

        System.out.println("Soma: " + (a + b));         // 13
        System.out.println("Subtração: " + (a - b));    // 7
        System.out.println("Multiplicação: " + (a * b));// 30
        System.out.println("Divisão: " + (a / b));      // 3
        System.out.println("Módulo: " + (a % b));       // 1
    }
}
```

---

## 🔢 Ordem de Operações (Precedência)

Java segue regras semelhantes às da matemática (lembra do **PEMDAS**?):

1. **Parênteses** `()`
 
2. **Multiplicação**, **Divisão**, **Módulo** `* / %`
    
3. **Soma** e **Subtração** `+ -`
    
4. **Esquerda para a direita** (ordem associativa)
    

---

### 🎯 Exemplo:

```java

`int resultado = 10 + 2 * 3; // resultado = 10 + 6 = 16  int resultado2 = (10 + 2) * 3; // resultado = 12 * 3 = 36`

```
**→ Use parênteses sempre que quiser garantir a ordem certa** e evitar confusão!

## 🔁 O que é **casting**?

**Casting** (ou **type casting**) é quando você **converte um valor de um tipo para outro tipo**.

### Existem dois tipos:

1. **Casting implícito (automático)** — feito pelo Java quando **não há perda de informação**
    
2. **Casting explícito (manual)** — feito por você, quando **há risco de perda de dados**
    

---

## 📌 1. **Casting implícito** (widening / promoção de tipo)

Java faz automaticamente quando converte de um tipo **menor para um maior**:

```java

int num = 10; double resultado = num;  // int → double (OK)
```

Outros exemplos válidos:

- `byte → short → int → long → float → double`
    

---

## 📌 2. **Casting explícito** (narrowing / redução de tipo)

Feito **manualmente**, com risco de **perda de precisão ou estouro**:

```java

double valor = 9.99; int inteiro = (int) valor;  // perde os decimais (inteiro = 9)
```

Outros exemplos:

```java

long numeroGrande = 100000L; int numeroPequeno = (int) numeroGrande;
```

---

## 🎯 Exemplos práticos:

```java

public class CastingExemplo {
    public static void main(String[] args) {
        int a = 10;
        double b = a;  // implícito
        System.out.println("int para double: " + b);

        double x = 5.7;
        int y = (int) x;  // explícito
        System.out.println("double para int: " + y);
    }
}

```

---

## 🧠 Também dá pra fazer casting com:

### 🔡 **char ↔ int**

```java

char letra = 'A';
int codigo = (int) letra; // resultado: 65
System.out.println(codigo);

int codigo2 = 66;
char letra2 = (char) codigo2; // resultado: 'B'
System.out.println(letra2);

```

### 📦 **Casting entre objetos (tipos de referência)**

Só funciona entre **classes relacionadas (herança)**.

```java
class Animal {}
class Cachorro extends Animal {}

Animal a = new Cachorro();  // upcasting (implícito)
Cachorro c = (Cachorro) a;  // downcasting (explícito)

```


⚠️ Downcasting precisa ser feito com cuidado — pode causar `ClassCastException`.

---

## 🚨 Dica: cuidado com **perda de dados**!

```java

int valor = 130; byte b = (byte) valor; // b = -126 (overflow) System.out.println(b);
```

## 📘 O que é a `Math` class?

A `Math` é uma **classe utilitária** da `java.lang`, ou seja, já está **importada por padrão**, e traz vários **métodos estáticos** (você não precisa instanciar ela) pra fazer cálculos matemáticos.

---

## 🧮 Principais métodos da classe `Math`

### 🔢 1. **Potência e raízes**

|Método|Descrição|Exemplo|
|---|---|---|
|`Math.pow(x, y)`|x elevado à potência y|`Math.pow(2, 3)` → `8.0`|
|`Math.sqrt(x)`|Raiz quadrada de x|`Math.sqrt(9)` → `3.0`|

---

### ➕➖ 2. **Valor absoluto e sinais**

|Método|Descrição|Exemplo|
|---|---|---|
|`Math.abs(x)`|Valor absoluto (sem sinal)|`Math.abs(-5)` → `5`|
|`Math.signum(x)`|Retorna -1, 0 ou 1 conforme o sinal|`Math.signum(-10)` → `-1.0`|

---

### ⬆️⬇️ 3. **Arredondamento**

|Método|Descrição|Exemplo|
|---|---|---|
|`Math.round(x)`|Arredonda pro mais próximo|`Math.round(3.6)` → `4`|
|`Math.floor(x)`|Arredonda pra baixo|`Math.floor(3.9)` → `3.0`|
|`Math.ceil(x)`|Arredonda pra cima|`Math.ceil(3.1)` → `4.0`|

---

### 🎲 4. **Aleatoriedade**

|Método|Descrição|Exemplo|
|---|---|---|
|`Math.random()`|Retorna valor `double` entre 0.0 e 1.0|`Math.random()` → `0.73` (por exemplo)|

💡 Exemplo de número aleatório entre 0 e 99:

java

CopiarEditar

`int aleatorio = (int)(Math.random() * 100);`

---

### 📈 5. **Trigonometria** (em radianos!)

|Método|Descrição|Exemplo|
|---|---|---|
|`Math.sin(x)`|Seno de x (em radianos)|`Math.sin(Math.PI/2)` → `1.0`|
|`Math.cos(x)`|Cosseno de x|`Math.cos(0)` → `1.0`|
|`Math.tan(x)`|Tangente de x|`Math.tan(...)`|

---

## 💎 Constantes da classe `Math`

|Constante|Valor aproximado|Descrição|
|---|---|---|
|`Math.PI`|`3.141592653...`|Pi (π)|
|`Math.E`|`2.718281828...`|Euler (e)|

---

## 🧪 Exemplo prático:

```java
public class MathDemo {
    public static void main(String[] args) {
        double base = 2;
        double exp = 3;
        System.out.println("Potência: " + Math.pow(base, exp));
        System.out.println("Raiz de 25: " + Math.sqrt(25));
        System.out.println("Aleatório: " + Math.random());
        System.out.println("PI: " + Math.PI);
        System.out.println("Arredondado: " + Math.round(3.6));
    }
}

```
