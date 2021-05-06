# :zap:Java NIO
 
* Java coding project for a Java Programming Masterclass see [:clap: Inspiration](#clap-inspiration) below

*** Note: to open web links in a new window use: _ctrl+click on link_**

## :page_facing_up: Table of contents

* [:zap: Angular Material Table](#zap-angular-material-table)
  * [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
  * [:books: General info](#books-general-info)
  * [:camera: Screenshots](#camera-screenshots)
  * [:signal_strength: Technologies](#signal_strength-technologies)
  * [:floppy_disk: Setup](#floppy_disk-setup)
  * [:computer: Code Examples](#computer-code-examples)
  * [:cool: Features](#cool-features)
  * [:clipboard: Status & To-Do List](#clipboard-status--to-do-list)
  * [:clap: Inspiration](#clap-inspiration)
  * [:envelope: Contact](#envelope-contact)

## :books: General info

* [Java.nio](https://docs.oracle.com/javase/8/docs/api/java/nio/package-summary.html) used to define buffers - containers for data.
* [Java.nio FileSystem class](https://docs.oracle.com/javase/7/docs/api/java/nio/file/FileSystem.html) provides an interface to a file system.
* [Java.nio IntBuffer class](https://docs.oracle.com/javase/9/docs/api/java/nio/IntBuffer.html) extends Buffer, an int buffer

## :camera: Screenshots

* Not applicable for this project

## :signal_strength: Technologies

* [Java v11](https://www.java.com/en/)

## :floppy_disk: Setup

* Open folder in an IDE such as IntelliJ.

## :computer: Code Examples

* class to create a data file and write data to it. flip() method used to flip the buffer so buffer trimmed to current position then position changed to zero.

```java
public class Main {

  public static void main(String[] args) {
    try(FileOutputStream binFile = new FileOutputStream("data.dat");
        FileChannel binChannel = binFile.getChannel()) {

      byte[] outputBytes = "Hello World".getBytes();
      ByteBuffer buffer = ByteBuffer.wrap(outputBytes);
      int numBytes = binChannel.write(buffer);
      System.out.println("numBytes written was: " + numBytes);

      ByteBuffer intBuffer = ByteBuffer.allocate(Integer.BYTES);
      intBuffer.putInt(245);
      intBuffer.flip();
      numBytes = binChannel.write(intBuffer);
      System.out.println("numBytes written was: " + numBytes);

      intBuffer.flip();
      intBuffer.putInt(-98765);
      intBuffer.flip();
      numBytes = binChannel.write(intBuffer);
      System.out.println("numBytes written was: " + numBytes);
    } catch(IOException e) {
      e.printStackTrace();
    }
  }
}
```

## :cool: Features

* tba

## :clipboard: Status & To-Do List

* Status: Working tutorial code Section 14-247 completed.
* To-Do: Complete tutorial

## :clap: Inspiration

* [Udemy: Java Programming Masterclass for Software Developers](https://www.udemy.com/course/java-the-complete-java-developer-course/learn/lecture/3561816#overview)

## :envelope: Contact

* Repo created by [ABateman](https://www.andrewbateman.org), email: gomezbateman@yahoo.com
