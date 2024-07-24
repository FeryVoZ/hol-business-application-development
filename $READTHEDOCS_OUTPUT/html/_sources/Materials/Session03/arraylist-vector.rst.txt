Arraylist dan Vector
====================

Arraylist dan Vector adalah dua kelas yang digunakan untuk menyimpan objek dalam bentuk array. Meski memiliki fungsi yang sama, namun keduanya memiliki perbedaan, berikut adalah perbedaan antara Arraylist dan Vector.

1. Sinkronisasi

- ArrayList: Tidak disinkronisasi. Ini berarti ArrayList tidak thread-safe dan tidak cocok digunakan dalam lingkungan multi-threaded tanpa pengelolaan sinkronisasi tambahan.

- Vector: Disinkronisasi. Vector thread-safe karena semua metode utama disinkronisasi. Ini membuat Vector cocok digunakan dalam lingkungan multi-threaded tetapi dengan biaya kinerja tambahan.

2. Kinerja

- ArrayList: Lebih cepat dibandingkan Vector karena tidak ada overhead sinkronisasi.

- Vector: Lebih lambat karena semua metode disinkronisasi, yang menambah overhead kinerja.

3. Pertumbuhan Kapasitas

- ArrayList: Ketika ukuran ArrayList melebihi kapasitas awal, ia meningkatkan kapasitasnya sebesar 50% dari ukuran saat ini.

- Vector: Ketika ukuran Vector melebihi kapasitas awal, ia meningkatkan kapasitasnya dua kali lipat dari ukuran saat ini. Namun, kita bisa menentukan pertumbuhan kapasitas secara manual dengan constructor yang menerima initialCapacity dan capacityIncrement.

4. Warisan (Legacy)

- ArrayList: Diperkenalkan di Java 1.2 sebagai bagian dari Collection Framework. Ini adalah implementasi yang lebih baru dan lebih direkomendasikan untuk penggunaan modern.

- Vector: Diperkenalkan di Java 1.0 sebagai bagian dari versi awal dari Collection Framework. Meskipun masih digunakan, ini dianggap usang (legacy) dan tidak direkomendasikan untuk penggunaan baru.

Berikut adalah contoh penggunaan Arraylist dan Vector dalam OOP Java.

.. code-block:: java

    import java.util.ArrayList;
    import java.util.Vector;

    public class Main {

        public class Binusian {
            public String binusianID;
            public String name;
            public String birthDate;
            public String role;
            public int registrationYear;

            public Binusian(String binusianID, String name, String birthDate, String role, int registrationYear) {
                this.binusianID = binusianID;
                this.name = name;
                this.birthDate = birthDate;
                this.role = role;
                this.registrationYear = registrationYear;
            }
        }

        public class Student extends Binusian {
            public String NIM;
            public String major;
            public int semester;

            public Student(String binusianID, String name, String birthDate, String role, int registrationYear, String NIM, String major, int semester) {
                super(binusianID, name, birthDate, role, registrationYear);
                this.NIM = NIM;
                this.major = major;
                this.semester = semester;
            }
        }

        public class Lecturer extends Binusian {
            public String lecturerCode;
            public String subject;
            public int salary;

            public Lecturer(String binusianID, String name, String birthDate, String role, int registrationYear, String lecturerCode, String subject, int salary) {
                super(binusianID, name, birthDate, role, registrationYear);
                this.lecturerCode = lecturerCode;
                this.subject = subject;
                this.salary = salary;
            }
        }

        public Main(){
            // Membuat objek ArrayList
            ArrayList<Binusian> binusianList = new ArrayList<Binusian>();

            // Membuat objek Vector
            Vector<Binusian> binusianVector = new Vector<Binusian>();

            // Menambahkan objek Student ke ArrayList
            binusianList.add(new Student("BN123456789", "Java", "01-01-2004", "Mahasiswa", 2022, "123456789", "Informatika", 3));

            // Menambahkan objek Lecturer ke Vector
            binusianVector.add(new Lecturer("BN987654321", "Python", "01-01-2000", "Dosen", 2000, "D1234", "Pemrograman", 10000000));

            // Menampilkan objek Student dari ArrayList
            for (Binusian binusian : binusianList) {
                System.out.println("Binusian ID = " + binusian.binusianID);
                System.out.println("Nama = " + binusian.name);
                System.out.println("Tanggal Lahir = " + binusian.birthDate);
                System.out.println("Peran = " + binusian.role);
                System.out.println("Tahun Pendaftaran = " + binusian.registrationYear);
            }

            // Menampilkan objek Lecturer dari Vector
            for (Binusian binusian : binusianVector) {
                System.out.println("Binusian ID = " + binusian.binusianID);
                System.out.println("Nama = " + binusian.name);
                System.out.println("Tanggal Lahir = " + binusian.birthDate);
                System.out.println("Peran = " + binusian.role);
                System.out.println("Tahun Pendaftaran = " + binusian.registrationYear);
            }
        }

        public static void main(String[] args) {
            new Main();
        }
    }

.. code:: console
    
        Binusian ID = BN123456789
        Nama = Java
        Tanggal Lahir = 01-01-2004
        Peran = Mahasiswa
        Tahun Pendaftaran = 2022
        Binusian ID = BN987654321
        Nama = Python
        Tanggal Lahir = 01-01-2000
        Peran = Dosen
        Tahun Pendaftaran = 2000

