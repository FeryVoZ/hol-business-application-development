Implementation
==============

Setelah mempelajari beberapa component tambahan pada JavaFX dan juga JFXtras, sekarang kita akan mencoba melakukan implementasi dari component dan jfxtras tersebut.

.. note:: 

    Bentuk implementasi code dari JavaFX dapat berbeda-beda tergantung dari kebutuhan aplikasi yang dibuat dan juga gaya penulisan code yang digunakan.
    Berikut ini, merupakan salah satu contoh implementasi dari component dan jfxtras, jika kalian menemukan cara implementasi yang berbeda, kalian dapat mencoba dan mempelajarinya untuk menentukan mana yang nyaman untuk kalian gunakan.

.. code-block:: java

    package main;

    import javafx.application.Application;
    import javafx.collections.FXCollections;
    import javafx.collections.ObservableList;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.control.CheckBox;
    import javafx.scene.control.ComboBox;
    import javafx.scene.control.Label;
    import javafx.scene.control.ListView;
    import javafx.scene.control.Menu;
    import javafx.scene.control.MenuBar;
    import javafx.scene.control.MenuItem;
    import javafx.scene.control.PasswordField;
    import javafx.scene.control.RadioButton;
    import javafx.scene.control.Spinner;
    import javafx.scene.control.TextArea;
    import javafx.scene.control.TextField;
    import javafx.scene.control.ToggleGroup;
    import javafx.scene.layout.BorderPane;
    import javafx.scene.layout.FlowPane;
    import javafx.scene.layout.GridPane;
    import javafx.stage.Stage;
    import jfxtras.labs.scene.control.window.Window;

    public class Main extends Application{

        // Deklarasi semua component yang akan digunakan
    	Scene scene;
    	BorderPane bp;
    	GridPane gp;
    	FlowPane fp, fp2;
    
    	Label titlelbl, usernamelbl, passwordlbl, genderlbl, addresslbl,countrylbl, agelbl;
    	TextField usernameField;
    	PasswordField passField;
    	RadioButton maleRadio, femaleRadio;
    	ToggleGroup genderToggle;
    	TextArea addressField;
    	ComboBox<String> countryBox;
    	CheckBox checkBox;
    	Spinner<Integer> ageSpinner;
    	Window window;
    	ListView<String> listView;
    	Button registerButton;
    
        // Inisialisasi semua component
    	public void init() {
    		bp = new BorderPane();
    		scene = new Scene(bp, 800, 500);
    		usernameField = new TextField();
    		passField = new PasswordField();
    		maleRadio = new RadioButton("Male");
    		femaleRadio = new RadioButton("Female");
    		genderToggle = new ToggleGroup();
    		addressField = new TextArea();
    		checkBox = new CheckBox("I agrre with terms of services");
    		ageSpinner = new Spinner<>(21, 60, 21);
    		countryBox = new ComboBox<>();
    		titlelbl = new Label("Regiter Page");
    		usernamelbl = new Label("Username");
    		passwordlbl = new Label("Password");
    		genderlbl = new Label("Gender");
    		addresslbl = new Label("Address");
    		countrylbl = new Label("Country");
    		agelbl = new Label("Age");
    
    		gp = new GridPane();
    		fp = new FlowPane();
    		fp2 = new FlowPane();
    		registerButton = new Button("Register");
    
    		window = new Window("Internal Window");
    		window.setMaxHeight(500);
    		window.setMinHeight(200);
    
    		listView = new ListView<>();
    	}
    
        // Inisialisasi dan layouting form
    	public void initializeForm() {
    		maleRadio.setToggleGroup(genderToggle);
    		femaleRadio.setToggleGroup(genderToggle);
    
    		countryBox.getItems().add("Indonesia");
    		countryBox.getItems().add("Singapore");
    		countryBox.getItems().add("Malaysia");
    		countryBox.getSelectionModel().selectFirst();
    
    		gp.add(titlelbl, 1, 0);
    
    		gp.add(usernamelbl, 0, 1);
    		gp.add(usernameField, 1, 1);
    
    		gp.add(passwordlbl, 0, 2);
    		gp.add(passField, 1, 2);
    
    		fp.getChildren().add(maleRadio);
    		fp.getChildren().add(femaleRadio);
    		gp.add(genderlbl, 0, 3);
    		gp.add(fp, 1, 3);
    
    		gp.add(addresslbl, 0, 4);
    		gp.add(addressField, 1, 4);
    
    		gp.add(agelbl, 0, 5);
    		gp.add(ageSpinner, 1, 5);
    
    		gp.add(countrylbl, 0, 6);
    		gp.add(countryBox, 1, 6);
    
    		gp.add(checkBox, 0, 7);
    
    		checkBox.setMinWidth(200);
    	}
    
        // Inisialisasi dan konfigurasi ListView
    	public void initializeListView() {
    		ObservableList<String> announcements = FXCollections.observableArrayList();
    		announcements.add("Announcement 1");
    		announcements.add("Announcement 2");
    		announcements.add("Announcement 3");
    		announcements.add("Announcement 4");
    		listView.setItems(announcements);
    		window.getContentPane().getChildren().add(listView);
    	}

        // Inisialisasi dan layouting stage
    	public void initializeStage() {
    		bp.setCenter(gp);
    		bp.setBottom(registerButton);
    		bp.setRight(window);
    	}
    
    	@Override
    	public void start(Stage PrimaryStage) throws Exception{
    		init();
    		initializeForm();		
    		initializeStage();
    		initializeListView();
    		PrimaryStage.setScene(scene);
    		PrimaryStage.show();
    	}
    
    	public static void main(String[] args) {
    		launch(args);
    	}

    }

.. note:: 

    Saat ingin menjalankan code di atas, pastikan semua library yang dibutuhkan sudah diimport dengan baik dan benar. Pastikan juga module-info.java sudah diatur dengan benar.

Berikut hasil dari contoh di atas.

.. image:: /Assets/Session07/implementation.png
    :width: 500
    :align: center