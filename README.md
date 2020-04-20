# CS12J
Material For Supplemental Instruction for CS12J (Introduction to Programming Concepts and Methodology, Java)

## [All Slides](https://drive.google.com/drive/folders/1XgwLqsDrXuAsVudMv9tlvET-yUtsR6Kt?usp=sharing)


# [Live Meeting](https://carter.page.link/zoom)

## Spring of 2020 Recordings
[Recordings](https://www.youtube.com/playlist?list=PLx97YYNRB4zQ98qMMXT19ZM00qu1Kb4Vi)  


# Examples/Work From Sessions

## FizzBuzz
```Java
import java.util.Scanner;
class FizzBuzz3 {
  public static void main(String[] args) {
    Scanner stdin = new Scanner(System.in);
    System.out.print("How many lines do you want to print: ");
    int input = stdin.nextInt();
//    int n = 1;
//    while(n <= input) {
for(int n = 1;n <=input;n++){
    if((n%3 == 0)&&(n%5 == 0)){System.out.println("FizzBuzz");}
    else if(n%3 == 0){System.out.println("Fizz");}
    else if(n%5 == 0){System.out.println("Buzz");}
    else {System.out.println(n);}
//	n++; // n += 1, n = n + 1
  } //end for
  } //end main
} //end Main class
```

## Scope
```Java
import java.util.Scanner;
public class Scope2 {
	
public static void main(String[] args) {
	int t = 5;
	addOne(t);
	//xx++;
	if(!addOne(t)){
	
	
	}
	int tt;
	if(true)
		tt = 11;

	{
		int ttt = 11; 
		tt = ttt+ 5;
	}
	tt++; 

} //end main

int addOne(int x){
	int xx = x + 1;
	return(xx);
}//end addOne
} //end class Scope2

```

## Args
Bash
```BASH
echo "arg 0 $0"
echo "arg 1 $1"
echo "arg 2 $2"
echo "Number of args $#"
echo "All args $@"
```
Java
```Java
import java.util.Scanner;
public class Args {
	public static void main(String[] args) {
		if(args.length > 0){
		//Requires one arg or it crashes
		System.out.printf("args0:%s\n", args[0]);
		} //end if more than one arg
		System.out.printf("args#:%d\n", args.length);
	} //end main
} //end class FilenameHere
```

## Pokemon
```Java
public class Pokemon{
		public Pokemon(){
			name = "None";
			hp = -9;
			attack = 0;
			speed = 0;
		}
		
		public Pokemon(String newname, int newhp, int newattack, int newspeed){ 
			name = newname;
			hp = newhp;
			attack = newattack;
			speed = newspeed;
		}
		
		public String getName(){
			return(this.name);
		} //end getName

		public int getHp(){
			return(this.hp);
		} //end getHp


		public void setHp(int newHp){
			if(newHp < 0){newHp = 0;}
			this.hp = newHp;
		} // end setHp

		
		public void print() {
			System.out.printf("Name:%s, HP:%d, Attack:%d, Speed:%d", this.name, this.hp, this.attack, this.speed);
		}
		public boolean battle(Pokemon other){return(true);} //what would we need
		public static void main(String[] args) {
			//Read 
			Pokemon blank = new Pokemon();
			Pokemon[] pokedex = new Pokemon[151];
			pokedex[0] = new Pokemon("Bulbasaur", 45, 49, 45);
			Pokemon squ = new Pokemon("Squirtle", 44, 48, 43);
			pokedex[1] = squ;
			Pokemon pika = new Pokemon("Pika",50,50,50);
			pokedex[2] = pika;
			pika.print();
			squ.battle(pokedex[0]); 
			blank.battle(pika);
} //end main
	private String name;
	private int hp, attack, speed;
} //end class
```
## Bank / BankAccount Classes
```Java
public class BankAccount {
	private String name;
	private int account_num;
	private double balance;
	public BankAccount(){
		name = "None";
		account_num = -1;
		balance = 0.0;
	} //end BankAccount constructor
	
	public BankAccount(String new_name, int new_account, double new_balance){
		name = new_name;
                account_num = new_account;
                balance = new_balance;
        } //end of overloaded BankAccount constructor
	public int get_account_num(){return(account_num);}
	public double get_balance(){return(balance);}

	public void set_account_num(int new_account_num){
		if(new_account_num < 0){
			account_num = -1; 
			return;
		} // end if negative
		account_num = new_account_num;
	} // end of set_account_num

	public boolean withdraw(double amount){
		if(balance >= amount){
			balance -= amount;
			return(true);
		} //end if suffecent funds
		return(false);
	} // end withdraw

	public void deposit(double amount){
		if(amount > 0){
			balance += amount;
		} // if positive deposit
	} //end deposit

} //end class BankAccount

public class Bank {
	private int cap_accounts = 10;
	private int open_accounts = 0;
	private BankAccount[] accounts = new BankAccount[cap_accounts];
	public Bank(){
		open_accounts = 0;
	} //end Bank construtor

	public int open_bank_account(){
		if(open_accounts == cap_accounts){
			return(-1);} //Might also throw an expetion
		// @TODO: collect user input
		accounts[open_accounts++]= new BankAccount();
		return(accounts[open_accounts-1].get_account_num());
	} // end open_bank_account

	public BankAccount get_bank_account(int account_num){
		for(int i =0; i < open_accounts; i++){
			if(accounts[i].get_account_num() == account_num){
				return(accounts[i]);
			} //if found account 
		} //end for
	// we should throw an expection if we are here
	return(new BankAccount());
 } //end get_bank_account
} //end class Bank


```


## Direction Enum
```Java
public enum Direction { NORTH, SOUTH, EAST, WEST }
Direction direction
direction = Direction.NORTH
```

## Size/Item Classes Inheritance using extends
```Java
public class Size {
        private double width;
        private double length;
        private double height;

        public Size(){
                this.width = 0;
                this.length = 0;
                this.height = 0;
        } //end of defalt Size constructor

        public Size(double nwidth, double nlength, double nheight){
                this.width = nwidth;
                this.length = nlength;
                this.height = nheight;
        } //end of overloaded Size constructor

        public double getWidth(){return(width);}
        public double getLength(){return(length);}
        public double getHeight(){return(height);}

        public void setWidth(double nwidth){this.width = nwidth;}
        public void setLength(double nlength){this.length = nlength;}
        public void setHeight(double nheight){this.height = nheight;}
        
} //end class Size
public class Item extends Size{
        private String material;
        private double weight;

        public Item(){
                this.material ="None";
                this.weight = 0;
                setWidth(0);
                setLength(0);
                setHeight(0);
         } //end default constructor

        public Item(String nmaterial, double nweight, double nwidth, double nlength, double nheight){
                this.material = nmaterial;
                this.weight = nweight;
                setWidth(nwidth);
                setLength(nlength);
                setHeight(nheight);
         } //end constructor

        public String getMaterial(){return(material);};
        public double getWeight(){return(weight);};

        public void setMaterial(String nmaterial){this.material = nmaterial;}
        public void setWeight(double nweight){this.weight = nweight;}
} //end class Item

```


## Recursion
```Java

//int num =6; for(int i=num; i >= 0; i--){ System.out.println(i); }
void countDown(int num){
if(num < 0){return;}
System.out.println(num);
countDown(num - 1);
} //end countDown

//int num =6; for(int i=0; i<= num; i++){ System.out.println(i); }
void countUp(int num){ //@NOTE: except num
if(num < 0){return;}
countDown(num - 1);
System.out.println(num);
} //end countUp

void printBackwards(ArrayList<String> text, int index){
	if(index < 0){return;}
	System.out.println(text.get(index));
	printBackwards(text, index - 1);
} //end printBackwards
ArrayList<String> sal = new ArrayList<String>();

sal.add("Greetings")
sal.add("Human")
sal.add("test")
sal.add("this")
sal.indexOf("yo")
sal.get(0)
printBackwards(sal, sal.size()-1)
```



## Recursion vs Iterative Division
```Java
public class DM {

public static void main(String[] args) {
	System.out.printf("%d == 0\n", divr(1,2));
        System.out.printf("%d == 1\n", divr(2,2));
	System.out.printf("%d == 2\n", divr(5,2));
	System.out.printf("%d == 3\n", divr(6,2));
	System.out.printf("%d == 5\n", divr(10,2));
	System.out.printf("%d == 2\n", divl(5,2));
	divl(5,0);
} //end main

/**
* divr - Division recursivly
* @param int arg0, int arg1
* @return int result
*/
private static int divr(int arg0, int arg1){
	if(arg1 == 0){throw new ArithmeticException("/ by zero");}
	if(arg1 > arg0){return(0);}
	//if(arg1 == arg0){return(1);} //save one recurise
	return(1 + divr(arg0-arg1, arg1));
} //end divr method 

/**
* divl - Division via loop
* @param int arg0, int arg1
* @return int result
*/
private static int divl(int arg0, int arg1){
	if(arg1 == 0){throw new ArithmeticException("/ by zero");}
	int result = 0;
	while(arg0 >= arg1){
		result++;
		arg0 -= arg1; 
	} //end while loop
	// right here arg0 is the remainder eqiv to %
	return(result);
} // end divl method
} //end class DM
```
