JFXtras 
=======

JFXtras adalah library tambahan yang dapat digunakan untuk memperkaya tampilan aplikasi JavaFX. JFXtras menyediakan berbagai komponen tambahan yang tidak disediakan oleh JavaFX, salah satunya kita dapat membuat new window dengan menggunakan JFXtras.

Berikut adalah contoh penggunaan JFXtras dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;
    import jfxtras.styles.jmetro.JMetro;
    import jfxtras.styles.jmetro.Style;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat Button
            Button button = new Button("Click Me");

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Membuat window dengan judul "Window Title"
            Window window = new Window("Window Title");

            // Menambahkan Button ke window
            window.getContentPane().getChildren().add(button);

            // Menambahkan window ke BorderPane
            root.setCenter(window);

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

.. note:: 

    Untuk menjalankan kode di atas, pastikan Anda sudah menambahkan library *JFXtras* ke dalam project Anda. 
    Cara menambahkan library JFXtras ke dalam project sama seperti menambahkan library *JavaFX*, bedanya hanya siapkan library *JFXtras* yang sudah diunduh pada *User Library*. 
    Kemudian tambahkan library JFXtras tersebut ke dalam project Anda dari *User Library*.

Berikut hasil dari contoh di atas.

.. image:: /Assets/Session07/jfxtras.png
    :width: 500
    :align: center