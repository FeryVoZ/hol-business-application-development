Primitive Data Type dan Wrapper Class
=====================================

Pada sesi ini, kita akan mempelajari tentang *primitive data type* dan *wrapper class* di Java.

Primitive Data Type
--------------------

*Primitive data type* adalah tipe data yang disediakan oleh Java untuk menyimpan data sederhana. *Primitive data type* tidak memiliki method dan tidak bisa disimpan dalam *collection* seperti *ArrayList*.

Berikut adalah *primitive data type* yang disediakan oleh Java:

-   `byte`: 8-bit signed integer
-   `short`: 16-bit signed integer
-   `int`: 32-bit signed integer
-   `long`: 64-bit signed integer
-   `float`: 32-bit floating point number
-   `double`: 64-bit floating point number
-   `char`: 16-bit Unicode character
-   `boolean`: true or false

Berikut adalah contoh penggunaan *primitive data type* di Java:

.. code-block:: java

    public class PrimitiveDataTypeExample {

        public static void main(String[] args) {
            // Primitive data type
            byte byteValue = 10;
            short shortValue = 20;
            int intValue = 30;
            long longValue = 40L;
            float floatValue = 50.5f;
            double doubleValue = 60.6;
            char charValue = 'A';
            boolean booleanValue = true;

            System.out.println("byteValue: " + byteValue);
            System.out.println("shortValue: " + shortValue);
            System.out.println("intValue: " + intValue);
            System.out.println("longValue: " + longValue);
            System.out.println("floatValue: " + floatValue);
            System.out.println("doubleValue: " + doubleValue);
            System.out.println("charValue: " + charValue);
            System.out.println("booleanValue: " + booleanValue);
        }
    }

.. code-block:: console

    byteValue: 10
    shortValue: 20
    intValue: 30
    longValue: 40
    floatValue: 50.5
    doubleValue: 60.6
    charValue: A
    booleanValue: true

Wrapper Class
-------------

*Wrapper class* adalah kelas yang digunakan untuk membungkus *primitive data type* agar bisa disimpan dalam *collection* seperti *ArrayList*. *Wrapper class* juga menyediakan method untuk melakukan operasi pada *primitive data type*.

Berikut adalah *wrapper class* yang sesuai dengan *primitive data type*:

-   `Byte`: untuk `byte`
-   `Short`: untuk `short`
-   `Integer`: untuk `int`
-   `Long`: untuk `long`
-   `Float`: untuk `float`
-   `Double`: untuk `double`
-   `Character`: untuk `char`
-   `Boolean`: untuk `boolean`

Berikut adalah contoh penggunaan *wrapper class* di Java:

.. code-block:: java

    import java.util.ArrayList;

    public class WrapperClassExample {

        public static void main(String[] args) {
            // Wrapper class
            Byte byteValue = 10;
            Short shortValue = 20;
            Integer intValue = 30;
            Long longValue = 40L;
            Float floatValue = 50.5f;
            Double doubleValue = 60.6;
            Character charValue = 'A';
            Boolean booleanValue = true;
            
            ArrayList<Integer> intList = new ArrayList<>();
            intList.add(10);
            intList.add(20);
            intList.add(30);

            System.out.println("byteValue: " + byteValue);
            System.out.println("shortValue: " + shortValue);
            System.out.println("intValue: " + intValue);
            System.out.println("longValue: " + longValue);
            System.out.println("floatValue: " + floatValue);
            System.out.println("doubleValue: " + doubleValue);
            System.out.println("charValue: " + charValue);
            
            for (Integer i : intList) {
                System.out.println("intList: " + i);
            }

            System.out.println("booleanValue: " + booleanValue);
        }

    }

.. code-block:: console

    byteValue: 10
    shortValue: 20
    intValue: 30
    longValue: 40
    floatValue: 50.5
    doubleValue: 60.6
    charValue: A
    intList: 10
    intList: 20
    intList: 30
    booleanValue: true

.. note:: 

    `String` adalah tipe data yang digunakan untuk menyimpan teks. `String` adalah tipe data yang tidak termasuk dalam *primitive data type* dan *wrapper class*. 
    Hal tersebut karena `String` adalah tidak membungkus *primitive data type* apapun, tetapi  `String` adalah tipe data yang memiliki method dan bisa disimpan dalam *collection* seperti *ArrayList*.