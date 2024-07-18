Form Validation dan Alert
=========================

Sama seperti form di apliksi lainnya, form yang dibuat menggunakan JavaFX juga memerlukan validasi agar data yang dimasukkan oleh pengguna sesuai dengan yang diharapkan. Selain itu, kita juga perlu memberikan feedback kepada pengguna jika terjadi kesalahan saat pengisian form. 
Feedback ini biasanya berupa pesan peringatan yang dapat dibuat dengan menggunakan *alert* yang disediakan oleh JavaFX.

Berikut adalah contoh simple form validation dalam JavaFX yang sering digunakan, beserta penggunaan *alert* untuk memberikan feedback kepada pengguna.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Alert;
    import javafx.scene.control.Alert.AlertType;
    import javafx.scene.control.Button;
    import javafx.scene.control.Label;
    import javafx.scene.control.TextField;
    import javafx.scene.layout.VBox;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat TextField
            TextField textField = new TextField();

            // Membuat Label
            Label label = new Label("Enter your name:");

            // Membuat Button
            Button button = new Button("Submit");

            // Menambahkan aksi pada Button
            button.setOnAction(e -> {

                // Cara mengambil value dari textField
                // textField.getText()

                // Validasi TextField
                if (textField.getText().isEmpty()) {
                    // Menampilkan alert jika TextField kosong
                    Alert alert = new Alert(AlertType.ERROR);
                    alert.setTitle("Error");
                    alert.setHeaderText(null);
                    alert.setContentText("Please enter your name!");
                    alert.showAndWait();
                } else {
                    // Menampilkan alert jika TextField tidak kosong
                    Alert alert = new Alert(AlertType.INFORMATION);
                    alert.setTitle("Information");
                    alert.setHeaderText(null);
                    alert.setContentText("Hello, " + textField.getText() + "!");
                    alert.showAndWait();
                }
            });

            // Membuat VBox
            VBox root = new VBox();
            root.getChildren().addAll(label, textField, button);

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

.. image:: /Assets/Session08/errorAlert.png
    :width: 500
    :align: center

.. centered:: Kondisi validasi salah

.. image:: /Assets/Session08/informationAlert.png
    :width: 500
    :align: center

.. centered:: Kondisi validasi benar