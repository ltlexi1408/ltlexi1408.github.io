---
layout: post
title:  "java recursion"
date:   2021-12-12 21:24:41 +1100
categories: [code ,java]
---
Basic java find min and max in array script

{% highlight java %}
import java.util.Random;

public class min_max {
    public static void main(String[]args){
        int[] list = new int[10];
        int min = 999;
        int max = -999;
        Random rand = new Random();

        for(int i = 0; i < 10; i++) {
            list[i] = rand.nextInt(100);
        }

        for(int i = 0; i < 10; i++) {
            if(list[i] < min) { min = list[i]; }
            else if(list[i] > max) { max = list[i]; }
        }
        
        for(int i = 0; i < 10; i++) {
            System.out.print(list[i] + ", ");
        }

        System.out.println();
        System.out.println("Min: " + min);
        System.out.println("Max: " + max);
    }
    
}

{% endhighlight %}