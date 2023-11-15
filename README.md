import java.util.concurrent.atomic.AtomicInteger;

public class AtomicIntegerDemo {

    public static void main(String[] args) {
        AtomicInteger number = new AtomicInteger(0);

        // Create two threads and start them.
        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                number.incrementAndGet();
            }
        });
        Thread t2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                number.incrementAndGet();
            }
        });
        t1.start();
        t2.start();

        // Wait for both threads to finish.
        t1.join();
        t2.join();

        // Print the final value of the number.
        System.out.println(number);
    }
}
# repository-one
