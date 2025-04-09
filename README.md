## Banknotes and Coins
### Problem Statement
Read a value of floating point with two decimal places. This represents a monetary value. After this, calculate the smallest possible number of notes and coins on which the value can be decomposed. The considered notes are of 100, 50, 20, 10, 5, 2. The possible coins are of 1, 0.50, 0.25, 0.10, 0.05 and 0.01. Print the message “NOTAS:” followed by the list of notes and the message “MOEDAS:” followed by the list of coins.

### Input
```c
double money;
int bankNote[] = {100, 50, 20, 10, 5, 2};
double coins[] = {1.0, 0.50, 0.25, 0.10, 0.05, 0.01};
// take input
scanf("%lf", &money);
// convert the money float to integer
int amount = money * 100;
```
### Calculate note:
```c
 for (int i = 0; i < sizeof(bankNote) / sizeof(bankNote[0]); i++)
    { // calculate the notes
        int notes = amount / (bankNote[i] * 100);
        amount %= (bankNote[i] * 100);
        // print the note
        printf("%d nota(s) de R$ %d.00\n", notes, bankNote[i]);
    }
```
### Calculate Coins:
```c
 for (int i = 0; i < sizeof(coins) / sizeof(coins[0]); i++)
    { // calculate the coins
        int coin = amount / (int)(coins[i] * 100);
        amount %= (int)(coins[i] * 100);
        // print the coins
        printf("%d moeda(s) de R$ %.2lf\n", coin, coins[i]);
    }
```
`Note: % operator in C only works for integers.`
