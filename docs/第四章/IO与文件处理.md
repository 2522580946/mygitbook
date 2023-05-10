# IO与文件处理

Java提供了丰富的IO类和方法，可以方便地进行文件和数据流的读写操作。下面介绍一些常用的Java IO与文件处理的方法：

## 读写文本文件

使用Java的File类和FileReader/FileWriter类可以读写文本文件。例如：

```
javaCopy codeFile file = new File("file.txt");

// 写入文件
FileWriter writer = new FileWriter(file);
writer.write("Hello, world!");
writer.close();

// 读取文件
FileReader reader = new FileReader(file);
char[] buffer = new char[1024];
int len = reader.read(buffer);
String content = new String(buffer, 0, len);
System.out.println(content); // 输出：Hello, world!
reader.close();
```

## 读写二进制文件

使用Java的FileInputStream/FileOutputStream类可以读写二进制文件。例如：

```
javaCopy codeFile file = new File("file.bin");

// 写入文件
byte[] data = {1, 2, 3};
FileOutputStream output = new FileOutputStream(file);
output.write(data);
output.close();

// 读取文件
FileInputStream input = new FileInputStream(file);
byte[] buffer = new byte[1024];
int len = input.read(buffer);
byte[] content = Arrays.copyOf(buffer, len);
System.out.println(Arrays.toString(content)); // 输出：[1, 2, 3]
input.close();
```

## 使用BufferedReader/BufferedWriter类读写文本文件

使用Java的BufferedReader/BufferedWriter类可以读写文本文件，并且可以一次读写一行文本。例如：

```
javaCopy codeFile file = new File("file.txt");

// 写入文件
BufferedWriter writer = new BufferedWriter(new FileWriter(file));
writer.write("Hello, world!");
writer.newLine(); // 换行
writer.write("Goodbye, world!");
writer.close();

// 读取文件
BufferedReader reader = new BufferedReader(new FileReader(file));
String line;
while ((line = reader.readLine()) != null) {
    System.out.println(line);
}
reader.close();
// 输出：
// Hello, world!
// Goodbye, world!
```

## 使用ObjectInputStream/ObjectOutputStream类读写对象

使用Java的ObjectInputStream/ObjectOutputStream类可以读写Java对象。例如：

```
javaCopy codeFile file = new File("file.obj");

// 写入对象
Person person = new Person("Alice", 20);
ObjectOutputStream output = new ObjectOutputStream(new FileOutputStream(file));
output.writeObject(person);
output.close();

// 读取对象
ObjectInputStream input = new ObjectInputStream(new FileInputStream(file));
Person newPerson = (Person) input.readObject();
input.close();
System.out.println(newPerson); // 输出：Person{name='Alice', age=20}
```

以上是Java中一些常用的IO与文件处理方法，开发者可以根据具体需求选择合适的方法来进行文件和数据流的读写操作。
