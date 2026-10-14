# Simulado para a Prova - Linguagem de Programação
<div align="center">
16/09/2026
</div>

# Exercício 1 ✅
Faça um programa que receba a idade e o peso de N pessoas. Calcule e mostre:
A quantidade de pessoas com mais de 90 quilos;
A média das idades de todas as pessoas;
Exibir os Resultados.

## Java
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int idade = 0;
    int contador = 0;
    double media = 0;

    System.out.print("Quantas pessoas serao digitadas: ");
    int n = sc.nextInt();

    int[] peso = new int[n];
    for (int i = 0; i < n; i++) {
        System.out.print("Idade: ");
        idade = sc.nextInt();
        media += idade;

        System.out.print("Peso: ");
        peso[i] = sc.nextInt();
    }

    for (int i = 0; i < n; i++) {
        if (peso[i] > 90) {
            contador++;
        }
    }

    media /= n;
    System.out.printf("----------------------------------\n");
    System.out.printf("Pessoas com peso > 90kg: %d\n", contador);
    System.out.printf("Média das idades: %.1f", media);

    sc.close();
    }
}
```

## C
```c
#include <stdio.h>

int main() {
    int n;
    int idade = 0;
    int contadorPeso = 0;
    float media = 0;
    printf("Quantas pessoas serao digitadas: ");
    scanf("%i", &n);

    int peso[n];
    for (int i = 0; i < n; i++) {
        printf("Idade: ");
        scanf("%i", &idade);
        media += idade;

        printf("Peso: ");
        scanf("%i", &peso[i]);
    }

    for (int i = 0; i < n; i++) {
        if (peso[i] > 90) {
            contadorPeso++;
        }
    }

    media /= n;
    printf("----------------------------------\n");
    printf("Pessoas com peso > 90kg: %i\n", contadorPeso);
    printf("Média das idades: %.2f", media);
}
```

# Exercício 2 ✅
Uma loja tem N clientes cadastradas e deseja enviar uma correspondência a cada uma delas anunciando um bônus especial. Faça um programa que leia o nome do Cliente e o valor de suas compras no ano passado. Calcule e mostre um bônus de 10% se o valor das compras for menor que R$ 1.100,00 e de 15% for maior.  A cada bônus obtido das compras efetuar a soma total de bônus promovido pela empresa. Exibir os resultados.

## Java
```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    String nome = "";
    double valor = 0;
    double bonus = 0;

    System.out.print("Quantos Clientes: ");
    int n = sc.nextInt(); 

    for (int i = 0; i < n; i++) {
        System.out.print("Nome do cliente: ");
        sc.nextLine();
        nome = sc.nextLine();

        System.out.print("Valor das compras ano passado: ");
        valor = sc.nextDouble();

        if (valor < 1100) {
          bonus = 0.10;
          valor = valor * bonus;
          System.out.println("---------------------");
          System.out.printf("Cliente: %s\n", nome);
          System.out.printf("Bônus: %.2f%%\n", bonus * 100);
          System.out.printf("Valor: %.2f\n", valor);
          System.out.println("---------------------");
        } else if (valor > 1100) {
          bonus = 0.15;
          valor = valor * bonus;
          System.out.println("---------------------");
          System.out.printf("Cliente: %s\n", nome);
          System.out.printf("Bônus: %.2f%%\n", bonus * 100);
          System.out.printf("Valor: %.2f\n", valor);
          System.out.println("---------------------");
        }
    }
    sc.close();
}
}
```

## C
```c
#include <stdio.h>

int main() {
    int n;
    char nome;
    int valor = 0;
    float bonus = 0;
    int soma = 0;
    printf("Quantos Clientes: ");
    scanf("%i", &n);

    for (int i = 0; i < n; i++) {
        printf("Nome do cliente (char): ");
        scanf(" %c", &nome);
        setbuf(stdin, NULL);

        printf("Valor das compras ano passado: ");
        scanf("%i", &valor);
        setbuf(stdin, NULL);

        if (valor < 1100) {
            bonus = 0.10;
            valor = valor * bonus;
            printf("---------------------\n");
            printf("Cliente: %c\n", nome);
            printf("Bônus: %.2f%%\n", bonus * 100);
            printf("Valor: %i\n", valor);
            printf("---------------------\n");
        } else if (valor > 1100) {
            bonus = 0.15;
            valor = valor * bonus;
            printf("---------------------\n");
            printf("Cliente: %c\n", nome);
            printf("Bônus: %.2f%%\n", bonus * 100);
            printf("Valor: %i\n", valor);
            printf("---------------------\n");
        }
    }
}
```

# Exercício 3 ✅
Cadastre um vetor de N Fornecedores do tipo string. Após o lançamento deste vetor, efetue uma pesquisa ou consulta, para encontrar um determinado Fornecedor nesta lista, caso encontre, informe a sua posição no vetor, caso este fornecedor não exista informar o usuário.

## Java
```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);

    int k = 0;
    boolean encontrado = false;
    String busca = "";

    System.out.print("Quantos fornecedores: ");
    int n = sc.nextInt();
    sc.nextLine();
    String[] fornecedores = new String[n];

    for (int i = 0; i < n; i++) {
      System.out.print("Fornecedor: ");
      fornecedores[i] = sc.nextLine();
    }
  
    System.out.print("Qual fornecedor quer procurar: ");
    busca = sc.nextLine();

    for (int i = 0; i < n; i++) {
      if (fornecedores[i].equals(busca)) {
        encontrado = true;
        k = i;
      }
    }
    
    if (encontrado == true) {
        System.out.println("Encontrado!");
        System.out.printf("Posição no vetor: %d", k);
    } else if (encontrado == false) {
        System.out.print("Nenhum fornecedor encontrado!");
    }
    sc.close();
  }
}
```

## C
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdbool.h>

int main() {
    int k = 0;
    int n = 0;
    bool encontrado = false;
    char busca[10];
    char fornecedores[10][10];

    printf("Quantos fornecedores: ");
    scanf("%i", &n);
    if (n < 0 || n > 10) return 1;

    for (int i = 0; i < n; i++) {
        printf("Fornecedor: ");
        scanf("%9s", fornecedores[i]);
    }
  
    printf("Qual fornecedor quer procurar: ");
    scanf("%9s", busca);

    for (int i = 0; i < n; i++) {
      if (strcmp(fornecedores[i], busca) == 0) {
        encontrado = true;
        k = i;
      }
    }
    
    if (encontrado == true) {
        printf("Encontrado!\n");
        printf("Posição no vetor: %i", k);
    } else if (encontrado == false) {
        printf("Nenhum fornecedor encontrado!");
    }
}
```

# Exercício 4 ✅
Elabore um vetor de N alunos do tipo String e um vetor contendo as suas médias. Desenvolva uma função que faça uma pesquisa e armazene os nomes dos alunos em um vetor resultante. Este vetor resultante deverá constar os nomes dos alunos que obteve media abaixo de 7,0. No final exibir os alunos deste vetor.

## Java
```java
import java.util.Scanner;

public class Main {
    public static String[] busca(String[] nomes, double[] medias) {
        int n = 0; 
        for (int i = 0; i < medias.length; i++) {
            if (medias[i] < 7.0) {
                n++;
            }
        }

        String[] resultado = new String[n];
        int index = 0;
        for (int i = 0; i < medias.length; i++) {
            if (medias[i] < 7.0) {
                resultado[index] = nomes[i];
                index++;
            }
        }
        return resultado;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Quantos alunos: ");
        int n = sc.nextInt();
        sc.nextLine();

        String[] nomes = new String[n];
        double[] medias = new double[n];

        for (int i = 0; i < n; i++) {
            System.out.print("Nome: ");
            nomes[i] = sc.nextLine();

            System.out.print("Média: ");
            medias[i] = sc.nextDouble();
            sc.nextLine();
        }

        String[] alunosAbaixoDaMedia = busca(nomes, medias);

        System.out.println("\n-----------------------------");
        System.out.println("Alunos com média abaixo de 7.0:");
        
        for (String aluno : alunosAbaixoDaMedia) {
            System.out.println("- " + aluno);
        }
        scanner.close();
    }
}
```

## C
```c
#include <stdio.h>
#include <string.h>

int busca(char nomes[][20], float medias[], int n, char copia[][20]) {
    int k = 0;

    for (int i = 0; i < n; i++) {
        if (medias[i] < 7.0) {
            strcpy(copia[k], nomes[i]);
            k++;  
        }
    }
    return k;
}

int main() {
    int n;
    printf("Quantos alunos: ");
    scanf("%d", &n);

    char nomes[n][20];
    float medias[n];
    char copia[n][20];

    for (int i = 0; i < n; i++) {
        printf("Nome do aluno %d: ", i + 1);
        scanf("%s", nomes[i]);


        printf("Média de %s: ", nomes[i]);
        scanf("%f", &medias[i]);
    }

    int reprovados = busca(nomes, medias, n, copia);

    printf("\n-----------------------------\n");
    printf("Alunos com média abaixo de 7.0:\n");

    if (reprovados == 0) {
        printf("Nenhum aluno ficou abaixo da média.\n");
    } else {
        for (int i = 0; i < reprovados; i++) {
            printf("- %s\n", copia[i]);
        }
    }
}
```
