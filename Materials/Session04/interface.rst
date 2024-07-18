Interface
=========

Interface adalah salah satu konsep dasar dalam pemrograman berorientasi objek yang memungkinkan kita untuk membuat *class* yang hanya berisi *method* tanpa implementasi. 
*Interface* digunakan untuk membuat *class* yang memiliki *method* yang sama, namun memiliki implementasi yang berbeda, 
namun berbeda dengan *abstraction*, *interface* hanya digunakan oleh *class* yang mengimplementasi *interface* tersebut.

Berikut adalah contoh implementasi *interface* dalam Java.

.. code-block:: java

    // Deklarasi interface (Class tanpa atribut)
    public interface Binusian {
        // Abstract method tanpa implementasi
        public void activity();
    }

    // Implementasi interface
    public class Student implements Binusian {
        // Implementasi abstract method activity
        public void activity() {
            System.out.println("Student is studying");
        }
    }

    public class Lecturer implements Binusian {
        // Implementasi abstract method activity
        public void activity() {
            System.out.println("Lecturer is teaching");
        }
    }

    public class Main {

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

    Keyword ``implements`` digunakan untuk mengimplementasi *interface* pada *class* yang mengimplementasi *interface* tersebut.