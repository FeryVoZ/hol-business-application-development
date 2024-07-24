Change Page 
===========

Pada saat membuat aplikasi menggunakan JavaFX, kita seringkali ingin mengganti halaman yang sedang ditampilkan. Hal ini bisa dilakukan dengan menggunakan `Scene` dan `Stage`.
Berikut adalah contoh sederhana untuk mengganti halaman pada JavaFX.

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
    		new PageA(primaryStage);
    	}

    }

.. code-block:: java

    package pages;

    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.VBox;
    import javafx.stage.Stage;

    public class PageA {
        private Stage primaryStage;

        public PageA(Stage primaryStage) {
            this.primaryStage = primaryStage;
            initView();
        }

        private void initView() {
            Button goToPageBButton = new Button("Go to Page B");
            goToPageBButton.setOnAction(e -> {
                PageB pageB = new PageB(primaryStage);
            });

            VBox root = new VBox(goToPageBButton);
            Scene scene = new Scene(root, 300, 200);
            primaryStage.setScene(scene);
            primaryStage.show();
        }
    }

.. code-block:: java

    package pages;

    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.VBox;
    import javafx.stage.Stage;

    public class PageB {
        private Stage primaryStage;

        public PageB(Stage primaryStage) {
            this.primaryStage = primaryStage;
            initView();
        }

        private void initView() {
            Button goToPageAButton = new Button("Go to Page A");
            goToPageAButton.setOnAction(e -> {
                PageA pageA = new PageA(primaryStage);
            });

            VBox root = new VBox(goToPageAButton);
            Scene scene = new Scene(root, 300, 200);
            primaryStage.setScene(scene);
            primaryStage.show();
        }
    }

Pada contoh di atas, kita membuat dua buah class yaitu `Page A` dan `Page B`. Ketika tombol pada `Page A` ditekan, maka aplikasi akan menampilkan `Page B` dan sebaliknya.