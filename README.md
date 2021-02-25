# kalkulator
package pl.llassoszkolenia;

import java.sql.SQLOutput;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        int liczba1, liczba2;
        String opreacja;

        System.out.println("Podaj pierwszą liczbę: ");
        liczba1 = getInt();
        System.out.println("Podaj drugą liczbę: ");
        liczba2 = getInt();
        System.out.println("Podaj rodzaj działąnia: (+ - * /)");
        opreacja = getString();

        int wynik = 0;
        boolean nieprawidlowaOperacja = false;

        if (opreacja.equals("+")) {
            wynik = liczba1 + liczba2;
        } else if (opreacja.equals("-")) {
            wynik = liczba1 - liczba2;
        } else if (opreacja.equals("*")) {
            wynik = liczba1 * liczba2;
        } else if (opreacja.equals("/")) {
            if (liczba2 == 0) {
                nieprawidlowaOperacja = true;
                System.out.println("Mianownik nie może wynosić 0. Nie można wykonać działania.");
            } else {
                wynik = liczba1 / liczba2;
            }
        } else {
            nieprawidlowaOperacja = true;
            System.out.println("Nieprawidłowa operacja");
        }
        if (!nieprawidlowaOperacja) {
            System.out.println(liczba1 + " " + opreacja + " " + liczba2 + " = " + wynik);
        }
    }
    public static int getInt() {
        return new Scanner(System.in).nextInt();
    }
    public static String getString() {
        return new Scanner(System.in).next();
    }
}
