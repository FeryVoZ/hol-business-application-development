Arithmetic dan Logical Operator
================================

Operator adalah simbol yang digunakan untuk melakukan operasi tertentu pada satu atau lebih operand. Operator aritmatika digunakan untuk melakukan operasi matematika seperti penjumlahan, pengurangan, perkalian, pembagian, dan sebagainya. Operator logika digunakan untuk melakukan operasi logika seperti AND, OR, NOT, dan sebagainya.

Operator Aritmatika
-------------------

Operator aritmatika digunakan untuk melakukan operasi matematika pada dua operand. Berikut adalah operator aritmatika yang disediakan oleh Java:

-   `+`: Penjumlahan
-   `-`: Pengurangan
-   `*`: Perkalian
-   `/`: Pembagian
-   `%`: Modulus

Berikut adalah contoh penggunaan operator aritmatika di Java:

.. code-block:: java

    public class ArithmeticOperatorExample {

        public static void main(String[] args) {
            // Arithmetic operator
            int a = 10;
            int b = 5;

            System.out.println("a + b = " + (a + b));
            System.out.println("a - b = " + (a - b));
            System.out.println("a * b = " + (a * b));
            System.out.println("a / b = " + (a / b));
            System.out.println("a % b = " + (a % b));
        }
    }

.. code-block:: console

    a + b = 15
    a - b = 5
    a * b = 50
    a / b = 2
    a % b = 0

Operator Logika
---------------

Operator logika digunakan untuk melakukan operasi logika pada dua operand. Berikut adalah operator logika yang disediakan oleh Java:

-   `&&`: AND
-   `||`: OR
-   `!`: NOT
-   `==`: Equal to
-   `!=`: Not equal to
-   `>`: Greater than
-   `<`: Less than
-   `>=`: Greater than or equal to
-   `<=`: Less than or equal to

Berikut adalah contoh penggunaan operator logika di Java:

.. code-block:: java

    public class LogicalOperatorExample {

        public static void main(String[] args) {
            // Logical operator
            int a = 10;
            int b = 5;

            System.out.println("a > b: " + (a > b));
            System.out.println("a < b: " + (a < b));
            System.out.println("a == b: " + (a == b));
            System.out.println("a != b: " + (a != b));
            System.out.println("a >= b: " + (a >= b));
            System.out.println("a <= b: " + (a <= b));
        }
    }

.. code-block:: console

    a > b: true
    a < b: false
    a == b: false
    a != b: true
    a >= b: true
    a <= b: false