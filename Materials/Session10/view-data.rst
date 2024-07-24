View Data from Database
=======================

Pada sesi ini, kita akan mempelajari bagaimana cara menampilkan data dari database MySQL ke dalam aplikasi Java. Berikut adalah contoh code untuk menampilkan data dari database MySQL.

Dalam class *DatabaseManager*, tambahkan method *getAllPersonQuery* untuk mengambil data dari database.

.. code-block:: java

    public ArrayList<Person> getAllPersonQuery(){

        ArrayList<Person> personList = new ArrayList<>();;

        String query = "SELECT * FROM msperson";
        PreparedStatement ps;
        ResultSet res = null;

        try {
            ps = connect.prepareStatement(query);
            res = ps.executeQuery();

            while(res.next()) {
                personList.add(new Person(res.getString(2), res.getString(3), res.getInt(4)));
            }

        } catch (SQLException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }

        return personList;
    }

Kemudian, pada class *PersonDatabase*, tambahkan method *getAllPerson* untuk memanggil method *getAllPersonQuery*.

.. code-block:: java

    public static ArrayList<Person> getAllPerson() {
        return db_manager.getAllPersonQuery();
    }

Kemudian, pada class *Main*, buat code berikut untuk menampilkan data dari database.

.. code-block:: java

    public static void main(String[] args) {
        // Get all person from the database
        ArrayList<Person> personList = PersonDatabase.getAllPerson();

        for (Person person : personList) {
            System.out.println("First Name: " + person.getFirstName());
            System.out.println("Last Name: " + person.getLastName());
            System.out.println("Age: " + person.getAge());
            System.out.println();
        }
    }

Setelah itu, jalankan aplikasi dan cek apakah data sudah berhasil ditampilkan ke dalam aplikasi.