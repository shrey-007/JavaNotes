### Standard Streams-:
1. System.in: This is the standard input stream that is used to read characters from the keyboard or any other standard input device.**IT IS A BYTE STREAM**
2. System.out: This is the standard output stream that is used to produce the result of a program on an output device like the computer screen.**IT IS A BYTE STREAM**
3. System.err

### Stream classification based on file types
- ByteStream-This is used to process data byte by byte (8 bits).These streams handle I/O of raw binary data. They are used for reading and writing binary data like images, audio, and video files. Byte streams read and write data in 8-bit bytes. Though it has many classes, the FileInputStream and the FileOutputStream are the most popular ones.  
Classes are-:
1. InputStream (abstract superclass for reading byte streams)
2. OutputStream (abstract superclass for writing byte streams)

Common Subclasses are-: 
1. FileInputStream, FileOutputStream
2. BufferedInputStream, BufferedOutputStream
3. DataInputStream, DataOutputStream

- CharacterStream: In Java, characters are stored using Unicode conventions . Character stream automatically allows us to read/write data character by character. These streams handle I/O of character data. They are used for reading and writing text data (characters). Character streams read and write data in 16-bit Unicode.
Classes are-:
1.  Reader (abstract superclass for reading character streams)
2.  Writer (abstract superclass for writing character streams)

Common Subclasses:
1. FileReader, FileWriter
2. BufferedReader, BufferedWriter
InputStreamReader, OutputStreamWriter

### When we give input through scanner, which stream it is?

When you give input through a Scanner in Java, it typically uses a character stream.

The Scanner class can read input from various sources, such as files, strings, or the console. When reading from the console (i.e., System.in), it wraps the InputStream (which is a byte stream) into an InputStreamReader, converting it to a character stream. This allows the Scanner to read characters, strings, and primitive data types in a convenient manner.

Here's how it works in common scenarios:

Console Input (System.in):

System.in is an InputStream (a byte stream).
Scanner wraps it with an InputStreamReader (converts byte stream to a character stream).
File Input:

When using a File object or FileReader with Scanner, it directly deals with character streams.
So, even though System.in is a byte stream, Scanner works on top of it as a character stream by internally converting the byte stream to a character stream.

### So when should we use which stream?
Choosing between byte streams and character streams in Java depends on the type of data you're working with:

- When to Use Byte Streams:
1. Binary Data:

Use byte streams when dealing with binary data like images, audio files, video files, and other non-text data. Since byte streams handle raw 8-bit binary data, they are ideal for these scenarios.
Examples:
Reading/writing image files (FileInputStream/FileOutputStream).
Handling binary data from network connections.
2. Non-Text Files:

If the file contains data that is not encoded as text (like an executable file or a compressed file), byte streams are the appropriate choice.
Examples:
Copying or manipulating binary files.
Reading/writing serialized objects (in conjunction with ObjectInputStream/ObjectOutputStream).
When to Use Character Streams:
Text Data:

Use character streams when working with text data (like .txt files) or when you need to process data as characters or strings. Character streams are designed to handle characters, supporting internationalization with Unicode.
Examples:
Reading/writing text files (FileReader/FileWriter).
Processing text input/output from a console or a file.
Character Encoding Awareness:

If you need to work with specific character encodings (like UTF-8, UTF-16), character streams allow you to specify the encoding and ensure proper handling of characters.
Examples:
Reading/writing text files with a specific encoding (InputStreamReader/OutputStreamWriter).

### So if i want to take input from user, which stream should i use?
When taking input from a user in Java, the most common and appropriate stream to use is a character stream. Specifically, you would typically use the Scanner class or BufferedReader class, which both operate on character streams.

---
# Character Stream
Its Main **abstract** classes are-:
- Reader(Abstract)
1. The abstract superclass for all character input streams.


- Writer(Abstract)
1. The abstract superclass for all character output streams.

- Important classes-:
1. FileReader/FileWriter-: To perform read/write operation on files char by char
2. BufferedReader/BufferedWriter-: To perform read/write operation on anything line by line. It can be used to read a line from file, or can be used to read a line from keyboard.
3. InputStreamReader/OutputStreamWriter-: To convert byte stream to character stream.

---

# Byte Streams
Its Main **abstract** classes are-:
- InputStream(Abstract)
1. The abstract superclass for all byte input streams.
2. Provides basic methods for reading raw bytes of data.
- OutputStream(Abstract)
1. The abstract superclass for all byte output streams.
2. Provides basic methods for writing raw bytes of data.





