# Wilhem's Wacky Bakery
* **Objective** - to implement a _webservice_ which exposes _endpoints_ for creating, reading, updating, and 
* deleting `Baker` and `Muffin` objects.
* **Purpose** - to demonstrate the use of
    * [Spring Annotations](https://springframework.guru/spring-framework-annotations/)
    * [CRUD Operations](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete)
    * [Web services](https://en.wikipedia.org/wiki/Web_service)
    * [API Endpoints](https://stackoverflow.com/questions/2122604/what-is-an-endpoint)
    * [Model View Controller Architecture](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)

## Instructions
* This project is a complete Spring boot application with annotations removed.
* Your objective is to add the correct annotations above each class member which requires it.
* Some tests have been created. However, the veracity of the application should be tested by making HTTP-requests via 
* the [Postman application](https://www.getpostman.com/downloads/).




## Developmental Notes





#### `@Entity`
* Annotates class signature
* **Description:**
    * Allows the persistence provider to recognize it as a persistence class.
    * An object representative of a snapshot of data from a database.
    * By default, maps this entity to a table whose name is the name of the annotated class. Can be rerouted via the `@Table` 
    * annotation
    * Entities are said to be _fungible_, or _mutually interchangeable_.
* **Pre-requisites for use:**
	* An interface cannot be an entity.
	* An enum cannot be an entity.
	* The class can be abstract or concrete.
	* The class must define a no-arg constructor.
	* Each `Entity` must be annotated with a respective `ID`.

	

<hr>

#### `@Id`
* Annotates field declarations
* **Description:**
	* Denotes the primary key for this `Entity`.
	* Can be generated manually by application or by automatically by the persistence provider.
* **Pre-requisites for use:**
	* Class must be annotated with `@Entity`

	
	
		
<hr>

#### `@GeneratedValue(strategy = GenerationType.ENUM_VALUE)`
* Annotates `Id` fields.
* **Description:**
    * Specifies how the persistence provider will generate this value.
    * `GenerationType.SEQUENCE` - specifies the use of database SQL sequence
    * `GenerationType.IDENTITY` - uses a database identity column
    * `GenerationType.TABLE` - instructs provider to store the sequence name and its current value in a table, increasing the 
    * value of each time a new instance of the entity is persisted.
    * `GenerationType.AUTO` - default when nothing specified. Provider does generation of a key automatically. It will select
    * an appropriate strategy for a particular database.
* **Pre-requisites for use:**
	* Field must be annotated with `@Id`.



	

<hr>

#### `@Autowired`
* Annotates field declaration or method-parameters
* **Description**
    * injects bean by type
    * can be used alone.
    * If is used alone, it will be wired by type
    * If more than one bean of same type are declared in the container `@Autowired` does not know which beans to use for
    * injection.
* **Pre-requisites for use:**
	* Field-type must be annotated with some form of `@Component`.



<hr>

#### `@Component`
* Annotates class signature
* **Description**
    * denotes that Spring framework will autodetect these classes for dependency injection when annotation-based 
    * configuration and classpath scanning is used.
* **Prerequisites for use:**
	* none	
	
	
<hr>

#### `@Service`
* Annotates class signature
* **Description**
	* specialized form of `@Component`
	* responsible for performing service tasks
	* in many case you use this annotation for best practice, but isn't _always_ necessary.
* **Prerequisites for use:**
	* none	
	
	
<hr>

#### `@Controller`
* Annotates class signature
* **Description**
	* specialized form of `@Component`
	* indicates that a particular class serves the role of a controller
	* acts as a stereotype for the annotated class, indicating its role
	* dispatcher scans such annotated classes for mapped methods and detects @RequestMapping annotations
* **Pre-requisites for use:**
	* none

 
 
<hr>
 
#### `@RequestMapping`
* Annotates a method signature
* **Description**
	* annotation maps HTTP requests to handler methods of MVC and REST controllers.
* **Pre-requisites for use**
	* class must be an annotated with `@Controller`

	
	
	
<hr>
 
#### `@PathVariable`
* Annotates a method parameter
* **Description**
	* indicates that a method parameter should be bound to a URI template variable
* **Pre-requisites for use**
	* class must be an annotated with `@Controller`

	

<hr>
 
#### `@RequestParam`
* Annotates a method parameter
* **Description**
	* indicates that a method parameter should be bound to a web request parameter
	* used to extract query parameters, form parameters 
* **Pre-requisites for use**
	* class must be an annotated with `@Controller`
 
 


