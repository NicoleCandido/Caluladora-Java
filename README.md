<h1 align="center">Calculadora em Java</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Java-8a2be2?style=for-the-badge&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Swing-ff69b4?style=for-the-badge&logo=java&logoColor=white" />
  <img src="https://img.shields.io/badge/POO-8a2be2?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Concluído-ff69b4?style=for-the-badge" />
</p>

<p align="center">
  Calculadora com interface gráfica que usa <b>herança</b> e <b>polimorfismo</b>:<br>
  cada operação é uma classe própria que sabe fazer o seu cálculo.
</p>

---

## Funcionalidades

- Soma
- Subtração
- Divisão
- Escolha da operação por botões de opção (*radio buttons*)

## Como funciona

Todas as operações herdam da classe base `OperacaoMatematica` e sobrescrevem o método `calcular`:

```
              OperacaoMatematica
              calcular(valor1, valor2)
                       ▲
        ┌──────────────┼──────────────┐
      Soma         Subtracao        Divisao
     v1 + v2        v1 - v2         v1 / v2
```

A tela usa um único método para qualquer operação. Ela recebe **qualquer objeto** que seja uma `OperacaoMatematica` e chama `calcular`, sem precisar saber qual operação é:

```java
public static double calcule(OperacaoMatematica op, double valor1, double valor2) {
    return op.calcular(valor1, valor2);
}

calcule(new Soma(), 10, 5);       // 15.0
calcule(new Divisao(), 10, 5);    // 2.0
```

## Conceitos de POO aplicados

- **Herança:** `Soma`, `Subtracao` e `Divisao` estendem `OperacaoMatematica`
- **Sobrescrita de método:** cada classe implementa o seu próprio `calcular`
- **Polimorfismo:** o método `calcule` funciona com qualquer operação
- **Extensibilidade:** para criar uma nova operação, basta criar uma nova classe, sem mexer nas existentes

## Estrutura

```
Calculadora-Java/
├── src/main/java/com/mycompany/calculadora/
│   ├── OperacaoMatematica.java   # Classe base
│   ├── Soma.java
│   ├── Subtracao.java
│   ├── Divisao.java
│   ├── JFcalculadora.java        # Interface gráfica
│   └── JFcalculadora.form        # Layout da tela (NetBeans)
├── pom.xml
└── README.md
```
