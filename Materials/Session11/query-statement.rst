Statement vs Prepared Statement
===============================

Dalam melakukan query database pada Java, terdapat dua cara yang umum digunakan, yaitu menggunakan *Statement* dan *Prepared Statement*. Berikut adalah perbedaan antara *Statement* dan *Prepared Statement*.
Keduanya memiliki perbedaan dalam hal keamanan, performa, dan fleksibilitas.

1. **Keamanan**
    *Prepared Statement* lebih aman daripada *Statement*. Hal ini dikarenakan *Prepared Statement* menggunakan *placeholder* untuk parameter yang akan di-*set*, sehingga mencegah *SQL Injection*. Sedangkan *Statement* tidak menggunakan *placeholder*, sehingga rentan terhadap *SQL Injection*.

2. **Performa**
    *Prepared Statement* lebih cepat daripada *Statement*. Hal ini dikarenakan *Prepared Statement* hanya melakukan *compile* sekali saja, sedangkan *Statement* melakukan *compile* setiap kali query dijalankan.

3. **Fleksibilitas**
    *Statement* lebih fleksibel daripada *Prepared Statement*. Hal ini dikarenakan *Statement* dapat menjalankan query yang dinamis, sedangkan *Prepared Statement* hanya dapat menjalankan query yang statis.

Berikut ini adalah contoh penggunaan *Statement* dan *Prepared Statement*.

1. **Statement**
   
   .. code-block:: java

       public boolean addPersonStatement(String first, String last, Integer age) {
   
           String query = String.format("INSERT INTO msperson (PersonFirstName, PersonLastName, PersonAge) VALUES ('%s', '%s', %d)", first, last, age);
           Statement st;
   
           try {
               st = connect.createStatement();
               st.executeUpdate(query);
   
           } catch (SQLException e) {
               // TODO Auto-generated catch block
               e.printStackTrace();
               return false;
           }
           return true;
       }

2. **Prepared Statement**

    .. code-block:: java
    
         public boolean addPersonPreparedStatement(String first, String last, Integer age) {
    
              String query = "INSERT INTO msperson (PersonFirstName, PersonLastName, PersonAge) VALUES (?, ?, ?)";
              PreparedStatement ps;
    
              try {
                ps = connect.prepareStatement(query);
                ps.setString(1, first);
                ps.setString(2, last);
                ps.setInt(3, age);
                ps.executeUpdate();
    
              } catch (SQLException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
                return false;
              }
              return true;
         }

Dari contoh di atas, kita dapat melihat perbedaan antara *Statement* dan *Prepared Statement*. Pada *Statement*, kita langsung menuliskan query SQL pada method *executeUpdate*, sedangkan pada *Prepared Statement*, kita menggunakan *?* sebagai *placeholder* untuk parameter yang akan di-*set* pada method *setString* dan *setInt*.
Prepared Statement lebih disarankan untuk digunakan karena lebih aman dan performa yang lebih baik daripada Statement.