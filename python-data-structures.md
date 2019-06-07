# Python data structures

Often the data structures in the `collections` module are better or more readable.

## Stacks

The built-in list type is pretty good.
But `collections.deque` is apparently better as it is implemented as a doubly linked list.
For instance:
{% highlight python%}
from collections import deque
s = deque()
s.append('a')
a = s.pop()
{% endhighlight %}
just like the usual list type.

## Queues

Again `collections.deque` is the one to use.
For instance:
{% highlight python%}
from collections import deque
s = deque()
s.appendleft('a')
a = s.popleft()
{% endhighlight %}
and `queue.Queue()` is probably not appropriate as it is intended to allow different threads to communicate.

## Hash tables

Here it is unclear whether to use the standard `dict` type or `collections.defaultdict`.
The distinction is that `dict` will throw an error on a missing key but `collections.defaultdict` will provide a default value.
For instance:
{% highlight python%}
from collections import defaultdict
d = defaultdict(int)
d['one'] = 1
four = d['four'] # four contains 0
{% endhighlight %}
where `0` is the default value for the `int` type and `[]` is the default value for the `list` type.
Further one can specify a function to customise the default value returned.