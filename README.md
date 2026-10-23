# EventHub - College Event Management Portal (AIP Mini Project)

Servlet + JSP + JDBC + Hibernate on Apache Tomcat 10.1 and MySQL 8.0.

## 1. Create the database
1. Open MySQL Workbench (or the mysql command line).
2. Run `database/eventhub_db.sql`. It creates `eventhub_db`, three tables and demo data.

## 2. Set your MySQL password (two places)
- `src/main/java/com/eventhub/util/DBConnection.java`  (USER / PASS)
- `src/main/resources/hibernate.cfg.xml`               (username / password)

## 3. Open in NetBeans
1. File > Open Project > select the `EventHub` folder (it is a Maven web project).
2. Wait while Maven downloads the libraries (internet needed the first time).
3. Tools > Servers: add your Apache Tomcat 10.1.57 folder if it is not listed.
4. Right-click the project > Properties > Run > Server: Apache Tomcat.
5. Right-click the project > Clean and Build, then Run.
6. Open http://localhost:8080/EventHub/

## Demo logins
| Role    | Email                | Password   |
|---------|----------------------|------------|
| Admin   | admin@eventhub.com   | admin123   |
| Student | student@eventhub.com | student123 |

## Troubleshooting
- `ClassNotFoundException: javax.servlet...` : use `jakarta.servlet` (Tomcat 10+).
- `Access denied for user 'root'` : fix the password in the two files from step 2.
- `Communications link failure` : MySQL service is not running.
- Hibernate / Byte Buddy "Java 26 not supported": add `-Dnet.bytebuddy.experimental=true`
  to the Tomcat VM options (Servers > Tomcat > Platform > VM Options), or run Tomcat on JDK 21.
- 404 on pages: check the URL uses the context path `/EventHub/`.
