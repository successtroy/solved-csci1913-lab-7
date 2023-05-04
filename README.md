Download Link: https://assignmentchef.com/product/solved-csci1913-lab-7
<br>
Two algorithms for searching arrays, called <em>linear search</em> and <em>binary search,</em> were discussed in the lectures. The linear search algorithm did only one comparison per iteration, but it needed many iterations. The binary search algorithm did more than one comparison per iteration, but it needed few iterations. As a result, linear search should be more efficient than binary search for small arrays, and binary search should be more efficient than linear search for large arrays. How big must an array be before binary search becomes more efficient than linear search? You will determine this experimentally.

<ol>

 <li></li>

</ol>

Here’s what you must do for this laboratory exercise. <strong>First,</strong> write a method called linearSearch that takes an integer called key and an integer array called keys as its arguments. Your method must use linear search to find key in keys. It must then return the number of comparisons that were needed to find it.

<strong>Second,</strong> write a method called binarySearch that takes an integer called key and a sorted integer array called keys as its arguments. Your method must use binary search to find key in keys. It must then return the number of comparisons that were needed to find it.       Unlike the methods discussed in the lectures, your linearSearch and binarySearch methods must return the number of comparisons they use to find key in keys. This is not necessarily the same as returning the index of key in keys! Here are two things to know about counting comparisons.

Count <em>only</em> comparisons made between key and elements of keys. Your methods may make other comparisons, but <em>do not</em> count those, because they are not relevant to this experiment.

Count these comparisons whether or not they succeed. It doesn’t matter if a comparison is true or false, you must still count it.

To write these methods, you can copy the linear search and binary search algorithms from the lectures, and then modify them. You can also copy algorithms from the textbook, or from the Internet, or from any other source. You can even write your own algorithms, but this is not recommended for binary search, because it is harder to get right than it looks.

<strong>Third,</strong> place your methods in the driver class <a href="https://html2pdf.com/files/em7bq9tg01reml6o/o_1e0e16fpe1hl61liu1guu18hgv30n/BinaryVsLinear.java"><strong>BinaryVsLinear</strong></a><a href="https://html2pdf.com/files/em7bq9tg01reml6o/o_1e0e16fpe1hl61liu1guu18hgv30n/BinaryVsLinear.java"><strong>, </strong></a>as shown below. (Source code for this class is available on Canvas.) The driver class’s main method constructs thirty arrays, each with sorted elements, and computes the average number of comparisons required to find an element in each array.

class BinaryVsLinear

{    private static int linearSearch(int key, int [] keys)    {

⋮

}




private static int binarySearch(int key, int [] keys)    {

⋮

}




public static void main(String [] args)

{

for (int length = 1; length &lt;= 30; length += 1)

{

int[] array = new int[length];

for (int index = 0; index &lt; length; index += 1)

{

array[index] = index;

}




double linearTotal = 0.0;        double binaryTotal = 0.0;

for (int element = 0; element &lt; length; element += 1)

{

linearTotal += linearSearch(element, array);          binaryTotal += binarySearch(element, array);        }




double linearAverage = linearTotal / length;        double binaryAverage = binaryTotal / length;

System.out.println(length + ” ” + linearAverage + ” ” + binaryAverage);      }

}

}

<strong>Fourth,</strong> run the class BinaryVsLinear. You should obtain a table with three columns of numbers. The first column is an array size (from 1 to 30). The second column is the average number of comparisons required by linearSearch to find an element in an array of that size. The third column is the average number of comparisons required by binarySearch to find an element in an array of that size.

<strong>Fifth,</strong> draw a graph using the numbers in the table. You can draw it by hand, or you can use a program, like a spreadsheet. The <em>x</em>-axis of the graph must be the array size. The <em>y</em>-axis must be the average number of comparisons required to find an element in an array of that size. Draw two curves in the graph: one for linear search, and the other for binary search.