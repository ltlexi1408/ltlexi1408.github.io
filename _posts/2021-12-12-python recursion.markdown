---
layout: post
title:  "Python recursion"
date:   2021-12-12 21:24:41 +1100
categories: [code ,python]
---
Basic python recursion script

{% highlight python %}
def sub(num):
    if num >= 1:
        num -= 1
        print(num)
        sub(num)
        print(num)

num = int(input("Number:"))
sub(num + 1)
print("Done")
{% endhighlight %}