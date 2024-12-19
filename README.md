#include <stdio.h>

int main() {
    int choice;
    float balance = 2000.0; 
    float amount;

    while (1) {
        printf("\n--- Virtual ATM ---\n");
        printf("1. Check Balance\n");
        printf("2. Deposit Money\n");
        printf("3. Withdraw Money\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("\nYour current balance: $%.2f\n", balance);
                break;
            case 2:
                printf("\nEnter deposit amount: $");
                scanf("%f", &amount);
                if (amount > 0) {
                    balance += amount;
                    printf("Deposit successful. Updated balance: $%.2f\n", balance);
                } else {
                    printf("Invalid amount! Try again.\n");
                }
                break;
            case 3:
                printf("\nEnter withdrawal amount: $");
                scanf("%f", &amount);
                if (amount > 0 && amount <= balance) {
                    balance -= amount;
                    printf("Withdrawal successful. Updated balance: $%.2f\n", balance);
                } else if (amount > balance) {
                    printf("Insufficient balance!\n");
                } else {
                    printf("Invalid amount! Try again.\n");
                }
                break;
            case 4:
                printf("\nThank you for using Virtual ATM. Goodbye!\n");
                return 0;
            default:
                printf("\nInvalid choice! Please select a valid option.\n");
        }
    }

    return 0;
}
