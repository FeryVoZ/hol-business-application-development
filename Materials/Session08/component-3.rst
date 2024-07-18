Component III
=============

Pada sesi ini, kita akan membahas tentang komponen GUI yang lebih kompleks dari sesi sebelumnya. Berikut beberapa komponennya.

TableView
---------

TableView adalah komponen yang digunakan untuk menampilkan data dalam bentuk tabel. TableView membutuhkan data dalam bentuk ObservableList. Berikut adalah contoh penggunaan TableView dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.collections.FXCollections;
    import javafx.collections.ObservableList;
    import javafx.scene.Scene;
    import javafx.scene.control.TableColumn;
    import javafx.scene.control.TableView;
    import javafx.scene.control.cell.PropertyValueFactory;
    import javafx.scene.layout.BorderPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        public class Person {
            private String firstName;
            private String lastName;
            private Integer age;

            public Person(String firstName, String lastName, Integer age) {
                this.firstName = firstName;
                this.lastName = lastName;
                this.age = age;
            }

            public String getFirstName() {
                return firstName;
            }

            public String getLastName() {
                return lastName;
            }

            public Integer getAge() {
                return age;
            }
        }

        @Override
        public void start(Stage primaryStage) {
            // Membuat ObservableList
            ObservableList<Person> items = FXCollections.observableArrayList(
                new Person("Budi", "Sentosa", 30),
                new Person("Riri", "Juwandi", 25),
                new Person("Moli", "Budiman", 35)
            );

            // Membuat TableView
            TableView<Person> tableView = new TableView<>(items);

            // Membuat TableColumn
            TableColumn<Person, String> firstNameColumn = new TableColumn<>("First Name");
            firstNameColumn.setCellValueFactory(new PropertyValueFactory<>("firstName"));

            TableColumn<Person, String> lastNameColumn = new TableColumn<>("Last Name");
            lastNameColumn.setCellValueFactory(new PropertyValueFactory<>("lastName"));

            TableColumn<Person, Integer> ageColumn = new TableColumn<>("Age");
            ageColumn.setCellValueFactory(new PropertyValueFactory<>("age"));

            // Menambahkan TableColumn ke TableView
            tableView.getColumns().addAll(firstNameColumn, lastNameColumn, ageColumn);

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan TableView ke BorderPane
            root.setCenter(tableView);

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

.. image:: /Assets/Session08/Component/tableView.png
    :width: 500
    :align: center

ScrollPane
----------

ScrollPane adalah komponen yang digunakan untuk menampilkan konten yang lebih besar dari area yang ditampilkan. Berikut adalah contoh penggunaan ScrollPane dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Label;
    import javafx.scene.control.ScrollPane;
    import javafx.scene.layout.StackPane;
    import javafx.stage.Stage;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat Label
            Label label = new Label("Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed non risus. Suspendisse lectus tortor, dignissim sit amet, adipiscing nec, ultricies sed, dolor. Cras elementum ultrices diam. Maecenas ligula massa, varius a, semper congue, euismod non, mi. Proin porttitor, orci nec nonummy molestie, enim est eleifend mi, non fermentum diam nisl sit amet erat. Duis semper. Duis arcu massa, scelerisque vitae, consequat in, pretium a, enim. Pellentesque congue. Ut in risus volutpat libero pharetra tempor. Cras vestibulum bibendum augue. Praesent egestas leo in pede. Praesent blandit odio eu enim. Pellentesque sed dui ut augue blandit sodales. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aliquam nibh. Mauris ac mauris sed pede pellentesque fermentum. Maecenas adipiscing ante non diam sodales hendrerit.");

            // Membuat ScrollPane
            ScrollPane scrollPane = new ScrollPane();
            scrollPane.setContent(label);

            // Membuat BorderPane
            BorderPane root = new BorderPane();

            // Menambahkan ScrollPane ke BorderPane
            root.setCenter(scrollPane);

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

.. image:: /Assets/Session08/Component/scrollPane.png
    :width: 500
    :align: center

File Chooser
------------

File Chooser adalah komponen yang digunakan untuk memilih file dari sistem operasi. Berikut adalah contoh penggunaan File Chooser dalam JavaFX.

.. code-block:: java

    import javafx.application.Application;
    import javafx.stage.FileChooser;
    import javafx.stage.Stage;

    import java.io.File;

    public class Main extends Application {

        @Override
        public void start(Stage primaryStage) {
            // Membuat FileChooser
            FileChooser fileChooser = new FileChooser();

            // Menampilkan dialog FileChooser
            File file = fileChooser.showOpenDialog(primaryStage);

            if (file != null) {
                System.out.println(file.getAbsolutePath());
            }
        }

        public static void main(String[] args) {
            launch(args);
        }

    }

Saat code dijalankan, maka akan muncul dialog untuk memilih file.

.. image:: /Assets/Session08/Component/fileChooser.png
    :width: 500
    :align: center