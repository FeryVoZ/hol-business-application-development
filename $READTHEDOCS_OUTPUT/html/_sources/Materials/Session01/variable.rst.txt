Variable
========

Variabel adalah tempat penyimpanan data. Ini adalah cara untuk memberi nama pada data sehingga data tersebut dapat diakses kembali.

Dalam Java, variabel harus dideklarasikan terlebih dahulu sebelum digunakan. Deklarasi variabel dilakukan dengan menentukan tipe data variabel dan memberikan nama variabel tersebut.

Contoh deklarasi variabel dalam Java:

.. code-block:: java

    int number;
    String name;
    double price;

Variabel juga dapat diinisialisasi saat dideklarasikan. Inisialisasi variabel dilakukan dengan memberikan nilai awal pada variabel tersebut.

Contoh inisialisasi variabel dalam Java:

.. code-block:: java

    int number = 10;
    String name = "John Doe";
    double price = 100.50;

Variabel juga dapat diinisialisasi dengan nilai dari variabel lain.

Contoh inisialisasi variabel dengan nilai dari variabel lain:

.. code-block:: java

    int number1 = 10;
    int number2 = number1;
    int number3 = number1 + number2;

Variabel juga dapat diinisialisasi dengan nilai dari input pengguna.

Contoh inisialisasi variabel dengan nilai dari input pengguna:

.. code-block:: java

    import java.util.Scanner;

    public class Main {

        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);

            System.out.print("Enter a number: ");
            int number = scanner.nextInt();

            System.out.println("You entered: " + number);
        }
    }