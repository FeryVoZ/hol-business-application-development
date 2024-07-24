Delete Data from Database
=========================

Pada sesi ini, kita akan mempelajari, bagaimana cara menghapus data di dalam database MySQL. Berikut adalah contoh code untuk menghapus data di dalam database MySQL.

.. code-block:: java

    public boolean deletePersonQuery(String first, String last) {

        String query = String.format("DELETE FROM msperson WHERE PersonFirstName = '%s' AND PersonLastName = '%s'", first, last);
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

Kemudian, pada class *PersonDatabase*, tambahkan method *deletePerson* untuk memanggil method *deletePersonQuery*.

.. code-block:: java

    public static boolean deletePerson(String firstName, String lastName) {
        return db_manager.deletePersonQuery(firstName, lastName);
    }

Kemudian, pada class *Main*, buat code berikut untuk menghapus data di dalam database.

.. code-block:: java

    public static void main(String[] args) {
        // Delete a person in the database
        boolean success = PersonDatabase.deletePerson("Dodi", "Wibowo");
        
        if (success) {
            System.out.println("Data successfully deleted in the database.");
        } else {
            System.out.println("Failed to delete data in the database.");
        }
    }

Setelah itu, jalankan aplikasi dan cek apakah data sudah berhasil dihapus di dalam database.