# docker-java-project

<pre>
Here’s a simple Java Docker project that:

Uses plain Java (not Spring Boot).

Compiles and runs a Main.java file using Docker.

Keeps all files in the same folder (no separate conf or setup folders).
</pre>

### ✅ Folder Structure:
<pre>
java-docker-app/
├── Dockerfile
├── docker-compose.yml
├── Main.java
</pre>

### 🔹 Main.java

<pre>
  public class Main {
    public static void main(String[] args) {
        System.out.println("Hello from Java inside Docker!");
    }
}

</pre>

### 🔹 Dockerfile

<pre>
FROM openjdk:21

WORKDIR /app

COPY Main.java .

RUN javac Main.java

CMD ["java", "Main"]

</pre>

### 🔹 docker-compose.yml
<pre>
version: "3.8"

services:
  java-app:
    build: .
    container_name: java-app

</pre>

### ✅ To Run:
**Open a terminal in the folder and run:**
<pre>
  docker-compose up --build

</pre>

***You’ll see:**

java-app  | Hello from Java inside Docker! 
