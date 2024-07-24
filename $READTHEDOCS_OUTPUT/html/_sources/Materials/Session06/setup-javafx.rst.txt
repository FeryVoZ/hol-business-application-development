Setup JavaFX Project in Eclipse
===============================

**Langkah 1**. Siapkan sebuah java project dengam versi java 11 dan pastikan module-info.java dibuat.

.. image:: /Assets/Session06/Setup/Picture1.png
    :width: 300
    :align: center
.. centered:: Java Project dengan module-info.java dan versi Java 11

**Langkah 2**. Membuat class Main dalam package main.

.. image:: /Assets/Session06/Setup/Picture2.png
    :width: 300
    :align: center
.. centered:: Membuat class Main dalam package main.

.. image:: /Assets/Session06/Setup/Picture3.png
    :width: 300
    :align: center
.. centered:: Hasil class Main dalam package main.

**Langkah 3**. Menambahkan JavaFX SDK ke dalam project. Klik kanan project, pilih build path, dan pilih configure build path.

.. image:: /Assets/Session06/Setup/Picture4.png
    :width: 300
    :align: center
.. centered:: Akses konfigurasi build path

**Langkah 4**. Pada tab *Library* dan bagian *Modulepath*, klik *Add Library*

.. image:: /Assets/Session06/Setup/Picture5.png
    :width: 300
    :align: center
.. centered:: Tampilan konfigurasi build path

**Langkah 5**. Pilih *User Library*, pastikan di user library sudah disiapkan library JavaFX. 

.. image:: /Assets/Session06/Setup/Picture6.png
    :width: 300
    :align: center
.. centered:: Tampilan add library

**Langkah 6**. Ceklis library JavaFX yang sudah disiapkan, lalu klik finish. 

.. image:: /Assets/Session06/Setup/Picture7.png
    :width: 300
    :align: center
.. centered:: Add JavaFX from User Library

**Langkah 7**. Setelah berhasil ditambahkan, klik apply and close. 

.. image:: /Assets/Session06/Setup/Picture8.png
    :width: 300
    :align: center
.. centered:: Menyelesaikan konfigurasi add JavaFX.

.. image:: /Assets/Session06/Setup/Picture9.png
    :width: 300
    :align: center
.. centered:: Hasil konfigurasi add JavaFX.

**Langkah 8**. Setelah menambahkan library JavaFX, setup class Main dengan ``extends Application`` dan import *Application* dari library JavaFX. 

.. image:: /Assets/Session06/Setup/Picture10.png
    :width: 300
    :align: center
.. centered:: Extends Application

.. image:: /Assets/Session06/Setup/Picture11.png
    :width: 300
    :align: center
.. centered:: Hasil Extends Application

**Langkah 9**. Hover error yang terjadi dan solve dengan klik *Add 'requires javafx.graphics' to module-info.java*.

.. image:: /Assets/Session06/Setup/Picture12.png
    :width: 300
    :align: center
.. centered:: Add 'requires javafx.graphics

**Langkah 9**. Hover error yang terjadi dan solve dengan klik *Add unimplemented methods*.

.. image:: /Assets/Session06/Setup/Picture13.png
    :width: 300
    :align: center
.. centered:: Add unimplemented methods

**Langkah 10**. Buat komponen dasar halaman JavaFX pada class Main. 

.. image:: /Assets/Session06/Setup/Picture14.png
    :width: 300
    :align: center
.. centered:: Komponen dasar halaman JavaFX.

**Langkah 11**. Pastikan module-info.java sudah lengkap dan membuka semua package yang ingin dijalankan.

.. image:: /Assets/Session06/Setup/Picture15.png
    :width: 300
    :align: center
.. centered:: module-info.java

.. image:: /Assets/Session06/Setup/Result.png
    :width: 300
    :align: center
.. centered:: Hasil halaman JavaFX setelah dijalankan.