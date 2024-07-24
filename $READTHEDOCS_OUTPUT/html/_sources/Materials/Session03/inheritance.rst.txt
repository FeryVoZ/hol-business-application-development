Inheritance
===========

Setelah mempelajari *encapsulation*, maka kita akan mempelajari pilar utama OOP yang selanjutnya, yaitu *inheritance*. *Inheritance* adalah salah satu konsep dasar dalam pemrograman berorientasi objek yang memungkinkan kita untuk membuat *class* baru yang mewarisi atribut dan metode dari *class* yang sudah ada. 
*Class* yang mewarisi disebut sebagai *subclass* atau *child class*, sedangkan *class* yang diwarisi disebut sebagai *superclass* atau *parent class*. Maka dapat disimpulkan, *inheritance* adalah proses dimana *subclass* mewarisi atribut dan metode dari *superclass*.

Berikut adalah contoh implementasi *inheritance* dalam Java:

.. code-block:: java

    public class Main {

        // Deklarasi class parent
        public class Binusian {
            // Atribut yang dimiliki oleh class Binusian
            public String binusianID;
            public String name;
            public String birthDate;
            public String role;
            public int registrationYear;

            // Constructor dari class Binusian
            public Binusian(String binusianID, String name, String birthDate, String role, int registrationYear) {
                this.binusianID = binusianID;
                this.name = name;
                this.birthDate = birthDate;
                this.role = role;
                this.registrationYear = registrationYear;
            }
        
            // Metode yang dimiliki oleh class Binusian
            public void masukBinus() {
                System.out.println("Selamat datang di Binus!");
            }
        
            public void keluarBinus() {
                System.out.println("Sampai jumpa! Hati-hati di jalan!");
            }
        }

        // Implementasi class child
        public class Student extends Binusian {
            // Atribut yang dimiliki oleh class Student
            public String NIM;
            public String major;
            public int semester;
        
            // Constructor dari class Student
            public Student(String binusianID, String name, String birthDate, String role, int registrationYear, String NIM, String major, int semester) {
                super(binusianID, name, birthDate, role, registrationYear);
                this.NIM = NIM;
                this.major = major;
                this.semester = semester;
            }

            // Metode yang dimiliki oleh class Student
            public void study() {
                System.out.println("Mahasiswa sedang belajar");
            }   
            public void exam() {
                System.out.println("Mahasiswa sedang ujian");
            }
        }

        public class Lecturer extends Binusian {
            // Atribut yang dimiliki oleh class Lecturer
            public String lecturerCode;
            public String subject;
            public int salary;
        
            // Constructor dari class Lecturer
            public Lecturer(String binusianID, String name, String birthDate, String role, int registrationYear, String lecturerCode, String subject, int salary) {
                super(binusianID, name, birthDate, role, registrationYear);
                this.lecturerCode = lecturerCode;
                this.subject = subject;
                this.salary = salary;
            }

            // Metode yang dimiliki oleh class Lecturer
            public void teach() {
                System.out.println("Dosen sedang mengajar");
            }
        
            public void caseMake() {
                System.out.println("dosen sedang membuat soal");
            }
        }

        public Main() {
            // Membuat objek Student
            Student student = new Student("BN123456789", "Java", "01-01-2004", "Mahasiswa", 2022, "2602000000", "Computer Science", 1);
            student.masukBinus();
            student.study();
            student.exam();
            student.keluarBinus();

            // Membuat objek Lecturer
            Lecturer lecturer = new Lecturer("BN987654321", "Python", "01-01-2000", "Dosen", 2000, "D1234", "Programming", 8000000);
            lecturer.masukBinus();
            lecturer.teach();
            lecturer.caseMake();
            lecturer.keluarBinus();
        }

        public static void main(String[] args) {
            new Main();
        }
    }

.. code:: console
    
        Selamat datang di Binus!
        Mahasiswa sedang belajar
        Mahasiswa sedang ujian
        Sampai jumpa! Hati-hati di jalan!
        Selamat datang di Binus!
        Dosen sedang mengajar
        Dosen sedang membuat soal
        Sampai jumpa! Hati-hati di jalan!

.. note:: 

    Keyword ``super`` digunakan untuk memanggil constructor dari *superclass*, sehingga atribut dari *superclass* dapat diwariskan ke *subclass*.

Pada contoh di atas, *class* `Student` dan `Lecturer` mewarisi atribut dan metode dari *class* `Binusian`. 
*Class* `Student` dan `Lecturer` adalah *subclass* dari *class* `Binusian`, sedangkan *class* `Binusian` adalah *superclass* dari *class* `Student` dan `Lecturer`.