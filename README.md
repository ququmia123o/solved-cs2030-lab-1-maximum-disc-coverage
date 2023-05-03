Download Link: https://assignmentchef.com/product/solved-cs2030-lab-1-maximum-disc-coverage
<br>



<strong>Tags &amp; Categories                                                      Related Tutorials</strong>

Tags:

Categories:

circles with their perimeters passing through the two points.

<ol start="3">

 <li>Find the length of line mc, denoted as d, which can be obtained using the Pythagorean Theorem</li>

</ol>

points are covered by each circle. Finally, return the maximum count.

<table width="606">

 <tbody>

  <tr>

   <td width="606">class Point {// include the properties of a Point // complete the constructorPoint(double x, double y) {} // include a toString method }</td>

  </tr>

 </tbody>

</table>

<table width="606">

 <tbody>

  <tr>

   <td width="606">class Point {… Point midPoint(Point q) {…}double angleTo(Point q) {…}}</td>

  </tr>

 </tbody>

</table>

<table width="606">

 <tbody>

  <tr>

   <td width="606">jshell&gt; /open Point.java jshell&gt; new Point(0.0, 0.0).midPoint(new Point(1.0, 1.0))$.. ==&gt; point (0.500, 0.500) jshell&gt; new Point(0.0, 0.0).angleTo(new Point(1.0, 1.0))$.. ==&gt; 0.7853981633974483 jshell&gt; new Point(0, 0).angleTo(new Point(-1, -1))$.. ==&gt; -2.356194490192345 jshell&gt; Point p = new Point(1, 1) p ==&gt; point (1.000, 1.000) jshell&gt; p.midPoint(new Point(2,2))</td>

  </tr>

 </tbody>

</table>

This task is divided into five levels. You may submit as soon as you complete one level. There is no restriction on the number of attempts.

<strong>In the spirit of incremental coding and testing, you will need to complete ALL levels to get full credit for this lab.</strong>

<strong>Level 1</strong>

<h1>Represent a Point</h1>

The first thing we can do is to group x and y coordinates into a single data structure or class.

Design a class Point to represent a point object with each pair of x- and y- coordinates.

Define an overriding toString method to output each point. In addition, the output of each double value, say d, is to be formatted with String.format(“%.3f”, d);

jshell&gt; /open Point.java




jshell&gt; new Point(0.0, 1.0) $.. ==&gt; point (0.000, 1.000)

jshell&gt; /exit

<strong>Level 2</strong>

<h1>Find the mid-point and angle of line pq</h1>

Find the mid-point between two consecutive points p and q. In addition, find the angle (in radians) of line pq using the atan or atan2 Math function (refer to the Java API specifications).

Complete the midPoint and angleTo methods and include them in the Point class. You may define other helper methods to further abstract away lower-level functionalities.

Inconsistencies between your output and the actual output involving -0.000 and 0.000 can be ignored.

<table width="606">

 <tbody>

  <tr>

   <td width="606">$.. ==&gt; point (1.500, 1.500)jshell&gt; pp ==&gt; point (1.000, 1.000) jshell&gt; /exit</td>

  </tr>

 </tbody>

</table>

<table width="606">

 <tbody>

  <tr>

   <td width="606">class Point {… Point moveTo(double theta, double d) {…         return new Point…;}}</td>

  </tr>

 </tbody>

</table>

<table width="606">

 <tbody>

  <tr>

   <td width="606">jshell&gt; /open Point.java jshell&gt; Point p = new Point(0.0, 0.0) p ==&gt; point (0.000, 0.000) jshell&gt; p.moveTo(Math.PI / 2, 1.0)$.. ==&gt; point (0.000, 1.000)jshell&gt; pp ==&gt; point (0.000, 0.000) jshell&gt; /exit</td>

  </tr>

 </tbody>

</table>

<table width="606">

 <tbody>

  <tr>

   <td width="606">Circle createUnitCircle(Point p, Point q) {…return new Circle…; }</td>

  </tr>

 </tbody>

</table>

<strong>Level 3</strong>

<h1>Moving the point</h1>

Now we need to allow points to be “moved”, so that we can move point m to c. However, in the spirit of immutability, the original point is not moved. Instead, a new point is returned, which reflects the new position of the original point if it has been moved by angle θ and distance d.

<em>Hint:</em> if a point, say m, is at (x, y), then moving m at an angle θ and distance d, would result in the new position having the coordinates (x + d cosθ, y + d sinθ)

<strong>Level 4</strong>

<h1>Creating the Circle</h1>

Define the Circle class to allow for the creation of circle objects with a given centre and radius. You may assume that all circles created are valid.

jshell&gt; /open Point.java




jshell&gt; /open Circle.java




jshell&gt; new Circle(new Point(0.0, 0.0), 1.0)

$.. ==&gt; circle of radius 1.0 centered at point (0.000, 0.000)




jshell&gt; new Circle(new Point(1, 1), 2)

$.. ==&gt; circle of radius 2.0 centered at point (1.000, 1.000)

We are now ready to construct unit circles whose perimeter passes through two given points.

By using the mid-point and angle of line pq, move the mid-point to the centre of the circle of radius r whose perimeter coincides with points p and q. You will need to work out the respective angle and distance values.

Create a jshell script maxDiscCoverage.jsh and define a createUnitCircle method that takes in two points p and q and returns the unit circle created.

Notice that if the distance between points p and q is larger than 2 units, then there is no unit circle whose perimeter coincides with the points. In this level, you may assume that the two points will form a unit circle.




<table width="680">

 <tbody>

  <tr>

   <td rowspan="2" width="37"> </td>

   <td width="607">jshell&gt; /open maxDiscCoverage.jsh jshell&gt; createUnitCircle(new Point(0, 0), new Point(1, 0)) $.. ==&gt; circle of radius 1.0 centered at point (0.500, 0.866) jshell&gt; createUnitCircle(new Point(0, 0), new Point(2, 0)) $.. ==&gt; circle of radius 1.0 centered at point (1.000, 0.000) jshell&gt; /exit</td>

   <td rowspan="2" width="37">  </td>

  </tr>

  <tr>

   <td width="607"><strong>Level 5</strong><strong>Maximum Disc Coverage</strong>You are now ready to find the maximum unit disc coverage.Within maxDiscCoverage.jsh, further define a method findMaxDiscCoverage that takes in an array of Point objects and finds the maximum coverage among them. You may make use of other helper methods.

    <table width="607">

     <tbody>

      <tr>

       <td width="607">Circle createUnitCircle(Point p, Point q) {…}int findMaxDiscCoverage(List&lt;Point&gt; points) {int maxDiscCoverage = 0;int numOfPoints = points.size(); for (int i = 0; i &lt; numOfPoints – 1; i++) {         for (int j = i + 1; j &lt; numOfPoints; j++) {// find coverage with points.get(i) and points.get(j)…}     }return maxDiscCoverage; }</td>

      </tr>

     </tbody>

    </table>Once again, keep in mind that if the distance between points p and q is larger than 2 units, then there is no unit circle whose perimeter coincides with the points.

    <table width="607">

     <tbody>

      <tr>

       <td width="607">jshell&gt; /open Point.java jshell&gt; /open Circle.java jshell&gt; /open maxDiscCoverage.jsh jshell&gt; List&lt;Point&gt; points = List.of(new Point(0, 0), new Point(1, 0))points ==&gt; [point (0.000, 0.000), point (1.000, 0.000)] jshell&gt; findMaxDiscCoverage(points)$.. ==&gt; 2 jshell&gt; points = List.of(new Point(0, -1), new Point(1, 0), new Point(0, 1), new Point(-1, 0)) points ==&gt; [point (0.000, -1.000), point (1.000, 0.000), poi … 0), point (-1.000, 0.000)] jshell&gt; findMaxDiscCoverage(points)$.. ==&gt; 4 jshell&gt; /exit</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>


