## Лаба 02 написанна на С++


```cpp
#include <iostream>
#include <vector>
#include <string>
#include <map>
#include <cmath>

using namespace std;

//Идентификаторы
string name = "Denis";
const int birthYear = 1998;

void greet(const string& name) {
    cout << "Hello, " << name << endl;
}

//Циклы
vector<int> range(int start, int end) {
    vector<int> result;
    for (int i = start; i <= end; ++i) result.push_back(i);
    return result;
}

vector<int> rangeOdd(int start, int end) {
    vector<int> result;
    for (int i = start; i <= end; ++i)
        if (i % 2 != 0) result.push_back(i);
    return result;
}

//Функции
double average(double a, double b) {
    return (a + b) / 2.0;
}

int square(int x) {
    return x * x;
}

int cube(int x) {
    return x * x * x;
}

vector<double> calculate() {
    vector<double> result;
    for (int i = 0; i <= 9; ++i)
        result.push_back(average(square(i), cube(i)));
    return result;
}

//Объекты
struct User {
    string name;
    string city;
};

User createUser(const string& name, const string& city) {
    return User{name, city};
}

//Коллекции
struct Contact {
    string name;
    string phone;
};

vector<Contact> phoneBook = {
    {"Marcus Aurelius", "+380445554433"},
    {"Denis", "+447123456789"}
};

string findPhoneByNameArray(const string& name) {
    for (const auto& contact : phoneBook)
        if (contact.name == name) return contact.phone;
    return "Not found";
}

map<string, string> phoneHash = {
    {"Marcus Aurelius", "+380445554433"},
    {"Denis", "+447123456789"}
};

string findPhoneByNameHash(const string& name) {
    return phoneHash.count(name) ? phoneHash[name] : "Not found";
}

int main() {
    greet(name);
    auto nums = range(15, 30);
    auto odds = rangeOdd(15, 30);
    auto results = calculate();

    User u = createUser("Marcus Aurelius", "Roma");
    cout << "User: " << u.name << ", " << u.city << endl;

    cout << findPhoneByNameArray("Denis") << endl;
    cout << findPhoneByNameHash("Marcus Aurelius") << endl;

    return 0;
}

```
