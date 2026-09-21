---
layout: post
title: On the Degrees of Freedom
date: 2026-09-14
description: Why degrees of freedom is 1 when testing independence assortment in testcross
tags: scicomm
categories: bio202
pretty_table: true
tikzjax: true
related_posts: false
---

#### Intution for Degrees of Freedom
In biostatistics, the concept of the [degrees of freedom (df)](https://en.wikipedia.org/wiki/Degrees_of_freedom_(statistics)) comes up often and is frequently misunderstood, or at least only partially understood. As a student, you may resort to *memorization* on a case-by-case basis when df comes up in biology classes. Well, so did I. Notably, the equation is `df = N-1`, when `N` is the number of classes of data.

To wrap your head around the idea of df, let's imagine that you're a coach for a soccer team. <i class="fa-solid fa-futbol"></i>

You have `11` players to fit `11` positions on the field. You may assign any player to any position you want, but once you've assigned `10` out of `11` players, you no longer have the choice to assign the last player as you desire. The player would have to play whichever the last position that's left open. So, the number of degrees of freedom that you have is `11 - 1 = 10`. However, *picking the right `N` can be tricky*.  

Say, you're interested in investigating the sources of daily caffeine—`coffee`, `tea`, `soda`, and `energy drinks`—for average Americans. 

<div class="text-center">
        {% include figure.liquid loading="eager" 
        path="assets/img/degrees_of_freedom/coffee-beans.jpg" 
        max-height="250px" 
        width="auto" 
        class="img-fluid rounded z-depth-1" %}
</div>
<div class="caption">
    What's your choice for caffeine? Or you may not need caffeine at all!
</div>

However, your research collaborator gave your the data, they were tabulated with brand choices for soda as well. Knowing whether the soda brand choice was a Coca-Cola or Dr. Pepper isn't more or less helpful for the question you're investigating, which only concerns the types of the drinks. So, the relevant level of *freedom* for this particular question for this particular set of data is within the constraint of caffeine sources, and not brands. So, you may use the number of degrees of freedom to be `4 - 1 = 3`. 

The key takeaway is that **the degrees of freedom depend on both the data AND the question** that's being asked. Same data but different question may have different degrees of freedom in your analysis. 

#### Lenticular Coin Flips: a Chi-Square Case-Study
On your last birthday, your parent surprised you with an amazing present, a collectible [lenticular](https://en.wikipedia.org/wiki/Lenticular_printing) coin you'd been asking for. It is special, because depending on the angle you're looking at the coin, the engraving may appear as a `dragon` or a `monkey`.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/degrees_of_freedom/dragon-head.png" 
        class="img-fluid rounded z-depth-1"
        caption="dragon heads"
        max-height="200px"
        width="auto"  %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/degrees_of_freedom/dragon-tail.png" 
        class="img-fluid rounded z-depth-1"
        caption="dragon tails"
        max-height="200px"
        width="auto"  %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/degrees_of_freedom/monkey-head.png" 
        class="img-fluid rounded z-depth-1"
        caption="monkey heads"
        max-height="200px"
        width="auto"  %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/degrees_of_freedom/monkey-tail.png" 
        class="img-fluid rounded z-depth-1"
        caption="monkey tails"
        max-height="200px"
        width="auto"  %}
    </div>
</div>

Now, your friend had asked you to referee a soccer game, you need to coin flip to decide who gets the kickoff. Naturally, you'd like to use your newly minted dragon-monkey coin, but you aren't sure if the coin was even *fair*. 

You set out to investigate if your gifted coin has the same chances of the coin landing `heads` as `tails` by tossing the coin `1000` times and conducting a Chi-square test. You write down all your observations. The coin still has `heads` and `tails` like any other coin; however, because the orientation in which the coin lands is random, when it lands a `heads`, about *50%* of the times you'd see a head of a `dragon`. The other *50%* of the times, you'd see a head of a `monkey`. The `heads` and `tails` results are independently of whether you're looking at a `dragon` or a `monkey`.


<br>
<div class="row mt-3">
  <table>
    <thead>
      <tr>
        <th align="left">coin toss results</th>
        <th align="right">count</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td valign="middle">
          <img src="/assets/img/degrees_of_freedom/dragon-head.png" width="50" style="vertical-align: middle;"> 
          dragon heads
        </td>
        <td valign="middle">119</td>
      </tr>
      <tr>
        <td valign="middle">
          <img src="/assets/img/degrees_of_freedom/dragon-tail.png" width="50" style="vertical-align: middle;"> 
          dragon tails
        </td>
        <td valign="middle">370</td>
      </tr>
      <tr>
        <td valign="middle">
          <img src="/assets/img/degrees_of_freedom/monkey-head.png" width="50" style="vertical-align: middle;"> 
          monkey heads
        </td>
        <td valign="middle">135</td>
      </tr>
      <tr>
        <td valign="middle">
          <img src="/assets/img/degrees_of_freedom/monkey-tail.png" width="50" style="vertical-align: middle;"> 
          monkey tails
        </td>
        <td valign="middle">376</td>
      </tr>
    </tbody>
    <caption style="caption-side:bottom">1000 coin toss results</caption>
  </table>
</div>
<br>

You finally have all the information you need to conduct a Chi-square test of your own. However, you remember that you're only testing to see if this coin is *fair*, which has nothing to do with whether you're observing a `dragon` or a `monkey` engraving. Therefore, whether you see a `dragon` or a `monkey` head engraving, you can lump both of them together as the times that the coin lands `heads`. Same for `tails`.

<br>
<div class="row mt-3">
  <table>
    <thead>
      <tr>
        <th>coin flip results</th>
        <th>counts</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>combined heads</td>
        <td>119 + 135 = 254</td>
      </tr>
      <tr>
        <td>combined tails</td>
        <td>370 + 376 = 746</td>
      </tr>
      <tr>
        <td>total</td>
        <td>254 + 746 = 1000</td>
      </tr>
    </tbody>
    <caption style="caption-side:bottom">1000 coin toss combined results</caption>
  </table>
</div>
<br>

It's probably quite obvious now that the coin is *NOT fair*, but you calculate the Chi-square test nonetheless.

<br>
<div class="row mt-3">
  <table>
    <thead>
      <tr>
        <th>classes</th>
        <th>observed</th>
        <th>expected</th>
        <th>$(O-E)$</th>
        <th>$(O-E)^2$</th>
        <th>$\frac{(O-E)^2}{E}$</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>heads</td>
        <td>254</td>
        <td>500</td>
        <td>254 - 500 = -246</td>
        <td>60516</td>
        <td>121.03</td>
      </tr>
      <tr>
        <td>tails</td>
        <td>746</td>
        <td>500</td>
        <td>746 - 500 = 246</td>
        <td>60516</td>
        <td>121.03</td>
      </tr>
    </tbody>
    <caption style="caption-side:bottom">Chi-square calculation</caption>
  </table>
</div>
<br>

Therefore, our Chi-square value is `242.06`! And what should the degrees of freedom be? Since there are only two
classes, `heads` or `tails`, the degrees of freedom is `2 - 1 = 1`! At `p = 0.05`, the Chi-square threshold is `3.841`.

Our calculated Chi-square value for this coin is *WAY HIGHER* than the threshold. So we can *reject* our null hypothesis that this coin is *fair*!! It looks like you're going to have to bring another coin to your friend's soccer game.

*Can you spot the connection between this example and testing for independent assortment using a test cross?*

#### Testcross Application

In a sexually-reproducing, diploid organism, let's set up a testcross for `1000` offspring (see diagram below) and to test for `independent assortment`—*meaning the chances that a meiotic gamete receives `parental` vs `recombinant` pairs of A and B allele are equal*. 

<div class="text-center">
  <script type="text/tikz">
    \begin{tikzpicture}[font=\sffamily\bfseries]

      \node (P) at (0, 1) {P};
      \node (Pa) at (2, 1) {\textcolor{red}{Ab}/\textcolor{red}{Ab}};
      \node (Pb) at (4, 1) {\textcolor{teal}{aB}/\textcolor{teal}{aB}};
      \node (X1) at (3, 1) {x};
      
      \node (F1) at (0, 0) {F1};
      \node (F1a) at (3, 0) {\textcolor{red}{Ab}/\textcolor{teal}{aB}};
      \node (F1b) at (5, 0) {ab/ab};
      \node (X2) at (4, 0) {x};

      \node (F2) at (0, -1) {F2};
      \node (F2a) at (2, -1) {\textcolor{red}{AA}/ab};
      \node (F2b) at (3.5, -1) {\textcolor{teal}{ab}/ab};
      \node (F2c) at (5, -1) {\textcolor{red}{A}\textcolor{teal}{b}/ab};
      \node (F2d) at (6.5, -1) {\textcolor{teal}{a}\textcolor{red}{b}/ab};

      \node (N) at (0, -2) {count};
      \node (Na) at (2, -2) {370};
      \node (Nb) at (3.5, -2) {376};
      \node (Nc) at (5, -2) {119};
      \node (Nd) at (6.5, -2) {135};

      \draw[->] (X1) -- (F1a);
      \draw[->] (X2) -- (F2a);
      \draw[->] (X2) -- (F2b);
      \draw[->] (X2) -- (F2c);
      \draw[->] (X2) -- (F2d);

    \end{tikzpicture}
  </script>
  <div class="caption">A diagram of the testcross experiment</div>
</div>

You observe `4` different phenotypes based on the `4` haplotypes shown above. However, similarly to how your lenticular coin can show a `dragon` or a `monkey`, when a crossing over occurs between the `A` and `B` loci during meiosis, you may observe `1` of the `2` possible `recombinant` haplotypes with equal probability. In this example, the `recombinant` haplotypes would be the `AB` or `ab` gametes. Recognizing this pattern, you combine those two categories into one `recombinant` class. The rest goes into the `parental` class. 

What's the degrees of freedom? Since there are `2` classes: `df = 2 - 1 = 1`.

<div class="text-center">
  {% include figure.liquid loading="eager" 
  path="assets/img/degrees_of_freedom/meiosis.svg"
  zoomable="true" 
  max-height="300px" 
  width="auto" 
  class="img-fluid rounded z-depth-1" %}
  <div class="caption">A (highly simplified) diagram of meiosis </div>
</div>

##### Bonus questions:
1. Can you calculate the Chi-square value for the testcross results above? What's the null hypothesis? Do you reject the null?
2. How would you test if the probability of seeing the `dragon` engraving is actually the same as a `monkey` (50:50)?