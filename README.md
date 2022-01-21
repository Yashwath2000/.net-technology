# C# programs

1.C# programs to print a binary triangle.
using System;

namespace exercises<br>
{<br>
    class binarytriangle<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int number, digit = 1;<br>
            Console.Write("\n enter the number of lines;");<br>
            number = Convert.ToInt32(Console.ReadLine());

            for (int i = 1; i <= number; i++)
            {
                for (int space = number - i; space > 0; space--)
                {
                    Console.Write(" ");
                }
                for (int j = 0; j < i; j++)
                {
                    Console.Write(digit + " ");
                    digit = (digit == 1) ? 0 : 1;
                }
                Console.Write("\n");
            }
        }
    }
}

Output
<br>
<br>
![image](https://user-images.githubusercontent.com/98145017/150476776-8e0ac215-e69c-46c4-a9f4-00c95d44e5f1.png)
<br>
<br>
2.C# program to check weather the entered number is an amicable number or not.
using System;

namespace amicable_num
{
    class amicablenumber
    {
        static void Main(string[] args)
        {
            int num1, num2, sum1 = 0, sum2 = 0;
            Console.WriteLine("\n-----------AMICABLE NUMBERS------");
            Console.WriteLine("\n enter the first number");
            num1 = Convert.ToInt32(Console.ReadLine());
            Console.Write("\nenter the second number");
            num2 = Convert.ToInt32(Console.ReadLine());

            for (int i = 1; i < num1; i++)
            {
                if (num1 % i == 0)
                {
                    sum1 += i;
                }
            }
            for (int i = 1; i < num2; i++)
            {
                if (num2 % i == 0)
                {
                    sum2 += i;
                }
            }
            if (sum1 == num2 && sum2 == num1)
            {
                Console.WriteLine("\n the numbers {0} and {1} are amicable", num1, num2);
            }
            else
            {
                Console.WriteLine("\n the numbers {0} and {1} are not amicable", num1, num2);
            }
        }
    }
}<br>
output<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/98145017/150484299-19828100-bba0-4bc2-87dd-8debfdd6f2d9.png)
