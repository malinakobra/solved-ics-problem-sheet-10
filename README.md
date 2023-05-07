Download Link: https://assignmentchef.com/product/solved-ics-problem-sheet-10
<br>
<table width="572">

 <tbody>

  <tr>

   <td width="448"><strong>Problem 10.1: </strong><em>assembler programming</em></td>

   <td width="123"> </td>

  </tr>

 </tbody>

</table>

The following program has been written for the simple central processing unit introduced in class. The table below shows the initial content of the 16 memory cells. The first column denotes the memory address and the second column shows the memory content in hexadecimal notation.

<table width="393">

 <tbody>

  <tr>

   <td width="47">Cell</td>

   <td width="58">Hex</td>

   <td width="72">Binary</td>

   <td width="78">Assembler</td>

   <td width="137">Description</td>

  </tr>

  <tr>

   <td width="47">0</td>

   <td width="58">2f</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">1</td>

   <td width="58">6a</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">2</td>

   <td width="58">4f</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">3</td>

   <td width="58">21</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">4</td>

   <td width="58">71</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">5</td>

   <td width="58">41</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">6</td>

   <td width="58">a9</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">7</td>

   <td width="58">d0</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">8</td>

   <td width="58">e0</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">9</td>

   <td width="58">6f</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">10</td>

   <td width="58">01</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">11</td>

   <td width="58">02</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">12</td>

   <td width="58">03</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">13</td>

   <td width="58">04</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">14</td>

   <td width="58">05</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td width="47">15</td>

   <td width="58">06</td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="137"> </td>

  </tr>

 </tbody>

</table>

<ol>

 <li>Convert the machine code from hexadecimal notation into binary notation.</li>

 <li>Write down the assembler code for the machine code. Add meaningful descriptions.</li>

 <li>The program leaves a result in memory cell 15 when it halts. What is the value? Explain how the program works.</li>

 <li>What happens if the value stored in memory cell 9 is changed to 0x70 before execution starts? Explain.</li>

</ol>

<strong>Problem 10.2: </strong><em>integer multiplication in risc-v rv32i assembler                                                     </em>(2+1 = 3 points)

The 32-bit RISC-V base integer instruction set (rv32i) does not support multiplication and division operations. To deal with this, a compiler may call a function when a multiplication is needed. For example, gcc expects that a function mulsi3(unsigned int a, unsigned int b) is provided to multiply two integers. A multiplication can be carried out by repeated additions and shifts:

unsigned int __mulsi3 (unsigned int a, unsigned int b)

{

unsigned int r = 0;

while (a) { if (a &amp; 1) { r += b;

}

a &gt;&gt;= 1; b &lt;&lt;= 1;

} return r;

}

<ol>

 <li>Translate the above C code into equivalent RISC-V rv32i assembler code. Comment the assembler code to explain how the calculation proceeds. Note that the arguments are passed via the registers a0 (x10) and a1 (x11) and that the result is returned in a0 (x10).</li>

 <li>Does the function need function call prolog and epilog? Explain why or why not.</li>

</ol>

You are invited to use <a href="http://tice.sea.eseo.fr/riscv/">emulsiV</a> to develop and test your assembler code.