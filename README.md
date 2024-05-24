import java.util.Scanner;

public class NumberToWords {
    private static final String[] units = {"", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine", "ten",
            "eleven", "twelve", "thirteen", "fourteen", "fifteen", "sixteen", "seventeen", "eighteen", "nineteen"};

    private static final String[] tens = {"", "", "twenty", "thirty", "forty", "fifty", "sixty", "seventy", "eighty", "ninety"};

    private static String convert(int n) {
        if (n < 20) {
            return units[n];
        }
        if (n < 100) {
            return tens[n / 10] + ((n % 10 != 0) ? " " + units[n % 10] : "");
        }
        if (n < 1000) {
            return units[n / 100] + " hundred" + ((n % 100 != 0) ? " and " + convert(n % 100) : "");
        }
        if (n < 1000000) {
            return convert(n / 1000) + " thousand" + ((n % 1000 != 0) ? " " + convert(n % 1000) : "");
        }
        return "Number too large to convert";
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = scanner.nextInt();
        System.out.println(convert(number));
    }
}


STRING :

  String str1 = "Hello";
	        String str2 = str1; // str2 points to the same "Hello" string as str1
	        
	        System.out.println(str1.hashCode() +" str1: " + str1); // Output: Hello
	        System.out.println(str2.hashCode() +" str2: " + str2); // Output: Hello
	        
	        // Modify str1
	        str1 = str1 + " World";
	        
	        System.out.println("After modification:");
	        System.out.println(str1.hashCode() +" str1: " + str1); // Output: Hello World
	        System.out.println(str2.hashCode() +" str2: "  + str2); // Output: Hello
	        
	        // str1 now points to a new "Hello World" string, but str2 still points to the original "Hello" string
	    
OUTPUT :	
69609650 str1: Hello
69609650 str2: Hello
After modification:
-862545276 str1: Hello World
69609650 str2: Hello







