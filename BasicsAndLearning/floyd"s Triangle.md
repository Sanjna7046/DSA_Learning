
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
