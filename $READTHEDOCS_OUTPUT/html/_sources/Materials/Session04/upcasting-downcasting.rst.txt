Upcasting dan Downcasting
=========================

Upcasting dan downcasting adalah dua konsep bagian dari *polymorphism* yang sering digunakan dalam pemrograman berorientasi objek, terutama ketika kita bekerja dengan *inheritance* dan *polymorphism*.

Upcasting
---------

Upcasting adalah proses konversi objek dari *subclass* ke *superclass*. Upcasting dilakukan ketika kita ingin mengakses objek *subclass* sebagai objek *superclass*. Upcasting dilakukan secara otomatis oleh Java, sehingga kita tidak perlu melakukan konversi secara eksplisit.

Berikut adalah contoh implementasi upcasting dalam Java:

.. code-block:: java

    import java.util.ArrayList;

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
        }

        ArrayList<Binusian> binusianList = new ArrayList<Binusian>();

        public Main() {
            // Membuat objek Student
            Student student = new Student("BN123456789", "Java", "01-01-2004", "Mahasiswa", 2022, "2602000000", "Computer Science", 1);

            // Membuat objek Lecturer
            Lecturer lecturer = new Lecturer("BN987654321", "Python", "01-01-2000", "Dosen", 2000, "D1234", "Programming", 8000000);

            // Menambahkan semua objek ke dalam ArrayList
            binusianList.add(student);
            binusianList.add(lecturer);

            // Mengakses objek Student dan Lecturer menggunakan ArrayList
            for (Binusian binusian : binusianList) {
                System.out.println("Binusian ID = " + binusian.binusianID);
                System.out.println("Name = " + binusian.name);
                System.out.println("Birth Date = " + binusian.birthDate);
                System.out.println("Role = " + binusian.role);
                System.out.println("Registration Year = " + binusian.registrationYear);
                binusian.masukBinus();
                binusian.keluarBinus();
                System.out.println();
            }

        }

        public static void main(String[] args) {
            new Main();
        }
    }

.. code:: console
    
        Binusian ID = BN123456789
        Name = Java
        Birth Date = 01-01-2004
        Role = Mahasiswa
        Registration Year = 2022
        Selamat datang di Binus!
        Sampai jumpa! Hati-hati di jalan!
    
        Binusian ID = BN987654321
        Name = Python
        Birth Date = 01-01-2000
        Role = Dosen
        Registration Year = 2000
        Selamat datang di Binus!
        Sampai jumpa! Hati-hati di jalan!

Ketika kita menggunakan upcasting, maka kita hanya dapat mengakses atribut dan method yang dimiliki oleh *superclass* saja. Hal ini dikarenakan objek *subclass* diakses sebagai objek *superclass*. 
Jika kita ingin mengakses atribut dan method yang dimiliki oleh *subclass*, maka kita perlu melakukan downcasting.

Downcasting
-----------

Downcasting adalah proses konversi objek dari *superclass* ke *subclass*. Downcasting dilakukan ketika kita ingin mengakses objek *superclass* sebagai objek *subclass*. Downcasting tidak dilakukan secara otomatis oleh Java, sehingga kita perlu melakukan konversi secara eksplisit.

Berikut adalah contoh implementasi downcasting dalam Java.

.. code-block:: java

    import java.util.ArrayList;

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
        }

        ArrayList<Binusian> binusianList = new ArrayList<Binusian>();

        public Main() {
            // Membuat objek Student
            Student student = new Student("BN123456789", "Java", "01-01-2004", "Mahasiswa", 2022, "2602000000", "Computer Science", 1);

            // Membuat objek Lecturer
            Lecturer lecturer = new Lecturer("BN987654321", "Python", "01-01-2000", "Dosen", 2000, "D1234", "Programming", 8000000);

            // Menambahkan semua objek ke dalam ArrayList
            binusianList.add(student);
            binusianList.add(lecturer);

            // Mengakses objek Student dan Lecturer menggunakan ArrayList
            for (Binusian binusian : binusianList) {
                System.out.println("Binusian ID = " + binusian.binusianID);
                System.out.println("Name = " + binusian.name);
                System.out.println("Birth Date = " + binusian.birthDate);
                System.out.println("Role = " + binusian.role);
                System.out.println("Registration Year = " + binusian.registrationYear);
                binusian.masukBinus();
                binusian.keluarBinus();
                System.out.println();

                // Downcasting
                if (binusian instanceof Student) {
                    Student student = (Student) binusian;
                    System.out.println("NIM = " + student.NIM);
                    System.out.println("Major = " + student.major);
                    System.out.println("Semester = " + student.semester);
                    student.study();
                    student.exam();
                } else if (binusian instanceof Lecturer) {
                    Lecturer lecturer = (Lecturer) binusian;
                    System.out.println("Lecturer Code = " + lecturer.lecturerCode);
                    System.out.println("Subject = " + lecturer.subject);
                    System.out.println("Salary = " + lecturer.salary);
                    lecturer.teach();
                    lecturer.research();
                }
                System.out.println();
            }

        }

        public static void main(String[] args) {
            new Main();
        }
    }

.. code:: console
    
        Binusian ID = BN123456789
        Name = Java
        Birth Date = 01-01-2004
        Role = Mahasiswa
        Registration Year = 2022
        Selamat datang di Binus!
        Sampai jumpa! Hati-hati di jalan!
    
        NIM = 2602000000
        Major = Computer Science
        Semester = 1
        Mahasiswa sedang belajar
        Mahasiswa sedang ujian
    
        Binusian ID = BN987654321
        Name = Python
        Birth Date = 01-01-2000
        Role = Dosen
        Registration Year = 2000
        Selamat datang di Binus!
        Sampai jumpa! Hati-hati di jalan!
    
        Lecturer Code = D1234
        Subject = Programming
        Salary = 8000000
        Dosen sedang mengajar
        Dosen sedang melakukan penelitian

Ketika kita menggunakan downcasting, maka kita dapat mengakses atribut dan method yang dimiliki oleh *subclass*. Hal ini dikarenakan objek *superclass* diakses sebagai objek *subclass*.

.. note:: 

    Keyword ``instanceof`` digunakan untuk mengecek apakah objek yang sedang diakses merupakan objek dari *subclass* tertentu atau bukan. Jika objek merupakan objek dari *subclass* tertentu, maka kita dapat melakukan downcasting untuk mengakses atribut dan method yang dimiliki oleh *subclass* tersebut.