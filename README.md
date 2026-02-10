#include <iostream>
#include <fstream>
#include <string>
#include <bitset>

using namespace std;

void processShift(int value, string op, int shift) {
    int result = (op == "<<") ? (value << shift) : (value >> shift);

    cout << "isxodnoe " << value << " (" << bitset<16>(value) << ")" << endl;
    cout << "operasciya " << op << " " << shift << endl;
    cout << "rezulytat " << result << " (" << bitset<16>(result) << ")" << endl;
    cout << "--------------------------" << endl;
}

int main() {
    int choice, n, s;
    string op;

    cout << "1 - konsol, 2 - fayl (input.txt): ";
    cin >> choice;

    if (choice == 1) {
        cout << "vvod ";
        cin >> n >> op >> s;
        processShift(n, op, s);
    }
    else {
        ifstream file("input.txt");
        if (file >> n >> op >> s) {
            processShift(n, op, s);
        }
        else {
            cout << "oshibka" << endl;
        }
    }

    return 0;
}
