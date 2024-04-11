

#include <iostream>
#include <string>

using namespace std;
// оголошую клас "Людина"
class Human {
protected:
	int x; 
	int y;
	int age;
	string firstName;
	string lastName;

public:
	// конструктор класу "Людина" 
	Human(int x, int y, int age, const string& firstName, const string& lastName)
		: x(x), y(y), age(age), firstName(firstName), lastName(lastName)
	{}

	//  Метод для збільшення координат на одиницю
	void move() {
		x++;
		y++;
	}

	// Метод для виведення інформації про людину 
	void displayInfo() const {
		cout << "Name: " << age << endl;
		cout << "Coordinates:  (" << x << ", " << y << ")" << endl;
	}
};

// Оголошую клас "Чоловік" який успадковує клас "Людина"
class Man : public Human {
private:
	int height;
	int weight;

public:
	Man(int x, int y, int age, const string& firstName, const string& lastName, int height, int weight)
		: Human(x, y, age, firstName, lastName), height(height), weight(weight) {}
	void eat() {
		cout << firstName << " is eating." << endl;
	}
	
	void sleep() {
		cout << firstName << " is sleeping." << endl;
	}
	void move() {
		x += 2;
		x += 2;
	}
	void displayInfo() const {
		Human::displayInfo();
		cout << "height: " << height << " cm" << endl;
		cout << "weight: " << weight << " kg" << endl;
	}
};
int main() {
	Man Danya(0, 0, 30, "Danya", "Doe", 180, 82);
	danya.displayInfo();
	cout << endl;
	danya.move();
	danya.displayInfo();
	danya.eat();
	danya.sleep();
	
	return 0;
}
