if statements in Bash are often used in four important ways:

1. if...then...fi statements
2. if...then...fi...else statements  
3. if..elif..else..fi  
4. if..then..else..if..then..fi..fi.. (Nested Conditionals)
The Recommended Resources section may give you a clearer idea of conditionals in Bash.

Your task: 
Given three integers (, , and ) representing the three sides of a triangle, identify whether the triangle is Scalene, Isosceles, or Equilateral.

Input Format 
Three integers, each on a new line.

Input Constraints 
 
Sum of any two sides will be greater than the third.

Output Format 
One word: either "SCALENE" or "EQUILATERAL" or "ISOSCELES" (quotation marks excluded).

Sample Input 1

2
3
4
Sample Output 1

SCALENE
Sample Input 2

6
6
6 
Sample Output 2

EQUILATERAL  

<code>
<p>read a</p>
<p>read b</p>
<p>read c</p>
<p>if [ "$a" -eq "$b" ] || [ "$b" -eq "$c" ] || [ "$a" -eq "$c" ];then</p>
<p>    if [ "$a" -eq "$b" ] && [ "$a" -eq "$c" ];then</p>
<p>        echo "EQUILATERAL" </p>
<p>    else</p>
<p>        echo "ISOSCELES"</p>
<p>    fi</p>
<p>        </p>
<p>else</p>
<p>    echo "SCALENE"</p>
<p>fi</p>

</code>
