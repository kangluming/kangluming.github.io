```C++
#define _CRT_SECURE_NO_WARNINGS
/*

emplace_front、emplace 和 emplace_back 

*/ 

#include <iostream>
#include <list>
#include <vector>
using namespace std;

class Student {
public:
	Student(string name,int age):name_(name),age_(age) {}

	void print() {
		cout << name_ << age_ << endl;
	}
	string name_;
	int age_;
};

int main(){
	cout << "emplace" << endl;
	list<Student> s1;
	s1.emplace(s1.end(), Student("小明", 18));
	s1.emplace(s1.end(), Student("小王", 19));
	s1.emplace(s1.end(), Student("小刚", 20));
	for (list<Student>::iterator it = s1.begin(); it != s1.end(); it++) {
		cout << it->name_ << "age" << it->age_ << endl;
	}
	s1.pop_front();
	s1.pop_front();
	s1.pop_front();

	
	cout << "emplace_back" << endl;
	s1.emplace_back(Student("小明", 18));
	s1.emplace_back(Student("小王", 19));
	s1.emplace_back(Student("小刚", 20));
	for (list<Student>::iterator it = s1.begin(); it != s1.end(); it++) {
		cout << it->name_ << "age" << it->age_ << endl;
	}

	s1.pop_front();
	s1.pop_front();
	s1.pop_front();
	cout << "emplace_front" << endl;
	s1.emplace_front(Student("小明", 18));
	s1.emplace_front(Student("小王", 19));
	s1.emplace_front(Student("小刚", 20));
	for (list<Student>::iterator it = s1.begin(); it != s1.end(); it++) {
		cout << it->name_ << "age" << it->age_ << endl;
	}

}

```