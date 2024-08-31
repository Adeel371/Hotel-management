 Hotel-management
 
#include <iostream>
#include <string>
#include <vector>

using namespace std;

class Hotel {
private:
    vector <Room> rooms;
    vector<Customer> customers;

public:
    void addRoom(Room room) {
        rooms.push_back(room);
    }

    void addCustomer(Customer customer) {
        customers.push_back(customer);
    }

    void displayRooms() {
        for (Room room : rooms) {
            cout << room.getRoomNumber() << " " << room.getRoomType() << endl;
        }
    }

    void displayCustomers() {
        for (Customer customer : customers) {
            cout << customer.getName() << " " << customer.getRoomNumber() << endl;
        }
    }
};

class Room {
private:
    int roomNumber;
    string roomType;

public:
    Room(int roomNumber, string roomType) {
        this->roomNumber = roomNumber;
        this->roomType = roomType;
    }

    int getRoomNumber() {
        return roomNumber;
    }

    string getRoomType() {
        return roomType;
    }
};

class Customer {
private:
    string name;
    int roomNumber;

public:
    Customer(string name, int roomNumber) {
        this->name = name;
        this->roomNumber = roomNumber;
    }

    string getName() {
        return name;
    }

    int getRoomNumber() {
        return roomNumber;
    }
};

int main() {
    Hotel hotel,Room;

    Room room1(101, "Single");
    Room room2(102, "Double");
    Room room3(103, "Suite");

    hotel.addRoom(room1);
    hotel.addRoom(room2);
    hotel.addRoom(room3);

    Customer customer1("John", 101);
    Customer customer2("Jane", 102);

    hotel.addCustomer(customer1);
    hotel.addCustomer(customer2);

    hotel.displayRooms();
    hotel.displayCustomers();

    return 0;
}
