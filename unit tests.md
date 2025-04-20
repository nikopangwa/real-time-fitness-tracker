
package tests;

import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

import creational_patterns.simple_factory.*;
import creational_patterns.factory_method.*;
import creational_patterns.abstract_factory.*;
import creational_patterns.builder.*;
import creational_patterns.prototype.*;
import creational_patterns.singleton.*;

public class CreationalPatternTests {

    // Simple Factory Test
    @Test
    void testSimpleFactory() {
        Vehicle car = VehicleFactory.createVehicle("Car");
        assertNotNull(car);
        assertEquals("Car", car.getType());
    }

    // Factory Method Test
    @Test
    void testFactoryMethod() {
        PaymentProcessor processor = new CreditCardProcessorFactory().createProcessor();
        assertTrue(processor instanceof CreditCardProcessor);
    }

    // Abstract Factory Test
    @Test
    void testAbstractFactory() {
        GUIFactory factory = new WindowsGUIFactory();
        Button button = factory.createButton();
        assertEquals("Windows Button", button.render());
    }

    // Builder Pattern Test
    @Test
    void testBuilder() {
        Pizza pizza = new PizzaBuilder().addCheese().addToppings("Olives").build();
        assertTrue(pizza.hasCheese());
        assertTrue(pizza.getToppings().contains("Olives"));
    }

    // Prototype Pattern Test
    @Test
    void testPrototype() throws CloneNotSupportedException {
        Circle original = new Circle(5);
        Circle clone = (Circle) original.clone();
        assertEquals(original.getRadius(), clone.getRadius());
        assertNotSame(original, clone);
    }

    // Singleton Pattern Test
    @Test
    void testSingleton() {
        DatabaseConnection instance1 = DatabaseConnection.getInstance();
        DatabaseConnection instance2 = DatabaseConnection.getInstance();
        assertSame(instance1, instance2);
    }
} 
