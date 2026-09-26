📌 Sobre o Projeto
# Calculadora de IMC em Java

Programa simples em Java que calcula o Índice de Massa Corporal (IMC) do usuário a partir do peso e da altura, e exibe a classificação correspondente.

## O que é o IMC?

O IMC (Índice de Massa Corporal) é calculado pela fórmula:

```
IMC = peso / (altura × altura)
```

Onde:
- **peso** é em quilogramas (kg)
- **altura** é em metros (m)

## Como o código funciona

### 1. Leitura dos dados de entrada

```java
Scanner scanner = new Scanner(System.in);

System.out.print("Digite seu peso em kg: ");
double peso = scanner.nextDouble();

System.out.print("Digite sua altura em metros (ex: 1.75): ");
double altura = scanner.nextDouble();
```

- `Scanner` é a classe do Java usada para ler dados digitados pelo usuário no terminal.
- `scanner.nextDouble()` lê um número decimal (`double`), já que peso e altura podem ter casas decimais (ex: `70.5` kg ou `1.75` m).

### 2. Cálculo do IMC

```java
double imc = peso / (altura * altura);
```

Aqui a fórmula do IMC é aplicada diretamente: o peso é dividido pela altura elevada ao quadrado (`altura * altura`).

### 3. Exibição do resultado

```java
System.out.printf("Seu IMC é: %.2f\n", imc);
```

- `printf` permite formatar a saída.
- `%.2f` significa "número decimal com 2 casas depois da vírgula", deixando o resultado mais legível (ex: `23.45` em vez de `23.4567891`).

### 4. Classificação do IMC

```java
if (imc < 18.5) {
    System.out.println("Classificação: Abaixo do peso");
} else if (imc >= 18.5 && imc < 25) {
    System.out.println("Classificação: Peso normal");
} else if (imc >= 25 && imc < 30) {
    System.out.println("Classificação: Sobrepeso");
} else {
    System.out.println("Classificação: Obesidade");
}
```

O programa usa uma cadeia de `if / else if / else` para verificar em qual faixa o valor do IMC se encaixa:

| Faixa de IMC       | Classificação      |
|--------------------|---------------------|
| Menor que 18.5      | Abaixo do peso       |
| De 18.5 até 24.9   | Peso normal          |
| De 25 até 29.9     | Sobrepeso            |
| 30 ou mais          | Obesidade            |

> **Observação:** como as condições são verificadas em ordem, a partir do segundo `else if` não seria estritamente necessário repetir o `imc >= 18.5` — mas isso deixa a condição mais explícita e fácil de entender.

### 5. Fechando o Scanner

```java
scanner.close();
```

Fecha o `Scanner` para liberar o recurso do sistema (boa prática ao terminar de usar leitura de entrada).

## Como executar

1. Salve o código em um arquivo chamado `CalculadoraIMC.java`.
2. Compile:
   ```bash
   javac CalculadoraIMC.java
   ```
3. Execute:
   ```bash
   java CalculadoraIMC
   ```
4. Digite o peso e a altura quando solicitado.

## Exemplo de uso

```
Digite seu peso em kg: 70
Digite sua altura em metros (ex: 1.75): 1.75
Seu IMC é: 22.86
Classificação: Peso normal
```

## Conceitos de Java praticados neste código

- Leitura de entrada do usuário com `Scanner`
- Operações matemáticas com `double`
- Formatação de saída com `printf`
- Estruturas condicionais (`if / else if / else`)
- Operadores relacionais (`<`, `>=`) e lógicos (`&&`)
