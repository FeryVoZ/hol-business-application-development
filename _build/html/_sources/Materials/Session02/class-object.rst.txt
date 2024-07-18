Class, Object, dan Constructor
==============================

Pada materi sebelumnya, disebutkan beberapa konsep dasar dalam OOP, salah satunya adalah class dan object. Berikut penjelasan lebih dalam mengenai class dan object.

Class
-----

Class adalah blueprint atau cetakan untuk menciptakan objek. Class mendefinisikan *atribut* (variabel) dan *metode* (fungsi) yang akan dimiliki oleh objek. Dalam Java, class adalah struktur dasar yang digunakan untuk membuat objek. Misalnya kita ingin membuat class Binusian (warga Binus). Maka atribut yang dimiliki oleh class tersebut adalah Binusian ID, nama, tanggal lahir, peran, dan lainnya. Sedangkan metode yang dimiliki oleh class tersebut adalah masukBinus(), keluarBinus(), absen(), dan lainnya.

Berikut adalah implementasi kode dalam membuat class berdasarkan contoh di atas.

.. code-block:: java
    
    // Deklarasi class Binusian
    public class Binusian {
        // Atribut yang dimiliki oleh class Binusian
        public String binusianID;
        public String name;
        public String birthDate;
        public String role;
        public int registrationYear;
        
        // Metode yang dimiliki oleh class Binusian
        public void masukBinus() {
            System.out.println("Selamat datang di Binus!");
        }
        
        public void keluarBinus() {
            System.out.println("Sampai jumpa! Hati-hati di jalan!");
        }
        
        public void absen() {
            System.out.println("Absen berhasil!");
        }
    }

Object
------

Object adalah instance dari class. Object adalah wujud nyata dari class yang telah didefinisikan sebelumnya. Dengan kata lain, object adalah realisasi dari class. Misalnya kita membuat objek dari class Binusian, maka objek tersebut adalah wujud nyata dari class Binusian yang memiliki atribut dan metode yang telah didefinisikan sebelumnya.
Object dapat dibuat dengan memanggil constructor dari class tersebut. Ketika sebuah object dibuat, semua atribut dan method yang sudah didefinisikan di dalam class dapat langsung digunakan.

Berikut adalah implementasi kode dalam membuat object berdasarkan contoh di atas.

.. code-block:: java

    public class Main {

        // Deklarasi class Binusian, yang sudah dibuat sebelumnya
        public class Binusian {
            public String binusianID;
            public String name;
            public String birthDate;
            public String role;
            public int registrationYear;
        
            public void masukBinus() {
                System.out.println("Selamat datang di Binus!");
            }
        
            public void keluarBinus() {
                System.out.println("Sampai jumpa! Hati-hati di jalan!");
            }
        
            public void absen() {
                System.out.println("Absen berhasil!");
            }
        }

        public Main() {

            // Membuat object dari class Binusian
            Binusian binusian = new Binusian();

            // Menampilkan isi atribut dari class Binusian
            System.out.println("Binusian ID = " + binusian.binusianID);
            System.out.println("Nama = " + binusian.nama);
            System.out.println("Tanggal Lahir = " + binusian.birthDate);
            System.out.println("Peran = " + binusian.role);
            System.out.println("Tahun Pendaftaran = " + binusian.registrationYear);

            // Memanggil perilaku dari class Binusian
            binusian.masukBinus();
            binusian.absen();
            binusian.keluarBinus();
        }

        public static void main(String[] args) {
            new Main();
        }
    }

.. code:: console

    Binusian ID = null
    Nama = null
    Tanggal Lahir = null
    Peran = null
    Tahun Pendaftaran = 0
    Selamat datang di Binus!
    Absen berhasil!
    Sampai jumpa! Hati-hati di jalan!

Pada kode di atas, atribut yang dimiliki pada class Binusian masih bernilai default. Selain itu, method yang dimiliki juga melakukan output secara statis. Oleh karena itu, perlu dibuat constructor pada class Binusian untuk menginisialisasikan atribut.

Constructor
-----------

Constructor adalah metode khusus yang digunakan untuk menginisialisasikan objek dari class. Constructor memiliki nama yang sama dengan nama class dan tidak memiliki nilai balik (void). Constructor akan dijalankan ketika objek dari class tersebut dibuat. Constructor digunakan untuk menginisialisasikan nilai awal dari atribut yang dimiliki oleh class.

Berikut adalah implementasi kode dalam membuat constructor pada class Binusian.

.. code-block:: java

    public class Main {

        // Deklarasi class Binusian, yang sudah dibuat sebelumnya
        public class Binusian {
            public String binusianID;
            public String name;
            public String birthDate;
            public String role;
            public int registrationYear;
        
            // Constructor untuk menginisialisasikan atribut
            public Binusian(String binusianID, String name, String birthDate, String role, int registrationYear) {
                this.binusianID = binusianID;
                this.name = name;
                this.birthDate = birthDate;
                this.role = role;
                this.registrationYear = registrationYear;
            }

            public void masukBinus() {
                System.out.println("Selamat datang di Binus!");
            }
        
            public void keluarBinus() {
                System.out.println("Sampai jumpa! Hati-hati di jalan!");
            }
        
            public void absen() {
                System.out.println("Absen berhasil!");
            }
        }

        public Main() {

            // Membuat object dari class Binusian
            Binusian binusian = new Binusian("BN123456789", "Java", "01-01-2004", "Mahasiswa", 2022);

            // Menampilkan isi atribut dari class Binusian
            System.out.println("Binusian ID = " + binusian.binusianID);
            System.out.println("Nama = " + binusian.nama);
            System.out.println("Tanggal Lahir = " + binusian.birthDate);
            System.out.println("Peran = " + binusian.role);
            System.out.println("Tahun Pendaftaran = " + binusian.registrationYear);

            // Memanggil perilaku dari class Binusian
            binusian.masukBinus();
            binusian.absen();
            binusian.keluarBinus();
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
    Selamat datang di Binus!
    Absen berhasil!
    Sampai jumpa! Hati-hati di jalan!

.. note:: 

    Pada saat melakukan inisialisasi atribut pada *class* Binusian di dalam *constructor*, digunakan kata kunci ``this``. Kata kunci ``this`` merupakan refrensi ke *object* tersebut. Apabila tidak menggunakan kata kunci tersebut, kode akan berubah menjadi ``name = name``, yang dapat menimbulkan ambiguitas. Oleh karena itu, kode dibuat menjadi ``this.name = name``, artinya variabel name pada *class* Binusian diubah berdasarkan nilai dari variabel name pada parameter *constructor*.