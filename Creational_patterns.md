
package creational_patterns.simplefactory;

public class BookFactory {
    public static Book createBook(String genre) {
        switch (genre.toLowerCase()) {
            case "fiction": return new Book("Fiction", "123456", "Available");
            case "nonfiction": return new Book("Non-Fiction", "654321", "Available");
            default: throw new IllegalArgumentException("Unknown genre: " + genre);
        }
    }
}

class Book {
    private String title;
    private String ISBN;
    private String status;

    public Book(String title, String ISBN, String status) {
        this.title = title;
        this.ISBN = ISBN;
        this.status = status;
    }

    public void checkOut() {
        this.status = "Checked Out";
    }

    public void returnBook() {
        this.status = "Available";
    }
}


package creational_patterns.factorymethod;

public interface LoanFactory {
    Loan createLoan();
}

class StandardLoanFactory implements LoanFactory {
    public Loan createLoan() {
        return new StandardLoan();
    }
}

class PremiumLoanFactory implements LoanFactory {
    public Loan createLoan() {
        return new PremiumLoan();
    }
}

abstract class Loan {
    protected String loanType;
    public abstract double calculateFine(int daysLate);
}

class StandardLoan extends Loan {
    public StandardLoan() { this.loanType = "Standard"; }

    public double calculateFine(int daysLate) {
        return daysLate * 1.0;
    }
}

class PremiumLoan extends Loan {
    public PremiumLoan() { this.loanType = "Premium"; }

    public double calculateFine(int daysLate) {
        return daysLate * 0.5;
    }
}


package creational_patterns.abstractfactory;

// Abstract Factory
public interface GUIFactory {
    Button createButton();
}

// Concrete Factories
class WindowsGUIFactory implements GUIFactory {
    public Button createButton() {
        return new WindowsButton();
    }
}

class MacGUIFactory implements GUIFactory {
    public Button createButton() {
        return new MacButton();
    }
}

// Abstract Product
interface Button {
    void render();
}

// Concrete Products
class WindowsButton implements Button {
    public void render() {
        System.out.println("Rendering Windows Button");
    }
}

class MacButton implements Button {
    public void render() {
        System.out.println("Rendering Mac Button");
    }
}

package creational_patterns.builder;

public class Report {
    private String title;
    private String body;
    private String footer;

    public void setTitle(String title) { this.title = title; }
    public void setBody(String body) { this.body = body; }
    public void setFooter(String footer) { this.footer = footer; }

    public void display() {
        System.out.println(title);
        System.out.println(body);
        System.out.println(footer);
    }
}

interface ReportBuilder {
    void buildTitle();
    void buildBody();
    void buildFooter();
    Report getReport();
}

class SimpleReportBuilder implements ReportBuilder {
    private Report report = new Report();

    public void buildTitle() { report.setTitle("Simple Report Title"); }
    public void buildBody() { report.setBody("Report Body Content"); }
    public void buildFooter() { report.setFooter("Report Footer"); }

    public Report getReport() { return report; }
}

class Director {
    public void construct(ReportBuilder builder) {
        builder.buildTitle();
        builder.buildBody();
        builder.buildFooter();
    }
}


package creational_patterns.prototype;

import java.util.HashMap;

class UserProfile implements Cloneable {
    private String name;
    private String role;

    public UserProfile(String name, String role) {
        this.name = name;
        this.role = role;
    }

    public Object clone() {
        try {
            return super.clone();
        } catch (CloneNotSupportedException e) {
            return null;
        }
    }

    public String getRole() { return role; }
}

public class UserCache {
    private static HashMap<String, UserProfile> cache = new HashMap<>();

    static {
        cache.put("admin", new UserProfile("Admin User", "Admin"));
        cache.put("member", new UserProfile("Member User", "Member"));
    }

    public static UserProfile getProfile(String type) {
        return (UserProfile) cache.get(type).clone();
    }
}


package creational_patterns.singleton;

public class DatabaseConnection {
    private static volatile DatabaseConnection instance;

    private DatabaseConnection() {
        System.out.println("Initializing DB connection...");
    }

    public static DatabaseConnection getInstance() {
        if (instance == null) {
            synchronized(DatabaseConnection.class) {
                if (instance == null) {
                    instance = new DatabaseConnection();
                }
            }
        }
        return instance;
    }

    public void connect() {
        System.out.println("Connected to DB.");
    }
}


