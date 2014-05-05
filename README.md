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
	 
3. Benefits of FXML
===================

In addition to providing web developers a familiar approach to designing user interfaces, FXML offers these benefits:

- Because the scene graph is more transparent in FXML, it is easy for a development team to create and maintain a testable user interface.
- FXML is not a compiled language; you do not need to recompile the code to see the changes. just run and see. 
- You can use FXML with any Java Virtual Machine (JVM) language, such as Java, Scala, or Clojure.
- FXML is not limited to the view portion of the MVC interface. You can construct services or tasks or domain objects, and you can use JavaScript or other scripting languages in FXML. For an example of using JavaScript.
- Use a Scripting Language to Handle Events in the FXML tutorial of the Getting Started guide, go for this link : http://docs.oracle.com/javafx/2/get_started/fxml_tutorial.htm#JFXGS213
- The content of an FXML file can be localized as the file is read. For example, if an FXML file is loaded using the en_US locale, then it produces the string "First Name" for a label based on the following resource string:
	<Label text="%firstName"/>
  If the locale is changed to fr_FR and the FXML file is reloaded, then the label shows "Prénom."
  The same is not true for Java code, because you must manually update the content of every element of your user interface by obtaining a reference to it and calling the appropriate setter (such as setText()).

- for more : http://docs.oracle.com/javafx/2/swing/overview.htm

4. Components of FXML
=====================

Here we are having a huge amount of component but we will talk about few ones as follows,

- HBox : As name says Horizontal Box, so It contains all element in horizontal manner.
		
		eg  : <HBox spacing="10" alignment="bottom_right" styleClass=”style.css”>
				// content reside here in horizontal
			  </HBox>

- VBox : As name says Vertical Box, so it contains all elements in vertical manner.
		
		eg  : <VBox spacing="10" alignment="bottom_right" styleClass=”style.css”>
				// content reside here
			  </VBox>
- Label : For text writing purpose
		
		eg	: <Label fx:id= “myWord” text=”Hello world”  />

- Button :
		
		eg	: 
			<Button fx:id= “myAction” text="My Button"/>

- TableView :
		
		eg	: 
		
		<TableView fx:id="tableView" GridPane.columnIndex="0" GridPane.rowIndex="1">
			 <columns>
				<TableColumn text="First Name">
				</TableColumn>
				<TableColumn text="Last Name">
				</TableColumn>
				<TableColumn text="Email Address">
				</TableColumn>
			</columns>    
		 </TableView>

- Image : For refering an image from FXML end
		
		<ImageView>
			<image>
				<fx:reference source="myImage"/>
			</image>
		</ImageView>
	
- And many more approximate same as HTML tags.
	
5. FXML CSS
===========

JavaFX Cascading Style Sheets (CSS) is based on the W3C CSS version 2.1 with some additions from current work on version 3.

The goal for JavaFX CSS is to allow web developers already familiar with CSS for HTML to use CSS to customize and develop themes for JavaFX controls and scene graph objects in a natural way.

This enables the mixing of CSS styles for JavaFX and for other purposes (such as for HTML pages) into a single style sheet. To this end, all JavaFX property names have been prefixed with a vendor extension of "-fx-". Even properties that might seem to be compatible with standard HTML CSS have been prefixed, because JavaFX has somewhat different semantics for their values.

JavaFX CSS does not support CSS layout properties such as float, position, overflow, and width. 
However, the CSS padding and margins properties are supported on some JavaFX scene graph objects.

All other aspects of layout are handled programmatically in JavaFX code. In addition, CSS support for HTML-specific elements such as Tables are not supported since there is no equivalent construct in JavaFX.

	eg : 
		.button {
			-fx-background-color: #000;
			-fx-text-fill: #fff;
			-fx-font-family: arial;
			-fx-font-weight: bold;
		}

5.1. CSS Limitations :
----------------------

While the JavaFX CSS parser will parse valid CSS syntax, it is not a fully compliant CSS parser.

- @-keyword statements are ignored.
- The ":first-child" and ":lang" pseudo-classes are not supported. 
- The ":first-line", ":first-letter", ":after", and ":before" pseudo-elements are not supported.
- The ":active" and ":focus" dynamic pseudo-classes are not supported. However, Nodes do support the ":pressed" and ":focused" pseudo-classes, which are similar
- The ":link" and ":visited" pseudo-classes are not supported in general. However, Hyperlink objects can be styled, and they support the ":visited" pseudo-class.

- JavaFX CSS does not support comma-separated series of font family names in the -fx-font-family property. The optional line height parameter when specifying fonts is not supported. There is no equivalent for the font-variant property.
	
- JavaFX CSS uses the HSB color model instead of the HSL color model.

-for more : http://docs.oracle.com/javafx/2/api/javafx/scene/doc-files/cssref.html

6. Layout of FXML
=================

As per project requirement FXML have rich number of layouts as follows,

- AnchorPane
- BorderPane
- FlowPane
- GridPane
- Pane
- Region
- StackPane
- TilePane

Every layout have their own flow and structure, so by using above layout we can reduce our Java code logic and it also reduce application rendering time.

7. Prerequisites
================

- You need to install Latest JDK(1.7 and abouve) with JavaFX support. You can download it 
	from here : http://www.oracle.com/technetwork/java/javase/downloads/jdk7u9-downloads-1859576.html

- Your favorite IDE (NetBeans or Intellij IDEA)

	for NetBeans : http://www.oracle.com/technetwork/java/javase/downloads/jdk-netbeans-jsp-142931.html
	
	for Intellij IDEA : http://www.jetbrains.com/idea/download/
	







  


  




