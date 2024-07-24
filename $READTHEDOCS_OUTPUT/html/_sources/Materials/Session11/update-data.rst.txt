Update Data in Database
=======================

Pada sesi ini, kita akan mempelajari, bagaimana cara mengupdate data di dalam database MySQL. Berikut adalah contoh code untuk mengupdate data di dalam database MySQL.

Dalam class *DatabaseManager*, tambahkan method *updatePersonQuery* untuk mengupdate data di dalam database.

.. code-block:: java

    public boolean updatePersonQuery(String first, String last,Integer newAge) {

        String query = String.format("UPDATE msperson SET PersonAge = %d WHERE PersonFirstName = '%s' AND PersonLastName = '%s'", newAge, first, last);
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

Kemudian, pada class *PersonDatabase*, tambahkan method *updatePerson* untuk memanggil method *updatePersonQuery*.

.. code-block:: java

    public static boolean updatePerson(String firstName, String lastName, Integer newAge) {
        return db_manager.updatePersonQuery(firstName, lastName, newAge);
    }

Kemudian, pada class *Main*, buat code berikut untuk mengupdate data di dalam database.

.. code-block:: java

    public static void main(String[] args) {
        // Update a person in the database
        boolean success = PersonDatabase.updatePerson("Dodi", "Wibowo", 31);
        
        if (success) {
            System.out.println("Data successfully updated in the database.");
        } else {
            System.out.println("Failed to update data in the database.");
        }
    }

Setelah itu, jalankan aplikasi dan cek apakah data sudah berhasil diupdate di dalam database.