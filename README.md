# jwt-basic demo

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
