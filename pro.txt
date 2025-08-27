#include <stdio.h>

// Recursive function for Tower of Hanoi
void towerOfHanoi(int n, char from_rod, char aux_rod, char to_rod) {
    if (n == 1) {
        printf("Move disk 1 from rod %c to rod %c\n", from_rod, to_rod);
        return;
    }
    towerOfHanoi(n - 1, from_rod, to_rod, aux_rod);     // Step 1
    printf("Move disk %d from rod %c to rod %c\n", n, from_rod, to_rod); // Step 2
    towerOfHanoi(n - 1, aux_rod, from_rod, to_rod);     // Step 3
}

int main() {
    int n;  
    printf("Enter number of disks: ");
    scanf("%d", &n);

    printf("Steps to solve Tower of Hanoi with %d disks:\n\n", n);
    towerOfHanoi(n, 'A', 'B', 'C'); // A=Source, B=Auxiliary, C=Destination

    printf("\nTotal moves required: %d\n", (1 << n) - 1); // Formula 2^n - 1
    return 0;
}
