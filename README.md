# Miguel Ribeiro - Software Developer

Computer Engineering student at **ISEP** (Instituto Superior de Engenharia do Porto), passionate about building robust software solutions. Experienced in **Java**, **Object-Oriented Programming**, and **software architecture**, with a strong foundation in full-stack development and systems design.

---

## Projects

| Project | Description | Technologies |
|---------|-------------|--------------|
| Eigenfaces | Image processing system using eigenfaces for face recognition, developed in the 1st semester | Java, Matrix Operations, CSV I/O |
| Warehouse & Train Station Management | Database-driven application for managing warehouses and train stations | Java, Oracle DB, JDBC |
| Trains Game Simulator] | A complete train simulation game with GUI, route planning, and time simulation | Java, JavaFX, Jackson, Maven |
| Airport Network Infrastructure | Network infrastructure project for airport communications | C, Socket Programming, TCP/UDP |
| Airport Infrastructure Management | Back-office management and flight simulation system for air traffic control | Java, Spring, PlantUML |

---

## Technical Skills

- **Languages:** Java, C, SQL, Python
- **Frameworks:** JavaFX, Spring Boot
- **Databases:** Oracle DB, JDBC
- **Tools:** Maven, Git, IntelliJ IDEA, PlantUML
- **Concepts:** OOP, Design Patterns, Unit Testing, MVC Architecture, JSON Serialization

---

## Code Showcase

Below is an example from the **Trains Game Simulator** project, demonstrating OOP principles such as encapsulation, validation, and proper use of collections:

```java
public class Train {
    private final Locomotive locomotive;
    private final List<Carriage> carriages;
    private final String serialNumber;
    private Route assignedRoute;
    private boolean isExecutingRoute;

    public Train(Locomotive locomotive, List<Carriage> carriages, String serialNumber) {
        if (locomotive == null) throw new IllegalArgumentException("Locomotive cannot be null.");
        if (carriages == null) throw new IllegalArgumentException("Carriages list cannot be null.");
        this.locomotive = locomotive;
        this.carriages = new ArrayList<>(carriages);
        this.serialNumber = serialNumber;
        this.assignedRoute = null;
        this.isExecutingRoute = false;
    }

    public int getMaxCargoCapacity() {
        int totalCapacity = 0;
        for (Carriage carriage : carriages) {
            totalCapacity += carriage.getMaxCargo();
        }
        return totalCapacity;
    }

    public boolean addCarriage(Carriage carriage) {
        if (carriage == null) throw new IllegalArgumentException("Carriage cannot be null.");
        return this.carriages.add(carriage);
    }

    public static String generateSerialNumber() {
        int firstDigit = (int) (Math.random() * 10);
        char letter = (char) ('A' + (int) (Math.random() * 26));
        int lastTwoDigits = (int) (Math.random() * 100);
        return String.format("%d%c%02d", firstDigit, letter, lastTwoDigits);
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Train train = (Train) o;
        return serialNumber.equals(train.serialNumber);
    }

    @Override
    public int hashCode() {
        return Objects.hash(serialNumber);
    }
}
```

