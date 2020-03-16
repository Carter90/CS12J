# CS12J
Material For Supplemental Instruction for CS12J (Introduction to Programming Concepts and Methodology, Java)

## [All Slides](https://drive.google.com/drive/folders/1XgwLqsDrXuAsVudMv9tlvET-yUtsR6Kt?usp=sharing)


# [Live Meeting](https://carter.page.link/zoom)

## Spring of 2020 Recordings
[Recording from Session #10](https://youtu.be/0Nwrni2hZlo)  
[Recording from Session #11](https://youtu.be/8eH97MXAkqQ)


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
class Pokemon{
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
