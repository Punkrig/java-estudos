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


