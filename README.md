# 6-10
6.Write a Program to Demonstrate Use of Virtual and override key words in C# with
a simple program.

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab6
{
    class Base
    {
        public virtual void show()
        {
            Console.WriteLine("showing the base class");
        }
    }
    class Derived : Base
    {
        public override void show()
        {
            Console.WriteLine("Showing the derived class");
        }
    }
    class demo
    {
        static void Main(string[] args)
        {
            Base b = new Base();
            b.show();
            Derived d = new Derived();
            d.show();
            Base b1 = new Derived();
            b1.show();
            Console.ReadLine();
        }
    }
}


7.Write a Program in C# to create and implement a Delegate for any two
arithmetic operations


using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
public delegate int operation(int p, int q);
namespace lab7
{
    class delegates
    {
        public static int AddNum(int p, int q)
        {
            return (p + q);
        }
        public int MultiNum(int p, int q)
        {
            return (p * q);
        }
        static void Main(string[] args)
        {
            operation op1 = new operation(AddNum);
            Console.WriteLine("Addition of two numbers :{0}", op1(10, 20));
            delegates d = new delegates();
            operation op2 = new operation(d.MultiNum);
            Console.WriteLine("multiplication of two numbers :{0}", op2(5, 2));
            Console.ReadLine();
        }
    }
}

8.Write a Program in C# to demonstrate abstract class and abstract methods in C#.
Solution

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab8
{
    abstract class shape
    {
        protected float l, b;
        public abstract float Area();
        public abstract float Circumference();
    }
    class Rectangle : shape
    {
        public void getlb()
        {
            Console.WriteLine("Enter the length");
            l = float.Parse(Console.ReadLine());
            Console.WriteLine("Enter the Breadth");
            b = float.Parse(Console.ReadLine());
        }
        public override float Area()
        {
            return l * b;
        }
        public override float Circumference()
        {
            return 2 * (l + b);
        }
    }
    class demo
    {
        static void Main(string[] args)
        {
            Rectangle r = new Rectangle();
            r.getlb();
            Console.WriteLine("The area is" + r.Area());
            Console.WriteLine("The circumference is" + r.Circumference());
            Console.ReadLine();
        }
    }
}

9.Write a program to Set & Get the Name & Age of a person using Properties of C#
to illustrate the use of different properties in C#.

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab9
{
    class Person
    {
        string name;
        int age;
        public string pername
        {
            get { return name; }
            set { name = value; }
        }
        public int perage
        {
            get { return age; }
            set { age = value; }
        }
    }
    class demo
    {
        static void Main(string[] args)
        {
            Person p1 = new Person();
            Console.WriteLine("Enter the name of a person");
            p1.pername = Console.ReadLine();
            Console.WriteLine("Enter the age of a person");
            p1.perage = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Name of a person is:" + p1.pername);
            Console.WriteLine("Age of a person is:" + p1.perage);
            Console.ReadLine();
        }
    }
}

10.Write a Program in C# Demonstrate arrays of interface types (for runtime polymorphism).

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab10
{
    interface ishape
    {
        void draw();
    }
    class circle : ishape
    {
        public void draw()
        {
            Console.WriteLine("Drawing circle");
        }
    }
    class square : ishape
    {
        public void draw()
        {
            Console.WriteLine("Drawing square");
        }
    }
    class triangle : ishape
    {
        public void draw()
        {
            Console.WriteLine("Drawing triangle");
        }
    }
    class hexagon : ishape
    {
        public void draw()
        {
            Console.WriteLine("Drawing hexagon");
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            ishape[] shape = { new circle(), new square(), new triangle(),new hexagon() };
            foreach (ishape s in shape)
                s.draw();
            Console.ReadLine();
        }
    }
}
