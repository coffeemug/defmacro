---
layout: post
title: Radical quantification
---

> When you cannot express it in numbers, your knowledge is of a meagre
> and unsatisfactory kind.  
> &nbsp;&nbsp;\- _Kelvin's Dictum_

> Yes, and when you can express it in numbers your knowledge is of a
> meagre and unsatisfactory kind.  
> &nbsp;&nbsp;\- _Frank Knight_

_Radical quantification_ is a technique for dramatically simplifying
complex problems with no obvious angle of attack. It works by picking
just _one_ quantity that illuminates the essence of the problem (or at
least gives you a good running start). In a sense it's a form of
dimensionality reduction-- like doing principal component analysis and
then looking only at the first component.

# Illustrative example

To this day my first encounter with this technique is the most
brilliant use of it I've ever seen-- it's William Nordhaus's 1996
paper [Do real-output and real-wage measures capture reality? The
history of lighting suggests not][] (Nordhaus went on to win the Nobel
Prize in economics in 2018 for his work on climate change). In the
paper he attempts to answer this question: how much richer is an
average American in 1992 than an average American in 1800? He explains
why it's an incredibly difficult problem:

[Do real-output and real-wage measures capture reality? The history of lighting suggests not]: /papers/nordhaus96.pdf

> The estimates of real income are only as good as the price indexes
> are accurate. During periods of major technological change, the
> construction of accurate price indexes that capture the impact of
> new technologies on living standards is beyond the practical
> capability of official statistical agencies.

His solution? Reduce the problem to one dimension: how many hours of
work did it take to produce one lux of light? Light is an especially
clever metric because the technology has been with us for half a
million years, has always been in demand, and has continually tracked
technological advancement. Nordhaus then goes on to do incredible
detective work to determine the cost of light over time; the whole
paper is worth reading, but here is the conclusion:

> In terms of living standards, the conventional growth in real wages
> has been by a factor of 13 over the 1800-1992 period. For the
> low-bias case, real wages have grown by a factor of 40, while in the
> high-bias case real wages have grown by a factor of 190.

# More examples

A more recent example of _radical quantification_: [How Superhuman
Built an Engine to Find Product/Market Fit][]. In this post Rahul
Vohra, Superhuman's CEO, explains his methodology for measuring
product/market fit, and running his whole company to maximize this
metric. This use of _radical quantification_ is incredible because
conventional wisdom is that product/market fit is a qualitative
endeavor. It also reminds me of [How to Measure Anything: Finding the
Value of Intangibles in Business][].

[How Superhuman Built an Engine to Find Product/Market Fit]: https://firstround.com/review/how-superhuman-built-an-engine-to-find-product-market-fit/
[How to Measure Anything: Finding the Value of Intangibles in Business]: https://www.amazon.com/gp/product/0470539399/

<p style="text-align: center;">&#1805;</p>

Another example use of _radical quantification_ to answer a
qualitative question: "how important will self-driving cars be as a
technology?" There is of course no way to know, but in [Artificial
intelligence and the modern productivity paradox: a clash of
expectations and statistics][] Brynjolfsson et al get a handle on it
by comparing the reduction in automotive jobs to the total number of
jobs in America:

> According to the US Bureau of Labor Statistics, in 2016 there were
> 3.5 million people working in private industry as “motor vehicle
> operators” of one sort or another (this includes truck drivers, taxi
> drivers, bus drivers, and other similar occupations). Suppose
> autonomous vehicles were to reduce, over some period, the number of
> drivers necessary to do the current workload to 1.5 million. We do
> not think this is a far-fetched scenario given the potential of the
> technology. Total nonfarm private employment in mid-2016 was 122
> million. Therefore, autonomous vehicles would reduce the number of
> workers necessary to achieve the same output to 120 million. This
> would result in aggregate labor productivity (calculated using the
> standard BLS nonfarm private series) increasing by 1.7 percent (=
> 122/120). Supposing this transition occurred over 10 years, this
> single technology would provide a direct boost of 0.17 percent to
> annual productivity growth over that decade.

[Artificial intelligence and the modern productivity paradox: a clash of expectations and statistics]: /papers/brynjolfsson2017.pdf

# Discretizing a continuous quantity

One interesting variation of this approach is to take a continuous
quantity and discretize it. Paul Graham does this in [Life is Short][]
to get a visceral sense of how short life really is:

> Having kids showed me how to convert a continuous quantity, time,
> into discrete quantities. You only get 52 weekends with your 2 year
> old. If Christmas-as-magic lasts from say ages 3 to 10, you only get
> to watch your child experience it 8 times. And while it's impossible
> to say what is a lot or a little of a continuous quantity like time,
> 8 is not a lot of something. If you had a handful of 8 peanuts, or a
> shelf of 8 books to choose from, the quantity would definitely seem
> limited, no matter what your lifespan was.

[Life is Short]: http://www.paulgraham.com/vb.html

Tim Urban does something very similar in [Your Life in Weeks][]. He
creates a life calendar (which you can [buy][]) where each row has 52
columns (weeks), and there are a total of 90 rows (about the average
life expectancy). Looking at the calendar gives you a visceral sense
of how long your life really is.

[Your Life in Weeks]: https://waitbutwhy.com/2014/05/life-weeks.html
[buy]: https://store.waitbutwhy.com/collections/life-calendars

<p style="text-align: center;">&#1805;</p>

A different example of discretizing a continuous quantity is the idea
of an [inferential step][] by Eliezer Yudkowsky. Consider the question
of "how much _more_ knowledge does Alice have over Bob?" This is a
vague and difficult question; to answer it you have to figure out what
exactly knowledge is and how to quantity it. But an inferential step
is a specific concept or an abstraction that Alice can explain to Bob.
And it's much easier to count the number of inferential steps than to
measure knowledge.

[inferential step]: https://www.lesswrong.com/posts/HLqWn5LASfhhArZ7w/expecting-short-inferential-distances

---

_This post is part of the [Creative Library][]-- a series of clever
techniques that simplify solving complex problems._

[Creative Library]: /2019/11/26/creative-library.html
