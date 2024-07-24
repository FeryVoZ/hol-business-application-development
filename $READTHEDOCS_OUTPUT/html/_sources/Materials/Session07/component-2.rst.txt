Component II 
============

Setelah mempelajari beberapa component dasar pada JavaFX, sekarang kita akan mempelajari beberapa komponen lain yang lebih lebih kompleks di dalam JavaFX.

TextArea
--------

TextArea adalah komponen yang digunakan untuk memasukkan teks dalam jumlah yang lebih banyak. Berikut adalah contoh penggunaan TextArea dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.TextArea;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat TextArea
            TextArea textArea = new TextArea();

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan TextArea ke BorderPane
            root.setCenter(textArea);

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

.. image:: /Assets/Session07/Component/textArea.png
    :width: 500
    :align: center

RadioButton dan ToggleGroup
----------------------------

RadioButton adalah komponen yang digunakan untuk memilih satu opsi dari beberapa opsi yang ada. RadioButton harus dikelompokkan dalam satu ToggleGroup agar hanya satu RadioButton yang dapat dipilih. Berikut adalah contoh penggunaan RadioButton dan ToggleGroup dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.RadioButton;
    import javafx.scene.control.ToggleGroup;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat RadioButton
            RadioButton maleButton = new RadioButton("Male");
            RadioButton femaleButton = new RadioButton("Female");

            // Membuat ToggleGroup
            ToggleGroup genderGroup = new ToggleGroup();

            // Menambahkan RadioButton ke ToggleGroup
            maleButton.setToggleGroup(genderGroup);
            femaleButton.setToggleGroup(genderGroup);

            // Membuat HBox
            HBox hbox = new HBox();

            // Menambahkan RadioButton ke HBox
            hbox.getChildren().addAll(maleButton, femaleButton);

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan hbox ke BorderPane
            root.setCenter(hbox);

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

.. image:: /Assets/Session07/Component/radioButton.png
    :width: 200
    :align: center

CheckBox
--------

CheckBox adalah komponen yang digunakan untuk memilih satu atau lebih opsi dari beberapa opsi yang ada. Berikut adalah contoh penggunaan CheckBox dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.CheckBox;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat CheckBox
            CheckBox checkBox = new CheckBox("I Agree");

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan CheckBox ke BorderPane
            root.setCenter(checkBox);

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

.. image:: /Assets/Session07/Component/checkBoxUnchecked.png
    :width: 500
    :align: center

.. image:: /Assets/Session07/Component/checkBoxChecked.png
    :width: 500
    :align: center

ComboBox
--------

ComboBox adalah komponen yang digunakan untuk memilih satu opsi dari beberapa opsi yang ada. Berikut adalah contoh penggunaan ComboBox dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.ComboBox;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat ComboBox
            ComboBox<String> comboBox = new ComboBox<>();

            // Menambahkan item ke ComboBox
            comboBox.getItems().addAll("Option 1", "Option 2", "Option 3");
            comboBox.setPromptText("Select an option");

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan ComboBox ke BorderPane
            root.setCenter(comboBox);

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

.. image:: /Assets/Session07/Component/comboBox.png
    :width: 500
    :align: center

Spinner
-------

Spinner adalah komponen yang digunakan untuk memilih satu nilai dari beberapa nilai yang ada. Berikut adalah contoh penggunaan Spinner dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Spinner;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat Spinner dengan nilai awal 5, nilai minimum 0, dan nilai maksimum 10
            Spinner<Integer> spinner = new Spinner<>(0, 10, 5);

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan Spinner ke BorderPane
            root.setCenter(spinner);

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

.. image:: /Assets/Session07/Component/spinner.png
    :width: 500
    :align: center

ListView
--------

ListView adalah komponen yang digunakan untuk menampilkan daftar item dalam bentuk list. Berikut adalah contoh penggunaan ListView dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.collections.FXCollections;
    import javafx.collections.ObservableList;
    import javafx.scene.Scene;
    import javafx.scene.control.ListView;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat ObservableList
            ObservableList<String> items = FXCollections.observableArrayList(
                "Item 1",
                "Item 2",
                "Item 3"
            );

            // Membuat ListView
            ListView<String> listView = new ListView<>(items);

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan ListView ke BorderPane
            root.setCenter(listView);

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

    ObservableList adalah list yang dapat di-observe. Artinya, jika terjadi perubahan pada list, maka list akan memberitahu semua yang meng-observe list tersebut.
    Untuk mengisi listView dengan data, kita harus membuat ObservableList terlebih dahulu. ObservableList dapat diisi dengan menggunakan FXCollections.observableArrayList().

Berikut hasil dari contoh di atas.

.. image:: /Assets/Session07/Component/listView.png
    :width: 500
    :align: center