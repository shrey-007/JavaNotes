### BufferReader vs Scanner
In Java, both Scanner and BufferedReader are used for reading input, but they have different characteristics and are suited for different use cases. Here's a comparison:

- Scanner
1. Ease of Use: Scanner is more user-friendly and provides built-in methods to parse different types of input (e.g., nextInt(), nextDouble(), nextLine()).
2. Data Parsing: Scanner can parse tokens directly (e.g., read integers, floating-point numbers) and has methods for checking for the existence of more tokens (e.g., hasNextInt()).
3. Input Sources: It can read input from different sources like InputStream, File, String, etc.
4. Performance: Scanner is slower compared to BufferedReader because it performs input parsing and tokenization, which adds overhead.
5. Buffer Size: Scanner uses a smaller buffer of 1024 characters by default.
- BufferedReader
1. Ease of Use: BufferedReader is more low-level compared to Scanner. It reads text from a character-input stream and provides methods like readLine() to read a line of text at a time.
2. Data Parsing: It doesn't provide built-in methods for parsing different data types, so you need to handle the parsing manually (e.g., using Integer.parseInt() or Double.parseDouble()).
3. Input Sources: It can read input from InputStreamReader, which can wrap around different input sources like FileReader or InputStream.
4. Performance: BufferedReader is generally faster than Scanner because it doesn't do token parsing. It's more suitable for reading large files or input streams quickly.
5. Buffer Size: BufferedReader uses a larger buffer of 8192 characters by default, which can be configured.
- When to Use Which
1. Use Scanner when you need to parse user input or read data types directly (like reading integers or doubles).
2. Use BufferedReader when you need to read large amounts of text efficiently, especially when reading lines of text or when performance is a critical concern.
### Inner class
An inner class in Java is a class that is declared within another class. Inner classes have access to the members (including private members) of the outer class. Java supports various types of inner classes:


- Why Use Inner Classes?
1. Encapsulation: Inner classes allow you to logically group classes that are only used in one place, thereby keeping your code more organized and encapsulated.
2. Logical Association: If a class is only relevant in the context of another class, defining it as an inner class makes the relationship between the two classes clear.
3. Access to Outer Class Members: Inner classes have direct access to the outer class's members, which can be convenient for certain designs.
- Where are Inner Classes Used?
1. Data Structures: In complex data structures, inner classes can be used to define helper classes like nodes within a tree or linked list.
2. Encapsulation of Implementation: Inner classes can be used to encapsulate implementation details, keeping them hidden from the outside world and exposing only the outer class interface.
### Throwable class
The Throwable class in Java is the superclass of all errors and exceptions in the Java language. It is a part of the java.lang package and serves as the root class for any object that can be thrown using the throw statement or caught using the catch clause.It has 2 direct subclasses Error and Exception.

### Marker Interface
A marker interface in Java is an interface that does not contain any methods or fields. It is used to "mark" or "tag" a class with a particular characteristic or capability. The presence of a marker interface on a class informs the Java runtime or other code that the class should be treated in a specific way.
Now they are not used. Instead of them Annotations are used.