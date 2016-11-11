<p><strong>Let&#39;s get started with some simple numerical computations in Bash.</strong></p>

<p>As can be observed from the examples below, there are several ways of making simple numerical calculations in Bash. Just trying to echo an expression wrapped in quotation marks will not work. Wrapping the expression in double parenthesis $((..)) evaluates it, but this is confined to integer computations. To evaluate expressions involving decimal places (floating points) &quot;bc -l&quot; is very useful.</p>

<pre>
<code>~$ echo &quot;5+5&quot;
5+5
~$ echo &quot;5+5&quot;| bc
10
~$ echo &quot;5+5&quot;| bc -l
10
~$ echo &quot;5+5.2&quot;| bc -l
10.2
~$ echo &quot;5+5.2&quot;| bc
10.2
~$ echo &quot;3/4&quot;| bc
0
~$ echo &quot;3/4&quot;| bc -l
.75000000000000000000 
~`$ echo $`((3+3))
6  
</code></pre>

<p>To display the final result by rounding it to a certain number of decimal places, &quot;printf&quot; with a format specified can accomplish the task by specifying the &quot;scale&quot; (number of decimal points). Note that the ordering of the numbers matters in this case, as demonstrated below.</p>

<pre>
<code>~$ echo &quot;scale = 2; 10 * 100 / 30&quot; | bc
33.33
~$ echo &quot;scale = 2; 10 / 30 * 100&quot; | bc
33.00
~$ echo &quot;scale = 2; (10 / 30) * 100&quot; | bc
33.00
</code></pre>

<p>&#39;Expr&#39; is another way to accomplish such tasks.</p>

<pre>
<code>~`$ echo $`(expr 5 + 5)
10
~`$ echo $`(expr 5 - 5 + 2 )
2
~`$ echo $`(expr 5 - 5 + 2 / 3 )
0
~`$ echo $`(expr 5 - 5 + 2 / 1 )
2
</code></pre>

<p>Be careful with spacing in such expressions! Bash is very sensitive to them.</p>

<p><strong>Task</strong></p>

<p>We provide you with expressions containing +,-,*,^, / and parenthesis. None of the numbers in the expression involved will exceed&nbsp;.&nbsp;<br />
Your task is to evaluate the expression and display the output correct to&nbsp;&nbsp;decimal places.</p>

<p><strong>Sample Input 1</strong></p>

<pre>
<code>5+50*3/20 + (19*2)/7
</code></pre>

<p><strong>Sample Output 1</strong></p>

<pre>
<code>17.929
</code></pre>

<p><strong>Sample Input 2</strong></p>

<pre>
<code>-105+50*3/20 + (19^2)/7
</code></pre>

<p><strong>Sample Output 2</strong></p>

<pre>
<code>-45.929
</code></pre>

<p><strong>Sample Input 3</strong></p>

<pre>
<code>(-105.5*7+50*3)/20 + (19^2)/7
</code></pre>

<p><strong>Sample Output 3</strong></p>

<pre>
<code> 22.146</code></pre>

<p>&nbsp;</p>

<h1><code>SOLUTIONS</code></h1>

<p><code>read a<br />
#echo &quot;scale = 3; $a&quot; | bc -l<br />
#echo $(printf %.3f $(echo &quot;scale=3;$a&quot; | bc -l))<br />
#echo $(round $a/1 3);<br />
printf %.3f $(echo &quot;$a&quot; | bc -l)</code></p>

<p>&nbsp;</p>
