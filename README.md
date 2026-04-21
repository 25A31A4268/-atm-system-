#include <iostream>
using namespace std;

class Account {
private:
    int accNumber;
    int pin;
    double balance;

public:
    // Constructor
    Account(int acc, int p, double bal) {
        accNumber = acc;
        pin = p;
        balance = bal;
    }

    // PIN Verification
    bool verifyPIN(int enteredPin) {
        return (enteredPin == pin);
    }

    // Deposit Function
    void deposit(double amount) {
        balance += amount;
        cout << "Amount Deposited Successfully!\n";
    }

    // Withdraw Function
    void withdraw(double amount) {
        if (amount > balance) {
            cout << "Insufficient Balance!\n";
        } else {
            balance -= amount;
            cout << "Please collect your cash.\n";
        }
    }

    // Check Balance
    void showBalance() {
        cout << "Current Balance: " << balance << endl;
    }
};

int main() {
    int acc, pin, choice;
    double amount;

    // Create Account object
    Account user(12345, 1111, 5000.0);

    cout << "Enter Account Number: ";
    cin >> acc;

    cout << "Enter PIN: ";
    cin >> pin;

    if (acc == 12345 && user.verifyPIN(pin)) {
        cout << "\nLogin Successful!\n";

        do {
            cout << "\n--- ATM MENU ---\n";
            cout << "1. Check Balance\n";
            cout << "2. Deposit\n";
            cout << "3. Withdraw\n";
            cout << "4. Exit\n";
            cout << "Enter choice: ";
            cin >> choice;

            switch (choice) {
                case 1:
                    user.showBalance();
                    break;

                case 2:
                    cout << "Enter amount to deposit: ";
                    cin >> amount;
                    user.deposit(amount);
                    break;

                case 3:
                    cout << "Enter amount to withdraw: ";
                    cin >> amount;
                    user.withdraw(amount);
                    break;

                case 4:
                    cout << "Thank you for using ATM!\n";
                    break;

                default:
                    cout << "Invalid choice!\n";
            }

        } while (choice != 4);

    } else {
        cout << "Invalid Account Number or PIN!\n";
    }

    return 0;
}# -atm-system-
A simple ATM system built in C++ using object-oriented programming concepts. The program supports PIN verification, balance checking, deposit, and withdrawal operations through a menu-driven interface. It demonstrates classes, objects, encapsulation, and basic control structures, making it ideal for beginners.
