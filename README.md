Download Link: https://assignmentchef.com/product/solved-cosc220-project-3
<br>
Write a program that uses recursive function to identify the path in a given maze. The layout of the maze is written in a file called “mazexxx.txt” (xxx represent three digit, maze123.txt) that contains a two dimensional array. The array has ‘0’, ‘1’, ‘S’,’F’’ as its values. ‘0’ indicates the square that is blocked and ‘1’ indicates the square that you can go through. ‘S’ indicates the starting square and ‘F’ indicates the finishing square. See below for an example layout of a maze.

<table width="297">

 <tbody>

  <tr>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">S</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">1</td>

   <td width="20">F</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

 </tbody>

</table>

Your program should also display the found path by drawing ‘X’ along the path (see below) and write the maze with the found path to another file called “solxxx.txt” (e.g., sol123.txt).

<table width="325">

 <tbody>

  <tr>

   <td width="20"> </td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">X</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">1</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">1</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">1</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">1</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="22">1</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">1</td>

   <td width="20">1</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">1</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">S</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">0</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="22">X</td>

   <td width="20">F</td>

   <td width="20">0</td>

  </tr>

  <tr>

   <td width="20">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="22">0</td>

   <td width="20">0</td>

   <td width="20">0</td>

  </tr>

 </tbody>

</table>

<strong> </strong>