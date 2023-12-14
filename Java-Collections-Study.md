# Java Collections Study

Collections or API's Collections of Java, area a conjunction of classes and interfaces that organize data (like filter them, added, deleted and several interactions with data) with List, Map, or connected lists. Java Collections emerged because it was hard to work with Arrays. 

Here are the types of Collections:
![Alt text](img1.png)

# Java List
Java `List` is the most usable interface, that offers interface list to manage every object that will be organized and also, there are methods to help add, remove or consultation etc. Example:

```java
List <ListExample> listExample = new ArrayList<>();
```

Also, there are `Vector`, another implementation class from List, but is not used as much than `ArraList` because he provides a better performance.

Now, figuring out that we gonna manipulate the objects bellow:
```java
import java.util.Objects;

//Objects
private Long id;
private String name;

//Constructor to helps create objects
public class People {
public Person (Long id, String name) { 
    this.id = id;
    this.name = name;
}

//Getters and setters
public Long getId() { 
    return id; 
}
public void setId(Long id) { 
    this.id = id;
}
public String getName() {
    return name;
}
public void setName (String name) { 
    this.name = name; 
}
}
```

And also, include the methods `Equals` and `Hash Code` (until inside the same class):

```java
@Override
public boolean equals(Object o) {
if (this == 0) return true;
if (!(o instanceof Person)) return false;
Person person = (Person) o;
I
return id.equals(person.id) && person.equals(person.name);
}

@Override
public int hashCode() {
return Objects.hash(id, name);
}
```

Let's use them with Java List, in another class, and manipulating with methods offered by List:

```java
public class ExampleList {
public static void main(String[] args) {
    List<Person> people = new ArrayList<>();
        people.add(new Person(id: 1L, name: "John")); // Add item
        
        Person a = people.get(0); // Backup of the index especified inside get

        people.remove (a); // Remove item

        for (Person person: people) {
            System.out.println(person.getName());
        }

        //Replica of people
        System.out.println("---------");

        people.add(a); // Add content inside the object one more time

        for (Person person: people) {
            System.out.println(person.getName());
        }
    }
}
```

The example above will generate a repetition of the same object already created. So, look at th output to check out (gonna work if remove part is marked as comment):
```output
John
---------
John
John
```

So, to difference them, we use Java Set.

# Java Set

Java `Set` it's similar to List, but works with without repeat the elements, using strategies accordingly the implementation of his interface. And there's the example using the same context above:

```java
public class ExampleList {
public static void main(String[] args) {
    Set<Person> people = new HashSet<>();
        people.add(new Person(id: 1L, name: "John"));

        for (Person person: people) {
            System.out.println(person.getName());
        }

        System.out.println("---------");

        people.add(a);

        for (Person person: people) {
            System.out.println(person.getName());
        }
    }
}
```

Output:
```output
John
---------
John
```

What's happened?: the Set use the HashCode method to discover if the object already exists inside the list. Even if you create an another instance, the output will be the same.

# Java Map
The Java Map is a concept of key and value. So, for each object that I’m going to store in this list, it has to be added through a key. This key can be any type of object, as long as it has the implementation of the hash method, which is a global identifier of the information of that object.
</br>
Map is used to carry a bunch of registers and help us to index values and do a consultation with earn more performance from the software.
</br>
So, using the example above:

```java
public class ExamplesMap {
    public static void main(String[] args) {
        Map<Long, Person> map = new HashMap<>(); //Long is the key

        Person john = new Person (id: 1L, name: "John");

        map.put(1L, john);

        Person john2 = map.get(1L);
    }
}
```

# Java Array List

The Java `ArrayList` is a resizeble `Array` that belongs to `java.util` package. An `Array` can't be modified, different than a `ArrayList`– which means that you can't add or remove an item from an array whitout creating a new objetc of him. Example creating an object and adding itens inside of an Array List:
```java
import java.util.ArrayList;

public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    System.out.println(cars);
  }
}
```
Access an element with `get` method and searching by index number:
```java
cars.get(0);
```
Change item by index with `set`:
```java
cars.set(0, "Opel");
```
Remove item by index with `remove` method:
```java
cars.remove(0);
```
To remove all the elements inside of an Array List, with `clear` method:
```java
cars.clear();
```
To search for how many elements there are inside an Array List with `size` method:
```java
cars.size();
```
To loop through an Array List and specify each element inside them:
```java
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");

    for (int i = 0; i < cars.size(); i++) {
      System.out.println(cars.get(i));
    }
  }
}
```
Also, using `for-each` loop:
```java
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    for (int i = 0; i < cars.size(); i++) {
      System.out.println(cars.get(i));
    }
  }
}
```