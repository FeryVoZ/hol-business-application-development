Abstraction
============

Setelah mengerti tentang *polymorphism*, mari kita pelajari *abstraction*.
*Abstraction* adalah salah satu konsep dasar dalam pemrograman berorientasi objek yang memungkinkan kita untuk menyembunyikan detail implementasi dari suatu objek dan hanya menampilkan fungsionalitas yang diperlukan. 
Dengan menggunakan *abstraction*, kita dapat membuat *class* yang hanya berisi *method* tanpa implementasi, yang kemudian diimplementasikan oleh *subclass* yang mewarisi *class* tersebut.
Method tanpa implementasi tersebut disebut sebagai *abstract method*, dan *class* yang memiliki *abstract method* disebut sebagai *abstract class*. 
Abstract method yang dimiliki oleh *abstract class* harus diimplementasikan oleh *subclass* yang mewarisi *abstract class* tersebut.

Berikut adalah contoh implementasi *abstraction* dalam Java:

.. code-block:: java

    public class Main {

        // Deklarasi class abstract
        public abstract class Binusian {
            // Abstract method tanpa implementasi
            public abstract void activity();
        }

        // Implementasi class Binusian
        public class Student extends Binusian {
            // Implementasi abstract method activity
            public void activity() {
                System.out.println("Student is studying");
            }
        }

        public class Lecturer extends Binusian {
            // Implementasi abstract method activity
            public void activity() {
                    System.out.println("Lecturer is teaching");
            }
        }

        public Main() {
            // Membuat objek Student
            Binusian student = new Student();
            student.activity();

            // Membuat objek Lecturer
            Binusian lecturer = new Lecturer();
            lecturer.activity();
        }

        public static void main(String[] args) {
            new Main();
        }
    }

.. code:: console
    
        Student is studying
        Lecturer is teaching

.. note:: 

    Keyword ``abstract`` digunakan untuk mendeklarasikan *class* atau *method* sebagai *abstract class* atau *abstract method*.

Dengan mengimplementasi *polymorphism* dan *abstraction*, kita dapat membuat *class* atau *method* yang lebih fleksibel dan dapat menyesuaikan dengan berbagai kebutuhan.