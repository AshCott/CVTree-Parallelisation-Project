---


---

<h1 id="cvtree-parallelisation-project">CVTree Parallelisation Project</h1>
<h2 id="introduction-to-cvtree">Introduction to CVTree</h2>
<p>Composition Vector Tree otherwise known as CVTree is an  alignment-free composition vector (CV) algorithm for phylogenetic analysis of a large dataset of DNA and/or Amino Acids sequences. The overall aim of the program is to create a variable matrix which contains  inferring evolutionary relatedness of microbial organisms. This implementation of CVTree has been implemented using the C++ programming language and works by taking in the input of bacteria genomes which are stored in Microsoft Fast Find files (.ffa). The program then searches through the bacteria to find correlations between the bacteria which is then passed to the program via a command-line argument. The program will then output the correlation to the console so the user can see the results.</p>
<h2 id="parallelisation-results">Parallelisation Results</h2>
<p>Final performance test of the program gained an averaged total speedup of 9.84 seconds this an 83.60% (3.79x) performance speedup over the sequential version. (See Figure 16 and Table 1 below)</p>
<p><img src="https://i.postimg.cc/XJq7L2GH/figure-1.png" alt="Final Parallelization Results"><br>
<em>Figure 1 - Final Parallelization Results</em></p>
<p><img src="https://i.postimg.cc/q7VpyJ47/Table-1-v2.png" alt="enter image description here"><br>
<em>Table 1 - Results of Raw Results</em></p>
<p>Using the visual studio performance profiler, we can see the that in Figure 2, the first loop maximises its usage of the CPU using around a constant 100%, but it does drop off towards the end when threads start finishing their tasks. The second loop only uses about 50% of the CPU’s processing ability this is likely caused by the loop printing out to console which slows down the time the program can spend performing the calculations.</p>
<p><img src="https://i.postimg.cc/bw0JwSfT/figure-2.png" alt="Final Parallelization CPU Usage"><br>
<em>Figure 2 - Final Parallelization CPU Usage</em></p>
<p>In Figure 3 we can see that using two threads increases improves the performance of the program from 37.32 to 19.14 seconds (saving of 18.18s). Going to three threads reduces the time by 3.91 seconds (15.23) and after this point adding another core only reduces the time by a second or less, and we start to see diminishing returns on adding more cores.</p>
<p><img src="https://i.postimg.cc/BvqvLZqG/figure-3.png" alt="Execution Time Across core count"><br>
<em>Figure 3  –  Execution Time Across core count</em></p>
<p>In Figure 4 we can see that the parallelization of the program was successful and as we add more and more threads, we achieve greater program performance.</p>
<p><img src="https://i.postimg.cc/MGdpykTf/figure-4.png" alt="enter image description here"><br>
<em>Figure 4 - Parallelization Speedup (Times)</em></p>

