Implementation
==============

Setelah mempelajari form validation dan event handling pada JavaFX, berikut adalah contoh implementasi dari form validation dan event handling dalam JavaFX.

.. note:: 

    Bentuk implementasi code dari JavaFX dapat berbeda-beda tergantung dari kebutuhan aplikasi yang dibuat dan juga gaya penulisan code yang digunakan.
    Berikut ini, merupakan salah satu contoh implementasi dari component dan jfxtras, jika kalian menemukan cara implementasi yang berbeda, kalian dapat mencoba dan mempelajarinya untuk menentukan mana yang nyaman untuk kalian gunakan.

.. code-block:: java

    import javafx.application.Application;
    import javafx.geometry.Insets;
    import javafx.scene.Scene;
    import javafx.scene.control.*;
    import javafx.scene.layout.GridPane;
    import javafx.stage.Stage;

    public class RegistrationForm extends Application {

        // Method alphanumeric validation
        private boolean isAlphanumeric(String str) {
            if (str == null || str.isEmpty()) {
                return false;
            }
            for (char c : str.toCharArray()) {
                if (!Character.isLetterOrDigit(c)) {
                    return false;
                }
            }
            return true;
        }

        @Override
        public void start(Stage primaryStage) {
            primaryStage.setTitle("Registration Form");

            GridPane gridPane = new GridPane();
            gridPane.setPadding(new Insets(20));
            gridPane.setHgap(10);
            gridPane.setVgap(10);

            // Email field
            Label emailLabel = new Label("Email:");
            TextField emailField = new TextField();
            gridPane.add(emailLabel, 0, 0);
            gridPane.add(emailField, 1, 0);

            // Username field
            Label usernameLabel = new Label("Username:");
            TextField usernameField = new TextField();
            gridPane.add(usernameLabel, 0, 1);
            gridPane.add(usernameField, 1, 1);

            // Password field
            Label passwordLabel = new Label("Password:");
            PasswordField passwordField = new PasswordField();
            gridPane.add(passwordLabel, 0, 2);
            gridPane.add(passwordField, 1, 2);

            // Confirm password field
            Label confirmPasswordLabel = new Label("Confirm Password:");
            PasswordField confirmPasswordField = new PasswordField();
            gridPane.add(confirmPasswordLabel, 0, 3);
            gridPane.add(confirmPasswordField, 1, 3);

            // Age spinner
            Label ageLabel = new Label("Age:");
            Spinner<Integer> ageSpinner = new Spinner<>(17, 100, 17);
            gridPane.add(ageLabel, 0, 4);
            gridPane.add(ageSpinner, 1, 4);

            // Aggrement Check Box
            CheckBox agreementCheckBox = new CheckBox("I agree with the terms and conditions");
            gridPane.add(agreementCheckBox, 1, 5);

            // Register button
            Button registerButton = new Button("Register");
            registerButton.setOnAction(e -> {
                if (!emailField.getText().endsWith("@gmail.com")) {
                    showAlert(Alert.AlertType.ERROR, "Invalid Email", "Email must end with '@gmail.com'");
                } else if (usernameField.getText().length() < 4) {
                    showAlert(Alert.AlertType.ERROR, "Invalid Username", "Username must have at least 4 characters");
                } else if (!isAlphanumeric(passwordField.getText())) {
                    showAlert(Alert.AlertType.ERROR, "Invalid Password", "Password must be alphanumeric");
                } else if (!passwordField.getText().equals(confirmPasswordField.getText())) {
                    showAlert(Alert.AlertType.ERROR, "Invalid Confirm Password", "Confirm password does not match");
                } else if (!agreementCheckBox.isSelected()) {
                    showAlert(Alert.AlertType.ERROR, "Agreement Required", "You must agree with the terms and conditions");
                } else {
                    showAlert(Alert.AlertType.INFORMATION, "Registration Success", "Registration successful!");
                }
            });
            gridPane.add(registerButton, 1, 6);

            Scene scene = new Scene(gridPane, 400, 300);
            primaryStage.setScene(scene);
            primaryStage.show();
        }

        private void showAlert(Alert.AlertType alertType, String title, String message) {
            Alert alert = new Alert(alertType);
            alert.setTitle(title);
            alert.setHeaderText(null);
            alert.setContentText(message);
            alert.showAndWait();
        }

        public static void main(String[] args) {
            launch(args);
        }
    }

.. note:: 

    Saat ingin menjalankan code di atas, pastikan semua library yang dibutuhkan sudah diimport dengan baik dan benar. Pastikan juga module-info.java sudah diatur dengan benar.

Pada contoh di atas, kita membuat sebuah form registrasi sederhana yang terdiri dari beberapa field, yaitu email, username, password, confirm password, age, dan agreement. Kemudian kita menambahkan validasi pada setiap field tersebut. Jika terjadi kesalahan saat pengisian form, maka akan muncul *alert* yang memberikan feedback kepada pengguna.

Berikut adalah hasil dari contoh di atas.

.. image:: /Assets/Session08/registerFailed.png
    :width: 500
    :align: center

.. centered:: Alert Registration Failed

.. image:: /Assets/Session08/registerSuccess.png
    :width: 500
    :align: center

.. centered:: Alert Registration Success