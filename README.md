# task-6
import java.util.*;
class Flight {
int id;
 String origin;
 String destination;
 int seats;
 double price;
 Flight(int id,String origin,String destination,int seats,double price){
 this.id=id;
 this.origin=origin;
 this.destination=destination;
 this.seats=seats;
 this.price=price;
 }
}
class Booking {
 int bookingId;
 int flightId;
 String passengerName;
 Booking(int bookingId,int flightId,String passengerName){
 this.bookingId=bookingId;
 this.flightId=flightId;
 this.passengerName=passengerName;
 }
}
public class AirlineReservationSystem {
 static ArrayList<Flight> flights = new ArrayList<>();
 static ArrayList<Booking> bookings = new ArrayList<>();
 static Scanner sc = new Scanner(System.in);
 static int bookingCounter = 1;
 public static void main(String[] args){
 flights.add(new Flight(1,"Delhi","Mumbai",5,4500));
 flights.add(new Flight(2,"Hyderabad","Chennai",3,3000));
 int choice;
 do{
 System.out.println("\n1. View Flights");
 System.out.println("2. Book Ticket");
 System.out.println("3. View Bookings");
 System.out.println("4. Exit");
 System.out.print("Enter choice: ");
 choice=sc.nextInt();
 switch(choice){
 case 1:
 viewFlights();
 break;
 case 2:
 bookTicket();
 break;
 case 3:
 viewBookings();
 break;
 }
 }while(choice!=4);
 }
 static void viewFlights(){
 for(Flight f:flights){
 System.out.println("Flight ID:"+f.id+" "+f.origin+" -> "+f.destination+" Seats:"+f.seats+ }
 }
 static void bookTicket(){
 System.out.print("Enter Flight ID: ");
 int id=sc.nextInt()
sc.nextLine();
 System.out.print("Passenger Name: ");
 String name=sc.nextLine();
 for(Flight f:flights){
 if(f.id==id && f.seats>0){
 f.seats--;
 bookings.add(new Booking(bookingCounter++,id,name));
 System.out.println("Booking Successful!");
 return;
 }
 }
 System.out.println("No seats available.");
 }
 static void viewBookings(){
 for(Booking b:bookings){
 System.out.println("BookingID:"+b.bookingId+" FlightID:"+b.flightId+" Passenger:"+b.passe }
 }
}

Sample Output
Sample Output
1. View Flights
Flight ID:1 Delhi -> Mumbai Seats:5 Price:4500
Flight ID:2 Hyderabad -> Chennai Seats:3 Price:3000
2. Book Ticket
Enter Flight ID: 1
Passenger Name: Rahul
Booking Successful!
3. View Bookings
BookingID:1 FlightID:1 Passenger:Rahul
