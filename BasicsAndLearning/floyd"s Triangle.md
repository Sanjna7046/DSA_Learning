
```cpp
int rows;
    int number = 1;

    cout << "Enter the number of rows: ";
    cin >> rows;

    // Outer loop handles the total number of rows
    for (int i = 1; i <= rows; i++) {
        // Inner loop handles the numbers printed in each row
        for (int j = 1; j <= i; j++) {
            cout << number << " ";
            number++; // Increment the counter
        }
        // Move to the next line after completing a row
        cout << "\n";


//OUTPUT
1 
2 3 
4 5 6 
7 8 9 10 
11 12 13 14 15

```

## Tower of Hanoi
```cpp
void towerOfHanoi(int n, char from_rod, char to_rod, char aux_rod)
{
if (n == 1)
{
printf("\nMove disk 1 from rod %c to rod %c", from_rod, to_rod);
return;
}
towerOfHanoi(n-1, from_rod, aux_rod, to_rod);
}
printf("\nMove disk %d from rod %c to rod %c", n, from_rod, to_rod);
towerOfHanoi(n-1, aux_rod, to_rod, from_rod);

```
