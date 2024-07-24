Implementation
==============

Setelah mengerti cara melakukan insert dan view database pada Java, kita akan mencoba melakukan implementasi dari kedua method tersebut.

.. note:: 

    Bentuk implementasi code dari JavaFX dapat berbeda-beda tergantung dari kebutuhan aplikasi yang dibuat dan juga gaya penulisan code yang digunakan.
    Berikut ini, merupakan salah satu contoh implementasi dari component dan jfxtras, jika kalian menemukan cara implementasi yang berbeda, kalian dapat mencoba dan mempelajarinya untuk menentukan mana yang nyaman untuk kalian gunakan.

Berikut adalah contoh implementasinya.

.. code-block:: java

    package model;

    public class Person {
    
    	private String firstName;
    	private String lastName;
    	private Integer age;
    
    	public Person(String firstName, String lastName, Integer age) {
    		super();
    		this.firstName = firstName;
    		this.lastName = lastName;
    		this.age = age;
    	}
    
    	public String getFirstName() {
    		return firstName;
    	}
    
    	public void setFirstName(String firstName) {
    		this.firstName = firstName;
    	}
    
    	public String getLastName() {
    		return lastName;
    	}
    
    	public void setLastName(String lastName) {
    		this.lastName = lastName;
    	}
    
    	public Integer getAge() {
    		return age;
    	}
    
    	public void setAge(Integer age) {
    		this.age = age;
    	}
    
    }

.. code-block:: java

    package database;

    import java.sql.Connection;
    import java.sql.DriverManager;
    import java.sql.PreparedStatement;
    import java.sql.ResultSet;
    import java.sql.SQLException;
    import java.util.ArrayList;

    import model.Person;

    public class DatabaseManager {
    	private String username;
        private String password;
        private String dbName;
        private String host;
        private Integer port;

        private Connection connect;

        private static DatabaseManager contextDatabase;

        private DatabaseManager(String username, String password, String host, String dbName, Integer port) {

            this.username = username;
            this.password = password;
            this.dbName = dbName;
            this.host = host;
            this.port = port;
            connection();
        }

        public static DatabaseManager getConnection(String username, String password, String host, String dbName, Integer port) {

            if(contextDatabase == null) {
                contextDatabase = new DatabaseManager(username, password, host, dbName, port);
            }

            return contextDatabase;
        }

        public void connection() {

            String payload = "jdbc:mysql://" + this.host + "/" + this.dbName + "?user=" +
                    this.username + "&password=" + this.password;

            try {
                connect = DriverManager.getConnection(payload);
                System.out.println("Connected!");
            } catch (SQLException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            }

        }

        public boolean addPersonQuery(Person person) {

            String query = String.format("INSERT INTO msperson (PersonFirstName, PersonLastName, PersonAge) VALUES ('%s', %s, '%d')", person.getFirstName(), person.getLastName(), person.getAge());
            PreparedStatement ps;

            try {
                ps = connect.prepareStatement(query);
                ps.executeUpdate();

            } catch (SQLException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
                return false;
            }
            return true;
        }

        public ArrayList<Person> getAllPersonQuery(){

            ArrayList<Person> personList = new ArrayList<>();;

            String query = "SELECT * FROM msperson";
            PreparedStatement ps;
            ResultSet res = null;

            try {
                ps = connect.prepareStatement(query);
                res = ps.executeQuery();

                while(res.next()) {
                    personList.add(new Person(res.getString(2), res.getString(3), res.getInt(4)));
                }

            } catch (SQLException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            }

            return personList;
        }
    }

.. code-block:: java

    package database;
    import java.util.ArrayList;

    import model.Person;

    public class PersonDatabase {
    	static String dbUsername = "root";
        static String dbPassword = "";
        static String dbHost = "localhost:3306";
        static String dbName = "hol_bad";
        static Integer dbPort = 3306;

        static DatabaseManager db_manager = DatabaseManager.getConnection(dbUsername, dbPassword, dbHost, dbName, dbPort);


        public static boolean addPerson(String firstName, String lastName, Integer age) {
            return db_manager.addPersonQuery(new Person(firstName, lastName, age));
        }

        public static ArrayList<Person> getAllPerson() {
            return db_manager.getAllPersonQuery();
        }
    }

.. code-block:: java

    package main;

    import javafx.application.Application;
    import javafx.stage.Stage;
    import pages.InsertPage;

    public class Main extends Application{

    	public static void main(String[] args) {
    		launch(args);
    	}

    	@Override
    	public void start(Stage primaryStage) throws Exception {
    		new InsertPage(primaryStage);
    	}

    }

.. code-block:: java

    package pages;

    import database.PersonDatabase;
    import javafx.geometry.Insets;
    import javafx.geometry.Pos;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.control.Label;
    import javafx.scene.control.Menu;
    import javafx.scene.control.MenuBar;
    import javafx.scene.control.MenuItem;
    import javafx.scene.control.TextField;
    import javafx.scene.layout.BorderPane;
    import javafx.scene.layout.GridPane;
    import javafx.stage.Stage;

    public class InsertPage {

    	Stage insertStage;
    	Scene insertScene;
    
    	BorderPane bp;
    	GridPane gp;
    
    	MenuBar menuBar;
    	Menu menu;
    	MenuItem insertBtn;
    	MenuItem viewBtn;
    
    	Label firstNameLabel,lastNameLabel, ageLabel;
    	Button insertButton;
    	TextField firstNameField, lastNameField, ageField;
    
    	public void initialize() {
    
    		firstNameLabel = new Label("First Name:");
            firstNameField = new TextField();

            lastNameLabel = new Label("Last Name:");
            lastNameField = new TextField();

            ageLabel = new Label("Age:");
            ageField = new TextField();

            insertButton = new Button("Insert");

            menuBar = new MenuBar();
        	menu = new Menu();
        	insertBtn = new MenuItem("Insert Page");
        	viewBtn = new MenuItem("View Page");
    
    		gp = new GridPane();
    
    		bp = new  BorderPane();
    		insertScene = new Scene(bp, 400, 300);
    
    	}
    
    	public void layouting() {
    		menuBar.getMenus().add(menu);
    		menu.setText("Pages");
    		menu.getItems().add(insertBtn);
    		menu.getItems().add(viewBtn);
    
    		gp.setPadding(new Insets(20));
    		gp.setHgap(10);
    		gp.setVgap(10);
    		gp.setAlignment(Pos.CENTER);

            // Add labels and text fields to grid pane
    		gp.add(firstNameLabel, 0, 0);
    		gp.add(firstNameField, 1, 0);
    		gp.add(lastNameLabel, 0, 1);
    		gp.add(lastNameField, 1, 1);
    		gp.add(ageLabel, 0, 2);
    		gp.add(ageField, 1, 2);
    		gp.add(insertButton, 1, 3);
    
    		bp.setTop(menuBar);
    		bp.setCenter(gp);
    	}
    
    	void action() {
    		insertButton.setOnAction(e -> insertPerson());
    		viewBtn.setOnAction(e->{
    			insertStage.close();
    			new ViewPage(insertStage);
    		});
    	}
    
    	void insertPerson() {
            String firstName = firstNameField.getText();
            String lastName = lastNameField.getText();
            int age = Integer.parseInt(ageField.getText());

            boolean success = PersonDatabase.addPerson(firstName, lastName, age);

            if (success) {
                System.out.println("Person inserted successfully!");
            } else {
                System.out.println("Failed to insert person.");
            }

            // Clear text fields
            firstNameField.clear();
            lastNameField.clear();
            ageField.clear();
        }
    
    	public InsertPage(Stage insertStage) {
    		this.insertStage = insertStage;
    
    		initialize();
    		layouting();
    		action();
    
    		insertStage.setScene(insertScene);
    		insertStage.show();
    	}
    
    }

Hasil dan tampilan insert page sebagai berikut.

.. image:: /Assets/Session10/insertPage.png
    :width: 500
    :align: center

.. code-block:: java

    package pages;

    import java.util.ArrayList;

    import database.PersonDatabase;
    import javafx.collections.FXCollections;
    import javafx.collections.ObservableList;
    import javafx.geometry.Insets;
    import javafx.geometry.Pos;
    import javafx.scene.control.cell.PropertyValueFactory;
    import javafx.scene.Scene;
    import javafx.scene.control.Menu;
    import javafx.scene.control.MenuBar;
    import javafx.scene.control.MenuItem;
    import javafx.scene.control.TableColumn;
    import javafx.scene.control.TableView;
    import javafx.scene.layout.BorderPane;
    import javafx.scene.layout.GridPane;
    import javafx.stage.Stage;
    import model.Person;

    public class ViewPage {

    	Stage viewStage;
    	Scene viewScene;
    
    	BorderPane bp;
    
    	MenuBar menuBar;
    	Menu menu;
    	MenuItem insertBtn;
    	MenuItem viewBtn;
    
    	TableColumn<Person, String> firstNameColumn;
    	TableColumn<Person, String> lastNameColumn;
    	TableColumn<Person, Integer> ageColumn;
    
    	ObservableList<Person> tableItems;
    	TableView<Person> tableView;
    
    	public void initialize() {
    		ArrayList<Person> personList = PersonDatabase.getAllPerson();
    
    		tableItems = FXCollections.observableArrayList(
                    personList
                );
    
    		firstNameColumn = new TableColumn<>("First Name");
            firstNameColumn.setCellValueFactory(new PropertyValueFactory<>("firstName"));

            lastNameColumn = new TableColumn<>("Last Name");
            lastNameColumn.setCellValueFactory(new PropertyValueFactory<>("lastName"));

            ageColumn = new TableColumn<>("Age");
            ageColumn.setCellValueFactory(new PropertyValueFactory<>("age"));

            tableView = new TableView<>(tableItems);
            tableView.getColumns().addAll(firstNameColumn, lastNameColumn, ageColumn);
    
    		menuBar = new MenuBar();
        	menu = new Menu();
        	insertBtn = new MenuItem("Insert Page");
        	viewBtn = new MenuItem("View Page");
    
    		bp = new  BorderPane();
    		viewScene = new Scene(bp, 400, 300);
    	}
    
    	public void layouting() {
    		menuBar.getMenus().add(menu);
    		menu.setText("Pages");
    		menu.getItems().add(insertBtn);
    		menu.getItems().add(viewBtn);
    
    		bp.setTop(menuBar);
    		bp.setCenter(tableView);
    	}
    
    	public void action() {
    		insertBtn.setOnAction(e->{
    			viewStage.close();
    			new InsertPage(viewStage);
    		});
    	}
    
    	public ViewPage(Stage viewStage) {
    		this.viewStage = viewStage;
    
    		initialize();
    		layouting();
    		action();
    
    		viewStage.setScene(viewScene);
    		viewStage.show();
    	}
    
    }

Hasil dan tampilan view page sebagai berikut.

.. image:: /Assets/Session10/viewPage.png
    :width: 500
    :align: center

.. note:: 

    Saat ingin menjalankan code di atas, pastikan semua library yang dibutuhkan sudah diimport dengan baik dan benar. Pastikan juga module-info.java sudah diatur dengan benar.