### Java Enterprise and Spring

#### What are the possible uses of reflection?

> Reflection is commonly used by programs which require the ability to **examine or modify the runtime behaviour** of applications running in the **Java Virtual Machine**.

1.  access private fields and methods
2.  invoke methods
3.  get a class annotations

#### What is Spring?

Spring is one of the **most widely used Java EE Frameworks** for building applications. Simply put, the **Spring framework** provides comprehensive infrastructure **support for developing Java applications**. It aims to **simplify the Java EE development** and **helps developers be more productive at work**. It's **packed** with some **nice features like Dependency Injection and out of the box modules** like:

-   Spring JDBC
-   Spring MVC
-   Spring Security
-   Spring Test

These modules can **drastically reduce the development time** of an application and **writing a lot of boilerplate code**.

#### What is Spring Boot?

**Spring Boot** is basically an **extension of the Spring framework** which **eliminated the boilerplate configurations required for setting up a Spring application**. While the Spring framework focuses on providing flexibility to you, **Spring Boot aims to shorten the code length** and **provide you with the easiest way to develop a web application**. With **annotation configuration and default codes**, Spring Boot shortens the time involved in developing an application. It helps create a **stand-alone application with less or almost zero-configuration**.

#### What is the major difference between the Standard edition (JSE) and Enterprise edition (JEE)? You can choose Spring (Spring Boot) instead of JavaEE. Focus on comparing them.

**Java SE** = **Standard Edition**. This is the core Java programming platform. It **contains all of the libraries and APIs** that any Java programmer should learn (java.lang, java.io, java.math, java.net, java.util, etc...).

> The Java platform (Enterprise Edition) differs from the Java Standard
> Edition Platform (Java SE) in that it adds libraries which provide
> functionality to deploy fault-tolerant, distributed, multi-tier Java
> software, based largely on modular components running on an
> application server.

In other words, if your application **demands a very large scale, distributed system,** then you should consider **using Java EE**. Built on top of Java SE, it **provides libraries for database access** (JDBC, JPA), remote method invocation (RMI), messaging, web services, XML processing, and defines standard APIs for Enterprise JavaBeans, servlets, portlets, Java Server Pages, etc...

#### What are the advantages of the Spring Framework? Focus on the Core part.

1.  Spring enables the developers to develop the **enterprise applications** using **POJOs (Plain Old Java Object**). The benefit of developing the applications using POJO is, that we do not need to have an enterprise container such as an application server but we have the option of using a robust servlet container.
2.  **Spring** comes with **some of the existing technologies** like **ORM** framework, **logging framework**, J2EE and JDK Timers etc, Hence we don’t need to integrate explicitly those technologies.
3.  Spring can **eliminate** the **creation of the singleton and factory classes**.
4.  Spring framework is both **complete** and **modular**, because spring framework has a **layered architecture**.
5.  Spring framework has taken **the best practice** that have been **proven over the years in several applications** and **formalized as design patterns**.

#### What is a servlet? What is the purpose of DispatcherServlet in Spring?

**Servlet**: A servlet is simply a class which **responds to a particular type of network request** - **most commonly an HTTP request**. Basically servlets are usually used to **implement web applications** - but there are also various frameworks which operate on top of servlets (e.g. Struts) to give a higher-level abstraction than the "here's an HTTP request, write to this HTTP response" level which servlets provide.

**DispatcherServlet:** The job of the **DispatcherServlet** is to take an **incoming URI** and **find the right combination of handlers** (generally **methods on Controller classes**) and views (generally JSPs) that **combine to form the page** or resource that's supposed to be found at that location. The task of the DispatcherServlet is to **send request to the specific Spring MVC controller**.

#### When do you use RestControllers, when just simple Controllers?

`@Controller` returns `View`. `@RestController` returns `ResponseBody`.

`@Controller`: is used to mark classes as Spring MVC Controller.

`@RestController`: is a convenience annotation that does nothing more than adding the `@Controller` and `@ResponseBody` annotations. (Java objects are serialized to JSON representation in the response body)

#### What is Spring Application Context?

One of the **main features** of the Spring framework is the **IoC** (Inversion of Control) **container**. The Spring IoC container is responsible for **managing the objects of an application**. It uses **dependency injection** to **achieve inversion of control**.

The interfaces **BeanFactory** and **ApplicationContext** represent the **Spring IoC container**. Here, **BeanFactory** is the **root interface** for accessing the **Spring container**. It provides **basic functionalities for managing beans**.

On the other hand, the **ApplicationContext is a sub-interface of the BeanFactory.** Hence, it offers all the functionalities of BeanFactory.

Furthermore, it **provides** **more enterprise-specific functionalities**. The important features of _ApplicationContext_ are **resolving messages, supporting internationalization, publishing events, and application-layer specific contexts**. This is why we use it as the default Spring container.

#### What are the main ways to define a bean in the Application Context?

A bean is **an object that the Spring container instantiates, assembles, and manages**. The primary job of the **ApplicationContext** is to **manage beans**. So, an application **must provide the bean configuration** to the ApplicationContext container. Therefore, a Spring bean **configuration** consists of **one or more bean definitions**. Also, Spring supports **different ways of configuring beans**.

1.  Java-Based Configuration: `@Bean`-annotated methods within a `@Configuration` class.
2.  Annotation-Based Configuration: `@Component, @Controller, @Service, @Repository, @Autowired, and @Qualifier`.
3.  XML-Based Configuration: It's the traditional way of configuring beans in Spring. We do all **bean mappings in an XML configuration file**.

#### Difference between .jar and .war files.

These files are simply zipped files using the java jar tool. These files are created for different purposes. Here is the description of these files:

-   .jar files: The .jar files **contain libraries, resources and accessories files** like property files.
-   .war files: The war file **contains the web application** that can be deployed on any servlet/jsp container. The .war file **contains jsp, html, javascript** and other files necessary for the development of web applications.

#### What are the major differences between Maven, Ant and Gradle?

**Ant:**
Ant was the first among "modern" build tools. It was released in 2000 and in a short period of time became **the most popular build tool for Java projects**. It is based on procedural programming idea. Major drawback was **XML as the format to write build scripts**. XML, being hierarchical in nature, is **not a good fit for procedural programming approach** Ant uses. Another problem with Ant is that its XML tends to become unmanageably big when used with all but very small projects.

**Maven:**
Maven was released in **2004.** Its goal was to **improve upon some of the problems developers were facing when using Ant.** Maven continues using XML as the format to write build specification. However, st ructure is diametrically different. Maven **relies on conventions** and **provides the available targets** (goals) that can be invoked. As the additional, and probably most important addition, **Maven introduced the ability to download dependencies over the network**. That in itself revolutionized **the way we deliver software**.

**Gradle:**
Gradle combines **good parts of both tools** and builds on top of them with **DSL** and other improvements. It has **Ant's power and flexibility with Maven's life-cycle** and ease of use. Gradle does **not use XML**. Instead, it had its own **DSL based on Groovy** (one of JVM languages). As a result, Gradle build scripts **tend to be much shorter and clearer than those written for Ant or Maven.** The **amount of boilerplate code is much smaller** with Gradle. Gradle effort can be summed as **"convention is good and so is flexibility"**.

#### What is Maven used for?

Maven is a **powerful project management tool** that is **based on POM (project object model).** It is used for **projects build, dependency and documentation.** It **simplifies the build process** like ANT. But it is too much advanced than ANT. In short terms we can tell maven is a tool that can be **used for building and managing any Java-based project**. Maven make the day-to-day work of Java developers easier and generally **help with the comprehension of any Java-based project**.

**Maven does a lot of helpful task like:**

1.  We can **easily build a project using maven**.
2.  We can **add jars and other dependencies** of the project easily using the help of maven.
3.  Maven **provides project information** (log document, dependency list, unit test reports etc.)
4.  Maven is very helpful for a project **while updating central repository of JARs** and other dependencies.
5.  With the help of **Maven we can build any number of projects into output types like the JAR, WAR** etc without doing any scripting.
6.  Using maven **we can easily integrate our project with source control system** (such as Subversion or Git).

![enter image description here](https://media.geeksforgeeks.org/wp-content/uploads/How-Maven-Works.jpg)

#### What does a pom.xml file contains in Maven?

POM is an XML file which **contains the project configuration details used by Maven**. It **provides all the configuration required for a project**.

POM means **project object model**, and, as the name suggests, it **defines the model of the project as well.**

In the normal project development you will add JAR files and libraries as required. In **Maven**-based development, those JAR files, libraries are added to the project using this **pom.xml**. In the **pom context we call those JAR files, libraries as dependencies**.

### Object Relational Mapping, JPA

#### What is an ORM? What are the benefits, when to use?

ORM **(Object-Relation Mapping)** helps you take advantage of the **object-oriented principles** while managing **relational databases**. This allows you to set up **objects and completely manage objects** while the ORM library/framework takes care of **translating all functionalities into database** schema and queries. By doing this, you can easily take advantage of all the experience you have in coding in ORMs and the programming related safety patterns that you are used to following. Object-relational mapping (ORM, O/RM, and O/R mapping tool) in computer science is a programming technique for **converting data between incompatible type systems** using **object-oriented programming languages**. This creates, in effect, a **"virtual object database"** that can be used from within the programming language.

Benefits:

-   They **write correct and optimized SQL queries**, thereby eliminating the hassle for developers
-   They make the code **easier to update, maintain, and reuse as the developer** can think of, and **manipulate data as objects**
-   ORMs will **shield your application from SQL injection attacks** since the framework will filter the data for you!
-   ORMs provide the concept of **Database Abstraction** which makes **switching databases easier and creates a consistent code base for your application.**

#### What is the difference between JDBC and JPA? Which are the advantages and disadvantages of each? Give a general overview.

**Main difference between JPA and JDBC is level of abstraction.**
**JDBC** is a **low level standard for interaction with databases**. **JPA** is **higher level standard for the same purpose**. **JPA** allows you to use an **object model in your application** which can make your life much easier. **JDBC allows you to do more things with the Database directly**, but it requires more attention. Some tasks can **not be solved efficiently using JPA**, but may be solved more efficiently with JDBC.

**JDBC** is a standard for connecting to a **DB directly and running SQL against it** - e.g `SELECT * FROM USERS`, etc. **Data sets can be returned which you can handle in your app**, and you can do all the usual things like `INSERT`, `DELETE`, run stored procedures, etc. It is one of the underlying technologies behind most Java database access (including JPA providers).

**JPA is a standard for Object Relational Mapping.** This is a technology which allows you to **map between objects in code and database tables**. This **can "hide" the SQL from the developer so that all they deal with are Java classes,** and the **provider allows you to save them and load them magically**. Mostly, XML mapping files or annotations on getters and setters can be used to tell the JPA provider which fields on your object map to which fields in the DB.

#### What is Hibernate? What are the advantages, limitations?

**Hibernate ORM** (or simply Hibernate) is an **object-relational mapping tool for the Java programming language.** It provides a **framework** for mapping an **object-oriented domain model to a relational database.** Hibernate **handles object-relational impedance mismatch problems** by replacing direct, persistent database accesses with high-level object **handling functions.**

**Advantages:**

-   Hibernate supports Inheritance, Associations, Collections
-   Hibernate supports relationships like One-To-Many,One-To-One, Many-To-Many-to-Many, Many-To-One
-   Hibernate has capability to generate primary keys automatically while we are storing the records into database
-   Hibernate has its own query language, i.e hibernate query language which is database independent
-   So if we change the database, then also our application will works as HQL is database independent

**Limitation:**

-   Its saying hibernate is little slower than pure JDBC, actually the reason being hibernate used to generate many SQL statements in run time

#### Name 3 different annotations used in JPA, what can they do for you?

**@Entity:**
The `@Entity` annotation is used to specify that the currently annotate class represents an entity type. Unlike basic and embeddable types, entity types have an identity and their state is managed by the underlying Persistence Context.

**@Id:**
The `@Id` annotation specifies the entity identifier. An entity must always have an identifier attribute, which is used when loading the entity in a given Persistence Context.

**@OneToMany**:
The `@OneToMany` annotation is used to specify a one-to-many database relationship.

#### What is object-relational impedance mismatch?

'**Object-Relational Impedance Mismatch'** (sometimes called the 'paradigm mismatch') is just a fancy way of saying that object models and relational models do not work very well together. **RDBMSs represent data in a tabular format** (a spreadsheet is a good visualization for those not familiar with RDBMSs), whereas **object-oriented languages, such as Java, represent it as an interconnected graph of objects.**

#### What is a JpaRepository? What are the 2 main methods to define queries in them?

`JpaRepository` is JPA specific extension of `Repository`. It contains the full API of `CrudRepository` and `PagingAndSortingRepository`. So it contains API for basic CRUD operations and also API for pagination and sorting.

Queries:

1. Query creation from method names:
   List<User> findByEmailAddressAndLastname(String emailAddress, String lastname);
2. Using `@Query` annotation

#### Why is the Set preferred over List when we want to store OneToMany relations?

#### What kind of inheritance strategies are available? Which annotations are used to solve this?

Relational databases **don't have a straightforward** way to map class hierarchies onto database tables.

To address this, the JPA specification provides several strategies:

-   MappedSuperclass – the parent classes, can't be entities
-   Single Table – the entities from different classes with a common ancestor are placed in a single table
-   Joined Table – each class has its table and querying a subclass entity requires joining the tables
-   Table-Per-Class – all the properties of a class, are in its table, so no join is required

**Entity inheritance means that we can use polymorphic queries for retrieving all the sub-class entities when querying for a super-class.**

**MappedSuperclass:**
Using the MappedSuperclass strategy, inheritance is only evident in the class, but not the entity model.
**Notice that this class no longer has an _@Entity_ annotation**, as it won't be persisted in the database by itself.

**Single Table:**
**The Single Table strategy creates one table for each class hierarchy.** This is also the default strategy chosen by JPA if we don't specify one explicitly.

**Joined Table:**
**Using this strategy, each class in the hierarchy is mapped to its table.** The only column which repeatedly appears in all the tables is the identifier, which will be used for joining them when needed.
