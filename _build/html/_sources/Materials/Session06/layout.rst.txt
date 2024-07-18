Layout
======

Sebelum mempelajari berbagai component yang disediakan oleh JavaFX, mari kita mempelajari fitur layout pada JavaFX terlebih dahulu.
Layout akan membantu kita dalam menyusun node-node component dalam JavaFX. JavaFX menyediakan beberapa layout untuk mengatur posisi kontrol yang dijelaskan sebagai berikut.

BorderPane
----------

BorderPane adalah layout yang membagi ruang menjadi lima bagian: atas, bawah, kiri, kanan, dan tengah. Setiap bagian dapat berisi satu node.

.. image:: /Assets/Session06/Layout/borderpane_layout.png
    :width: 500
    :align: center
    
.. centered::  BorderPane Layout

Berikut adalah contoh simple penggunaan BorderPane dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.BorderPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Membuat Button
            Button btn = new Button("Click Me");

            // Menambahkan Button ke BorderPane
            root.setCenter(btn);

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

GridPane
--------

GridPane adalah layout yang membagi ruang menjadi grid. Setiap node ditempatkan pada baris dan kolom tertentu.

.. image:: /Assets/Session06/Layout/gridpane_layout.png
    :width: 500
    :align: center

.. centered::  GridPane Layout

Berikut adalah contoh simple penggunaan GridPane dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.GridPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat GridPane
            GridPane root = new GridPane();

            // Membuat Button
            Button btn1 = new Button("Button 1");
            Button btn2 = new Button("Button 2");
            Button btn3 = new Button("Button 3");

            // Menambahkan Button ke GridPane
            root.add(btn1, 0, 0);
            root.add(btn2, 1, 0);
            root.add(btn3, 0, 1);

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

FlowPane
--------

FlowPane adalah layout yang menempatkan node secara berurutan dari kiri ke kanan, dan dari atas ke bawah.

.. image:: /Assets/Session06/Layout/flowpane_layout.png
    :width: 500
    :align: center

.. centered::  FlowPane Layout

Berikut adalah contoh simple penggunaan FlowPane dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.FlowPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat FlowPane
            FlowPane root = new FlowPane();

            // Membuat Button
            Button btn1 = new Button("Button 1");
            Button btn2 = new Button("Button 2");
            Button btn3 = new Button("Button 3");

            // Menambahkan Button ke FlowPane
            root.getChildren().addAll(btn1, btn2, btn3);

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

VBox
----

VBox adalah layout yang menempatkan node secara vertikal.

.. image:: /Assets/Session06/Layout/vbox_layout.png
    :width: 500
    :align: center

.. centered:: VBox Layout

Berikut adalah contoh simple penggunaan VBox dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.VBox;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat VBox
            VBox root = new VBox();

            // Membuat Button
            Button btn1 = new Button("Button 1");
            Button btn2 = new Button("Button 2");
            Button btn3 = new Button("Button 3");

            // Menambahkan Button ke VBox
            root.getChildren().addAll(btn1, btn2, btn3);

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

HBox
----

HBox adalah layout yang menempatkan node secara horizontal.

.. image:: /Assets/Session06/Layout/hbox_layout.png
    :width: 500
    :align: center

.. centered:: HBox Layout

Berikut adalah contoh simple penggunaan HBox dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.HBox;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat HBox
            HBox root = new HBox();

            // Membuat Button
            Button btn1 = new Button("Button 1");
            Button btn2 = new Button("Button 2");
            Button btn3 = new Button("Button 3");

            // Menambahkan Button ke HBox
            root.getChildren().addAll(btn1, btn2, btn3);

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