# Unfair candy distribution

(The 'candies' questions in the Hackerrank interview preparation section.)

Consider the following exercise:-
* given an array of scores `a`
* find a array of rewards `r`
* such that if `a[i]>a[i+1]` then `r[i]>r[i+1]` and if `a[i]<a[i+1]` then `r[i]<r[i+1]`

This was listed under dynamic programming exercises but my solution uses a slightly different approach.
It is true that one needs to keep track of elements already parsed.

First I tried a natural `O(N^2)` solution that went back and corrected itself every time the current score was lower than the previous one.
{% highlight python %}
def candies(n, a): #O(N^2)
    if not a:
        return 0
    elif len(a) == 1:
        return 1
    l = [1]
    while len(l) < len(a):
        n = len(l)
        if a[n] > a[n-1]:
            l.append(l[-1]+1)
        elif a[n] == a[n-1]:
            l.append(1)
        elif a[n] < a[n-1]:
            l.append(1)
            for j in range(len(l)-1, 0, -1):
                if a[j-1] > a[j] and l[j-1] == l[j]:
                    l[j-1] += 1
                else:
                    break
    return sum(l)
{% endhighlight %}
This passed all of the tests except for one which failed with a `timeout` type error.
However going back to correct the previous entries is not necessary.
Instead one can keep track of where one started going down and then fill in everything at once when one knows when to stop going down.
A rough implementation of this idea:
{% highlight python %}
def candies(n, a): # O(N)
    if not a:
        return 0
    elif len(a) == 1:
        return 1
    l = [1]
    while len(l) < len(a):
        n = len(l)
        if a[n-1] < a[n]:
            l.append(l[-1]+1)
        elif a[n-1] == a[n]:
            l.append(1)
        elif a[n-1] > a[n]:
            down_steps = 0
            i = n
            while i < len(a) and a[i-1] > a[i]:
                down_steps += 1
                i += 1
            for j in range(down_steps):
                l.append(down_steps-j)
            if l[n-1] <= down_steps: 
                l[n-1] = down_steps + 1
    return sum(l)
{% endhighlight %}
which did pass all the tests.