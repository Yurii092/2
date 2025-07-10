#include <stdio.h>

int gcd(int a, int b) {
    while (b != 0) {
        int temp = a % b;
        a = b;
        b = temp;
    }
    return a;
}

int lcm(int a, int b) {
    return (a / gcd(a, b)) * b;
}

int main() {
    int p;
    printf("Введіть кількість чисел: ");
    scanf("%d", &p);

    if (p < 2 || p > 20) {
        printf("Кількість чисел повинна бути в межах від 2 до 20.\n");
        return 1;
    }

    int numbers[20];
    printf("Введіть %d натуральних чисел: ", p);
    for (int i = 0; i < p; i++) {
        scanf("%d", &numbers[i]);
    }

    int result = numbers[0];
    for (int i = 1; i < p; i++) {
        result = lcm(result, numbers[i]);
    }

    printf("Найменше спільне кратне: %d\n", result);
    return 0;
}
