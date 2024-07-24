Selection
=========

Selection adalah proses pengambilan keputusan berdasarkan kondisi yang diberikan. Dalam Java, seleksi dilakukan dengan menggunakan *if statement*.

Berikut adalah contoh penggunaan *if statement* di Java:

.. code-block:: java

    public class SelectionExample {

        public static void main(String[] args) {
            // Selection
            int a = 10;
            int b = 5;

            if (a > b) {
                System.out.println("a is greater than b");
            }

            if (a < b) {
                System.out.println("a is less than b");
            }

            if (a == b) {
                System.out.println("a is equal to b");
            }
        }
    }

.. code-block:: console

    a is greater than b

*If statement* dapat digunakan *nested* untuk mengecek kondisi yang lebih kompleks.

Berikut adalah contoh penggunaan *nested if statement* di Java:

.. code-block:: java

    public class NestedIfExample {

        public static void main(String[] args) {
            // Nested if statement
            int a = 10;
            int b = 5;
            int c = 15;

            if (a > b) {
                if (a > c) {
                    System.out.println("a is the greatest");
                } else {
                    System.out.println("c is the greatest");
                }
            } else {
                if (b > c) {
                    System.out.println("b is the greatest");
                } else {
                    System.out.println("c is the greatest");
                }
            }
        }
    }

.. code-block:: console

    a is the greatest

*If statement* juga dapat digunakan dengan *else if statement* dan *else statement* untuk mengecek kondisi yang lebih kompleks.

Berikut adalah contoh penggunaan *else if statement* dan *else statement* di Java:

.. code-block:: java

    public class ElseIfExample {

        public static void main(String[] args) {
            // Else if statement
            int a = 10;
            int b = 5;

            if (a > b) {
                System.out.println("a is greater than b");
            } else if (a < b) {
                System.out.println("a is less than b");
            } else {
                System.out.println("a is equal to b");
            }
        }
    }

.. code-block:: console

    a is greater than b