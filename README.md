### Task №1(7kuy)
John wants to decorate the walls of a room with wallpaper. He wants a fool-proof method for getting it right.

John knows that the rectangular room has a length of meters, a width of meters, a height of meters. The standard width of the rolls he wants to buy is centimeters. The length of a roll is meters. He bears in mind however, that it’s best to have an extra length of wallpaper handy in case of mistakes or miscalculations so he wants to buy a length greater than the one he needs.
~~~ Java
l w h 52 10 15%
~~~

Last time he did these calculations he got a headache, so could you help John?

Task

Your function should return as a plain English word in lower case the number of rolls he must buy.
~~~ Java
wallpaper(l, w, h)
~~~

Example:
~~~ Java
wallpaper(4.0, 3.5, 3.0) should return "ten"

wallpaper(0.0, 3.5, 3.0) should return "zero"
~~~

Notes:

all rolls (even with incomplete width) are put edge to edge

0 <= l, w, h (floating numbers); it can happens that is zero w * h * l

the integer (number of rolls) will always be less or equal to 20r

FORTH: the number of rolls will be a positive or null integer (not a plain English word; this number can be greater than 20)

In Coffeescript, Javascript, Python, Ruby and Scala the English numbers are preloaded and can be accessed as:

~~~ Java
numbers = ["zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine", "ten", "eleven", "twelve","thirteen", "fourteen", "fifteen", "sixteen", "seventeen", "eighteen", "nineteen", "twenty"]
~~~

For other languages it is not preloaded and you can instead copy the above list if you desire.


[Task_link](https://www.codewars.com/kata/567501aec64b81e252000003)

#### Solution

~~~ Java
public class EasyWallpaper {

  public String wallpaper(double l, double w, double h) {
    var numbers = new String[]{"zero", "one", "two", "three", "four", "five",
                "six", "seven", "eight", "nine", "ten", "eleven",
                "twelve", "thirteen", "fourteen", "fifteen",
                "sixteen", "seventeen", "eighteen", "nineteen", "twenty"};
       return w * h * l == 0 ? numbers[0] : numbers[(int)(Math.ceil((l * h * 2 + w * h * 2) * 1.15 / 5.2))];
        // help John!
    }

}
  
~~~

#### Fav Solution

~~~ Java
public class EasyWallpaper {

    private static String[] nbs = {"zero","one","two","three","four","five","six","seven","eight","nine","ten","eleven","twelve","thirteen","fourteen","fifteen","sixteen","seventeen","eighteen","nineteen","twenty"};
    
    public String wallpaper(double l, double w, double h) {

        if (l*w*h==0) return nbs[0];

        double roomM2 = 2 * (l * h) + 2 * (w * h);
        double rollM2 = 10 * .52;
        int r = (int)((roomM2 / rollM2) * 1.15 + 1);

        return nbs[r];
    }
}
~~~

### Task №2(6kuy)
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Finish the solution so that it returns the sum of all the multiples of 3 or 5 below the number passed in. Additionally, if the number is negative, return 0 (for languages that do have them).

Note: If the number is a multiple of both 3 and 5, only count it once.

[Task_link](https://www.codewars.com/kata/514b92a657cdc65150000006)

#### Solution

~~~ Java
public class Solution {

    public int solution(int number) {
        int sum = 0;
        for (int i = 0; i < number; i++) {
            if (i % 3 == 0 || i % 5 == 0) {
                sum = sum + i;
            }
        }
        if (number <= 0) {
            return 0;
        }
        return sum;
    }
}
~~~

#### Fav Solution

~~~ Java
public class Solution {

  public int solution(int number) {
    int sum=0;
    
    for (int i=0; i < number; i++){
      if (i%3==0 || i%5==0){sum+=i;}
    }
    return sum;
  }
}
~~~