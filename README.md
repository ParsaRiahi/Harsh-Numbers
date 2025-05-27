# Harsh-Numbers

#include <stdio.h>

int sizeCal(int input)
{
    int size = 0;

    if(input == 0)
    {
        return 1;
    }

    while(input > 0)
    {
        input /= 10;
        size++; 
    }
    return size;
}

void numToArray(int *array, int size, int input)
{
    for(int i = size - 1; i >= 0; i--)
    {
        array[i] = input % 10;
        input /= 10;
    }
    
}

int main(void)
{
    int input;
    int size;
    int sum = 0;

    printf("Enter a number: ");
    scanf("%d", &input);
    
    size = sizeCal(input);
    int array[size];

    numToArray(array, size, input);

    printf("Numbers:\n");
    for(int i = 0; i < size; i++)
    {
        printf("%d ", array[i]);
    }
    printf("\n");

    for(int i = 0; i < size; i++)
    {
        sum = sum + array[i];
    }
    printf("Sum: %d\n", sum);

    if(input % sum == 0)
    {
        printf("%d is a harshed number.\n", input);
    }
    else
    {
        printf("%d is not a harshed number.\n", input);
    }

    return 0;
}
