Method 
======

Methods adalah blok kode yang berisi serangkaian pernyataan yang diberi nama. Method digunakan untuk menjalankan serangkaian pernyataan yang sama berulang kali. Method dapat menerima parameter dan mengembalikan nilai. Method digunakan untuk mengatur kode menjadi lebih terstruktur dan mudah dibaca.

Deklarasi Method
----------------

Method dideklarasikan dengan menentukan visibilitas, tipe data kembalian, nama method, dan parameter yang diterima. Berikut adalah contoh deklarasi method di Java:

.. code-block:: java

    public class MethodExample {

        public static void main(String[] args) {
            // Call method
            sayHello();
        }

        // Method declaration
        public static void sayHello() {
            System.out.println("Hello, World!");
        }
    }

.. code-block:: console

    Hello, World!

Pemanggilan Method
------------------

Method dipanggil dengan menggunakan nama method diikuti dengan tanda kurung buka dan tutup. Jika method menerima parameter, parameter diberikan di dalam tanda kurung. Berikut adalah contoh pemanggilan method di Java:

.. code-block:: java

    public class MethodExample {

        public static void main(String[] args) {
            // Call method
            sayHello("Budi Setiawan");
        }

        // Method declaration
        public static void sayHello(String name) {
            System.out.println("Hello, " + name + "!");
        }
    }

.. code-block:: console

    Hello, Budi Setiawan!

Parameter dan Nilai Kembalian Method
------------------------------------

Method dapat menerima parameter yang digunakan untuk mengirim data ke method. Parameter dideklarasikan di dalam tanda kurung setelah nama method. 
Method dapat mengembalikan nilai dengan menggunakan kata kunci `return`. Tipe data kembalian method dideklarasikan setelah visibilitas method.
Berikut adalah contoh penggunaan parameter dan nilai kembalian method di Java:

.. code-block:: java

    public class MethodExample {

        public static void main(String[] args) {
            // Call method
            int sum = add(10, 20);
            System.out.println("Sum: " + sum);
        }

        // Method declaration
        public int add(int a, int b) {
            return a + b;
        }
    }

.. code-block:: console

    Sum: 30

