# task-7
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main() {
    int n;
    cin >> n;

    vector<int> arr(n);
    for (int i = 0; i < n; ++i) {
        cin >> arr[i];
    }

    long long suma = 0;
    for (int x : arr) {
        suma += x;
    }

    int min_val = arr[0];
    int min_idx = 0;
    for (int i = 1; i < n; ++i) {
        if (arr[i] < min_val) {
            min_val = arr[i];
            min_idx = i;
        }
    }

    int max_val = arr[0];
    int max_idx = 0;
    for (int i = 1; i < n; ++i) {
        if (arr[i] > max_val) {
            max_val = arr[i];
            max_idx = i;
        }
    }

    int dodatni = 0;
    for (int x : arr) {
        if (x > 0) {
            dodatni++;
        }
    }

    for (int i = 0; i < n / 2; ++i) {
        swap(arr[i], arr[n - 1 - i]);
    }

    cout << "suma " << suma << endl;
    cout << "min " << min_val << " index " << min_idx << endl;
    cout << "max " << max_val << " index " << max_idx << endl;
    cout << "dodatni " << dodatni << endl;
    
    cout << "navpaky";
    for (int i = 0; i < n; ++i) {
        cout << " " << arr[i];
    }
    cout << endl;

    return 0;
}
