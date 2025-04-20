package src;

import java.util.*;

// ---------------------
// User.java
// ---------------------
public class User {
    private String userId;
    private String name;
    private List<Loan> loans = new ArrayList<>();

    public User(String userId, String name) {
        this.userId = userId;
        this.name = name;
    }

    public void borrowBook(Book book) {
        Loan loan = new Loan(this, book);
        loans.add(loan);
        book.checkOut();
    }

    public void returnBook(Book book) {
        for (Loan loan : loans) {
            if (loan.getBook().equals(book)) {
                loan.endLoan();
                book.returnBook();
                break;
            }
        }
    }
}

// ---------------------
// Book.java
// ---------------------
public class Book {
    private String bookId;
    private String title;
    private String status;

    public Book(String bookId, String title) {
        this.bookId = bookId;
        this.title = title;
        this.status = "available";
    }

    public void checkOut() {
        this.status = "checked out";
    }

    public void returnBook() {
        this.status = "available";
    }
}

// ---------------------
// Loan.java
// ---------------------
public class Loan {
    private String loanId;
    private Date dueDate;
    private User user;
    private Book book;

    public Loan(User user, Book book) {
        this.user = user;
        this.book = book;
        this.loanId = UUID.randomUUID().toString();
        Calendar c = Calendar.getInstance();
        c.add(Calendar.DATE, 14);
        this.dueDate = c.getTime();
    }

    public void endLoan() {
        // logic to mark loan complete
    }

    public Book getBook() {
        return book;
    }

    public double calculateFine() {
        // dummy fine calculation
        return 0.0;
    }
}

// ---------------------
// FitnessSession.java
// ---------------------
public class FitnessSession {
    private String sessionId;
    private Date date;
    private String type;
    private int durationMinutes;

    public FitnessSession(String type, int durationMinutes) {
        this.sessionId = UUID.randomUUID().toString();
        this.date = new Date();
        this.type = type;
        this.durationMinutes = durationMinutes;
    }
}

// ---------------------
// Trainer.java
// ---------------------
public class Trainer {
    private String trainerId;
    private String name;

    public Trainer(String trainerId, String name) {
        this.trainerId = trainerId;
        this.name = name;
    }

    public WorkoutPlan createPlan(String goal) {
        return new WorkoutPlan(goal);
    }
}

// ---------------------
// WorkoutPlan.java
// ---------------------
public class WorkoutPlan implements Cloneable {
    private String planId;
    private String goal;

    public WorkoutPlan(String goal) {
        this.planId = UUID.randomUUID().toString();
        this.goal = goal;
    }

    @Override
    public WorkoutPlan clone() {
        try {
            return (WorkoutPlan) super.clone();
        } catch (CloneNotSupportedException e) {
            throw new AssertionError();
        }
    }
}

// ---------------------
// Notification.java
// ---------------------
public class Notification {
    private String message;

    public Notification(String message) {
        this.message = message;
    }

    public void send() {
        System.out.println("Sending: " + message);
    }
}

