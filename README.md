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
