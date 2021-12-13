---
layout: post
title:  "C# recursion"
date:   2021-12-12 21:24:41 +1100
categories: [code ,C#]
---
Basic java recursion script

{% highlight python %}
import java.util.Scanner;

class sub_recursion {
    public static void main(String[]args) {
        int num;
        Scanner input = new Scanner(System.in);

        System.out.print("Number:");
        num = input.nextInt();

        recursion(num + 1);

        System.out.println("Done");

        input.close();
    }

    public static void recursion(int num) {
        if(num >= 1) {
            num -= 1;
            System.out.println(num);
            recursion(num);
            System.out.println(num);
        }
    }
}
{% endhighlight %}