# Respostas
//1) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...)
//escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando
//se o número informado pertence ou não a sequência.

import java.util.Scanner;

public class Fibonacci {
    public static int Fibo(int n) {
        if (n <= 1) {
            return n;
        } else {
            return Fibo(n - 1) + Fibo(n - 2);
        }
    }

    public static boolean verNum(int num) {
        int a = 0, b = 1, aux;

        if (num < 0) {
            return false;
        }

        if (num == 0 || num == 1) {
            return true;
        }

        while (b < num) {
            aux = b;
            b = a + b;
            a = aux;
        }

        return b == num;
    }

    public static void main(String[] args) {
        int n;
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite quantos numeros quer imprimir na sequencia: ");
        n = sc.nextInt();

        System.out.println("\nDigite um numero para verificar se pertence à sequência de Fibonacci:");
        int num = sc.nextInt();

        if (verNum(num)) {
            System.out.println("O numero " + num + " pertence à sequência de Fibonacci.\n");
        } else {
            System.out.println("O numero " + num + " não pertence à sequência de Fibonacci.\n");
        }

        System.out.println("Sequência de Fibonacci até o " + n + "º termo:");
        for (int i = 0; i < n; i++) {
            System.out.print(Fibo(i) + " ");
        }
        sc.close();
    }
}


//2) Escreva um programa que verifique, em uma string, a existência da letra ‘a’, seja maiúscula
// ou minúscula além de informar a quantidade de vezes em que ela ocorre.

import java.util.Scanner;

public class Letra {
    public static void verLetra(String frase) {
        int cont = 0;

        for (int i = 0; i < frase.length(); i++) {
            char aux = frase.charAt(i);
            if (aux == 'a' || aux == 'A') {
                cont++;
            }
        }

        if (cont > 0) {
            System.out.println("A letra 'a' aparece " + cont + " vezes.");
        } else {
            System.out.println("A letra 'a' não aparece na frase.");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String frase;

        System.out.println("Digite uma frase: ");
        frase = sc.nextLine();

        verLetra(frase);
        sc.close();
    }
}

3) Observe o trecho de código abaixo: int INDICE = 12, SOMA = 0, K = 1; enquanto K < INDICE faça { K = K + 1; SOMA = SOMA + K; } imprimir(SOMA); Ao final do processamento, qual será o valor da variável SOMA?

R: 77

4) Descubra a lógica e complete o próximo elemento:
a) 1, 3, 5, 7, ___
b) 2, 4, 8, 16, 32, 64, ____
c) 0, 1, 4, 9, 16, 25, 36, ____
d) 4, 16, 36, 64, ____
e) 1, 1, 2, 3, 5, 8, ____
f) 2,10, 12, 16, 17, 18, 19, ____

R:
a) 1, 3, 5, 7, 9
b) 2, 4, 8, 16, 32, 64, 128
c) 0, 1, 4, 9, 16, 25, 36, 49
d) 4, 16, 36, 64, 100
e) 1, 1, 2, 3, 5, 8, 13
f) 2,10, 12, 16, 17, 18, 19, 14


5) Você está em uma sala com três interruptores, cada um conectado a uma lâmpada em salas diferentes. Você não pode ver as lâmpadas da sala em que está, mas pode ligar e desligar os interruptores quantas vezes quiser. Seu objetivo é descobrir qual interruptor controla qual lâmpada. Como você faria para descobrir usando apenas duas idas até uma das salas das lâmpadas, qual interruptor controla cada lâmpada?  

R: Ligaria o interruptor numero 1, por exemplo, e deixaria a lampada ligada por tempo suficiente para que ela fique quente, depois desligaria esse e ligaria outro interruptor, o de numero 2 por exemplo, e deixaria ligado. Na ida eu iria a uma sala e verificaria a condição da lampada, se a lampada tivesse desligada e fria, entao ela seria a do interruptor numero 3, se ela estivesse desligada e quente, seria a do interruptor numero 1, e se estivesse ligada, seria a de numero 2. Na outra ida eu iria a outra sala e verificaria a mesma condição para a lampada, o interruptor que restasse seria a da sala restante. 
