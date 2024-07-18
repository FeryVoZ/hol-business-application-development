Event Driven Programming II
===========================

Setelah mempelajari berbagai cara dalam melakukan event driven programming, kita akan mempelajari apa saja jenis-jenis event yang ada dalam JavaFX. 
Pada sesi ini, kita akan mempelajari beberapa jenis event yang sering digunakan dalam JavaFX, yaitu:

Mouse Listener
---------------

Mouse listener adalah event yang terjadi ketika pengguna melakukan interaksi dengan mouse. Beberapa contoh event yang sering digunakan dalam mouse listener sebagai berikut.

-   Mouse Clicked -> event yang terjadi ketika pengguna melakukan klik pada mouse.
-   Mouse Entered -> event yang terjadi ketika mouse masuk ke dalam area node.
-   Mouse Exited -> event yang terjadi ketika mouse keluar dari area node.
-   Mouse Pressed -> event yang terjadi ketika pengguna menekan tombol mouse.
-   Mouse Released -> event yang terjadi ketika pengguna melepas tombol mouse.

Berikut contoh simple code untuk mouse listener.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.ComboBox;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {

            // Membuat combo box
            ComboBox<String> comboBox = new ComboBox<>();
            comboBox.getItems().addAll("Option 1", "Option 2", "Option 3");

            // Menambahkan event item selected pada combo box
            comboBox.setOnAction(e -> {
                String selectedOption = comboBox.getValue();
                System.out.println("Selected Option: " + selectedOption);
            });

            // Membuat StackPane
            StackPane root = new StackPane();

            // Menambahkan combo box ke StackPane
            root.getChildren().add(comboBox);

            // Membuat scene
            Scene scene = new Scene(root, 300, 250);

            primaryStage.setTitle("Item Event Listener");
            primaryStage.setScene(scene);
            primaryStage.show();
        }

        public static void main(String[] args) {
            launch(args);
        }
    }
