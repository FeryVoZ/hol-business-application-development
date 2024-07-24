Insert Data to Database
=======================

Pada sesi ini, kita akan mempelajari, bagaimana cara menyimpan data ke dalam database MySQL. Berikut adalah contoh code untuk menyimpan data ke dalam database MySQL.

Dalam class *DatabaseManager*, tambahkan method *addPersonQuery* untuk menyimpan data ke dalam database.

.. code-block:: java

    public boolean addPersonQuery(Person person) {

        String query = String.format("INSERT INTO msperson (PersonFirstName, PersonLastName, PersonAge) VALUES ('%s', %s, '%d')", person.getFirstName(), person.getLastName(), person.getAge());
        PreparedStatement ps;

        try {
            ps = connect.prepareStatement(query);
            ps.executeUpdate();

        } catch (SQLException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
            return false;
        }
        return true;
    }

Kemudian, pada class *PersonDatabase*, tambahkan method *addPerson* untuk memanggil method *addPersonQuery*.

.. code-block:: java

    public static boolean addPerson(String firstName, String lastName, Integer age) {
        return db_manager.addPersonQuery(new Person(firstName, lastName, age));
    }

Kemudian, pada class *Main*, buat code berikut untuk menambahkan data ke dalam database.

.. code-block:: java

    public static void main(String[] args) {
        // Add a person to the database
        boolean success = PersonDatabase.addPerson("Dodi", "Wibowo", 30);
        
        if (success) {
            System.out.println("Data successfully inserted into the database.");
        } else {
            System.out.println("Failed to insert data into the database.");
        }
    }

Setelah itu, jalankan aplikasi dan cek apakah data sudah berhasil disimpan ke dalam database.