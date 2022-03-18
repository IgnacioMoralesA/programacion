# programacion
codigo evidencia
package com.mycompany.mavenproject35;

public class NumeroAleatorio {
    public static void main(String[] args) {
        int[] arreglo = generarArreglo(10, 5);
        mostrar(arreglo);
        ordenar(arreglo);
        mostrar(arreglo);
    }

    public static int[] generarArreglo(int largo, int rango) {
        if(rango<largo){
            rango = largo;
        }
        int[] arr = new int[largo];
        for (int i = 0; i < arr.length; i++) {
            int  nuevoNumero =(int)(Math.random()*rango);
            while(existeNumero(arr,nuevoNumero, i)){
                nuevoNumero = (int)(Math.random()*rango);
            }
            arr[i]=nuevoNumero;
        }
        return arr;
    }

    public static boolean existeNumero(int[] arr, int numero, int limite) {
        for (int i = 0; i < limite; i++) {
            if(arr[i]==numero){
                return true;
            }
        }
        return false;
    }

    public static void mostrar(int[] arreglo) {
        for (int j : arreglo) {
            System.out.print("[" + j + "]");
        }
        System.out.println();
    }

    private static void ordenar(int[] arreglo) {
        for (int i = 0; i < arreglo.length-1; i++) {
            for (int j = 0; j < arreglo.length-1; j++) {
                if(arreglo[j]>arreglo[j+1]){
                    int aux = arreglo[j];
                    arreglo [j] = arreglo[j+1];
                    arreglo[j+1]= aux;
                }
            }
        }
    }
}
