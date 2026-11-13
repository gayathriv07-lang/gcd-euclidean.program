include <stdio.h>

unsigned long long findGCD(long long a, long long b)
{
    unsigned long long x = (a < 0) ? 0ULL - (unsigned long long)a : (unsigned long long)a;
    unsigned long long y = (b < 0) ? 0ULL - (unsigned long long)b : (unsigned long long)b;

    while (y != 0)
    {
        unsigned long long temp = y;
        y = x % y;
        x = temp;
    }

    return x;
}

int main()
{
    long long num1, num2;

    printf("================================\n");
    printf("     GCD CALCULATOR\n");
    printf("================================\n");

    printf("Enter first number: ");

    if (scanf("%lld", &num1) != 1)
    {
        printf("Invalid input!\n");
        return 1;
    }

    printf("Enter second number: ");

    if (scanf("%lld", &num2) != 1)
    {
        printf("Invalid input!\n");
        return 1;
    }

    if (num1 == 0 && num2 == 0)
    {
        printf("GCD is undefined for two zeros.\n");
    }
    else
    {
        printf("\nGreatest Common Divisor: %llu\n",
               findGCD(num1, num2));
    }
printf("---------------------------------\n");
return 0;
}
