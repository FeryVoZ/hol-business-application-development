Repetition
==========

Repetition adalah proses melakukan perulangan kode tertentu. Dalam Java, terdapat beberapa cara untuk melakukan perulangan, yaitu:

1. `for loop`
2. `while loop`
3. `do-while loop`
4. `foreach loop`


For Loop
--------

`For loop` digunakan untuk melakukan perulangan kode dengan jumlah perulangan yang sudah diketahui sebelumnya. Berikut adalah contoh penggunaan `for loop` di Java:

.. code-block:: java

    public class ForLoopExample {

        public static void main(String[] args) {
            // For loop
            for (int i = 0; i < 5; i++) {
                System.out.println("i: " + i);
            }
        }
    }

.. code-block:: console

    i: 0
    i: 1
    i: 2
    i: 3
    i: 4

While Loop
----------

`While loop` digunakan untuk melakukan perulangan kode selama kondisi yang diberikan bernilai `true`. Berikut adalah contoh penggunaan `while loop` di Java:

.. code-block:: java

    public class WhileLoopExample {

        public static void main(String[] args) {
            // While loop
            int i = 0;
            while (i < 5) {
                System.out.println("i: " + i);
                i++;
            }
        }
    }

.. code-block:: console

    i: 0
    i: 1
    i: 2
    i: 3
    i: 4

Do-While Loop
-------------

`Do-while loop` digunakan untuk melakukan perulangan kode minimal satu kali, kemudian dilanjutkan selama kondisi yang diberikan bernilai `true`. Berikut adalah contoh penggunaan `do-while loop` di Java:

.. code-block:: java

    public class DoWhileLoopExample {

        public static void main(String[] args) {
            // Do-while loop
            int i = 0;
            do {
                System.out.println("i: " + i);
                i++;
            } while (i < 5);
        }
    }

.. code-block:: console

    i: 0
    i: 1
    i: 2
    i: 3
    i: 4

Foreach Loop
------------

`Foreach loop` digunakan untuk melakukan perulangan kode pada elemen-elemen dalam sebuah *collection* seperti `array` atau `list`. Berikut adalah contoh penggunaan `foreach loop` di Java:

.. code-block:: java

    import java.util.ArrayList;

    public class ForeachLoopExample {

        public static void main(String[] args) {
            // Foreach loop
            ArrayList<Integer> intList = new ArrayList<>();
            intList.add(10);
            intList.add(20);
            intList.add(30);

            for (Integer i : intList) {
                System.out.println("i: " + i);
            }
        }
    }

.. code-block:: console

    i: 10
    i: 20
    i: 30

.. note:: 

    Dalam perulangan terdapat istilah `break` dan `continue`. `break` digunakan untuk menghentikan perulangan, sedangkan `continue` digunakan untuk melanjutkan perulangan ke iterasi selanjutnya.