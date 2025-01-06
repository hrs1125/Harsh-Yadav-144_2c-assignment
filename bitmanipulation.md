# Harsh-Yadav-144_2c-assignment

#include <stdio.h>
int main() {
    int n, count = 0;
    printf("Enter a number: ");
    scanf("%d", &n);

    while (n > 0) {
        count += (n & 1);
        n >>= 1;
    }

    printf("Number of set bits: %d\n", count);
    return 0;
}
//Check if a Number is a Power of Two
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);

    if (n > 0 && (n & (n - 1)) == 0)
        printf("%d is a power of two.\n", n);
    else
        printf("%d is not a power of two.\n", n);

    return 0;
}
// Find Position of the Only Set Bit
#include <stdio.h>

int findPstn(int n) {
    if (n <= 0 || (n & (n - 1)) != 0) return -1;
    int pos = 1;
    while ((n & 1) == 0) {
        n >>= 1;
        pos++;
    }
    return pos;
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    int pos = findPstn(num);
    if (pos == -1)
        printf("The number does not have only one set bit.\n");
    else
        printf("The position of the only set bit is %d.\n", pos);
    return 0;
}
//Count Total Set Bits from 1 to n
#include <stdio.h>

int countSetBits(int n) {
    int count = 0;
    for (int i = 1; i <= n; i++) {
        int num = i;
        while (num > 0) {
            count += (num & 1);
            num >>= 1;
        }
    }
    return count;
}

int main() {
    int n;
    printf("Enter the number: ");
    scanf("%d", &n);
    printf("Total set bits from 1 to %d: %d\n", n, countSetBits(n));
    return 0;
}
//Genrate Power Set
#include <stdio.h>
#include <math.h>

void printPowerSet(char set[], int n) {
    int powerSetSize = pow(2, n);
    for (int i = 0; i < powerSetSize; i++) {
        printf("{ ");
        for (int j = 0; j < n; j++) {
            if (i & (1 << j))
                printf("%c ", set[j]);
        }
        printf("}\n");
    }
}

int main() {
    char set[] = {'a', 'b', 'c'};
    int n = sizeof(set) / sizeof(set[0]);
    printPowerSet(set, n);
    return 0;
}



