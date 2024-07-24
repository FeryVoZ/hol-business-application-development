Polymorphism
============

Pada sesi ini kita akan membahas tentang *polymorphism* (polimorfisme) dalam pemrograman berorientasi objek. *Polymorphism* berasal dari bahasa Yunani, yaitu *poly*, yang berarti banyak, dan *morph*, yang berarti bentuk. Sehingga, *polymorphism* berarti sebuah *object* dapat memiliki banyak bentuk. Terdapat dua konsep *polymorphism* yang dapat diterapkan, yaitu *overloading* dan *overriding*.

Overloading
-----------

Konsep ini memungkinkan pembuat program dapat mendeklarasikan *method* dengan nama yang sama di dalam sebuah *class*, namun dengan *parameter* atau *return type* yang berbeda. Berikut adalah contoh implementasi *overloading*.

.. code-block:: java

    public class Main {
        // Method add dengan 2 parameter bertipe integer
        public int add(int a, int b) {
            return a + b;
        }

        // Method add dengan 3 parameter bertipe integer
        public int add(int a, int b, int c) {
            return a + b + c;
        }

        // Method add dengan 2 parameter bertipe double
        public double add(double a, double b) {
            return a + b;
        }

        public Main() {
            // Memanggil method add dengan 2 parameter bertipe integer
            System.out.println(add(1, 2));
            // Memanggil method add dengan 3 parameter bertipe integer
            System.out.println(add(1, 2, 3));  
            // Memanggil method add dengan 2 parameter bertipe double
            System.out.println(add(1.5, 2.5));
        }

        public static void main(String[] args) {
            new Main();
        }
    }

.. code:: console

    3
    6
    4.0

Overriding
----------

Konsep ini terjadi ketika child class (sub-class) memiliki method dengan nama yang sama, tipe parameter yang sama, dan return type yang sama dengan method dari parent class (super-class), namun isinya sudah disesuaikan dengan child class (sub-class) tersebut. Maka, program hanya akan menjalankan method yang berada pada child class. Berikut adalah contoh implementasi overriding.

.. code-block:: java

    public class Main {

        // Class parent
        public class Binusian {
            public void activity() {
                System.out.println("Binusian doing activities");
            }
        }

        // Class child
        public class Student extends Binusian {
            @Override
            public void activity() {
                System.out.println("Student is studying");
            }
        }

        // Class child
        public class Lecturer extends Binusian {
            @Override
            public void activity() {
                System.out.println("Lecturer is teaching");
            }
        }

        public Main() {
            // Membuat object dari class Student
            Student student = new Student();
            // Memanggil method activity dari class Student
            student.activity();

            // Membuat object dari class Lecturer
            Lecturer lecturer = new Lecturer();
            // Memanggil method activity dari class Lecturer
            lecturer.activity();
        }

        public static void main(String[] args) {
            new Main();
        }
    }

.. code:: console

    Student is studying
    Lecturer is teaching

