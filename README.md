Download Link: https://assignmentchef.com/product/solved-cis450-computer-organization-and-architecture-homework-4
<br>
<ol>

 <li>Download the memory <strong>mountain </strong>program from /pub/cis450/programs/mountain.tgz and run it on your favorite Linux system in the lab or at home:</li>

</ol>




<ol>

 <li>tar xvzf mountain.tgz</li>

 <li>cd mountain</li>

 <li>make clean</li>

 <li>make —  ignore the warning regarding the volatile variable</li>

 <li>./mountain &gt; output.txt</li>

</ol>




<ol start="2">

 <li>Open the output data set, output.txt, in your favorite spreadsheet program; e.g., Microsoft Excel, etc., create a 3d graph showing the performance for different stride lengths and working set sizes. This graph should be similar to the one shown on the cover of your textbook. Try to record a sample when the system is lightly loaded to avoid interference from other processes executing at the same time.</li>

</ol>




<ol start="3">

 <li>Use the results to estimate the sizes of the L1 and L2 (and if they exist L3) caches on your system.</li>

</ol>




<ol start="4">

 <li>Finally, roughly estimate the access times to different parts of the memory hierarchy, in CPU cycles, to read a 4-byte word from:</li>

</ol>




<ol>

 <li>The on-chip L1 d-cache.</li>

 <li>The on/off-chip L2 cache.</li>

 <li>The integrated/off-chip L3 cache (if it exists on your system).</li>

 <li>Main memory.</li>

</ol>




Hint: See practice problem 6.19 (1<sup>st</sup> Edition) or 6.22 (2<sup>nd</sup> Edition).










Hints:




<ol>

 <li>Suppose that we log onto a Linux machine, say putty into <strong>cs.ksu.edu</strong>.</li>

 <li>To determine the machines canonical (standard) name, type the command: <strong>hostname</strong>. In this case, the canonical name is <strong>cs.ksu.edu</strong>, cislinux is an alias.</li>

 <li>Run the mountain program and redirect the output to output.txt: <strong>./mountain &gt; output.txt</strong></li>

 <li>Graph your output after importing the <strong>txt</strong> file into a spreadsheet.</li>

</ol>










<ol start="5">

 <li>Estimate the cache size; L1 about 32 kilobytes, L2 about 256 kilobytes, and L3 cache 8-12 MB. Throughput to L2 cache = 2400 MBps or 600 million 32-bit integers per second. Since the machine is running at roughly 2.53 Ghz = 2.53 billion cycles per second, it takes about 4.2 cycles/integer read from the L2 cache, etc.</li>

</ol>




<ol start="6">

 <li>To check your answer, issue the command: cat /proc/cpuinfo &gt; cpuinfo.txt</li>

</ol>




processor   : 0 to 23 (24 cores) vendor_id   : GenuineIntel

cpu family  : 6 model       : 44

model name  : Intel(R) Xeon(R) CPU           E5649  @ 2.53GHz cache size  : 12288 KB




<ol start="7">

 <li>Look up the specifications for the given CPU online. A google search for Intel Xeon E5649 specification yields:</li>

</ol>




<table width="563">

 <tbody>

  <tr>

   <td width="221"><strong>Level 1 cache size  </strong></td>

   <td width="341"><strong>24 x 32 KB 4-way set associative instruction caches </strong><strong>24 x 32 KB 8-way set associative data caches </strong></td>

  </tr>

  <tr>

   <td width="221"><strong>Level 2 cache size  </strong></td>

   <td width="341"><strong>24 x 256 KB 8-way set associative caches </strong></td>

  </tr>

  <tr>

   <td width="221"><strong>Level 3 cache size </strong></td>

   <td width="341"><strong>12 MB 16-way set associative shared cache </strong></td>

  </tr>

 </tbody>

</table>




Note: 32 KB L1 data cache for each core, 256 KB L2 cache for each core, 12 MB L3 cache shared by all cores.