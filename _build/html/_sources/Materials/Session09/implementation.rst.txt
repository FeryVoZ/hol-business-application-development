Implementation
==============

Berikut ada implementasi dari event driven programming dan pergantian halaman pada JavaFX.

.. note:: 

    Bentuk implementasi code dari JavaFX dapat berbeda-beda tergantung dari kebutuhan aplikasi yang dibuat dan juga gaya penulisan code yang digunakan.
    Berikut ini, merupakan salah satu contoh implementasi dari component dan jfxtras, jika kalian menemukan cara implementasi yang berbeda, kalian dapat mencoba dan mempelajarinya untuk menentukan mana yang nyaman untuk kalian gunakan.

.. code-block:: java

    package main;

    import javafx.application.Application;
    import javafx.stage.Stage;
    import pages.LoginPage;

    public class Main extends Application{

    	public static void main(String[] args) {
    		launch(args);
    	}

    	@Override
    	public void start(Stage primaryStage) throws Exception {
    		// TODO Auto-generated method stub
    		new LoginPage(primaryStage);
    	}

    }

.. code-block:: java

	package pages;

	import javafx.scene.Scene;
	import javafx.scene.control.Alert;
	import javafx.scene.control.Button;
	import javafx.scene.control.ComboBox;
	import javafx.scene.control.Label;
	import javafx.scene.control.PasswordField;
	import javafx.scene.control.Spinner;
	import javafx.scene.control.TextField;
	import javafx.scene.layout.BorderPane;
	import javafx.scene.layout.GridPane;
	import javafx.stage.Stage;

	public class LoginPage {

		Stage loginStage;
		Scene loginScene;

		BorderPane bp;
		GridPane gp;

		Label emailLbl, passLbl, ageLbl, countryLbl, statusLbl;

		TextField emailTF;
		PasswordField passPF;
		Spinner<Integer> ageSpinner;
		ComboBox<String> countryBox;

		Button loginButton;

		public void intialize() {
			emailLbl = new Label("Email: ");
			passLbl = new Label("Password: ");
			ageLbl = new Label("Age: ");
			countryLbl = new Label("Country: ");
			statusLbl = new Label();

			emailTF = new TextField();
			emailTF.setPromptText("Must ends with @gmail.com");
			passPF = new PasswordField();
			passPF.setPromptText("Must have minimum 8 characters");
			ageSpinner = new Spinner<>(17, 80, 17);
			countryBox = new ComboBox<>();

			loginButton = new Button("Login");

			gp = new GridPane();
			bp = new BorderPane();
		}

		public void layout() {
			countryBox.getItems().add("Indonesia");
			countryBox.getItems().add("Singapore");
			countryBox.getItems().add("Malaysia");

			gp.add(emailLbl, 0, 0);
			gp.add(emailTF, 1, 0);
			gp.add(passLbl, 0, 1);
			gp.add(passPF, 1, 1);
			gp.add(ageLbl, 0, 2);
			gp.add(ageSpinner, 1, 2);
			gp.add(countryLbl, 0, 3);
			gp.add(countryBox, 1, 3);
			gp.add(loginButton, 0, 4);
			gp.add(statusLbl, 0, 5);

			bp.setCenter(gp);
			loginScene = new Scene(bp, 600, 600);
		}

		public void loginAction() {
			loginButton.setOnMouseClicked( e -> {
				Alert alert = new Alert(Alert.AlertType.ERROR);
				String email = emailTF.getText();
				String pass = passPF.getText();
				String ctr = countryBox.getValue();

				if(!email.endsWith("@gmail.com")) {
					alert.setTitle("Error");
					alert.setContentText("Email must ends with @gmail.com!");
					alert.show();
				}
				else if(pass.length()<8) {
					alert.setTitle("Error");
					alert.setContentText("Password must have minimum 8 characters!");
					alert.show();
				}
				else {
					loginStage.close();
					new MouseEventPage(loginStage);
				}
			});
		}

		public LoginPage(Stage loginStage) {
			this.loginStage = loginStage;

			intialize();
			layout();
			loginAction();

			loginStage.setScene(loginScene);
			loginStage.show();
		}

	}

Tampilan login page

.. image:: /Assets/Session09/loginPage.png
	:width: 500
	:align: center


.. code-block:: java

	package pages;

	import javafx.event.EventHandler;
	import javafx.scene.Scene;
	import javafx.scene.control.Button;
	import javafx.scene.control.Label;
	import javafx.scene.control.Menu;
	import javafx.scene.control.MenuBar;
	import javafx.scene.control.MenuItem;
	import javafx.scene.input.MouseEvent;
	import javafx.scene.layout.BorderPane;
	import javafx.stage.Stage;

	public class MouseEventPage implements EventHandler<MouseEvent>{
		Stage mouseEventStage;
		Button button = new Button("Make event to me!");
		BorderPane bp = new BorderPane();
		Scene mouseScene = new Scene(bp, 600, 600);

		MenuBar menuBar = new MenuBar();
		Menu menu = new Menu();
		MenuItem mouseEventBtn = new MenuItem("Mouse Event Page");
		MenuItem keyboardEventBtn = new MenuItem("Keyboard Event Page");
		MenuItem itemEventBtn = new MenuItem("Item Event Page");

		public MouseEventPage(Stage mouseEventStage) {
			this.mouseEventStage = mouseEventStage;

			bp.setTop(menuBar);
			menuBar.getMenus().add(menu);
			menu.setText("Pages");
			menu.getItems().add(mouseEventBtn);
			menu.getItems().add(keyboardEventBtn);
			menu.getItems().add(itemEventBtn);
			bp.setCenter(button);

			setMouseEvent();

			keyboardEventBtn.setOnAction(e->{
				mouseEventStage.close();
				new KeyboardEventPage(mouseEventStage);
			});

			itemEventBtn.setOnAction(e->{
				mouseEventStage.close();
				new ItemEventPage(mouseEventStage);
			});

			mouseEventStage.setScene(mouseScene);
			mouseEventStage.show();
		}

		public void setMouseEvent() {
			button.setOnMouseEntered(
					event -> {
						button.setStyle("-fx-background-color: #87CEFA");
					});

			button.setOnMouseExited(this);
			button.setOnMousePressed(this);
			button.setOnMouseReleased(this);

		}

		@Override
		public void handle(MouseEvent event) {
			switch (event.getEventType().getName()) {
			case "MOUSE_EXITED":
				button.setStyle("-fx-background-color: #FFFFFF");
				break;
			case "MOUSE_PRESSED":
				button.setStyle("-fx-background-color: #FF0000");
				break;
			case "MOUSE_RELEASED":
				button.setStyle("-fx-background-color: #008000");
				break;
			}

		}
	}

Tampilan mouse event page

.. image:: /Assets/Session09/mousePage.png
	:width: 500
	:align: center


.. code block:: java

	package pages;

	import javafx.event.EventHandler;
	import javafx.scene.Scene;
	import javafx.scene.control.Button;
	import javafx.scene.control.Menu;
	import javafx.scene.control.MenuBar;
	import javafx.scene.control.MenuItem;
	import javafx.scene.control.TextField;
	import javafx.scene.input.KeyCode;
	import javafx.scene.input.KeyEvent;
	import javafx.scene.layout.BorderPane;
	import javafx.stage.Stage;

	public class KeyboardEventPage {
		Stage keyboardEventStage;
		TextField textField = new TextField();
		BorderPane bp = new BorderPane();
		Scene keyboardScene = new Scene(bp, 600, 600);

		MenuBar menuBar = new MenuBar();
		Menu menu = new Menu();
		MenuItem mouseEventBtn = new MenuItem("Mouse Event Page");
		MenuItem keyboardEventBtn = new MenuItem("Keyboard Event Page");
		MenuItem itemEventBtn = new MenuItem("Item Event Page");

		public KeyboardEventPage(Stage keyboardEventStage) {
			this.keyboardEventStage = keyboardEventStage;

			bp.setTop(menuBar);
			menuBar.getMenus().add(menu);
			menu.setText("Pages");
			menu.getItems().add(mouseEventBtn);
			menu.getItems().add(keyboardEventBtn);
			menu.getItems().add(itemEventBtn);
			bp.setCenter(textField);

			setKeyEvent();

			mouseEventBtn.setOnAction(e->{
				keyboardEventStage.close();
				new MouseEventPage(keyboardEventStage);
			});

			itemEventBtn.setOnAction(e->{
				keyboardEventStage.close();
				new ItemEventPage(keyboardEventStage);
			});

			keyboardEventStage.setScene(keyboardScene);
			keyboardEventStage.show();
		}

		public void setKeyEvent() {
			textField.setOnKeyPressed(new EventHandler<KeyEvent>() {

				@Override
				public void handle(KeyEvent event) {

					if(event.getCode().equals(KeyCode.SPACE)) {
						System.out.println("Space Pressed");
					}

				}

			});

			textField.setOnKeyReleased(new EventHandler<KeyEvent>() {

				@Override
				public void handle(KeyEvent event) {

					if(event.getCode().equals(KeyCode.SPACE)) {
						System.out.println("Space Released");
					}

				}

			});
		}
	}

Tampilan keyboard event page

.. image:: /Assets/Session09/keyboardPage.png
	:width: 500
	:align: center


.. code block:: java

	package pages;

	import javafx.beans.value.ChangeListener;
	import javafx.beans.value.ObservableValue;
	import javafx.scene.Scene;
	import javafx.scene.control.ComboBox;
	import javafx.scene.control.Menu;
	import javafx.scene.control.MenuBar;
	import javafx.scene.control.MenuItem;
	import javafx.scene.layout.BorderPane;
	import javafx.stage.Stage;

	public class ItemEventPage {
		Stage itemEventStage;
		ComboBox<String> box = new ComboBox<String>();
		BorderPane bp = new BorderPane();
		Scene itemScene = new Scene(bp, 600, 600);

		MenuBar menuBar = new MenuBar();
		Menu menu = new Menu();
		MenuItem mouseEventBtn = new MenuItem("Mouse Event Page");
		MenuItem keyboardEventBtn = new MenuItem("Keyboard Event Page");
		MenuItem itemEventBtn = new MenuItem("Item Event Page");

		public ItemEventPage(Stage itemEventStage) {
			this.itemEventStage = itemEventStage;

			box = new ComboBox<>();
			box.getItems().add("Item1");
			box.getItems().add("Item2");
			box.getItems().add("Item3");
			box.getItems().add("Item4");
			box.getSelectionModel().selectFirst();

			bp.setTop(menuBar);
			menuBar.getMenus().add(menu);
			menu.setText("Pages");
			menu.getItems().add(mouseEventBtn);
			menu.getItems().add(keyboardEventBtn);
			menu.getItems().add(itemEventBtn);
			bp.setCenter(box);

			setItemEvent();

			keyboardEventBtn.setOnAction(e->{
				itemEventStage.close();
				new KeyboardEventPage(itemEventStage);
			});

			mouseEventBtn.setOnAction(e->{
				itemEventStage.close();
				new MouseEventPage(itemEventStage);
			});

			itemEventStage.setScene(itemScene);
			itemEventStage.show();
		}

		public void setItemEvent() {
			box.valueProperty().addListener(new ChangeListener<String>() {

				@Override
				public void changed(ObservableValue<? extends String> arg0, String arg1, String arg2) {
					// TODO Auto-generated method stub
					System.out.println(arg0);
					System.out.println(arg1);
					System.out.println(arg2);
				}

			});
		}
	}

Tampilan item event page

.. image:: /Assets/Session09/itemPage.png
	:width: 500
	:align: center


.. note:: 

    Saat ingin menjalankan code di atas, pastikan semua library yang dibutuhkan sudah diimport dengan baik dan benar. Pastikan juga module-info.java sudah diatur dengan benar.