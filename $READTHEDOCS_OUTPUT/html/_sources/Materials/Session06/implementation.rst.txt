Implementation
==============

Setelah mengerti layout dan beberapa jenis component yang disediakan JavaFX, kita akan mencoba melakukan implementasi dari layout dan component tersebut.

.. note:: 

    Bentuk implementasi code dari JavaFX dapat berbeda-beda tergantung dari kebutuhan aplikasi yang dibuat dan juga gaya penulisan code yang digunakan.
    Berikut ini, merupakan salah satu contoh implementasi dari layout dan component, jika kalian menemukan cara implementasi yang berbeda, kalian dapat mencoba dan mempelajarinya untuk menentukan mana yang nyaman untuk kalian gunakan.

.. code-block:: java

    package main;

    import javafx.application.Application;
    import javafx.geometry.Insets;
    import javafx.geometry.Orientation;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.control.CheckBox;
    import javafx.scene.control.ComboBox;
    import javafx.scene.control.DatePicker;
    import javafx.scene.control.Label;
    import javafx.scene.control.PasswordField;
    import javafx.scene.control.RadioButton;
    import javafx.scene.control.TextArea;
    import javafx.scene.control.TextField;
    import javafx.scene.control.ToggleButton;
    import javafx.scene.control.ToggleGroup;
    import javafx.scene.layout.BorderPane;
    import javafx.scene.layout.FlowPane;
    import javafx.scene.layout.GridPane;
    import javafx.scene.layout.HBox;
    import javafx.scene.layout.VBox;
    import javafx.stage.Stage;

    public class Main extends Application{

        // Deklarasi semua component yang akan digunakan
    	Scene scene;
    	BorderPane bp;
    	GridPane gp;
    	FlowPane fp;
    
    	VBox vb1, vb2, vb3;
    	HBox hb1, hb2;
    
    	Label about, contact, newsLetter, subs, report;
    	Label titleLbl, nameLbl, emailLbl, passLbl, genderLbl, countryLbl, dobLbl;
    
    	TextField nameTF, emailTF;
    	PasswordField passPF;
    	RadioButton maleTB, femaleTB;
    	ToggleGroup genderGroup;
    	ComboBox<String> countryCB;
    	CheckBox tnc;
    	DatePicker dobDP;
    	TextArea reportTA;
    
    	Button submitBtn, cancelBtn;
    
        // Initialize semua component
    	public void initialize() {
    
    		vb1 = new VBox();
    		vb2 = new VBox();
    		vb3 = new VBox();
    		hb1 = new HBox();
    		hb2 = new HBox();
    
    		contact = new Label("Contact");
    		about = new Label("About");
    		newsLetter = new Label("News Letter");
    		subs = new Label("Subscribe");
    		report = new Label("Report here if you found any problem with the app!");
    
    		reportTA = new TextArea();
    		reportTA.setWrapText(true);
    		reportTA.setMaxSize(200, 150);
    
    		titleLbl = new Label("Register Page");
    		nameLbl = new Label("Name: ");
    		emailLbl = new Label("Email: ");
    		passLbl = new Label("Password: ");
    		genderLbl = new Label("Gender: ");
    		countryLbl = new Label("Country: ");
    		dobLbl = new Label("Date of Birth: ");
    
    		nameTF = new TextField();
    		nameTF.setPromptText("Input Name");
    
    		emailTF = new TextField();
    		emailTF.setPromptText("Input Email");
    
    		passPF = new PasswordField();
    		passPF.setPromptText("Input Password");
    
    		maleTB = new RadioButton("Male");
    		femaleTB = new RadioButton("Female");
    		genderGroup = new ToggleGroup();
    
    		countryCB = new ComboBox<>();
    		countryCB.getItems().addAll("Indonesia", "Malaysia", "Singapore");
    		countryCB.setPromptText("Select a Country..");
    
    		tnc = new CheckBox("Aggred to terms and contidions");
    		dobDP = new DatePicker();
    
    		submitBtn = new Button("Submit");
    		cancelBtn = new Button("Cancel");
    
    		fp = new FlowPane();
    		gp = new GridPane();
    		bp = new BorderPane();
    		scene = new Scene(bp, 600,600);
    	}
    
        // Layout semua component
    	public void layout() {
    
    		hb1.getChildren().addAll(submitBtn, cancelBtn);
    		hb1.setSpacing(10);
    		hb2.getChildren().addAll(maleTB, femaleTB);
    		hb2.setSpacing(10);
    		vb1.getChildren().addAll(about, contact);
    		vb2.getChildren().addAll(newsLetter, subs);
    		vb3.getChildren().addAll(report, reportTA);
    
    		maleTB.setToggleGroup(genderGroup);
    		femaleTB.setToggleGroup(genderGroup);
    
    		fp.getChildren().addAll(vb1, vb2, vb3);
    		fp.setHgap(10);
    
    		gp.add(titleLbl, 0, 0);
    		gp.setColumnSpan(titleLbl, 2);
    		gp.add(nameLbl, 0, 1);
    		gp.add(nameTF, 1, 1);
    		gp.add(emailLbl, 0, 2);
    		gp.add(emailTF, 1, 2);
    		gp.add(passLbl, 0, 3);
    		gp.add(passPF, 1, 3);
    		gp.add(genderLbl, 0, 4);
    		gp.add(hb2, 1, 4);
    		gp.add(countryLbl, 0, 5);
    		gp.add(countryCB, 1, 5);
    		gp.add(dobLbl, 0, 6);
    		gp.add(dobDP, 1, 6);
    		gp.add(tnc, 1, 7);
    		gp.add(hb1, 1, 8);
    
    		gp.setVgap(10);
    		gp.setHgap(10);
    
    		bp.setPadding(new Insets(20));
    		bp.setCenter(gp);
    		bp.setBottom(fp);
    
    	}
    
    	public static void main(String[] start) {
    		// TODO Auto-generated method stub
    		launch(start);
    	}

    	@Override
    	public void start(Stage primaryStage) throws Exception {
    		initialize();
    		layout();
    		primaryStage.setTitle("Session 6");
    		primaryStage.setResizable(false);
    		primaryStage.setScene(scene);
    		primaryStage.show();
    	}

    }

.. note:: 

    Saat ingin menjalankan code di atas, pastikan semua library yang dibutuhkan sudah diimport dengan baik dan benar. Pastikan juga module-info.java sudah diatur dengan benar.

.. image:: /Assets/Session06/implementation-result.png
    :width: 500
    :align: center

.. centered:: Hasil Implementasi

.. note:: 

    Sebagaian component yang belum dipelajari disesi ini, akan dibahas disesi selanjutnya.