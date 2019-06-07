# List of bit twiddles

A growing list of bit twiddles as I come across them.

## Flip bits

If we XOR with `1` we flip a bit.
Therefore to flip all the bits in a 32-bit integer:
{% highlight python%}
def flippingBits(n):
    return n ^ int('11111111111111111111111111111111', 2)
{% endhighlight %}
where the number of `1`s in the string is `32`.