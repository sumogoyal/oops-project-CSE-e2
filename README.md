# oops-project-CSE-e2
#include <iostream>
#include <string>
using namespace std;

class Student {
protected:
    string name;
    int rollNo;
    float marks;

public:
    Student(string n, int r, float m) {
        name = n;
        rollNo = r;
        marks = m;
    }

    void displayStudent() {
        cout << "\nName: " << name;
        cout << "\nRoll No: " << rollNo;
        cout << "\nMarks: " << marks;
    }
};

class Result : public Student {
public:
    Result(string n, int r, float m) : Student(n, r, m) {}

    void showResult() {
        displayStudent();

        if (marks >= 40)
            cout << "\nResult: PASS";
        else
            cout << "\nResult: FAIL";
    }
};

int main() {
    string name;
    int rollNo;
    float marks;

    cout << "Enter Student Name: ";
    cin >> name;

    cout << "Enter Roll Number: ";
    cin >> rollNo;

    cout << "Enter Marks: ";
    cin >> marks;

    Result s(name, rollNo, marks);

    cout << "\n--- Student Result ---";
    s.showResult();

    return 0;
}
