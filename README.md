# StudentManagement
برنامج بلغة C++ لإدارة بيانات الطلاب، يمكنه حفظ الاسم، العمر، والمعدل، ويحسب التقدير تلقائيًا ويعرض بيانات الطالب بشكل مرتب.

#include <iostream>
using namespace std;

class Student {
private:
    string name;
    int age;
    double gpa;

public:
    Student() {
        name = "غير معروف";
        age = 0;
        gpa = 0.0;
    }

    Student(string n, int a, double g) {
        setName(n);
        setAge(a);
        setGpa(g);
    }

    void setName(string n) { name = n; }
    string getName() { return name; }

    void setAge(int a) { age = (a >= 0) ? a : 0; }
    int getAge() { return age; }

    void setGpa(double g) { gpa = (g >= 0.0 && g <= 4.0) ? g : 0.0; }
    double getGpa() { return gpa; }

    void printInfo() {
        cout << "الاسم: " << name << endl;
        cout << "العمر: " << age << endl;
        cout << "المعدل: " << gpa << endl;
        cout << "التقدير: " << getGrade() << endl;
    }

    string getGrade() {
        if (gpa >= 3.7) return "امتياز";
        else if (gpa >= 3.0) return "جيد جدا";
        else if (gpa >= 2.0) return "جيد";
        else if (gpa >= 1.0) return "مقبول";
        else return "راسب";
    }
};

int main() {
    Student s1;
    s1.printInfo();

    Student s2("محمد", 17, 3.5);
    s2.printInfo();

    return 0;
}
