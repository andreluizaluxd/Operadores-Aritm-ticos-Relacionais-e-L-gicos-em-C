
# 📘 Estudo e Aplicação de Algoritmos na Programação Estruturada

![C](https://img.shields.io/badge/Linguagem-C-blue)  
![Status](https://img.shields.io/badge/Status-Concluido-brightgreen)  

**Disciplina:** Algoritmos e Programação Estruturada

**Faculdade:** Anhanguera

**Aluno:** André Luiz da Silva

**Data:** 28/08/2025

---

## 📑 Sumário

1. [Objetivo](#-objetivo)
2. [Enunciado (Resumo)](#-enunciado-resumo)
3. [Descrição da Solução](#-descrição-da-solução)

   * [Fluxo da aplicação](#-fluxo-da-aplicação)
   * [Decisões de implementação](#-decisões-de-implementação)
4. [Código-fonte (C)](#-código-fonte-c)
5. [Testes e Resultados](#-testes-e-resultados)
6. [Como Executar](#-como-executar)
7. [Conclusão](#-conclusão)

---

## 🎯 Objetivo

Implementar um programa em **C** que:

* Leia três números inteiros.
* Realize operações aritméticas (soma, subtração, multiplicação e divisão sequencial).
* Compare valores usando operadores relacionais.
* Valide condições com operadores lógicos combinados.
* Exiba os resultados e mensagens personalizadas.

---

## 📌 Enunciado (Resumo)

* Ler três inteiros do usuário.
* Calcular:

  * Soma
  * Subtração sequencial
  * Multiplicação
  * Divisão sequencial `num1 / num2 / num3` (evitando divisão por zero).
* Verificar com operadores relacionais:

  * Se `num1 > num2`.
  * Se `num2 < num3`.
* Validar com operadores lógicos:

  * `(num1 > 0) && (num2 % 2 == 0)`.
  * Se verdadeiro, exibir mensagem específica.

---

## 🛠️ Descrição da Solução

A aplicação segue o fluxo **Entrada → Processamento → Saída**, com validações para evitar divisão por zero.

### 🔄 Fluxo da aplicação

```text
Início 
 └─► Ler num1, num2, num3 
      ├─► Calcular soma, subtração, multiplicação 
      ├─► Se (num2 != 0 E num3 != 0) então calcular divisão sequencial 
      ├─► Comparar: (num1 > num2), (num2 < num3) 
      ├─► Validar lógica: (num1 > 0) E (num2 % 2 == 0) 
      └─► Exibir resultados e mensagens 
Fim
```

### ⚙️ Decisões de implementação

* **Divisão sequencial:** `(float) num1 / num2 / num3` com casting explícito.
* **Proteção contra divisão por zero:** cálculo apenas se `num2 != 0 && num3 != 0`.
* **Tipos:**

  * Inteiros para soma, subtração e multiplicação.
  * `float` para divisão (exibida com duas casas decimais).
* **Mensagens:** cada verificação imprime valores e resultados lógicos.
* **Limitação:** multiplicações grandes podem causar *overflow* (usar `long long` se necessário).

---

## 💻 Código-fonte (C)

```c
#include <stdio.h>

int main() {
    int num1, num2, num3;
    int soma, subtracao, multiplicacao;
    float divisao;

    // Entrada de dados
    printf("Digite o primeiro numero inteiro: ");
    scanf("%d", &num1);

    printf("Digite o segundo numero inteiro: ");
    scanf("%d", &num2);

    printf("Digite o terceiro numero inteiro: ");
    scanf("%d", &num3);

    // Operações aritméticas
    soma = num1 + num2 + num3;
    subtracao = num1 - num2 - num3;
    multiplicacao = num1 * num2 * num3;

    if (num2 != 0 && num3 != 0) {
        divisao = (float)num1 / num2 / num3;
    }

    // Saída dos resultados
    printf("\nResultados das operacoes:\n");
    printf("Soma: %d\n", soma);
    printf("Subtracao: %d\n", subtracao);
    printf("Multiplicacao: %d\n", multiplicacao);

    if (num2 != 0 && num3 != 0) {
        printf("Divisao sequencial: %.2f\n", divisao);
    } else {
        printf("Divisao sequencial: nao realizada (divisao por zero)\n");
    }

    // Comparações relacionais
    printf("\nComparacoes:\n");
    printf("num1 > num2: %s\n", (num1 > num2) ? "Verdadeiro" : "Falso");
    printf("num2 < num3: %s\n", (num2 < num3) ? "Verdadeiro" : "Falso");

    // Lógica combinada
    printf("\nValidacao logica combinada:\n");
    if ((num1 > 0) && (num2 % 2 == 0)) {
        printf("O primeiro numero e positivo E o segundo numero e par.\n");
    } else {
        printf("As condicoes logicas NAO foram satisfeitas.\n");
    }

    return 0;
}
```

---

## 🧪 Testes e Resultados

### 🔹 Teste A

Entrada: `num1 = 10, num2 = 4, num3 = 20`
Resultados:

* Soma: 34
* Subtração: -14
* Multiplicação: 800
* Divisão: 0.13
* Comparações: `num1 > num2` → Verdadeiro, `num2 < num3` → Verdadeiro
* Lógica combinada: Verdadeiro → Mensagem exibida

### 🔹 Teste B

Entrada: `num1 = -5, num2 = 7, num3 = 3`
Resultados:

* Soma: 5
* Subtração: -15
* Multiplicação: -105
* Divisão: -0.24
* Comparações: `num1 > num2` → Falso, `num2 < num3` → Falso
* Lógica combinada: Falso → Mensagem exibida

### 🔹 Teste C

Entrada: `num1 = 8, num2 = 0, num3 = 2`
Resultados:

* Soma: 10
* Subtração: 6
* Multiplicação: 0
* Divisão: não realizada (divisão por zero)
* Comparações: `num1 > num2` → Verdadeiro, `num2 < num3` → Verdadeiro
* Lógica combinada: Verdadeiro → Mensagem exibida

---

## 🖥️ Como Executar

1. Clone o repositório:

```bash
git clone <URL_DO_REPOSITORIO>
```

2. Navegue até a pasta do projeto:

```bash
cd nome-do-repositorio
```

3. Compile o código em C usando GCC:

```bash
gcc main.c -o programa
```

4. Execute o programa:

```bash
./programa    # Linux/Mac
programa.exe  # Windows
```

---

## ✅ Conclusão

O programa cumpre os objetivos ao combinar **operadores aritméticos, relacionais e lógicos**, realizando cálculos e tomando decisões simples.
Os testes demonstram consistência em diferentes cenários, garantindo confiabilidade na execução e aprendizado prático de programação estruturada em C.

---


