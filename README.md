//Programmer: Arashi Gautam
//Date: 2/24/2024
#include <iostream>
#include<string>

using namespace std;

//car struct

struct Car{
	string make;
	string model;
	int year;
	double price;	
};

//Function Prototypes

void initializeCars(Car* cars, int numCars);
void displayCars(Car* cars, int numCars);

int main(){
	int numCars;
	
	//prompt to enter the number of cars from user 
	cout<<"Enter the number of cars: ";
	cin>>numCars;
	
	//Allocates the memory dynamically for array of cars
	Car* cars = new Car[numCars];
	
	//Initialize the cars
	initializeCars(cars, numCars);
	
	//Direct access to memory elements
	int index;
	
	cout<<"\nEnter the index of the car you want to access  (0 - "<< numCars-1 <<")  :";
	cin>>index;
	
	//Check if the index is within bounds
	if ( index >= 0 && index < numCars){
		cout<<"Make : "<<cars[index].make<<endl;
		cout<<"Model : "<<cars[index].model<<endl;
		cout<<"Year : "<<cars[index].year<<endl;
		cout<<"Price : $ "<<cars[index].price<<endl;		
	} else{
		cout<<"Invalid Index."<<endl;
		}
		
		//Deallocate memory
		delete[]cars;
		
		return 0;
		
	
}


///function to initialize the car
void initializeCars(Car* cars, int numCars){
	for (int i = 0 ; i < numCars ; ++i ){
		cout<< "\nEnter details for Cars " << i+1 <<  " : " <<endl;
		
		cout<<"Make: ";
		cin>>cars[i].make;
		cout<<"Model: ";
		cin>>cars[i].model;
		cout<<"Year: ";
		cin>>cars[i].year;
		cout<<"Price: $";
		cin>>cars[i].price;
		
		
	}
}

//Func to display the information about the cars 
void displayCars(Car* cars, int numCars){
	cout<<"Car Information : "<<endl;
	for ( int i = 0; i < numCars; ++i){
		cout<<"Car: "<<i+1<<":"<<endl;
		cout<<"Make: "<<cars[i].make<<endl;
		cout<<"Model: "<<cars[i].model<<endl;
		cout<<"Year: "<<cars[i].year<<endl;
		cout<<"Price: $ "<<cars[i].price<<endl;
	}
}
