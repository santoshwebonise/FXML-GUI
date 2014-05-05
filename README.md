FXML-GUI
========

FXML is XML based markup language for creating Desktop Application user interface. With the help of FXML we can create rich GUI for a Desktop Application/Web based Desktop Apps.

1. What is FXML?
================

FXML is an XML-based language that provides the structure for building a user interface separate from the application logic of your code for Desktop Application / Web based Desktop application.

FXML does not have a schema, but it does have a basic predefined structure. What you can express in FXML, and how it applies to constructing a scene graph, depends on the API of the objects you are constructing.

Because FXML maps directly to Java, you can use the API documentation to understand what elements and attributes are allowed.

While you can use FXML to create any user interface, FXML is particularly useful for user interfaces that have large, complex scene graphs, forms, data entry, or complex animation. FXML is also well-suited for defining static layouts such as forms, controls, and tables. In addition, you can use FXML to construct dynamic layouts by including scripts.

2. Why Use FXML?
================

Earlier we used java swing for the desktop application (standalone application) but that is not that much rich in gui and many more drawback so to overcome all these things Java introduce JavaFX with FXML with lots of new feature and rich GUI.

In swing we need to design each and every component in java code format not in XML format so there is no separation of UI and Java code logic, both mixed in a same place.

Now in JavaFx they separate java logic code and GUI.

From a Model View Controller (MVC) perspective, 

- The FXML file that contains the description of the user interface is the view.
- The controller is a Java class, optionally implementing theInitializable class, which is declared as the controller for the FXML file.
- The model consists of domain objects, defined on the Java side, that you connect to the view through the controller. 

2.1. Simple Example of FXML
---------------------------

  The easiest way to show the advantages of FXML is with an example. Take a look at Figure 1-1, which shows a user interface that includes a border pane layout that has a top and center region, each of which contains a label.

  
  ![alt tag](https://raw.githubusercontent.com/santoshwebonise/FXML-GUI/master/images/borderpane_simple_example.png)
  Figure 1-1 Border Pane Simple Example
  
  First, look at how the user interface is constructed and built directly in the source code, as shown in Example 1-1.
	  
	  Example 1-1 Java Code for a User Interface
	  
	  BorderPane border = new BorderPane();
	  Label toppanetext = new Label("Page Title");
	  border.setTop(toppanetext);
	  Label centerpanetext = new Label ("Some data here");
	  border.setCenter(centerpanetext);
  
Next, look at Example 1-2, which shows the same user interface, but in FXML markup. You can see the hierarchical structure of the user interface, which in turn makes it easier to add components and build upon the user interface.

    Example 1-2 FXML Markup for a User Interface
	 <BorderPane>
		<top>
			<Label text="Page Title"/>
		</top>
		<center>
			<Label text="Some data here"/>
		</center>
	 </BorderPane>
  


  




