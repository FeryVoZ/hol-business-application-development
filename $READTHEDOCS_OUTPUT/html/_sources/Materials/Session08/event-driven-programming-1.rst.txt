Event Driven Programming I
===========================

Pada sesi ini kita akan membahas tentang Event Driven Programming. 
Event Driven Programming adalah sebuah logika pemrograman yang berfokus pada perubahan status, tindakan, atau kejadian yang terjadi pada sebuah objek. 
Dalam logika ini, sebuah objek akan menunggu hingga sebuah event terjadi, kemudian objek tersebut akan melakukan aksi yang sesuai dengan event yang terjadi.

Dalam JavaFX terdapat 3 cara dalam melakukan Event Driven Programming, yaitu:

1. Menggunakan Anonymous Inner Class
2. Menggunakan Lambda Expression
3. Menggunakan EventHandler

Anonymous Inner Class
----------------------

Anonymous Inner Class adalah sebuah class yang tidak memiliki nama dan hanya digunakan sekali.

Berikut adalah contoh penggunaan Anonymous Inner Class dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat Button
            Button button = new Button("Click Me");

            // Menambahkan event handler ke button menggunakan Anonymous Inner Class
            button.setOnAction(new EventHandler<ActionEvent>() {
                @Override
                public void handle(ActionEvent event) {
                    button.setStyle("-fx-background-color: #87CEFA");
                }
            });

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan Button ke BorderPane
            root.setCenter(button);

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

Lambda Expression
------------------

Lambda Expression adalah sebuah fitur yang diperkenalkan pada Java 8 yang memungkinkan kita untuk menulis kode yang lebih ringkas dan mudah dibaca.

Berikut adalah contoh penggunaan Lambda Expression dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat Button
            Button button = new Button("Click Me");

            // Menambahkan event handler ke button menggunakan Lambda Expression
            button.setOnAction(event -> {
                button.setStyle("-fx-background-color: #87CEFA");
            });

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan Button ke BorderPane
            root.setCenter(button);

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

EventHandler
------------

EventHandler adalah sebuah interface yang digunakan untuk menangani event. 

Berikut adalah contoh penggunaan EventHandler dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat Button
            Button button = new Button("Click Me");

            // Membuat EventHandler
            EventHandler<ActionEvent> eventHandler = new EventHandler<ActionEvent>() {
                @Override
                public void handle(ActionEvent event) {
                    button.setStyle("-fx-background-color: #87CEFA");
                }
            };

            // Menambahkan event handler ke button
            button.setOnAction(eventHandler);

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan Button ke BorderPane
            root.setCenter(button);

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

Semua code di atas akan menghasilkan hasil yang sama, yaitu ketika button di klik maka button akan berubah warna menjadi biru muda. 
Berikut adalah hasil dari contoh di atas.

.. image:: /Assets/Session08/clickedButton.png
    :width: 300
    :align: center