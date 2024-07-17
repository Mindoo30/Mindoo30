// 1. Simple Classes

// Person.java
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getters and toString()
    public String getName() { return name; }
    public int getAge() { return age; }
    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + '}';
    }
}

// Car.java
public class Car {
    private String model;
    private int year;

    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    // Getters and toString()
    public String getModel() { return model; }
    public int getYear() { return year; }
    @Override
    public String toString() {
        return "Car{model='" + model + "', year=" + year + '}';
    }
}

// Book.java
public class Book {
    private String title;
    private String author;

    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }

    // Getters and toString()
    public String getTitle() { return title; }
    public String getAuthor() { return author; }
    @Override
    public String toString() {
        return "Book{title='" + title + "', author='" + author + "'}";
    }
}

// Laptop.java
public class Laptop {
    private String brand;
    private int ramSize;

    public Laptop(String brand, int ramSize) {
        this.brand = brand;
        this.ramSize = ramSize;
    }

    // Getters and toString()
    public String getBrand() { return brand; }
    public int getRamSize() { return ramSize; }
    @Override
    public String toString() {
        return "Laptop{brand='" + brand + "', ramSize=" + ramSize + "GB}";
    }
}

// Building.java
public class Building {
    private String address;
    private int floors;

    public Building(String address, int floors) {
        this.address = address;
        this.floors = floors;
    }

    // Getters and toString()
    public String getAddress() { return address; }
    public int getFloors() { return floors; }
    @Override
    public String toString() {
        return "Building{address='" + address + "', floors=" + floors + '}';
    }
}

// 2. Main Object Class with Subclasses

// MainObject.java
public class MainObject {
    private String name;

    public MainObject(String name) {
        this.name = name;
    }

    public String getName() { return name; }

    // Subclasses
    public static class SubObject1 extends MainObject {
        public SubObject1(String name) {
            super(name);
        }
    }

    public static class SubObject2 extends MainObject {
        public SubObject2(String name) {
            super(name);
        }
    }

    public static class SubObject3 extends MainObject {
        public SubObject3(String name) {
            super(name);
        }
    }
}

// 3. Abstract Class

// AbstractEntity.java
public abstract class AbstractEntity {
    protected String id;

    public AbstractEntity(String id) {
        this.id = id;
    }

    public abstract void display();

    public String getId() { return id; }
}

// 4. Collection Class with Inner Iterator Class

// MyCollection.java
import java.util.Iterator;
import java.util.ArrayList;

public class MyCollection<T> {
    private ArrayList<T> list = new ArrayList<>();

    public void add(T item) {
        list.add(item);
    }

    public Iterator<T> iterator() {
        return new MyIterator();
    }

    private class MyIterator implements Iterator<T> {
        private int index = 0;

        @Override
        public boolean hasNext() {
            return index < list.size();
        }

        @Override
        public T next() {
            return list.get(index++);
        }
    }
}

// 5. Comparator Class

// PersonComparator.java
import java.util.Comparator;

public class PersonComparator implements Comparator<Person> {
    @Override
    public int compare(Person p1, Person p2) {
        return p1.getName().compareTo(p2.getName());
    }
}

// 6. Simple GUI Class

// SimpleGUI.java
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.SwingUtilities;

public class SimpleGUI {
    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> {
            JFrame frame = new JFrame("Simple GUI");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setSize(300, 200);
            frame.add(new JLabel("Hello, World!"));
            frame.setVisible(true);
        });
    }
}
