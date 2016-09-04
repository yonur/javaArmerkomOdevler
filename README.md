# javaArmerkomOdevler
--------------------------------------------ALGORITMA70_SORU-------------------------------------------------------------------------
Soru-1)

import java.util.Scanner;

class Fact {
	
	int factValue;
	
	Fact(int f){
		
		factValue = f;
	}
	
	long myFactResult(){
		
		long factResult = 1;
	
		for (int i = 1; i <= factValue; i++)
			factResult *= i;

		return factResult;
	}
}

public class Driver {
	public static void main(String arg[]){

		long factResult;
		
		int myint;
		
		Scanner keyboard = new Scanner(System.in);
		
		System.out.print("Please enter a new value between 1 and 25: ");
			
		myint = keyboard.nextInt();

		while(myint > 1 && myint < 25){
			
			Fact myfact = new Fact(myint);
			
			factResult = myfact.myFactResult();

			System.out.println("My new value: " + myint);

			System.out.println("My factoriel result is: " + factResult);
			
			System.out.print("Please enter a new value between 1 and 25: ");
			
			if (keyboard.hasNextInt())
				myint = keyboard.nextInt();
			else{
				break;
			}
		}
		
		System.out.println("Value is not between please try again  later");
		
		System.out.println("Bye");
	}
}

Soru-2)

public class Driver {
	public static void main(String arg[]){
		
		int myint;
		
		Scanner keyboard = new Scanner(System.in);

		System.out.print("Please enter a new value between 10 and 15: ");

		do
		{			
			myint = keyboard.nextInt();
			
			System.out.println("My new value: " + myint);
			
			if( (!( myint > 10 && myint < 15 )) )
				System.out.print("Please enter a new value between 10 and 15: ");
			
		}
		while( (!( myint > 10 && myint < 15 )) && ( keyboard.hasNextInt()) );
		
		System.out.println("Value is: " + myint);
		
		System.out.println("Bye");
		
		keyboard.close();
		
	}
}

Soru-3)

class Square {
	
	long squareResult(int myValue){
		
		long squareResult;
	
		squareResult = myValue * myValue;

		return squareResult;
	}
}

public class Driver {
	public static void main(String arg[]){
		
		long squareSum = 0;
		
		int counter = 1;
		
		Square mysquare = new Square();
		
		while (counter < 26){
			
			squareSum += mysquare.squareResult(counter++);
		}
		
		System.out.println("Square values sum is " + squareSum);
		
	}
}

Soru-4)

public class Driver {
	public static void main(String arg[]){
		
		int myint;
		
		int counter = 0;
		
		int[] myArray = new int[10];
		
		Scanner keyboard = new Scanner(System.in);

		System.out.print("Please enter maximum 10 values: ");

		do
		{			
			myint = keyboard.nextInt();
			
			System.out.println("My new value: " + myint);
			
			myArray[counter] = myint;
			
			counter++;
		}
		while( ( counter < 10 ) && ( keyboard.hasNextInt()) );
		
		int negcounter = 0;
		
		for (int i = 0; i < 10; i++){
			
			if (myArray[i] < 0)
				negcounter++;
			
			}
		
		System.out.println("Negatif values count is " + negcounter);
		
		keyboard.close();
		
	}
}

Soru-5)

public class Driver {
	public static void main(String arg[]){
		
		double secondOrder, firstOrder, zeroOrder, disc, x1, x2, x, sqrtDisc;
		
		Scanner keyboard = new Scanner(System.in);

		System.out.println("Ikinci dereceden bir denklemin kokleri bulunacaktir");
		
		System.out.print("Lutfen denklemin ikinci dereceden elemaninin katsayisini giriniz ");
							
		secondOrder = keyboard.nextDouble();
		
		System.out.print("Lutfen denklemin birinci dereceden elemaninin katsayisini giriniz");
			
		firstOrder = keyboard.nextDouble();
		
		System.out.print("Lutfen denklemin sifirinci dereceden elemaninin katsayisini giriniz");

		zeroOrder = keyboard.nextDouble();
		
		System.out.println("Denkleminiz: " + secondOrder + " * x^2 + ( " + firstOrder + " ) * x + " + zeroOrder);
		
		disc = (firstOrder)*(firstOrder) - 4 * secondOrder * zeroOrder;
		
		if (disc > 0){
			
			sqrtDisc = Math.sqrt(disc);
			
			x1 = ( ( -firstOrder ) - sqrtDisc ) / ( 2 * secondOrder );
			
			System.out.println("Denklemin iki adet koku vardir");
			
			System.out.print("Bunlardan biri: " + x1 + " 'dir. ");
			
			x2 = ( (-firstOrder) + sqrtDisc ) / ( 2 * secondOrder );
			
			System.out.print("Digeri ise: " + x2 + " 'dir.");
			
		} else if (disc == 0){
		
			x = ( -firstOrder ) / ( 2 * secondOrder );
			
			System.out.println("Denklemin tek koku vardir o da x: " + x + " 'dir.");
			
		} else 
			System.out.println("Denklemin reel koku yoktur.");			

		keyboard.close();
		
	}
}

Soru-6)

public class Driver {
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int month;
		
		String monthString;
		
		System.out.print("Klavyeden 1 ile 12 arasinda bir sayi giriniz: ");
		
		month = keyboard.nextInt();
		
		while ((month > 0 && month < 13)) {
		
			switch (month) {
            case 1:  monthString = "January";
                     break;
            case 2:  monthString = "February";
                     break;
            case 3:  monthString = "March";
                     break;
            case 4:  monthString = "April";
                     break;
            case 5:  monthString = "May";
                     break;
            case 6:  monthString = "June";
                     break;
            case 7:  monthString = "July";
                     break;
            case 8:  monthString = "August";
                     break;
            case 9:  monthString = "September";
                     break;
            case 10: monthString = "October";
                     break;
            case 11: monthString = "November";
                     break;
            case 12: monthString = "December";
                     break;
            default: monthString = "Invalid month";
                     break;
			}
			
			System.out.println("Girdiginiz rakamin karsiligi ay: " + monthString + " 'dir");
		
			System.out.print("Klavyeden 1 ile 12 arasinda yeni bir sayi giriniz: ");
			
			month = keyboard.nextInt();
		}
		
		System.out.println("Bye");
		
		keyboard.close();
		
	}
}

Soru-7)

public class Driver {
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int mathCode;
		
		int x1, x2;
		
		System.out.print("Klavyeden  giriniz '+' islemi icin 1 kodunu '-' islemi icin 2 kodunu '*' islemi icin 3 kodunu '/' islemi icin 4 kodunu giriniz: ");
		
		mathCode = keyboard.nextInt();
		
		System.out.print("Birinci sayiyi giriniz: ");
		
		x1 = keyboard.nextInt();
		
		System.out.print("Ikinci sayiyi giriniz: ");
		
		x2 = keyboard.nextInt();
		
			switch (mathCode) {
        		    case 1:  
        		    	System.out.println("Sonuc: " + (x1 + x2));
            			break;
            		    case 2:
            			System.out.println("Sonuc: " + (x1 - x2));
                     		break;
            		    case 3: 
            			System.out.println("Sonuc: " + (x1 * x2));
                     		break;
            	            case 4: 
            			System.out.println("Sonuc: " + (x1 / x2));
                     		break;
            	            default: 
            			System.out.println("Gecerli bir kod degildir");
                     		break;
			}
		
		
		System.out.println("Gule Gule");
		
		keyboard.close();
		
	}
}


Soru-8)

public class Driver {
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int newInput;
		
		int sum = 0;
		
		System.out.print("Please enter a new value which isn't negative: ");
		
		newInput = keyboard.nextInt();
		
		while (newInput >= 0){
			
			sum += newInput;
			
			System.out.println("New sum is: " + sum);
			
			System.out.print("Please enter a new value which isn't negative: ");
			
			newInput = keyboard.nextInt();
			
		}

		System.out.println("Oops! This is negative value.");
		
		System.out.println("Final sum is: " + sum);
		
		System.out.println("Bye");
		
		keyboard.close();
		
	}
}


Soru-9)

public class Driver {
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		System.out.print("Yeni bir not giriniz: ");
		
		int newInput = keyboard.nextInt();
		
		while (newInput > 0 && newInput < 100){
						
			if (newInput > 0 && newInput < 50)
				System.out.println("Basarisiz");
			else if(newInput >= 50 && newInput < 65)
				System.out.println("Orta");
			else if (newInput >= 65 && newInput < 85)
				System.out.println("Iyi");
			else 
				System.out.println("Cok iyi");
			
			System.out.print("Yeni bir not giriniz: ");

			newInput = keyboard.nextInt();
			
		}
		
		System.out.println("Gecerli aralikta bir sayi girmediniz");
		
		System.out.println("Bye");
		
		keyboard.close();
	}
}

Soru-10)

public class Driver {
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int x1, x2;
		
		System.out.print("Birinci sayiyi giriniz: ");
		
		x1 = keyboard.nextInt();
		
		System.out.print("Ikinci sayiyiyi giriniz: ");
		
		x2 = keyboard.nextInt();
		
		if (x1 > x2)
			System.out.println("Buyuk sayi " + x1);
		else if (x2 > x1)
			System.out.println("Buyuk sayi " + x2);
		else
			System.out.println("Sayilar birbirine esittir");
		
		keyboard.close();
	}
}

Soru-11)

public class Driver {
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int x1, x2, temp;
		
		System.out.print("Birinci sayiyi giriniz: ");
		
		x1 = keyboard.nextInt();
		
		System.out.print("Ilk sayinin kuvveti olacak ikinci sayiyiyi giriniz: ");
		
		x2 = keyboard.nextInt();
		
		temp = x1;
		
		for (int i = 1; i < x2; i++ ){
			
			x1 *= temp;
			
		}
		
		System.out.println("Kuvveti alinmis ilk sayi: " + x1);
		
		keyboard.close();
	}
}

Soru-12)

import java.util.Scanner;

class Fact {
	
	int factValue;
	
	Fact(int f){
		
		factValue = f;
	}
	
	long myFactResult(){
		
		long factResult = 1;
	
		for (int i = 1; i <= factValue; i++)
			factResult *= i;

		return factResult;
	}
}

public class Driver {
	public static void main(String arg[]){
		
		int myint;
		
		long factResult;
		
		Scanner keyboard = new Scanner(System.in);

		System.out.print("Please enter the value to find its factoriel: ");

		do {
		
			myint = keyboard.nextInt();
			
			Fact myFact = new Fact(myint);
			
			factResult = myFact.myFactResult();
			
			System.out.println("Factoriel result is: " + factResult);
	
			System.out.print("Please enter the new value to find its factoriel: ");

		} while (keyboard.hasNext());
		
		System.out.println("Bye");
		
		keyboard.close();
	}
}

Soru-13)

class Square {
	
	long squareResult(int myValue){
		
		long squareResult;
	
		squareResult = myValue * myValue;

		return squareResult;
	}
}


class SquareSum {
	
	long sum = 0;
	
	Square mysquare = new Square();
	
	long squareSum (int squareLim){
		for (int i = 1; i <= squareLim; i++){
			sum += mysquare.squareResult(i);
		}
		return sum;
	}
}

public class Driver {
	public static void main(String arg[]){
		
		int myint;
		
		long result;
		
		Scanner keyboard = new Scanner(System.in);

		System.out.print("Please enter the value to find its square sums until the value: ");

		myint = keyboard.nextInt();
			
		SquareSum newsumSquare = new SquareSum();
		
		result = newsumSquare.squareSum(myint);
		
		System.out.println("Result is: " + result);
		
		keyboard.close();
	}
}

Soru-14)

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);
			
			String mathCode;
			
			int x1, x2;
			
			System.out.print("Klavyeden yapmak istediginiz dort islemi giriniz ('+', '-', '*', '/') : ");
			
			mathCode = keyboard.next();
			
			System.out.print("Birinci sayiyi giriniz: ");
			
			x1 = keyboard.nextInt();
			
			System.out.print("Ikinci sayiyi giriniz: ");
			
			x2 = keyboard.nextInt();
			
				switch (mathCode) {
	        		    case "+":  
	        		    	System.out.println("Sonuc: " + (x1 + x2));
	            			break;
	            	    case "-":
	            			System.out.println("Sonuc: " + (x1 - x2));
	                     	break;
	            		case "*": 
	            			System.out.println("Sonuc: " + (x1 * x2));
	                     	break;
	                    case "/": 
	            			System.out.println("Sonuc: " + (x1 / x2));
	                     	break;
	            	    default: 
	            			System.out.println("Dort islem operatoru gecerli bir islem degildir");
	                   		break;
				}
			
			
			System.out.println("Gule Gule");
			
			keyboard.close();
			
		}
	}

Soru-15)

class VelocityCalc {
	
	int speedValue = 60;
	
	
	int myTimeResult(int totalDistance){
		
		int totalTime;
		
		totalTime = totalDistance / speedValue;
		
		return totalTime;
		
	}
}

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);
			
			int distance, time;
			
			System.out.print("Klavyeden toplam gittiginiz mesafeyi km cinsinden giriniz: ");
			
			distance = keyboard.nextInt();
			
			VelocityCalc myTime = new VelocityCalc();
			
			time = myTime.myTimeResult(distance);
			
			System.out.println("Toplam harcanan zaman: " + time + " saattir");
			
			System.out.println("Gule Gule");
			
			keyboard.close();
			
		}
	}

Soru-16)

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);

			int[] myArray = new int[10];			
			
			System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
			
			for (int i = 0; i < 10; i++){
				
				System.out.print("Klavyeden dizinin " + i + ".nci elemanini giriniz: ");

				myArray[i] = keyboard.nextInt();
				
			}

			
			System.out.println("Dizinin elemanlari: ");
			
			for (int i = 0; i < 10; i++){
			
				System.out.println(" " + myArray[i] + " ");	
			
			}

			int temp;
			
			for ( int i = 1; i < 10; i++ ){
				for ( int j = 0; j < 10 - i; j++ )
					if (myArray[j] < myArray[j + 1]){
						temp = myArray[j + 1];
						myArray[j + 1] = myArray[j];
						myArray[j] = temp;
					}			
			}
			
			System.out.println("Dizinin elemanlari buyukten kucuge: ");
			
			for (int i = 0; i < 10; i++){
			
				System.out.println(" " + myArray[i] + " ");	
			
			}
			
			System.out.println("Bye");
			
			keyboard.close();
			
		}
	}

Soru-17)

import java.util.Scanner;

public class Days {

	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int myDay;
		
		String day[] = {"Pazartesi", "Sali", "Carsamba", "Persembe", "Cuma", "Cumartesi", "Pazar"};
		
		System.out.print("1 ile 7 arasinda bir sayi giriniz: ");
		
		myDay = in.nextInt();
		
		for (int i = 1; i <= 7; i++){
			
			if (i == myDay)
				System.out.print("Girdiginiz rakama karsilik gelen gun: " + day[myDay - 1]);
			
		}
		
		in.close();
	}
}


Soru-18) 

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);

			int myInt, zeroCounter;			
			
			System.out.println("Klavyeden sonundaki sifir sayisinin bulunacagi sayiyi giriniz: ");
			
			myInt = keyboard.nextInt();
			
			zeroCounter = 0;
			
			while ((myInt % 5) == 0){
				
				myInt /= 5;
				
				zeroCounter++;
			
			}
			
			System.out.println("Sayinin sonundaki sifir sayisi: " + zeroCounter);
			
			System.out.println("Bye");
			
			keyboard.close();
			
		}
	}
Soru-19) 

import java.util.Scanner;

public class Dividing {
	
	private static int divider(int divided, int divisor){
		
		int divide = 0;
		
		if (divisor != 0){
			if((divided > 0 && divisor > 0) || (divided < 0 && divisor < 0))
				while (divided >= divisor){
					divided -= divisor;
					divide++;
				} 
			else if ((divided < 0 && divisor > 0))
				while ((-divided) >= divisor ){
					divided += divisor;
					divide--;
				}
			else if ((divided > 0 && divisor < 0))
				while (divided >= (-1 * divisor)){
					divided += divisor;
					divide--;
				}
		}else
			System.out.println("Bolum sonsuzdur.");
				
 		return divide;
	}

	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int myDivided;
		
		int myDivisor;
		
		System.out.print("Bolunecek sayiyi giriniz: ");
		
		myDivided = in.nextInt();
		
		System.out.print("Bolen sayiyi giriniz: ");
		
		myDivisor = in.nextInt();
		
		System.out.println("Bolum: " + divider(myDivided, myDivisor));
		
		in.close();
	}
}

Soru-20) 

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);

			int myValue, sum;			
			
			sum = 0;
			
			System.out.print("Klavyeden o sayiya kadar toplami bulunacak sayiyi giriniz: ");
			
			myValue = keyboard.nextInt();
		
			for (int i = 1; i <= myValue; i++){
				
				sum += i;
				
			}
			
			System.out.println("Toplam: " + sum);
			
			keyboard.close();
			
		}
	}


Soru-21)

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);

			int myValue;
			
			int[] myArray = new int[10];
			
			myArray = new int[]{2,4,5,67,2,67,21,4,9,0};
			
			System.out.print("Klavyeden dizide aranacak elemani giriniz: ");
			
			myValue = keyboard.nextInt();
			
			int counter = 0;
			
			for (int i = 0; i < 10; i++){
				
				if ( myArray[i] == myValue)
					
					counter++;	
				
			}
			
			System.out.println("Klavyeden girilen eleman dizide " + counter + " adet bulunmaktadir.");
			
			keyboard.close();
			
		}
	}

Soru-22)

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);

			int myValue;
			
			System.out.print("Klavyeden dizide aranacak elemani giriniz: ");
			
			myValue = keyboard.nextInt();
			
			for (int i = 2; i < myValue; i++){
				
				if (myValue % i == 0){
				
					System.out.println("Klavyeden girilen sayi asal degildir.");
					
					keyboard.close();
					
					return;
				}
				else 
					continue;

			}
			
			System.out.println("Klavyeden girilen sayi asaldir");
			
			keyboard.close();
			
		}
	}

Soru-23) Bu cevapta class kullanarak bir iyilestirme YAP!

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);

			int myArrayMax;

			int myArrayMin;
			
			int[] myArray = new int[10];			
			
			System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
			
			for (int i = 0; i < 10; i++){
				
				System.out.print("Klavyeden dizinin " + i + ".nci elemanini giriniz: ");

				myArray[i] = keyboard.nextInt();
				
			}
			
			myArrayMax = myArray[0];
			
			for (int i = 0; i < 10 ; i++){
				
				if (myArray[i] > myArrayMax)
				
					myArrayMax = myArray[i];
							
			}
			
			System.out.println("En buyuk sayi " + myArrayMax);
			
			myArrayMin = myArray[0];
			
			for (int i = 0; i < 10 ; i++){
				
				if (myArray[i] < myArrayMin)
				
					myArrayMin = myArray[i];
			
			}
			
			System.out.println("En kucuk sayi " + myArrayMin);
			
			keyboard.close();
			
		}
	}

Soru-24)

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);

			int myArraySize;
			
			float myArrayMean;
			
			float sum = 0;
			
			float[] myArray = new float[10];			
			
			System.out.print("Klavyeden kac adet tam sayi girilecegini giriniz: ");
			
			myArraySize = keyboard.nextInt();
			
			System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
			
			for (int i = 0; i < myArraySize; i++){
				
				System.out.print("Klavyeden dizinin " + i + ".nci elemanini giriniz: ");

				myArray[i] = keyboard.nextFloat();
				
			}
			
			for (int i = 0; i < myArraySize; i++){
				
				sum += myArray[i];
				
			}
			
			myArrayMean = (sum / myArraySize);
			
			System.out.println("Klavyeden girilen sayilarin ortalamasi " + myArrayMean);
			
			keyboard.close();
			
		}
	}

Soru-25)

import java.util.Scanner;

class Inverter {
	
	int inputValue;
	
	Inverter (int i){
		
		inputValue = i;
	
	}
	
	int myInvert(){
		
		int invertResult = 0;
		
		int divider = 10;
		
		int digitCounter = 2;
		
		int temp;
		
		int tempValue = inputValue;
		
		while ((tempValue /= divider) >= 10) {
			
			digitCounter++;
			
		}

		int[] myDigits = new int[digitCounter];
		
		for (int i = 0; i < digitCounter; i++){
			
			temp = inputValue % 10;
			
			inputValue /= 10; 
			
			myDigits[i] = temp;
			
		}
		
		for (int i = 0; i < digitCounter; i++){
			
			invertResult += myDigits[i];
			
			if (!(i == (digitCounter - 1) ))
				invertResult *= 10;
			
		}
		
		return invertResult;
		
	}
}

public class Driver {
		
		public static void main(String arg[]){
			
			Scanner keyboard = new Scanner(System.in);

			int myArraySize, tempPrinter;
			
			int[] myArray = new int[10];			
			
			System.out.print("Klavyeden kac adet tam sayi girilecegini giriniz: ");
			
			myArraySize = keyboard.nextInt();
			
			System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
			
			for (int i = 0; i < myArraySize; i++){
				
				System.out.print("Klavyeden dizinin " + i + ".nci elemanini giriniz: ");

				myArray[i] = keyboard.nextInt();
				
			}
			
			for (int i = 0; i < myArraySize; i++){
				
				Inverter mytempinvert = new Inverter(myArray[i]);
				
				tempPrinter = mytempinvert.myInvert();
				
				System.out.print(" " + tempPrinter + " ");
			}
			
			System.out.println(" ");
			
			keyboard.close();
			
		}
	}

Soru-26)

import java.util.Scanner;

public class Driver {
		
		public static void main(String arg[]){
			
			int myLength;
			
			Scanner keyboard = new Scanner(System.in);
			
			String str;
			
			System.out.println("Metni giriniz: ");
			
			str = keyboard.nextLine();

			myLength = str.length();
			
			System.out.println("Klavyeden girilen string' in uzunlugu " 
			+ myLength + " harftir.");
						
			keyboard.close();
			
		}
	}

Soru-27) * Bu cevap incelenecek(Not: Nasil determinant alinir incele once)

public class Driver {
		
	public int determinant (int[][] arr){
		int sonuc = 0;
		if (arr.length == 1){
			sonuc = arr[0][0];
			return sonuc;
		}
		if (arr.length == 2){
			sonuc = arr[0][0]*arr[1][1] - arr[0][1]*arr[1][0];
			return sonuc;
		}
		for (int i = 0; i < arr[0].length; i++){
			int gecici[][] = new int[arr.length - 1][arr[0].length -1];
			
				for (int j = 1; j < arr.length; j++){
					for (int k = 0; k < arr[0].length; k++){
				
						if( k < i){
							gecici[j -1][k] = arr[j][k];
						}else if (k > i){
							gecici[j -1][k-1] = arr[j][k];
						}
				}
			}
			sonuc += arr[0][i]*Math.pow(-1, (int) i) * determinant(gecici);
		}
1		return sonuc;
	}
		public static void main(String arg[]){
			
			int myArr[][] = {{5,3,7,4},{2,4,9,6},{6,3,6,4}};
			Driver d = new Driver();
			int sonuc = d.determinant(myArr);
			System.out.println(sonuc);
			
		}
	}

Soru-28)

import java.util.Scanner;

public class Driver {
		
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		String str;
		
		System.out.println("Metni giriniz: ");
		
		str = keyboard.nextLine();
		
		System.out.println("Klavyeden girilen metin: " + str);

		String reverse = new StringBuffer(str).reverse().toString();
		
		System.out.println("Klavyeden girilen metinin tersi " + reverse);
					
		keyboard.close();
		
	}
}

Soru-29)

public class Driver {
		
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		String str;
		
		System.out.println("Metni giriniz: ");
		
		str = keyboard.nextLine();

		String[] strArr = str.split(" ");
				
		int length = strArr.length;
		
		System.out.println("Klavyeden girilen cumlenin kelimelerinin ilk harfleri");
		
		for (int i = 0; i < length; i++){
			System.out.println(strArr[i].charAt(0));
		}
		
		keyboard.close();
		
	}
}

Soru-30)

import java.util.Scanner;

public class Driver {
		
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		String str;
		
		System.out.println("Metni giriniz: ");
		
		str = keyboard.nextLine();

		String[] strArr = str.split(" ");
				
		int length = strArr.length;
		
		System.out.println("Klavyeden girilen cumlenin kelimelerinin ilk harfleri");
		
		for (int i = length -1; i >= 0 ; i--){
			System.out.println(strArr[i]);
		}
		
		keyboard.close();
		
	}
}

Soru-31)

import java.util.Scanner;

class Students {
	
	String name;
	
	float note;
	
	Students (String s, float n){
		
		name = s;
		
		note = n;
		
	}
	
}
public class Driver {
		
	public static void main(String arg[]){
		
		System.out.println("Siniftaki ogrenci adedini giriniz");
		
		int studentCounter;
		
		String studentName;
		
		float studentNote;
		
		Scanner keyboard = new Scanner(System.in);
	
		studentCounter = keyboard.nextInt();
		
		Students[] newStudents = new Students[studentCounter];
		
		float sum = 0; //Ogrencilerin notlarinin toplami
		
		for (int i = 0; i < studentCounter; i++){
			
			System.out.print("Ogrencinin ismini giriniz: ");
			
			studentName = keyboard.next();
			
			System.out.print("Ogrencinin notunu giriniz: ");
			
			studentNote = keyboard.nextFloat();
			
			newStudents[i] = new Students(studentName, studentNote);
			
			sum += newStudents[i].note;
			
		}
		
		float mean = sum / studentCounter; //Ogrencilerin notlarinin ortalamasi

		float maxNote = newStudents[0].note;
		
		String maxStudent = "No student";
		
		for(int i = 1; i < studentCounter; i++){
			
			if( newStudents[i].note > maxNote)
				
				maxNote = newStudents[i].note;
			
				maxStudent = newStudents[i].name;
		}

		System.out.println("Ogrencilerin notlarinin ortalamasi" + mean);

		System.out.println("En yuksek notlu ogrenci" + maxStudent + "dir.");
		
		System.out.println("En yuksek notta bu ogrencinin notu olan" + maxNote + "tur.");
		
		keyboard.close();
		
	}
}

Soru-32)

public class Driver {
		
	public static void main(String arg[]){
		
		int[] myArr = {5,7,4,21,-2,45,-23,98};
	
		int len = myArr.length;

		int sum = 0;
		
		for (int i = 0; i < len; i++){
			
			if (myArr[i] < 0)
			
				sum += myArr[i];
			
		}
		
		System.out.println("Dizideki negatif sayilarin toplami: " + sum);
	}
}

Soru-33)

public class Driver {
		
	public static void main(String arg[]){
		
		int[] myArr = {5,7,4,21,-2,45,-23,98,0,31,0,-69};
	
		int len = myArr.length;

		int zeroCounter = 0;
		
		int pozCounter = 0;
		
		int negCounter = 0;
		
		for (int i = 0; i < len; i++){
			
			if (myArr[i] < 0)
			
				negCounter++;
			
			else if (myArr[i] == 0)
				
				zeroCounter++;
			
			else
				
				pozCounter++;
			
		}
		
		System.out.println("Dizideki negatif sayilarin sayisi: " + negCounter);
		
		System.out.println("Dizideki pozitif sayilarin sayisi: " + pozCounter);

		System.out.println("Dizideki sifirlarin sayisi: "   	 + zeroCounter);

	}
}

Soru-34)

public class Driver {
		
	private static int[] extendArray(int [] array, int newValue){
        
		int [] temp = array.clone();
	    
		array = new int[array.length + 1];
	    				
		System.arraycopy(temp, 0, array, 0, temp.length);
        
		array[array.length - 1] = newValue;
        
        return array;
    }
	
	public static void main(String arg[]){
		
		int[] myArr = {5,7,4,21,-2,45,-23,98,0,31,0,-69};
	
		int[] negArr = new int[0];
		
		int[] pozArr = new int[0];
		
		for (int i = 0; i < myArr.length; i++){
			
			if(myArr[i] < 0){
				
				negArr = extendArray(negArr, myArr[i]);

			}
			else{
	
				pozArr = extendArray(pozArr, myArr[i]);
				
			}
		}
		
		System.out.println("Dizideki:");
		
		System.out.println("Sayilar: ");
		
		for (int i = 0; i < myArr.length; i++){
			
			System.out.print(" " + myArr[i] + " ");
		}
		
		System.out.println();
		
		System.out.println("Negatif sayilar: ");
		
		for (int i = 0; i < negArr.length; i++)
			System.out.print(" " + negArr[i] + " ");
		
		System.out.println();
		
		System.out.println("Pozitif sayilar ve sifirlar");
		
		for (int i = 0; i < pozArr.length; i++)
			System.out.print(" " + pozArr[i] + " ");

		System.out.println();
		
		System.out.println("Bye");
		
	}
}

Soru-35)

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		int myArraySize;
		
		int[] myArray = new int[10];			
		
		System.out.print("Klavyeden dizinin boyutunu giriniz: ");
		
		myArraySize = keyboard.nextInt();
		
		System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
		
		for (int i = 0; i < myArraySize; i++){
			
			System.out.print("Klavyeden dizinin " + i + ".nci elemanini giriniz: ");

			myArray[i] = keyboard.nextInt();
			
		}
		
		float evenSum = 0;
		
		int evenCounter = 0;
		
		float evenMean;
		
		for (int i = 0; i < myArraySize; i++){
			
			if (myArray[i] % 2 == 0){
				
				evenSum += myArray[i];
				
				evenCounter++;
			
			}
				
		}
		
		evenMean = evenSum / evenCounter;
		
		System.out.println("Cift sayilarin ortalamasi: " + evenMean);
		
		System.out.println("Bye");
		
		keyboard.close();
	}
}

Soru-37)

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		int myArrayRow;
		int myArrayColumn;
		
		float sum = 0; // Esas kosegen uzerindeki elemanlarin toplami
		int counter = 0; //Esas kosegen uzerindeki elemanlarin sayisi
		
		System.out.print("Klavyeden dizinin satir sayisini giriniz: ");
		
		myArrayRow = keyboard.nextInt();
		
		System.out.print("Klavyeden dizinin sutun sayisini giriniz: ");
		
		myArrayColumn = keyboard.nextInt();
		
		System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
		
		int[][] myArray = new int[myArrayRow][myArrayColumn];			
		
		for (int i = 0; i < myArrayRow; i++)
			for (int j = 0; j < myArrayColumn; j++){
			
			System.out.print("Klavyeden dizinin array[" + i + "][" + j + "].nci elemanini giriniz: ");

			myArray[i][j] = keyboard.nextInt();
			
		}
		
		
		for (int j = 0; j < myArrayColumn; j++){
			
			sum += myArray[j][j];
			
			counter++;
			
		}
		
		System.out.println("Esas kosegen uzerindeki elemanlarin toplami " + sum);
		
		System.out.println("Esas kosegen uzerindeki elemanlarin ortalamasi " + (sum / counter));
		
		System.out.println("Bye");
		
		keyboard.close();
	}
}


Soru-38)

public class Driver {
		
	static void rowandcolumnSummer (int myArr[][], int row, int column){

		int rowSum;
		int columnSum;

		for (int i = 0; i < row; i++){
			rowSum = 0;
			for (int j = 0; j < column; j++){
				rowSum += myArr[i][j];
			}
			System.out.println("Dizinin " + i + ".nci satirindaki sayilarin toplami" + rowSum);
		}
		
		for (int i = 0; i < column; i++){
			columnSum = 0;
			for (int j = 0; j < row; j++){
				columnSum += myArr[j][i];
			}
			System.out.println("Dizinin " + i + ".nci sutunundaki sayilarin toplami" + columnSum);
		}
	}
	
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		int myArrayRow;
		int myArrayColumn;
		
		System.out.print("Klavyeden dizinin satir sayisini giriniz: ");
		
		myArrayRow = keyboard.nextInt();
		
		System.out.print("Klavyeden dizinin sutun sayisini giriniz: ");
		
		myArrayColumn = keyboard.nextInt();
		
		System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
		
		int[][] myArray = new int[myArrayRow][myArrayColumn];			
		
		for (int i = 0; i < myArrayRow; i++)
			for (int j = 0; j < myArrayColumn; j++){
			
			System.out.print("Klavyeden dizinin array[" + i + "][" + j + "].nci elemanini giriniz: ");

			myArray[i][j] = keyboard.nextInt();
			
		}
		
		rowandcolumnSummer(myArray,myArrayRow,myArrayColumn);
		
		System.out.println("Bye");
		
		keyboard.close();
	}
}


Soru-39)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		int myArrayRow;
		int myArrayColumn;
		
		System.out.print("Klavyeden dizinin satir sayisini giriniz: ");
		
		myArrayRow = keyboard.nextInt();
		
		System.out.print("Klavyeden dizinin sutun sayisini giriniz: ");
		
		myArrayColumn = keyboard.nextInt();
		
		System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
		
		int[][] myArray = new int[myArrayRow][myArrayColumn];			
		
		for (int i = 0; i < myArrayRow; i++)
			for (int j = 0; j < myArrayColumn; j++){
				System.out.print("Klavyeden dizinin array[" + i + "][" + j + "].nci elemanini giriniz: ");
				myArray[i][j] = keyboard.nextInt();			
		}
		
		for(int i = 0; i < myArrayRow; i++)
			for(int j = 0; j < myArrayColumn; j++){
				
				if(!(myArray [i][j] == myArray[j][i])){
					
					System.out.println("Matris simetrik degildir");
		
					return;
				}
			}
		
		System.out.println("Matris simetriktir");
		
		for (int i = 0; i < myArrayRow; i++)
			for (int j = 0; j < myArrayColumn; j++){
			
			System.out.print(" " + myArray[i][j] + " ");
			
			if(j == (myArrayColumn -1))
				System.out.println();
			
		}
			
		System.out.println("Bye");
		
		keyboard.close();
	}
}

Soru-40)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		int myArrayRow;
		int myArrayColumn;
		float maxArr;
		float minArr;
		
		System.out.print("Klavyeden dizinin satir sayisini giriniz: ");		

		myArrayRow = keyboard.nextInt();
		
		System.out.print("Klavyeden dizinin sutun sayisini giriniz: ");
		
		myArrayColumn = keyboard.nextInt();
		
		System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
		
		float[][] myArray = new float[myArrayRow][myArrayColumn];			
		
		for (int i = 0; i < myArrayRow; i++)
			for (int j = 0; j < myArrayColumn; j++){
				System.out.print("Klavyeden dizinin array[" + i + "][" + j + "].nci elemanini giriniz: ");
				myArray[i][j] = keyboard.nextFloat();
		}
			
		maxArr = myArray[0][0];
		
		for (int i = 0; i < myArrayRow; i++)
			for (int j = 0; j < myArrayColumn; j++){
				if(myArray[i][j] > maxArr)
				maxArr = myArray[i][j];
				
		}
		
		System.out.println("Dizinin en buyuk elemani: " + maxArr);
		
		minArr = myArray[0][0];
		
		for (int i = 0; i < myArrayRow; i++)
			for (int j = 0; j < myArrayColumn; j++){
				if(myArray[i][j] < minArr)
					minArr = myArray[i][j];
							
		}
		
		System.out.println("Dizinin en kucuk elemani: " + minArr);

		
		float bolum = (maxArr / minArr);
		
		System.out.println("Dizideki en buyuk elemanin en kucuk elemana bolumu: " + bolum);
		
		System.out.println("Bye");
		
		keyboard.close();
	}
}

Soru-41)

public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		String metin;
		char character;
		int sum = 0;
		
		System.out.print("Klavyeden metni giriniz: ");		

		metin = keyboard.nextLine();
		
		for(int i = 0; i < metin.length(); i++){
			character = metin.charAt(i);
			if (Character.isDigit(metin.charAt(i))){
				System.out.println(character);
				sum += Character.getNumericValue(character);;
			}
		}
		
		System.out.println("Klavyeden girilen metindeki rakamlarin toplami: " + sum);
		
		keyboard.close();
	}
}

Soru-42)

public class Driver {

	private static void percentArray(double [] array, double arrPer[], int index, double sum){
        
		double percent = array[index] / sum;
        
		arrPer[index] = (percent*100);
		
	}
	
	public static void main(String arg[]){
		
		double arr[] = {4,18,15,16,23,42};
		
		double sum = 0;

		double arrPercent[] = new double[arr.length];
		
		for (int i = 0; i < arr.length; i++){
			
			sum += arr[i];
		}
		
		for (int i = 0; i < arr.length; i++)
			
			percentArray(arr,arrPercent,i,sum);
		
		for (int i = 0; i < arrPercent.length; i++){
			
			System.out.print(i + ".nci elemanin toplama orani" + arrPercent[i]);
			
			System.out.println();

		}
		
		System.out.println();
		
	}
}

Soru-43)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int myValue;
		
		System.out.print("Klavyeden bir sayi giriniz: ");
		
		myValue = keyboard.nextInt();
		
		if (myValue%2 == 0)
			System.out.println("Girilen sayi cifttir");
		else
			System.out.println("Girilen sayi tektir");
		
		System.out.println();
		
		keyboard.close();
		
	}
}

Soru-44)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int myValue1;
		
		System.out.print("Klavyeden bir sayi giriniz: ");
		
		myValue1 = keyboard.nextInt();
		
		int myValue2;

		System.out.print("Klavyeden ikinci bir sayi giriniz: ");

		myValue2 = keyboard.nextInt();
		
		System.out.println("Birinci sayinin ikinci sayiya bolumu " 
		+ (myValue1 / myValue2) + " kalan: " + myValue1%myValue2);
				
		System.out.println();
		
		keyboard.close();
		
	}
}

Soru-45)

public class Driver {

	public static void main(String arg[]){
		

		Scanner keyboard = new Scanner(System.in);

		int myArraySize;
		
		float[] myArray = new float[0];			
		
		System.out.print("Klavyeden dizinin boyutunu giriniz: ");
		
		myArraySize = keyboard.nextInt();
		
		myArray = new float[myArraySize];
		
		System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
		
		for (int i = 0; i < myArraySize; i++){
			
			System.out.print("Klavyeden dizinin " + i + ".nci elemanini giriniz: ");

			myArray[i] = keyboard.nextFloat();
			
		}
		
		float sum = 0;
		
		for (int i = 0; i < myArraySize; i++){
			
				sum += myArray[i];
				
		}
				
		System.out.println("Sayilarin toplami: " + sum);
		
		System.out.println("Bye");
		
		keyboard.close();
	}
		
}

Soru-46)

public class Driver {

	public static void main(String arg[]){
		

		Scanner keyboard = new Scanner(System.in);

		int myArraySize;
		
		float[] myArray = new float[0];			
		
		System.out.print("Klavyeden dizinin boyutunu giriniz: ");
		
		myArraySize = keyboard.nextInt();
		
		myArray = new float[myArraySize];
		
		System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
		
		for (int i = 0; i < myArraySize; i++){
			
			System.out.print("Klavyeden dizinin " + i + ".nci elemanini giriniz: ");

			myArray[i] = keyboard.nextFloat();
			
		}
		
		System.out.println("Cift sayilar:");
		
		for (int i = 0; i < myArray.length; i++){
			
			if (myArray[i] %2 == 0)
				System.out.print(" " + myArray[i] + " ");
		}
				
		System.out.println();
		
		System.out.println("Tek sayilar:");
		
		for (int i = 0; i < myArray.length; i++){
			
			if (myArray[i] %2 == 1)
				System.out.print(" " + myArray[i] + " ");
		}
				
		System.out.println("Bye");
		
		keyboard.close();
	}
		
}

Soru-47)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		float myValue;
		
		System.out.println("Klavyeden bir sayi giriniz: ");
		
		myValue = keyboard.nextFloat();
		
		float myArray[] = {25,22,17,19,47,3,98,5,124,10};
	
		System.out.println("Klavyeden girdigimiz sayidan buyuk olan dizideki sayilar sunlardir" );
		
		for (int i = 0; i < myArray.length; i++){
			
			if(myArray[i] > myValue)
				System.out.println(myArray[i]);
		}
		
		System.out.println("Bye");
		
		keyboard.close();
	}
		
}

Soru-48)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		float myValue;
		
		System.out.println("Klavyeden bir sayi giriniz: ");
		
		myValue = keyboard.nextFloat();
		
		float myArray[] = {25,22,17,19,47,3,98,5,124,10};
	
		System.out.println("Klavyeden girdiginiz sayiya tam bolunen dizi elemanlari: " );
		
		for (int i = 0; i < myArray.length; i++){
			
			if(myArray[i] % myValue == 0)
				
				System.out.println(myArray[i]);
			
		}
		
		System.out.println("Bye");
		
		keyboard.close();
	}
		
}

Soru-49)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		int myValue;
		
		int myArray[] = {25,22,17,19,47,3,98,5,124,10};

		System.out.println("Klavyeden bir sayi giriniz: ");
		
		int counter = 1;
		
		while ((myValue = keyboard.nextInt()) > 0 && myValue < 11) {				

			int orderCounter = myValue;

			if (myValue < 0 && myValue > 11){
				System.out.println("Klavyeden gecerli bir sayi giriniz!");
				break;
			}
			
			for (int i = 0; i < myArray.length; i++){
				
				counter = 1;
				
				for (int j = 0; j < i; j++){
					if (myArray[i] > myArray[j])
						counter++;
					if (counter > orderCounter){
						break;
					}			
				}
				
				for (int j = i + 1; j < myArray.length; j++){
					if (myArray[i] > myArray[j])
						counter++;
					if (counter > orderCounter)
						break;
				}			
					
				if (counter == orderCounter){
						System.out.println(orderCounter + ".nci kucuk sayi " + myArray[i]);
						break;
				}
			 }
			
			System.out.println("Yeni sira girebilirsiniz");
			
		}
		
		System.out.println("Bye");

		keyboard.close();
	}
		
}

Soru-50)

public class Driver {

	public static void main(String arg[]){
		
		int myArr[][] = {{3,5,6},{4,2,3},{4,8,7}};
		
		for (int i = 0; i < 3; i++){
			for (int j = 0; j < 3; j++){
				System.out.print(" " + myArr[i][j] + " ");
			}
			System.out.println();
		}
		
		System.out.println("Bye");

	}
		
}

Soru-51)

public class Driver {

	private static void rowSumArray(int [][] array, int row, int column){
        
		for(int i = 0; i < row; i++){
			int rowSum = 0;
			for(int j = 0; j < column; j++){
				rowSum += array[i][j];
			}
			System.out.println(i + ".nci satirin elemanlari toplami: " + rowSum);
		}
	}
	
	private static void columnSumArray(int [][] array, int row, int column){
        
		for(int j = 0; j < column; j++){
			int columnSum = 0;
			for(int i = 0; i < row; i++){
				columnSum += array[i][j];
			}
			System.out.println(j + ".nci sutunun elemanlari toplami: " + columnSum);
		}
				
	}
	
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int[][] myArr = new int[3][3];
		
		System.out.println("Diznin elemanlarini giriniz");
		
		for (int i = 0; i < 3; i++){
			for (int j = 0; j < 3; j++){
				myArr[i][j] = keyboard.nextInt();
			}
		}
		
		rowSumArray(myArr, 3, 3);
		
		columnSumArray(myArr, 3, 3);
		
		System.out.println("Bye");

		keyboard.close();
		
	}
		
}

Soru-52)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int[][] myArr = new int[5][5];
		
		for (int i = 0; i < 5; i++){
			for (int j = 0; j < 5; j++){
				if (j == i)
					myArr[i][j] = 1;
				else
					myArr[i][j] = 0;
			}
		}
		
		for (int i = 0; i < 5; i++){
			for (int j = 0; j < 5; j++){
				System.out.print(" " + myArr[i][j] + " ");
			}
			System.out.println();
		}
		
		System.out.println("Bye");

		keyboard.close();
		
	}
		
}

Soru-53)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int[][] myArr = new int[5][5];
		
		for (int i = 0; i < 5; i++){
			for (int j = 0; j < 5; j++){
				if (j <= i)
					myArr[i][j] = 1;
				else
					myArr[i][j] = 0;
			}
		}
		
		for (int i = 0; i < 5; i++){
			for (int j = 0; j < 5; j++){
				System.out.print(" " + myArr[i][j] + " ");
			}
			System.out.println();
		}
		
		System.out.println("Bye");

		keyboard.close();
		
	}
		
}

Soru-54)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int[][] myArr = new int[5][5];
		
		int counter;
		
		for (int i = 0; i < 5; i++){
			counter = 1;
			for (int j = 0; j < 5; j++){
				if (j <= i)
					myArr[i][j] = counter++;
				else
					myArr[i][j] = 0;
			}
		}
		
		for (int i = 0; i < 5; i++){
			for (int j = 0; j < 5; j++){
				System.out.print(" " + myArr[i][j] + " ");
			}
			System.out.println();
		}
		
		System.out.println("Bye");

		keyboard.close();
		
	}
		
}

Soru-55)

public class Driver {

	public static void main(String arg[]){
		
		int[][] myArr = new int[5][5];
		
		for (int i = 0; i < 5; i++){
			for (int j = 0; j < 5; j++){
				if (j % 2 == 0 )
					myArr[i][j] = 1;
				else
					myArr[i][j] = 0;
			}
		}
		
		for (int i = 0; i < 5; i++){
			for (int j = 0; j < 5; j++){
				System.out.print(" " + myArr[i][j] + " ");
			}
			System.out.println();
		}
		
		System.out.println("Bye");
		
	}
		
}


Soru-56)

public class Driver {

	public static void main(String arg[]){
		
		int[][] myArr = new int[5][5];
		
		for (int i = 0; i < 5; i++){
			if(i % 2 == 1 )
				for (int j = 0; j < 5; j++){
					if (j % 2 == 0 )
						myArr[i][j] = 1;
					else
						myArr[i][j] = 0;
				}
			else if (i % 2 == 0)
				for (int j = 0; j < 5; j++){
					myArr[i][j] = 1;
				}
		}
		
		for (int i = 0; i < 5; i++){
			for (int j = 0; j < 5; j++){
				System.out.print(" " + myArr[i][j] + " ");
			}
			System.out.println();
		}
		
		System.out.println("Bye");
		
	}
		
}


Soru-57)

public class Driver {

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int[][] myArr = new int[5][5];
		
		int myValue;
		
		System.out.println("4x4' lük dizinin elemanlarini giriniz: ");
		for (int i = 0; i < 4; i++){
			for (int j = 0; j < 4; j++){
				System.out.print(i + ".nci satir" + j + ".nci sutun degerini giriniz: ");
				myArr[i][j] = keyboard.nextInt();
			}
		}
		
		System.out.print("Dizide aranilacak degeri giriniz: ");
		
		myValue = keyboard.nextInt();
		
		for (int i = 0; i < 5; i++){
			for (int j = 0; j < 5; j++){
				if (myArr[i][j] == myValue)
					System.out.println("Aranilan deger olan " + myValue + " degeri " + i + ".nci satir ve " + j + ".nci sutunda bulundu.");
			}
		}
		
		System.out.println("Hoscakalin");

		keyboard.close();
		
	}
		
}

Soru-58)

public class Driver {

	private static void maxValue (int myValue1, int myValue2){
        
		if(myValue1 > myValue2)
			System.out.println("Buyuk olan sayi " + myValue1);
		else
			System.out.println("Buyuk olan sayi " + myValue2);
			
	}
	
	private static void minValue (int myValue1, int myValue2){
        
		if(myValue1 < myValue2)
			System.out.println("Kucuk olan sayi " + myValue1);
		else
			System.out.println("Kucuk olan sayi " + myValue2);
			
	}

	private static void maxDoubleValue (double myValue1, double myValue2){
        
		if(myValue1 > myValue2)
			System.out.println("Buyuk olan sayi " + myValue1);
		else
			System.out.println("Buyuk olan sayi " + myValue2);
			
	}
	
	private static void minDoubleValue (double myValue1, double myValue2){
        
		if(myValue1 < myValue2)
			System.out.println("Kucuk olan sayi " + myValue1);
		else
			System.out.println("Kucuk olan sayi " + myValue2);
			
	}
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int myValue1, myValue2;
		
		double myValueD1, myValueD2;
		
		System.out.println("Ilk degeri giriniz: ");
		
		myValue1 = keyboard.nextInt();
		
		System.out.println("Ikinci degeri giriniz: ");
		
		myValue2 = keyboard.nextInt();
		
		maxValue(myValue1, myValue2);
		
		minValue(myValue1,myValue2);
		
		System.out.println("Ilk double degeri giriniz: ");
		
		myValueD1 = keyboard.nextDouble();
		
		System.out.println("Ikinci double degeri giriniz: ");
		
		myValueD2 = keyboard.nextDouble();
		
		maxDoubleValue(myValueD1, myValueD2);
		
		minDoubleValue(myValueD1, myValueD2);
		
		
		
		System.out.println("Hoscakalin");

		keyboard.close();
		
	}
		
}

soru-59)

public class Driver {

	private static void squareValue (double myValue){
		
		double squareValue;
		
		squareValue = myValue*myValue;
		
		System.out.println("Girdiginiz sayinin karesi " + squareValue);
			
	}
	

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		double myValue;
		
		System.out.println("Degeri giriniz: ");
		
		myValue = keyboard.nextDouble();
		
		squareValue(myValue);
				
		System.out.println("Hoscakalin");

		keyboard.close();
		
	}
		
}

Soru-60)

public class Driver {

	private static void squareValue (double myValue1, double myValue2){
		
		double squareValue = 1;
		
		double temp = myValue1;
		
		for (int i = 0; i < myValue2; i++){
			squareValue *= temp;
		}
		System.out.println(squareValue);
			
	}
	

	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		double myValue1 = 5;
		double myValue2 = 2;
		
		System.out.print("5 in 2 inci cinsinden kuvveti: ");
		
		squareValue(myValue1, myValue2);
				
		System.out.println("Hoscakalin");

		keyboard.close();
		
	}
		
}

Soru-61)

public class Driver {

	private static double cevreHesapla (double yaricap){
		
		double cevre;
		
		double pi = 3.14;
		
		return (cevre = 2 * pi* yaricap);
			
	}
	
	private static double alanHesapla (double yaricap){
		
		double alan;
		
		double pi = 3.14;
		
		return (alan = pi* yaricap * yaricap);
			
	}
	
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		double yaricap = 5;
		
		double cevre = cevreHesapla(yaricap);
		
		System.out.println("Dairenin cevresi " + cevre);

		double alan = alanHesapla(yaricap);
		
		System.out.println("Dairenin alani " + alan);

		System.out.println("Hoscakalin");

		keyboard.close();
		
	}
		
}

Soru-62)

public class Driver {

	private static double asalBulucu (double myValue){
		
		for (int i = 2; i < myValue; i++){
			
			if (myValue % i == 0){
				
				return 0;
			}
			else 
				continue;

		}
		
		return 1;
		
	}
	
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		double myValue;
		
		System.out.print("Klavyeden asalligi test edilecek elemani giriniz: ");
		
		myValue = keyboard.nextInt();
		
		if (asalBulucu(myValue) == 1)
			System.out.print("Klavyeden girilen sayi asal");
		else if(asalBulucu(myValue) == 0)
			System.out.print("Klavyeden girilen sayi asal degil");

		keyboard.close();
		
	}
		
}

Soru-63)

public class Driver {

	private static double asalBulucu (double myValue){
		
		for (int i = 2; i < myValue; i++){
			
			if (myValue % i == 0){
				
				return 0;
			}
			else 
				continue;
		}
		
		return 1;
		
	}
	
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);

		double myValue;
		
		System.out.print("Klavyeden icindeki asal sayilarin tespit edilecegi sayiyi giriniz: ");
		
		myValue = keyboard.nextInt();
		
		if (myValue == 2){
			
			System.out.print(" " + myValue + " ");
		}
		else if (myValue > 2){
			System.out.print(" 2.0");
			for (double i = 3; i <= myValue; i++){
				if (asalBulucu(i) == 1)
					System.out.print(" " + i + " ");
			}
			
		}
		keyboard.close();
		
	}
		
}

Soru-64)

public class Driver {

	private static double diziToplayici (double myArray[], int size){
		
		double sum = 0;
		
		for (int i = 0; i < size; i++){
			
			sum += myArray[i];
			
		}
		return sum;
		
	}
	
	public static void main(String arg[]){
		
		double myArray[] = {2,4,6,5,10};
		
		double sum;
		
		sum = diziToplayici(myArray, 5);
		
		System.out.print("Dizi elemanlarinin toplami " + sum);
		
	}
		
}

Soru-65)

public class Driver {
	
	private static int enBuyuk(int myArray[], int size){
		
		int myArrayMax = myArray[0];
		
		for (int i = 0; i < 10 ; i++){
			
			if (myArray[i] > myArrayMax)
			
				myArrayMax = myArray[i];
						
		}
		
		return myArrayMax;
		
	}

	private static int enKucuk(int myArray[], int size){
		
		int myArrayMin = myArray[0];
		
		for (int i = 0; i < 10 ; i++){
			
			if (myArray[i] < myArrayMin)
			
				myArrayMin = myArray[i];
						
		}
		
		return myArrayMin;
		
	}
	
	public static void main(String arg[]){
		
		Scanner keyboard = new Scanner(System.in);
		
		int min, max;
		
		int[] myArray = new int[10];			
		
		System.out.println("Klavyeden dizinin elemanlarini giriniz: ");
		
		for (int i = 0; i < 10; i++){
			
			System.out.print("Klavyeden dizinin " + i + ".nci elemanini giriniz: ");

			myArray[i] = keyboard.nextInt();
			
		}
		
		min = enKucuk(myArray, 10);
		
		max = enBuyuk(myArray, 10);
		
		System.out.println("Dizideki en kucuk eleman " + min);
		
		System.out.println("Dizideki en buyuk eleman " + max);
		
		keyboard.close();
		
	}
}

Soru-66)

public class Driver {
	
	private static int diziSiraBulucu (int myArray[], int size, int n){
		
		int orderCounter = 1;
		int myValue = 0;
		
		for (int i = 0; i < size; i++){
			orderCounter = 1;
			myValue = myArray[i];
			for (int j = 0; j < size; j++){
			
				if (myValue > myArray[j])
					orderCounter++;
		
			}
			
			if (orderCounter == n)		
				return myValue;
		}
		
		return 0;

	}
	
	public static void main(String arg[]){
		
		int myArray[] = {25,22,17,19,47,3,98,5,124,10};
		
		int myValue;
		
		myValue = diziSiraBulucu(myArray, 10, 4);

		System.out.println(4 + ".ncu en kucuk sayi " + myValue);

		System.out.println("Bye");

	}
}

Soru-67)

public class Driver {
	
	private static void rowSumArray(int [][]array, int row){
        
		for(int i = 0; i < row; i++){
			int rowSum = 0;
			for(int j = 0; j < 5; j++){
				rowSum += array[i][j];
			}
			System.out.println(i + ".nci satirin elemanlari toplami: " + rowSum);
		}
	}
	
	public static void main(String arg[]){
		
		int myArray[][] = {{25,22,17,19,47},{3,98,5,124,10}};
		
		rowSumArray(myArray, 2);

		System.out.println("Bye");

	}
}

Soru-68)

public class Driver {
	
	private static void sumArray(int [][] array, int row, int column){
        
		for(int i = 0; i < row; i++){
			int rowSum = 0;
			for(int j = 0; j < column; j++){
				rowSum += array[i][j];
			}
			System.out.println(i + ".nci satirin elemanlari toplami: " + rowSum);
		}
		
		for(int j = 0; j < column; j++){
			int columnSum = 0;
			for(int i = 0; i < row; i++){
				columnSum += array[i][j];
			}
			System.out.println(j + ".nci sutunun elemanlari toplami: " + columnSum);
		}
	}
	
		
	public static void main(String arg[]){
		
		int myArray[][] = {{25,22,17,19,47},{3,98,5,124,10}};
		
		sumArray(myArray, 2, 5);

		System.out.println("Bye");

	}
}

Soru-69)

public class Driver {
	
	private static int ikiBoyutSiralama (int myArray[][], int row, int column, int n){
		
		int orderCounter;
		int myValue = 0;
		
		for (int i = 0; i < row; i++)
			for (int j = 0; j < column; j++){
			orderCounter = 1;
			myValue = myArray[i][j];
			for (int k = 0; k < row; k++)
				for (int l = 0; l < column; l++){
			
				if (myValue < myArray[k][l])
					orderCounter++;
		
			}
			
			if (orderCounter == n)		
				return myValue;
		}
		
		return 0;

	}
	
	public static void main(String arg[]){
		
		int myArray[][] = {{18,12,11},{9,8,5},{3,2,0}};		
		
		int order = 1;
		
		for (int i = 0; i < 3; i++)
			for (int j = 0; j < 3; j++){
				myArray[i][j] = ikiBoyutSiralama(myArray, 3, 3, order++);
				if(order == 10)
					break;
			}
			
		for (int i = 0; i < 3; i++){
			for (int j = 0; j < 3; j++){
				System.out.print(" " + myArray[i][j] + " ");
			}
			System.out.println();
		}
		
		System.out.println("Bye");

	}
}

Soru-70)

import java.util.Scanner;

public class Fibonacci {
	
	private static int fibo(int n){
		
		if (n < 2)
			return n;
		else				
 		return fibo(n-1) + fibo(n-2);
	
	}

	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int myFiboNum;
		
		System.out.print("Fiboniacci dizinin kacinci elemanini gireceksiniz: " );
		myFiboNum = in.nextInt();
		
		System.out.println("Fiboniacci eleman: " + fibo(myFiboNum));
		
		in.close();
	}
}

-------------------------------------------------------------------------------------------------------------------------------------
********************************************algoritma_prog_guz_2012_odev_1***********************************************************
Soru-1)
a) (3910)10 = (7506)8 = (F46)16 b) (1010010.00101011100001010001111010111000010100011110101110000101000)2 = (66,234375)8
c) (01101)2 (01100)2

Soru-2)

import java.util.Scanner;

public class Algoritma {

	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int X, N;
		
		X = 1;
		N = 3;
		
		int Enb = X;
		
		for (int i = 1; i < N; i++){
			
			System.out.print("Yeni X degeri giriniz: ");
			
			X = in.nextInt();
			
			System.out.print("Enb: " + Enb + " i: " + i);
			if(Enb > X == false){
				Enb = X;
			}
			System.out.println(" " + "Yeni Enb: " + Enb);
		}
		
		in.close();
	}
}

Soru-3)

import java.util.Scanner;

public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		double r, alan, hacim;

		System.out.print("Kurenin yari capini cm cinsinden giriniz: ");
		
		r = in.nextDouble();
		
		alan = Math.PI * r * r;
		
		hacim = (4*Math.PI*r*r*r)/3;
		
		System.out.println("Kurenin alani: " + alan + " cm^2 ve hacmi: " + hacim + " cm^3.");
		
		in.close();
	}
	
}

Soru-4)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
		
			
			double pozAvg, negAvg;
			
			int pozCount = 0;
			int negCount = 0;
			double pozSum = 0;
			double negSum = 0;
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden kac adet sayi girilecegini giriniz: ");
			int N = in.nextInt();
				
			double[] A = new double[N];
			
			for (int i = 0; i < N; i++){
				System.out.print("Yeni sayi giriniz: ");
				A[i] = in.nextDouble();
			}
			
			for (int i = 0; i < N; i++){
				if(A[i] > 0){
					pozSum += A[i];
					pozCount++;
				}
				else if (A[i] < 0){
					negSum += A[i];
					negCount++;
				}
			}
			
			pozAvg = pozSum / pozCount;
			
			negAvg = negSum / negCount;
			
			System.out.println("Pozitif sayilarin ortalamasi" + pozAvg);
			
			System.out.println("Negatif sayilarin sayisi" + negAvg);
			
			in.close();
		}
	
}
------------------------------------------------------------------------------------------------------------------------------------
*******************************algoritma_prog_guz_2012_odev_2************************************************************************
Soru-1)

import java.util.Scanner;

public class AlgıoKarsilastirma {

	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int A[]	 = {4, -2, 7};
		int B[] = {2, 7, 4};
		
		int S = 0;
		
		for (int i = 1; i <= 3; i++)
			for (int j = 1; j <= 1; j++){
				if (A[i] == B[j])
					S += 1;
			}
		
		System.out.println("S degeri: " + S);
		
		in.close();
	}
}

Soru-2)

package test;
import java.util.Scanner;;

class Exam {

	Scanner scan = new Scanner(System.in);
	int row;
	int column;
	
	Exam(int row, int column){
		this.row = row;
		this.column = column;
	}
	
	void averageStudents(){
		
		int[][] arr = new int[row][column];	
		for (int i = 0; i < row; i++)
			for (int j = 0; j < column; j++)
			{
				System.out.println(i + "nolu ogrencinin " + j + ".inci ders notunu giriniz");
				arr[i][j]  = scan.nextInt();
			}
		
		int[] ortalama = new int[row];
		int toplam;
		
		for (int i = 0; i < row; i++){
			toplam = 0;
			for (int j = 0; j < column; j++)
			{
				toplam += arr[i][j];
			}
			ortalama[i] = (toplam / column);
		}
		
		for (int i = 0; i < row; i++)
			for (int j = 0; j < column; j++)
			{
				if (arr[i][j] > ortalama[i])
					System.out.println(i + "nolu ogrencinin " + j + ".inci dersten gecti");
				else
					System.out.println(i + "nolu ogrencinin " + j + ".inci dersten kaldi");
		}
	}	
}

public class Main {
	public static void main(String arg[]){

		Exam students = new Exam(4, 5);
		
		students.averageStudents();
		
	}
}

Soru-3)

package test;

public class detectNumberSigns {
	public static void main (String arg[]){
		int pozCount = 0;
		int negCount = 0;
		int zeroCount = 0;
	int[] A = new int[100];
	
		for (int i = 0; i < 100; i++){
			if(i%2 == 0)
				A[i] = i;
			else
				A[i] = -i;
		}
		
		for (int i = 0; i < 100; i++){
			if (A[i] < 0)
				negCount++;
			else if (A[i] > 0)
				pozCount++;
			else zeroCount++;
		}
		System.out.println("Pozitif sayilarin sayisi" + pozCount);
		
		System.out.println("Negatif sayilarin sayisi" + negCount);
		
		if (zeroCount != 0)
			System.out.println("Sýfýr elemaný mevcuttur");
	}
}

Soru-4)

import java.util.Scanner;
import java.util.Random;

public class Driver {
	
	private static void arrayTransposer(int myArr[][], int row, int column){
		
		int[][] myNewArray = new int[column][row];
		
		for (int i = 0; i < row; i++)
			for(int j = 0; j < column; j++){
				
				myNewArray[j][i] = myArr[i][j];
			}

		System.out.println("Transposesi alinmis dizi: ");
		
		for (int i = 0; i < column; i++){
			for (int j = 0; j < row; j++){
				System.out.print(" " + myNewArray[i][j] + " ");
			}
			System.out.println();
		}
		 
	}
	
	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int m,n;
		
		System.out.print("Matrisin satir sayisini giriniz: ");
		
		m = in.nextInt();

		System.out.print("Matrisin sutun sayisini giriniz: ");
		
		n = in.nextInt();

		int[][] myArray = new int[m][n];
		
		Random r = new Random();
		
		for (int i = 0; i < m; i++)
			for (int j = 0; j < n; j++){
		
			myArray[i][j] = r.nextInt(99);	
	
		}

		System.out.println();

		System.out.println("Esas dizi: ");

		for (int i = 0; i < m; i++){
			for (int j = 0; j < n; j++){
			
			System.out.print(" " + myArray[i][j] + " ");
			
			}
			System.out.println();
		}
				
		arrayTransposer(myArray, m, n);

		System.out.println();
		
		in.close();
	}
	
}

Soru-5)

import java.util.Scanner;
import java.util.Random;

public class Driver {
	
	private static void arrayTransposer(int myArr1[][], int row1, int column1, int myArr2[][], int row2, int column2){
		
		if (column1 != row2){
			System.out.println("Girilen matris boyutlari carpim icin uygun degildir!");
			System.exit(1);
		}
		int[][] myNewArray = new int[row1][column2];
		
		int temp = column1;
		int sum;
		
		for (int i = 0; i < row1 ; i++){
			for (int j = 0; j < column2; j++){
				sum = 0;
				for (int k= 0; k < temp; k++){
					sum += myArr1[i][k] * myArr2[k][j];
				}
				myNewArray[i][j] = sum;	
			}
		}

		System.out.println("Transposesi alinmis dizi: ");
		
		for (int i = 0; i < row1 ; i++){
			for (int j = 0; j < column2; j++){
				System.out.print(" " + myNewArray[i][j] + " ");
			}
			System.out.println();
		}
		 
	}
	
	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int m,n,k,l;
		
		System.out.print("Ilk matrisin satir sayisini giriniz: ");
		
		m = in.nextInt();

		System.out.print("Ilk matrisin sutun sayisini giriniz: ");
		
		n = in.nextInt();

		int[][] myArray = new int[m][n];
		
		Random r = new Random();
		
		for (int i = 0; i < m; i++)
			for (int j = 0; j < n; j++){
		
			myArray[i][j] = r.nextInt(99);	
	
		}

		System.out.println();

		System.out.println("Esas dizi: ");

		for (int i = 0; i < m; i++){
			for (int j = 0; j < n; j++){
			
			System.out.print(" " + myArray[i][j] + " ");
			
			}
			System.out.println();
		}
		
		System.out.print("Ikinci matrisin satir sayisini giriniz: ");
		
		k = in.nextInt();

		System.out.print("Ikinci matrisin sutun sayisini giriniz: ");
		
		l = in.nextInt();

		int[][] myArray2 = new int[k][l];
		
		Random r2 = new Random();
		
		for (int i = 0; i < k; i++)
			for (int j = 0; j < l; j++){
		
			myArray2[i][j] = r2.nextInt(99);	
	
		}

		System.out.println();

		System.out.println("Ikinci dizi: ");

		for (int i = 0; i < k; i++){
			for (int j = 0; j < l; j++){
			
			System.out.print(" " + myArray2[i][j] + " ");
			
			}
			System.out.println();
		}
				
		System.out.println("Iki dizinin carpimi: ");
		
		arrayTransposer(myArray, m, n, myArray2, k, l);
		
		System.out.println();
		
		in.close();
	}
	
}
------------------------------------------------------------------------------------------------------------------------------------
*******************************************************AlgoritmaSorulariWord********************************************************
Soru-1)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden baslangic sayisini girilecegini giriniz: ");
			
			int X = in.nextInt();
			
			System.out.print("Klavyeden bitis sayisini girilecegini giriniz: ");
			
			int N = in.nextInt();
				
			System.out.print("Klavyeden girilen sayilar ve arasindaki sayilar: ");
			
			for (int i = X; i <= N; i++){
				
				System.out.print(" " + i + " ");
				
			}
			
			System.out.println();
			
			in.close();
		}
	
}
	
Soru-2)

import java.util.Scanner;

public class Fibonacci {
	
	private static int fibo(int n){
		
		if (n < 2)
			return n;
		else				
 		return fibo(n-1) + fibo(n-2);
	
	}

	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int myFiboNum;
		
		System.out.print("Fiboniacci dizinin kacinci elemanini gireceksiniz: " );
		myFiboNum = in.nextInt();
		
		System.out.println("Fiboniacci eleman: " + fibo(myFiboNum));
		
		in.close();
	}
}

Soru-3)

import java.util.Scanner;

public class Driver {
	
	private static void bolenBulucu(int myValue){
		
		System.out.println("Klavyeden girilen sayinin tam bolenleri: ");
		
		for (int i = 1; i <= myValue; i++){
			
			if(myValue%i == 0)
				System.out.print(" " + i + " ");
		
		}
		 
	}

	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden bolenleri bulunacak sayiyi giriniz: ");
			
			int sayi = in.nextInt();
			
			bolenBulucu(sayi);
			
			in.close();
		}
	
}
	
Soru-4)

import java.util.Scanner;

public class Driver {
	
	private static int min (int myArr[], int index, int size){
		
		int temp = 0;
		
		for (int i = 0; i < size ; i++)
		{
				temp = myArr[index];
				
				if (myArr[i] < temp)
					return 0;
				if (myArr[i] > temp && i == 2)
					break;
				
		}
		
		return temp;			

	}
	
	private static int max (int myArr[], int index, int size){
	
	int temp = 0;
	
		for (int i = 0; i < size; i++)
		{
				temp = myArr[index];
				
				if (myArr[i] > temp)
					return 0;
				if (myArr[i] < temp && i == 2)
					break;
				
		}
		
		return temp;			
	}
	
	private static void ortadakiBulucu(int myValue1, int myValue2, int myValue3){
		
		int[] arr = {myValue1, myValue2, myValue3};
		
		for (int i = 0; i < 3; i++){
			if((min(arr,i,arr.length) == 0) && (max(arr,i,arr.length) == 0))
				System.out.println("Ortadaki sayi " + arr[i]);
		}
		 
	}

	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden ortadaki bulunacak uc sayidan ilkini giriniz: ");
			
			int sayi1 = in.nextInt();
			
			System.out.print("Klavyeden ortadaki bulunacak uc sayidan ikincisini giriniz: ");
			
			int sayi2 = in.nextInt();
			
			System.out.print("Klavyeden ortadaki bulunacak uc sayidan ucuncusunu giriniz: ");
			
			int sayi3 = in.nextInt();
			
			ortadakiBulucu(sayi1, sayi2, sayi3);
			
			in.close();
		}
	
}

Soru-5)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden ilk sayiyi giriniz: ");
			
			double sayi = in.nextDouble();
			
			int sayici = 1;
			
			double top = 0;
			
			double ort;
			
			while (sayi != 0)
			{
				
				top += sayi;
				
				ort = top / sayici;

				sayici++;

				System.out.println("Su ana kadarki girilen sayilarin ortalamasi: " + ort);
				
				System.out.print("Yeni sayi giriniz: ");
				
				sayi = in.nextDouble();
				
			}
			
			System.out.println("0 girisi kabul edilmemektedir. Hoscakalin.");
			
			in.close();
		
	}
	
}
	
Soru-6)

import java.util.Scanner;

public class Driver {
	
	private static void tekciftToplamBulucu(int newArr[], int size){
		
		int oddCounter = 0;
		int evenCounter = 0;
		for (int i = 0; i < size; i++){
			
			if (newArr[i] % 2 == 0)
				evenCounter += newArr[i];
			else if (newArr[i] % 2 == 1)
				oddCounter += newArr[i];
			
		}
		
		System.out.println("Klavyeden girilen cift sayilarin toplami " + evenCounter + 
				" tek sayilarin toplami " + oddCounter);
		 
	}

	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			int []myArr = new int[20];
			
			System.out.print("Klavyeden ilk sayiyi giriniz: ");
			
			for (int i = 0; i < 20; i++){
				
				myArr[i] = in.nextInt();
				
				System.out.print("Klavyeden sonraki sayiyi giriniz: ");
			}
			
			tekciftToplamBulucu(myArr, myArr.length);
			
			in.close();
		
	}
	
}
	
Soru-7)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden ilk sayiyi giriniz: ");
			
			double sayi = in.nextDouble();
			
			int sayici = 1;
			
			double top = 0;
			
			double ort;
			
			while (sayi != 0)
			{
				
				top += (sayi*sayi);
				
				ort = top / sayici;

				sayici++;

				System.out.println("Su ana kadarki girilen sayilarin ortalamasi: " + ort);
				
				System.out.print("Yeni sayi giriniz: ");
				
				sayi = in.nextDouble();
				
			}
			
			System.out.println("0 girisi kabul edilmemektedir. Hoscakalin.");
			
			in.close();
		
	}
	
}

Soru-8)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden sayiyi giriniz: ");
			
			int x = in.nextInt();
			
			int top = 0;
			
			for (int i = 1; i <= x; i++){
				top += i;
			}
			
			System.out.println("1' den x' e kadar olan sayilarin toplami: " + top);
			
			in.close();
		
	}
	
}

Soru-9)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden ilk sayiyi giriniz: ");
			
			int A = in.nextInt();
			
			System.out.print("Klavyeden ikinci sayiyi giriniz: ");
			
			int B = in.nextInt();
			
			System.out.println(B + " " + A );
			
			in.close();
		
	}
	
}

Soru-10)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden sayiyi giriniz: ");
			
			int sayi = in.nextInt();
			
			int bolucu = 10;
			
			int bolum;
			
			int basamak = 1;
			
			System.out.println(basamak + "ler basamagi " + sayi % bolucu);

			bolum = sayi / bolucu;
			
			basamak *= 10;
			
			do{
				System.out.println(basamak + " basamagi " + bolum % bolucu);
				
				basamak *= 10;
			}
			while ((bolum /= bolucu) != 0);
			
			System.out.print("Klavyeden ikinci sayiyi giriniz: ");
	
			in.close();
		
	}
	
}

Soru-11)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden kac adet sayi girilecegini giriniz: ");
			
			int N = in.nextInt();
			
			int negCounter = 0;
			int pozCounter = 0;
			int negSum = 0;
			int pozSum = 0;
			int negAvg, pozAvg;
			
			int[] myArr = new int[N];
			
			System.out.print("Klavyeden sayi giriniz: ");
			
			for (int i = 0; i < N; i++){
				myArr[i] = in.nextInt();
				System.out.print("Yeni sayiyi giriniz: ");
			}
			
			for (int i = 0; i < N; i++){
				
				if (myArr[i] < 0){
					negSum += myArr[i];
					negCounter++;
				}else if(myArr[i] > 0){
					pozSum += myArr[i];
					pozCounter++;
				}
			
			}
	
			negAvg = negSum / negCounter;
			pozAvg = pozSum / pozCounter;
			
			System.out.println("Pozitif sayilarin ortalamasi " + pozAvg + 
					" negatif sayilarin ortalamasi " + negAvg);
			
			in.close();
		
	}
	
}

Soru-12)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);	
			
			int tDividedCounter = 0;
		
			int[] myArr = new int[10];
			
			System.out.print("Klavyeden sayi giriniz: ");
			
			for (int i = 0; i < 10; i++){
				myArr[i] = in.nextInt();
				System.out.print("Yeni sayiyi giriniz: ");
			}
			
			System.out.println();
			
			for (int i = 0; i < 10; i++){
				
				if (myArr[i] % 3 == 0){
					tDividedCounter++;
					System.out.println( myArr[i] + " " + tDividedCounter);
				}
			}
	
			System.out.println("Klavyeden girilen sayilardan "
					+ " uce bolunabilenlerin sayisi " + tDividedCounter );
			
			in.close();
		
	}
	
}

Soru-13)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);	
			
			System.out.print("Klavyeden bir karakter giriniz: ");
			
			char myChar = in.nextLine().charAt(0);
		
			switch(myChar){
			
				case 'a': System.out.println("ANKARA");
					break;
				case 'b': System.out.println("BURSA");
					break;
				case 'r': System.out.println("BURSA");
					break;
				case 't': System.out.println("BURSA");
					break;
				case 'd': System.out.println("DENIZLI");
					break;
				case 'e': System.out.println("EDIRNE");
					break;
				case 'f': System.out.println("EDIRNE");
					break;
				case 'k': System.out.println("KIRIKKALE");
					break;
				default:
					System.out.println("Girdiginiz harfin karsilik sehri yoktur.");
			
			}
			
			in.close();
		
	}
	
}

Soru-14)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden sayiyi giriniz: ");
			
			int sayi = in.nextInt();
			
			int bolucu = 10;
			
			int bolum;
			
			System.out.println("Klavyeden girilen sayinin tersi: ");

			System.out.print(sayi % bolucu);

			bolum = sayi / bolucu;	
			
			do{
				System.out.print(bolum % bolucu);
			}
			while ((bolum /= bolucu) != 0);
			
			System.out.println();

			in.close();
		
	}
	
}
-------------------------------------------------------------------------------------------------------------------------------------
**********************************************AlgoritmaveProgramlama_Odev3***********************************************************
Soru-1)
public class Driver {
	
	private static void arraySummer (int array[], int size){

		if (size > 100){
			System.out.println("Dizi boyutu istenen buyuklugun ustundedir");
			System.exit(1);
		}
		
		int oddCounter = 0; //tek sayi sayici
		int evenCounter = 0; //cift sayici
		int oddTempSum = 0;
		int evenTempSum = 0;
		
				for (int i = 0; i < size; i++){
					if (array[i] % 2 == 0){
						
						if (evenCounter == 0){
							System.out.print(" " + array[i] + " ");
							evenTempSum = array[i];
							evenCounter++;
						}else {
							evenTempSum += array[i];							
							System.out.print(" " + evenTempSum + " ");
						}
						
					}
					else if (array[i] % 2 == 1){
						
						if (oddCounter == 0){
							System.out.print(" " + array[i] + " ");
							oddTempSum = array[i];
							oddCounter++;
						}else {
							oddTempSum += array[i];							
							System.out.print(" " + oddTempSum + " ");
						}
					}
				}

	}
	
	public static void main(String arg[]){
		
		int[] myArray = new int[10];
		
		Random r = new Random();
		for (int i = 0; i < 10; i++){
		
			myArray[i] = r.nextInt(20);	
	
		}

		for (int i = 0; i < 10; i++){
			
			System.out.print(" " + myArray[i] + " ");
			
		}
		
		System.out.println();
		
		arraySummer(myArray, 102);
		
	}
}

Soru-2)

public class Driver {
	
	public static void main(String arg[]){
		
		Scanner strIn = new Scanner(System.in);
		String myStr;

		System.out.print("String ifadeyi giriniz: ");
		myStr = strIn.nextLine();
		
		System.out.println(myStr);
					
		myStr = myStr.toUpperCase();
		
		System.out.println(myStr);

		strIn.close();
	}
}

Soru-3)

public class Driver {
	
	public static void main(String arg[]){
		
		float[] myArray = new float[10];
		float[] myNewArray = new float[10];
		
		float sum = 0;
		float average;
		int counter = 0;
		Random r = new Random();
		
		for (int i = 0; i < 10; i++){
			myArray[i] = r.nextInt(20);	
		}

		for (int i = 0; i < 10; i++){
			System.out.print(" " + myArray[i] + " ");
			sum += myArray[i];
		}
		
		System.out.println();
		
		average = sum / myArray.length; 
		
		System.out.println("Ortalama: " + average);
		
		for (int i = 0; i < myArray.length; i++){
			if (myArray[i] >= average){
				myNewArray[counter++] = myArray[i]; 
			}
		}
		
		for (int i = 0; i < myArray.length; i++){
			
			if(myArray[i] < average){
			    myNewArray[counter++] = myArray[i];
			}
		}
		
		for (int i = 0; i < 10; i++){	
			System.out.print(" " + myNewArray[i] + " ");
		}
		
	}
}

Soru-4)

public class Driver {
	
	public static void main(String arg[]){
		
		Scanner strIn = new Scanner(System.in);
		String myStr;
		char ch;
		
		System.out.print("Ifadeyi giriniz: ");
		myStr = strIn.nextLine();
		
		System.out.print("Ekrana basilmasini istemediginiz karakteri giriniz: ");
		ch = strIn.next().charAt(0);
		
		for (int i = 0; i < myStr.length(); i++){
			
			if(myStr.charAt(i)!= ch){
				System.out.print(myStr.charAt(i));
			} 
		}
		
		strIn.close();
		
	}
}
-------------------------------------------------------------------------------------------------------------------------------------
************************************************AlgoritmaveProgramlama_Odev4*******************************************************
Soru-1)

import java.util.Scanner;

public class Driver {
	
	private static double fact (int myValue){
		
		double myFact = 1;
		
		if(myValue < 0){
			System.out.println("Lutfen 0' dan buyuk esit bir sayi giriniz!");
			System.exit(1);
		}
		
		if (myValue > 0){
			for(int i = 1; i <= myValue; i++){
				myFact *= i;
			}
		}
		
		return myFact;
	}
	
	private static double eCalc (int myN){
	
		double myE = 0;
		
		if (!(myN < 0)){
			for (int i = 0; i <= myN; i++){
				myE += (1/fact(i));
			}
		}
		return myE; 
	}
	
	public static void main(String arg[]){
		
		Scanner myIn = new Scanner(System.in);
		int myInt;
		double myE;
		
		System.out.print("n sayisini giriniz: ");
		myInt = myIn.nextInt();
		myE = eCalc(myInt);
		
		System.out.println("Girilen " + myInt + " sayisinin e degeri: " + myE);
		
		myIn.close();
		
	}
}

Soru-2)

import java.util.Random;

public class Driver {
	
	private static void indexSummer (int array[]){

		for (int i = 0; i < array.length; i++){
			array[i] += i;
			System.out.print(" " + array[i] + " ");
		}
		System.out.println();

	}
	
	public static void main(String arg[]){
		
		int[] myArray = new int[10];
		
		Random r = new Random();
		for (int i = 0; i < 10; i++){
		
			myArray[i] = r.nextInt(20);	
	
		}

		for (int i = 0; i < 10; i++){
			
			System.out.print(" " + myArray[i] + " ");
			
		}
		
		System.out.println();
		
		indexSummer(myArray);
		
	}
}

Soru-3)

import java.util.Scanner;

public class Driver {
	
	private static int arraySearcher(String myStr, char ch){
		
		int counter = 0;
		
		for (int i = 0; i < myStr.length(); i++){
			if(myStr.charAt(i) == ch)
				counter++;
		}
		return counter;

	}
	
	public static void main(String arg[]){
		
		Scanner strIn = new Scanner(System.in);
		String myStr;
		char myChar;
		
		System.out.print("String ifadeyi giriniz: ");
		myStr = strIn.nextLine();
		
		System.out.println("Ifadem: " + myStr);
		
		System.out.print("Ifadede aranacak harfi giriniz: ");
		myChar = strIn.next().charAt(0);
		
		System.out.println("Ifadede arancak harf: " + myChar);
		
		System.out.println("Ifadedeki aranan harf sayisi: " + arraySearcher(myStr,myChar));
		
		strIn.close();
	}
	
}

Soru-4)

public class Driver {
	
	private static void stringReverser(String myStr){
		
		for (int i = myStr.length() -1 ; i >= 0 ; i--){
			System.out.print(myStr.charAt(i));
		}

	}
	
	public static void main(String arg[]){
		
		Scanner strIn = new Scanner(System.in);
		
		String myStr;
		
		System.out.print("String ifadeyi giriniz: ");
		
		myStr = strIn.nextLine();
		
		System.out.print("Ifadenin tersi: ");

		stringReverser(myStr);
		
		strIn.close();
	}
	
}
-------------------------------------------------------------------------------------------------------------------------------------
*********************************************AlgoritmaveProgramlama_Odev5***********************************************************
Soru-1)

import java.util.Scanner;
import java.util.Random;

public class Driver {
	
	private static int[][] arrayExtracter(int myArr[][], int row, int column){
		
		int[][] newArr = new int[row-2][column-2]; //n-2,n-2 cikarilacak matrisin aktarilacagi 
												   //gecici dizi olusturulur.
		for (int i = 1 ; i < row - 1; i++)
			for (int j = 1; j < column - 1; j++){
			
				newArr[i-1][j-1] = myArr[i][j]; //parametre olan dizideki n-2, n-2 araligindaki
												//elemanlar geri dondurulecek yeni olusturulan 
												//matrise aktarilir.
		}

		return newArr; 
	}
	
	private static int[][] arraySummer(int myArr[][], int row, int column){
		
		int[][] newArr = new int[row][column];
		
		int sum; //gecici toplayiciyi tanimla
		
		if(row > 3 && column > 3) //eger parametre olarak alinan dizinin satir ve sutun
								  //boyutu 3' ten buyukse
		{
				for (int i = 0; i < row - 2; i++){ //satir sayisi tamamlanmaya 2 eksige kadar
		
					for (int j = 0; j < column - 2; j++){ //sutun sayisi tamamlanmaya 2 eksige kadar
					
						sum = 0; //gecici toplayiciyi sifirla
						
						//Bulundugumuz konum [0][0].inci eleman olmak uzere 3x3'luk matrisin elemanlarinin
						//ortalamasini elde edecegiz.
						for (int k = i; k < i + 3; k++) // sirasiyla satiri bulundugu konumdan 
														//3 buyugune kadar arttir
							for (int l = j; l < j + 3; l++){ // sirasiyla satiri bulundugu konumdan
															//3 buyugune kadar
								sum += myArr[k][l];			//sirasiyla elemanlari gecici toplayiciya ekle
							}
						newArr[i][j] = (sum/9); //toplamlarin ortalamasi
					}
					for (int j = column - 2; j < column; j++){ //sutun sayisinin tamamlanmas
						
						sum = 0;
						
						for (int k = i; k < i + 3; k++)
		
							for (int l = j; l > j - 3; l--){
								
								sum += myArr[k][l];
							}
						newArr[i][j] = (sum/9);
					}
					
				}
			
				for (int i = row - 2; i < row; i++){
					
					for (int j = 0; j < column - 2; j++){
						
						sum = 0;
						
						for (int k = i; k > i - 3; k--)
							for (int l = j; l < j + 3; l++){
								
								sum += myArr[k][l];
							}
						newArr[i][j] = (sum/9);
					}
					for (int j = column - 2; j < column; j++){
					
						sum = 0;
						
						for (int k = i; k > i - 3; k--)
							for (int l = j; l > j - 3; l--){
								
								sum += myArr[k][l];
							}
						newArr[i][j] = (sum/9);
					}
				}
		}else{

			for (int i = 0; i < row; i++)
				for (int j = 0; j < column; j++){
					sum  = 0;
					
					for (int k = i; k < row; k++)
						for (int l = j; l < column; l++){
							sum += myArr[k][l];
						}
					newArr[i][j] = (sum/9);
				}
		}
		
		return newArr;
	}
	
	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int n;
		
		System.out.print("Matrisin satir sutun boyutunu giriniz: ");
		
		n = in.nextInt();

		int[][] myArray = new int[n][n];
		
		Random r = new Random();
		
		for (int i = 0; i < n; i++)
			for (int j = 0; j < n; j++){
		
			myArray[i][j] = r.nextInt(99);	
	
		}

		System.out.println();

		for (int i = 0; i < n; i++){
			for (int j = 0; j < n; j++){
			
			System.out.print(" " + myArray[i][j] + " ");
			
			}
			System.out.println();
		}
				
		int[][] myNewArray = new int[n - 2][n - 2];
		
		myNewArray = arrayExtracter(myArray, n, n);

		System.out.println();

		for (int i = 0; i < n - 2; i++){
			for (int j = 0; j < n - 2; j++){
			
			System.out.print(" " + myNewArray[i][j] + " ");
			
			}
			System.out.println();
		}
		
		int[][] myFinalArray = new int[n-2][n-2];
		
		myFinalArray = arraySummer(myNewArray, n - 2,n - 2);

		System.out.println();

		for (int i = 0; i < n - 2; i++){
			for (int j = 0; j < n - 2; j++){
			
			System.out.print(" " + myFinalArray[i][j] + " ");
			
			}
			System.out.println();
		}
		
		in.close();
	}
	
}
-------------------------------------------------------------------------------------------------------------------------------------
************************************************algoritmaCprogramlama*************************************************************
import java.util.Scanner;

class Account {
	
	private int password;
	private String userName;
	private int money;
	
	//public int bankMoney;
	
	Account(int pass, String user, int accountMoney){
		password = pass;
		userName = user;
		money = accountMoney;
	}
	
	Account(){
		password = 0;
		userName = "bos";
		money = 0;
	}
	
	int myAccResult(Account ext){
		
		if((password == ext.password) && (userName == ext.userName))
			return 1;
		else
			return 0;
		
	}
	
	int showMoney(){
		return money;
	}
	
	void showName(){
		System.out.println(userName + " kullanicisinin hesabina giris yaptiniz ");		
	}
	
	int nameControl(String str){
		if (str ==  userName)
			return 1;
		else 
			return 0;
	}
	
	int moneyAdd(Account a, int newMoney, int mainMoney){
		a.money += newMoney;
		mainMoney += newMoney;

		return a.money;
	}
	
	int moneySubtract(Account a, int minusMoney, int mainMoney){

			if (a.money >= minusMoney){
				mainMoney -= minusMoney;
				a.money -= minusMoney;
				return a.money;

			}
		
		return 0;
		
	}
	
}

public class Driver {
	
	public static void main(String arg[]){
					
			Scanner in = new Scanner(System.in);
		
			int tempPass;	
			String tempUser;
		
			int newAddMoney;
			int newSubtractMoney;
	
			int tempSubtract;	
			int tempInput = -1;
			
			int accIndex = -1;

			int bank = 0;

			//Sistemde tanimlanmis kullanicilar

			Account[] accArr = new Account[3];
			
			accArr[0] = new Account(123,"onur",0);
			
			accArr[1] = new Account(1234,"abuzittin",0);

			accArr[2] = new Account(1237,"hagi",0);

			System.out.println("Sistemden cikmak icin 0 a basınız");
			
			System.out.print("Klavyeden kullanici adini giriniz: ");
			
			tempUser= in.next();
			
			System.out.print("Sifrenizi giriniz: ");

			tempPass = in.nextInt();

			int res;
			
			Account tp = new Account(tempPass, tempUser, bank);
			
			while (tempUser.charAt(0) != '\n'){	
														
				for (int index = 0; index < 3; index++){
					res = accArr[index].myAccResult(tp);

					if( ( res ) == 1){
						accIndex = index;
						accArr[accIndex].showName();
						break;
					}
					else {
						System.out.println("Lutfen gecerli bir kullanici giriniz!");
						
					}
				}
				
				if (accIndex != -1){
					
					while (tempInput != 0){
						System.out.println("Asagidaki islemlerden hangisini yapmak "
								+ "istiyorsunuz");
						System.out.println("Kendi hesabinizdaki miktari gormek icin 1 giriniz");
						System.out.println("Kendi hesabiniza para eklemek icin 2 giriniz");
						System.out.println("Kendi hesabinizdan para cekmek icin 3 giriniz");
						System.out.println("Baska hesaba para gondermek icin 4 giriniz");
						System.out.println("Cikmak icin 0 giriniz");
						
						tempInput = in.nextInt();
						
						switch(tempInput){
							case 1:
								System.out.println("Hesabinizdaki para " + accArr[accIndex].showMoney());
								break;
							case 2:
								System.out.print("Hesabiniza ne kadar "
										+ "para eklemek istediginizi giriniz: ");
								newAddMoney = in.nextInt();
								accArr[accIndex].moneyAdd(accArr[accIndex], newAddMoney,bank);
					
								break;
							case 3:
								System.out.print("Hesabinizdan ne kadar "
										+ "para cekmek istediginizi giriniz: ");
								newSubtractMoney = in.nextInt();
								if ( ( tempSubtract = accArr[accIndex].moneySubtract(accArr[accIndex], newSubtractMoney,bank) ) == 0){
									System.out.println("Hesapta olandan fazla para cekilemez");
									break;
								}
								break;
							case 4:
								System.out.println("Para gondermek istediginiz "
										+ "hesabin kullanici adini giriniz");
								tempUser = in.next();
								for (int i = 0; i < accArr.length; i++){
									if(accArr[i].nameControl(tempUser) == 1){
										System.out.print("Gondereceginiz miktari giriniz: ");
										newAddMoney = in.nextInt();
										accArr[i].moneyAdd(accArr[i], newAddMoney,bank);
							
										break;
									}
									else {
										System.out.println("Lutfen gecerli bir kullanici giriniz!");
										break;
									}
								}
								break;
							default:
								System.out.println("Lutfen gecerli bir miktar giriniz!");
								break;
						}
						
					}

				}
				
				System.out.print("Kullanici adini giriniz: ");
				
				tempUser= in.nextLine();
				
				System.out.print("Sifrenizi giriniz: ");

				tempPass = in.nextInt();


			}
			
			in.close();
		
	}
	
}
-------------------------------------------------------------------------------------------------------------------------------------
***************************************************AlgoritmaveProgramlamaI_Odev1****************************************************
Soru-1)
import java.util.Scanner;

public class UceBolunen {

	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
			
		int[] arr = new int[10];
		
		for (int i = 0; i< 10; i++){
			System.out.print("Sayi giriniz: ");
			arr[i] = in.nextInt();
		}
		
		System.out.println("Klavyeden girilen sayilardan 3' e bolunebilenler: ");
		for (int i = 0; i < 10; i++){
			if (arr[i] % 3 == 0)
				System.out.print(" " + arr[i] + " ");
		}
		
		in.close();
	}
}

Soru-2)

import java.util.Scanner;

public class Sehir {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);	
			
			System.out.print("Klavyeden bir karakter giriniz: ");
			
			char myChar = in.nextLine().charAt(0);
		
			switch(myChar){
			
				case 'a': System.out.println("ANKARA");
					break;
				case 'b': System.out.println("BURSA");
					break;
				case 'r': System.out.println("BURSA");
					break;
				case 't': System.out.println("BURSA");
					break;
				case 'd': System.out.println("DENIZLI");
					break;
				case 'e': System.out.println("EDIRNE");
					break;
				case 'f': System.out.println("EDIRNE");
					break;
				case 'k': System.out.println("KIRIKKALE");
					break;
				default:
					System.out.println("Girdiginiz harfin karsilik sehri yoktur.");
			
			}
			
			in.close();
		
	}
	
}

Soru-3)

import java.util.Scanner;

public class EnBuyuk {

	private static int max(int arr[], int size){
		
		int max = arr[0];
		
		for (int i = 1; i < size; i++){
			if (arr[i] > max)
				max = arr[i];
		}
		return max;
	}
	public static void main(String arg[]){
		
		Scanner in = new Scanner(System.in);
		
		int maxValue;
		
		int[] arr = new int[10];
		
		for (int i = 0; i< 10; i++){
			System.out.print("Sayi giriniz: ");
			arr[i] = in.nextInt();
		}
		
		maxValue = max(arr, arr.length);
		
		System.out.println("Klavyeden girilen sayilardan en buyugu: " + maxValue);
		
		in.close();
	}
}

Soru-4)

import java.util.Scanner;

public class Driver {
	
	public static void main(String arg[]){
			
			Scanner in = new Scanner(System.in);
			
			System.out.print("Klavyeden sayiyi giriniz: ");
			
			int sayi = in.nextInt();
			
			int bolucu = 10;
			
			int bolum;
			
			System.out.println("Klavyeden girilen sayinin tersi: ");

			System.out.print(sayi % bolucu);

			bolum = sayi / bolucu;	
			
			do{
				System.out.print(bolum % bolucu);
			}
			while ((bolum /= bolucu) != 0);
			
			System.out.println();

			in.close();
		
	}
	
}
-------------------------------------------------------------------------------------------------------------------------------------

***********************************************************javaodev-1****************************************************************

Soru-1) “temel tip tanımlamalarının” bilgisayarın RAM hafızasında nasıl yer aldığını araştırınız. Örnekle açıklayınız.

Java' da Primitive data tipleri tanımlandıklatı zaman RAM' e yerleştirilirler ve RAM' de lokal stack kullanılır.
new operatörü kullanılarak bir sınıfın data  member' i oluşturuluyorsa heap alanı kullanılır.

Soru-2)
 
import java.util.Scanner;

class Fact {

	int factValue;

	Fact(int f){

    	factValue = f;
	}

	long myFactResult(){

		long factResult = 1;

    	for (int i = 1; i <= factValue; i++)
        	factResult *= i;

    	return factResult;
	}
}

public class Driver { public static void main(String arg[]){

	    long factResult;
	
	    int myint;
	
	    Scanner keyboard = new Scanner(System.in);
	
	    System.out.print("Faktoriyeli alinacak degeri giriniz: ");

    	myint = keyboard.nextInt();

        Fact myfact = new Fact(myint);

        factResult = myfact.myFactResult();

        System.out.println("Klavyeden girilen deger: " + myint);

        System.out.println("Klavyeden girilen degerin faktöriyeli: " + factResult);

    	System.out.println("Bye");
    	
    	keyboard.close();
    	
	}
}   

Soru-3)

import java.util.Scanner;

class OzelToplayici {

	private int baslangic;
	private int son;
	private int aralik;

	OzelToplayici(int b, int s, int a){

    	baslangic = b;
    	son = s;
    	aralik = a;
	}

	int OzelToplayiciSonuc(){

		int toplam = 0;

    	for (int i = baslangic; i <= son;i+=aralik){
        	toplam += i;
    		
		}
    	return toplam;
	}
	
}

public class Driver { public static void main(String arg[]){

	    int basla, bit, arttir, sonuc;
	
	    Scanner keyboard = new Scanner(System.in);
	
	    System.out.print("Baslangic degerini giriniz: ");

    	basla = keyboard.nextInt();

    	System.out.print("Bitis degerini giriniz: ");
    	
    	bit = keyboard.nextInt();
        
    	System.out.print("Arttirma degerini giriniz: ");
    	
    	arttir = keyboard.nextInt();
    	
    	OzelToplayici myValue = new OzelToplayici(basla, bit, arttir);

        sonuc = myValue.OzelToplayiciSonuc();

        System.out.println("Klavyeden girilen araliktaki istenilen arttis ile artan sayilarin toplami: " + sonuc);

    	System.out.println("Bye");
    	
    	keyboard.close();
    	
	}
}

Soru-4)

import java.util.Scanner;

class Maksimum {

	int maksimumBulucu(int[] myarr, int size){

		int max = 0;
		max = myarr[0];
    	for (int i = 1; i < size; i++){
        	
    		if (myarr[i] > max)
    			max = myarr[i];
		}
    	return max;
	}
	
}

public class Driver { public static void main(String arg[]){

	    int maksimum, size;
	
	    Scanner keyboard = new Scanner(System.in);
	
	    System.out.print("Kaç eleman gireceginizi giriniz: ");

	   size = keyboard.nextInt();

    	   int[] newArr = new int[size];
    	
    	   System.out.print("Ilk sayiyi giriniz: ");
    	
    	   for (int i = 0; i < size; i++){
    		
    		newArr[i] = keyboard.nextInt();
    		
    		if (i != size -1)
    			System.out.print("Yeni degeri giriniz: ");
    	   }
    	
            Maksimum myValue = new Maksimum();

            maksimum = myValue.maksimumBulucu(newArr, size);

            System.out.println("Klavyeden girilen sayilardan en buyugu: " + maksimum);

    	    System.out.println("Bye");
    	
    	    keyboard.close();
    	
	}
}
