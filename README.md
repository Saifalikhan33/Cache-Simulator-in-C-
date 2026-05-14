#include <iostream>
using namespace std;

int main() {
    int cache[4] = {-1, -1, -1, -1};
    int memory[] = {1, 2, 3, 1, 4, 2, 5};
    int hits = 0, misses = 0;

    for (int i = 0; i < 7; i++) {
        int index = memory[i] % 4;

        if (cache[index] == memory[i]) {
            hits++;
            cout << "Hit: " << memory[i] << endl;
        } else {
            misses++;
            cache[index] = memory[i];
            cout << "Miss: " << memory[i] << endl;
        }
    }

    cout << "\nTotal Hits: " << hits << endl;
    cout << "Total Misses: " << misses << endl;

    return 0;
}
