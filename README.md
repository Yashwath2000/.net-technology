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
![image](https://user-images.githubusercontent.com/98145017/150485232-527fed68-5ec5-47a4-b1b8-c36deb81e619.png)
<br>
<br>
<br>
4.C# PROGRAM TO CREATE GRAY CODE<br>
using System;<br>

namespace prog4<br>
{<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n^(n>>1);<br>
        }<br>
        static void Main(string[] args)<br>
        {<br>
            int InputNum, GrayNum;<br>
            Console.WriteLine("\n enter the decimal number:");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\nBinary equivalent of {0}:{1}", InputNum, Convert.ToString(InputNum, 2));<br>
            GrayNum = getGray(InputNum);<br>
            Console.WriteLine("\ngray code equivalent of {0}:{1}", InputNum, Convert.ToString(GrayNum, 2));<br>
        }<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145017/152292190-b8673f16-91be-42c7-8824-1602356c6892.png)

<br>
<br>
5.C3 PROGRAM TO CALCULATE VOLUME OF 2 BOXES AND FIND THE RESULTANT VOLUME AFTER ADDITION OF 2 BOXES BY IMPLEMENTING OPERATOR OVERLOADING<br>
using System;<br>
namespace prog5<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>

        public float Volume
        {
            get
            {
                return width * height * length;
            }
        }
                public Box(float width, float height, float length)
                {
                    this.width=width;
                    this.height=height;
                    this.length=length;
                }
                public static float operator +(Box box1, Box box2)
                {
                    return box1.Volume + box2.Volume;
                }
                public override String ToString()
                {
                    return "box with width " + width + ",height " + height + "and length " + length;
                }
    }
        class OperatorOverloading
        {
            public static void Main()
            {
                Box box1 = new Box(10, 20, 30);
                Box box2 = new Box(25, 32, 15);

                Console.WriteLine("volume of {0} is :{1}", box1, box1.Volume);
                Console.WriteLine("volume of {0} is :{1}", box2, box2.Volume);
                Console.WriteLine("volume after adding boxes:{0}", box1 + box2);
            }
        }
}
  
OUTPUT:<BR>
![image](https://user-images.githubusercontent.com/98145017/152293199-fc67bd7d-a06a-4191-8247-0aab2aa5e188.png)<br><br>
6.C#PROGRAM TO IMPLEMENT PRINCIPLE OF DELEGATES CONVERTING INPUT STRING TO UPPERCASEFIRST,LAST AND ENTIRE STRING.
    using System;<br>

namespace program6<br>
{<br>
    class Delegates<br>
    {<br>
        delegate string UppercaseDelegate(string input);<br>
        static string UppercaseFirst(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[0]=char.ToUpper(buffer[0]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseLast(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseAll(string input)<br>
        {<br>
            return input.ToUpper();<br>
        }<br>
        static void WriteOutput(string input, UppercaseDelegate del)<br>
        {<br>
            Console.WriteLine("Input.String:{0}", input);<br>
            Console.WriteLine("output string:{0}", del(input));<br>
        }<br>
        static void Main()<br>
        {<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseFirst));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseLast));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseAll));<br>
            Console.ReadLine();<br>
        }<br>
    }<br>
}<br>
 OUTPUT:<br>
    ![image](https://user-images.githubusercontent.com/98145017/152299602-a4948d0b-1039-48d6-aee9-a71d3a996cff.png)<br>
    7.register number<br>
    using System;

namespace register
{
    class RegisterNum
    {
        int regno;
        static int startNum;
        static RegisterNum()
        {
            startNum = 20210000;
        }
        RegisterNum()
        {
            regno = ++startNum;
        }
        public static void Main(string[] args)
        {
            for (int i = 0; i < 100; i++)
            {
                RegisterNum student = new RegisterNum();
                Console.WriteLine("student {0}:{1}", i + 1, student.regno);
            }
        }
    }
}



