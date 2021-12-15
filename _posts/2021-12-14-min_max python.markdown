---
layout: post
title:  "pyhton min max"
date:   2021-12-12 21:24:41 +1100
categories: [code ,python]
---
Basic pythom find min and max in array script

{% highlight java %}
import random

list = []
min = 99
max = -999

for x in range(10):
    list.append(random.randint(0, 100))

for x in list:
    if x < min:
        min = x
    elif x > max:
        max = x

print(list)

print("Min: {}" .format(min))
print("Max: {}" .format(max))
{% endhighlight %}