Input dan Output
================

Input
-----

Input adalah proses memasukkan data ke dalam program. Data yang dimasukkan bisa berupa data yang diinputkan oleh pengguna atau data yang diambil dari file atau database.

Berikut contoh code untuk mengambil input dari pengguna.

.. code-block:: java

    import java.util.Scanner;

    public class Main {

        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);

            System.out.print("Enter your name: ");
            String name = scanner.nextLine();

            System.out.println("Hello, " + name + "!");
        }
    }

Output
------

Output adalah proses menampilkan data dari program ke layar atau ke file atau ke database.

Berikut contoh code untuk menampilkan output ke layar.

.. code-block:: java

    public class Main {

        public static void main(String[] args) {
            System.out.println("Hello, World!");
        }
    }