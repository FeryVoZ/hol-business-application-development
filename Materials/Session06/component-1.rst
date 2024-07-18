Component I
===========

Setelah mempelajari leyout pada JavaFX. Sekarang kita akan mempelajari berbagai komponen yang disediakan oleh JavaFX. Komponen ini akan membantu kita dalam membuat aplikasi GUI yang lebih interaktif dan menarik.

Label
-----

Label adalah komponen yang digunakan untuk menampilkan teks statis. Label tidak dapat diubah oleh pengguna. Berikut adalah contoh penggunaan Label dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Label;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat Label
            Label label = new Label("Hello, World!");

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan Label ke BorderPane
            root.setCenter(label);

            // Membuat Scene
            Scene scene = new Scene(root, 300, 250);

            // Menambahkan Scene ke Stage
            primaryStage.setScene(scene);

            // Menampilkan Stage
            primaryStage.show();
        }

        public static void main(String[] args) {
            launch(args);
        }
    }

Berikut hasil dari contoh di atas.

.. image:: /Assets/Session06/Component/label.png
    :width: 500
    :align: center

TextField
---------

TextField adalah komponen yang digunakan untuk memasukkan teks. Berikut adalah contoh penggunaan TextField dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.TextField;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat TextField
            TextField textField = new TextField();

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan TextField ke BorderPane
            root.setCenter(textField);

            // Membuat Scene
            Scene scene = new Scene(root, 300, 250);

            // Menambahkan Scene ke Stage
            primaryStage.setScene(scene)

            // Menampilkan Stage
            primaryStage.show();
        }

        public static void main(String[] args) {
            launch(args);
        }

    }

Berikut hasil dari contoh di atas.

.. image:: /Assets/Session06/Component/textField.png
    :width: 500
    :align: center

PasswordField
----------------

PasswordField adalah komponen yang digunakan untuk memasukkan teks yang bersifat rahasia. Berikut adalah contoh penggunaan PasswordField dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.PasswordField;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat PasswordField
            PasswordField passwordField = new PasswordField();

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan PasswordField ke BorderPane
            root.setCenter(passwordField);

            // Membuat Scene
            Scene scene = new Scene(root, 300, 250);

            // Menambahkan Scene ke Stage
            primaryStage.setScene(scene);
            
            // Menampilkan Stage
            primaryStage.show();

        }

        public static void main(String[] args) {
            launch(args);
        }

    }

Berikut hasil dari contoh di atas.

.. image:: /Assets/Session06/Component/passwordField.png
    :width: 500
    :align: center