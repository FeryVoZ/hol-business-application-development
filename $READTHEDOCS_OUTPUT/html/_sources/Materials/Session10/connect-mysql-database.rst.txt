Introduction to MySQL Database & Connect to MySQL Database
==========================================================

MySQL adalah sistem manajemen basis data relasional (RDBMS) open-source yang menggunakan bahasa SQL (Structured Query Language). 
MySQL adalah salah satu RDBMS paling populer di dunia dan banyak digunakan oleh berbagai aplikasi web dan bisnis.
Pada sesi kali ini, kita akan belajar bagaimana cara menghubungkan aplikasi Java dengan database MySQL.

Untuk menyambungkan aplikasi Java dengan database MySQL,, kita perlu menggunakan JDBC (Java Database Connectivity). JDBC adalah API Java yang digunakan untuk mengakses dan memanipulasi data dari database.

Berikut adalah template JDBC yang bisa digunakan untuk menyambungkan aplikasi Java dengan database MySQL.

.. code-block:: java

    import java.sql.DriverManager;
    import java.sql.PreparedStatement;
    import java.sql.ResultSet;
    import java.sql.SQLException;
    import java.util.ArrayList;

    public class DatabaseManager {
    	private String username;
        private String password;
        private String dbName;
        private String host;
        private Integer port;

        private Connection connect;

        private static DatabaseManager contextDatabase;

        private DatabaseManager(String username, String password, String host, String dbName, Integer port) {

            this.username = username;
            this.password = password;
            this.dbName = dbName;
            this.host = host;
            this.port = port;
            connection();
        }

        public static DatabaseManager getConnection(String username, String password, String host, String dbName, Integer port) {

            if(contextDatabase == null) {
                contextDatabase = new DatabaseManager(username, password, host, dbName, port);
            }

            return contextDatabase;
        }

        public void connection() {

            String payload = "jdbc:mysql://" + this.host + "/" + this.dbName + "?user=" +
                    this.username + "&password=" + this.password;

            try {
                connect = DriverManager.getConnection(payload);
                System.out.println("Connected!");
            } catch (SQLException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            }

        }
    }

Pada kode di atas, kita membuat class DatabaseManager yang berfungsi untuk menyambungkan aplikasi Java dengan database MySQL.

Dari template JDBC tersebut, kita buat class *PersonDatabase* yang berfungsi untuk menyambungkan dan mengakses data dari tabel *msperson* pada database MySQL.

.. code-block:: java

    package database;

    public class PersonDatabase {
    	static String dbUsername = "root";
        static String dbPassword = "";
        static String dbHost = "localhost:3306";
        static String dbName = "hol_bad";
        static Integer dbPort = 3306;

        static DatabaseManager db_manager = DatabaseManager.getConnection(dbUsername, dbPassword, dbHost, dbName, dbPort);
    }

Pada kondisi ini, kita sudah berhasil menyambungkan aplikasi Java dengan database MySQL. Selanjutnya, kita akan belajar bagaimana cara mengakses data dari tabel *msperson* pada database MySQL.
