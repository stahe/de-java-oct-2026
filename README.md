# Java 25 lernen

📖 **Das Tutorial lesen: [https://stahe.github.io/de-java-oct-2026/](https://stahe.github.io/de-java-oct-2026/)**

Dieser Kurs vermittelt die Sprache [Java](https://dev.java/) 25 **anhand von Beispielen**: über zweihundert Programme (320 Java-Dateien), zeilenweise kommentiert und mit ihren Ausführungsergebnissen. Er beginnt mit den Grundlagen der Sprache und behandelt den Datenbankzugriff mit JDBC und Hibernate, die Netzwerkprogrammierung und Webservices mit Spring Boot.

Es ist die Java-Portierung des Kurses [C# 14 lernen mit .NET 10](https://stahe.github.io/de-csharp-oct-2026/) (Oktober 2026), der seinerseits eine Neufassung eines C#-Kurses von 2008 ist: derselbe Aufbau, dieselben Beispiele, derselbe rote Faden, aber in modernem Java geschrieben. Alle Programme lassen sich mit JDK 25 **ohne Fehler und ohne Warnungen** kompilieren (`javac -Xlint:all`) und wurden ausgeführt; die im Kurs gezeigten Ergebnisse stammen aus diesen Läufen.

| C#-14-Kurs (2026) | Java-25-Kurs (2026) |
|---|---|
| C# 14, .NET 10 (LTS) | Java 25 (LTS), JDK 25 |
| Einzeldatei-Anwendungen (`dotnet run prog.cs`) | kompakte Quelldateien (`java Prog.java`) |
| `.csproj`-Projekte, `.slnx`-Projektmappen, NuGet | Maven-Projekte (`pom.xml`), Maven Central |
| Eigenschaften, Strukturen, Operatorüberladung | Accessoren, Records, Sealed Classes, Pattern Matching |
| LINQ | Stream API |
| Delegaten und Ereignisse | funktionale Schnittstellen, Lambdas, Listener |
| `Task`, `async` / `await` | `CompletableFuture`, virtuelle Threads |
| MSTest, Microsoft.Extensions.DependencyInjection | JUnit 6, Spring Framework 7 |
| System.Text.Json | Jackson 3 |
| ADO.NET, MySqlConnector | JDBC, MySQL Connector/J, HikariCP |
| Entity Framework Core | **Hibernate 7** (Jakarta Persistence 3.2) |
| `HttpClient`, `TcpClient` / `TcpListener` | `java.net.http.HttpClient`, `Socket` / `ServerSocket` |
| ASP.NET Core Minimal API | Spring Boot 4 |

## Kursgliederung

| Kapitel | Inhalt |
|---|---|
| Installation | JDK 25, IntelliJ IDEA / VS Code, die Befehle `java` und `javac`, kompakte Quelldateien, Maven, Multimodul-Projekte |
| Grundlagen der Sprache | Typen, `var`, Codeblöcke, Konvertierungen, Arrays, Operatoren, `switch`-Ausdrücke und Pattern Matching, geprüfte und ungeprüfte Ausnahmen, `try` mit Ressourcen, Aufzählungen, Parameterübergabe |
| Klassen, Records, Schnittstellen | Klassen, Vererbung, Polymorphie, Sealed Classes, `equals` / `hashCode` / `compareTo`, Schnittstellen, abstrakte Klassen, Generics, Pakete und Module, Records, Pattern Matching auf Objekten, `Optional` |
| Häufig verwendete Java-Klassen | Zeichenketten, Arrays, Collections (einschließlich Sequenced Collections), **Stream API** und `Gatherers`, Text- und Binärdateien (`java.nio.file`), JSON mit Jackson 3, reguläre Ausdrücke |
| Schichtenarchitekturen | Schichten [DAO] / [Business] / [UI], Multimodul-Maven-Projekte, Unit-Tests mit **JUnit 6**, **Dependency Injection** mit Spring |
| Funktionale Schnittstellen, Lambdas und Ereignisse | `java.util.function`, Lambdas, Methodenreferenzen, Closures, Komposition, Ereignis-Listener, `PropertyChangeSupport` |
| Ausführungs-Threads | `Thread`, **virtuelle Threads**, `synchronized`, `ReentrantLock`, `Condition`, atomare Operationen, `Semaphore`, `CountDownLatch`, nebenläufige Collections, `ExecutorService`, Fork/Join, `ThreadLocal`, `ScopedValue` |
| Asynchrone Programmierung | `CompletableFuture` und virtuelle Threads, Komposition, Ausnahmen, Abbruch und Timeouts, Fortschritt, asynchrone Ein-/Ausgabe, `Flow`, Structured Concurrency (Überblick) |
| Datenbankzugriff mit JDBC | MySQL, MySQL Connector/J, `DataSource` und HikariCP, parametrisierte Abfragen und SQL-Injection, Transaktionen, Batches, `CachedRowSet` |
| **Hibernate** | Entitäten, `SessionFactory` / `Session`, CRUD, Persistenzkontext, HQL und Criteria API, Beziehungen und Lazy Loading, Migrationen, optimistische Nebenläufigkeit, native SQL, `StatelessSession`, Spring ORM und `@Transactional` |
| Webprogrammierung | TCP/IP, IPv6, `InetAddress`, TCP-Clients und -Server (ein virtueller Thread pro Client), HTTP, `HttpClient`, SMTP |
| Webservices | REST / JSON mit **Spring Boot 4**, Java-Konsolenclients, JavaScript-Webclient, Node.js-Client |

## Der rote Faden: ein Einkommensteuerrechner in 9 Versionen

Im Verlauf des Kurses bauen wir Version für Version eine Anwendung zur **Berechnung der Einkommensteuer** auf:

- **Version 1**: ein einziges Programm; **Version 2**: Klassen und Schnittstellen; **Version 3**: Daten, die aus einer Text- oder JSON-Datei gelesen werden;
- **Versionen 4 und 5**: eine Schichtenarchitektur mit Maven-Modulen, getestet mit JUnit und per Dependency Injection mit Spring integriert;
- **Versionen 6 und 7**: in einer MySQL-Datenbank gespeicherte Daten, die zunächst mit JDBC und dann mit Hibernate gelesen werden;
- **Version 8**: ein TCP-Server zur Steuerberechnung und sein Client;
- **Version 9**: ein REST-Webservice mit Spring Boot, sein Konsolenclient und sein Webclient.

## Technologien

Java 25 · JDK 25 · Maven 3.9 · IntelliJ IDEA · VS Code · JUnit 6 · Spring Framework 7 · Jackson 3 · MySQL 8 · MySQL Connector/J 9 · HikariCP · Hibernate ORM 7.4 · Jakarta Persistence 3.2 · Spring Boot 4.1 · Laragon

## Voraussetzungen

- Vorherige Programmiererfahrung in einer beliebigen Sprache.
- Ein [JDK 25](https://adoptium.net) (Eclipse Temurin oder eine andere Distribution), [Maven](https://maven.apache.org) und eine IDE ([IntelliJ IDEA](https://www.jetbrains.com/idea/) oder [VS Code](https://code.visualstudio.com) mit dem Extension Pack for Java); [Laragon](https://laragon.org) für MySQL (Kapitel zu Datenbanken). Anleitungen zur Installation finden sich im Kurs.

## Autor

Dieser Kurs und sein Code wurden von **Claude**, der KI von [Anthropic](https://www.anthropic.com) (Oktober 2026), im Auftrag von Serge Tahé geschrieben, auf der Grundlage seines C#-14-Kurses.

Prüfer: [Serge Tahé](https://stahe.github.io)
