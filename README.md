# Hanoi-Tower
Implement the solution for Hanoi Tower using Recursion


public class TowerOfHanoi {
    // Recursive function to solve Tower of Hanoi
    public static void hanoi(int n, char source, char auxiliary, char destination) {
        if (n == 1) {
            System.out.println("Move disk 1 from " + source + " to " + destination);
            return;
        }
        
        // Move (n-1) disks from source to auxiliary using destination as buffer
        hanoi(n - 1, source, destination, auxiliary);
        
        // Move the nth disk from source to destination
        System.out.println("Move disk " + n + " from " + source + " to " + destination);
        
        // Move the (n-1) disks from auxiliary to destination using source as buffer
        hanoi(n - 1, auxiliary, source, destination);
    }

    // Main function to test Tower of Hanoi
    public static void main(String[] args) {
        int n = 3; // Number of disks
        System.out.println("Solution for Tower of Hanoi with " + n + " disks:");
        hanoi(n, 'A', 'B', 'C'); // A = Source, B = Auxiliary, C = Destination
    }
}
