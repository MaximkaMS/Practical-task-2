# Practical-task-2
#include <stdio.h>

// Функція для обчислення НСД двох чисел
int gcd(int a, int b) {
    if (b == 0)
        return a;
    return gcd(b, a % b);
}

// Функція для обчислення НСК різних чисел
int lcm(int numbers[], int count) {
    int result = numbers[0];
    for (int i = 1; i < count; i++) {
        result = (result * numbers[i]) / gcd(result, numbers[i]);
    }
    return result;
}

int main() {
    int count;
    printf("Введіть кількість чисел: ");
    scanf("%d", &count);

    int numbers[count];
    printf("Введіть числа, розділені пробілом: ");
    for (int i = 0; i < count; i++) {
        scanf("%d", &numbers[i]);
    }

    int result = lcm(numbers, count);
    printf("Найменше спільне кратне: %d\n", result);

    return 0;
}
