---
layout: post
title:  "C# recursion"
date:   2021-12-12 21:24:41 +1100
categories: [code ,C#]
---
Basic C# recursion script

{% highlight csharp %}
using System;
     
namespace Recursion {
    class sub_recursion {
        static void Main(string[]args) {
            int num;

            Console.WriteLine("Number:");
            num = Convert.ToInt32(Console.ReadLine());

            recursion(num + 1);

            Console.WriteLine("Done");
        }

        static void recursion(int num) {
            if(num >= 1){
                num -= 1;
                Console.WriteLine(num);
                recursion(num);
                Console.WriteLine(num);
            }
        }
    }
}
{% endhighlight %}