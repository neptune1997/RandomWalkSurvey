# quantum walk
> In 1994 Peter Shor [Algorithms for quantum computation: Discrete log and factoring.] discovered a quantum algorithm to factor numbers efficiently (that is in timethat grows only polynomial with the length of the number to be factored), which has unleashed a wave of activity across a broad range of disciplines: physics, computer science, mathematics and engineering.As a part of quantum algorithms, quantum walk is motivated by the wide use of random walk. But there are some differences between random walk and quantum walk. One of the differences is that random walk converge to a certain distribution, but quantum walk don't. [quantum random walks-an introductory overview] 
>
> 



Kempe et al[quantum random walks - an introductory overvew] presented us two kinds of quantum walks. They are discrete time quantum walk and continus time random walk.   

1. discrete time quantum walk

   The discrete time model first appeared in the work of Feynman[Quantum mechanics and
   path integrals.] in 1966. In the field of quantum computation, Meyer rediscoveried the discrete time model of quantum walk in [ From quantum cellular automata to quantum
   lattice gases.][On the absence of homogeneous scalar unitary
   cellular automata ]. we define a space $\mathcal{H}=\mathcal{H_{p}}\bigotimes \mathcal{ H_{c}}$ for one dimentional quantum walk, . $\mathcal{H_{p}}$ denotes _Hilbert_ space.  For one dimentianl _Hilbert_ space, it can be represented as follows.

   $\mathcal{H_{p}}=\lbrace \vert i\rangle : i \in Z\rbrace$

   $\mathcal{H_{c}} $ is spanned by two basic states $ \lbrace \vert\uparrow  \rangle,\vert \downarrow\rangle \rbrace$.  Operation $\mathcal{S}$ defines the translation on space $\mathcal{H}$. 

   $$S =\vert \uparrow\rangle\langle\uparrow\vert\otimes\sum_{i}{\vert i+1\rangle\langle i \vert +\vert\downarrow\rangle\langle \downarrow\vert \otimes\sum_{i}{\vert i-1\rangle}}\langle i \vert$$ 

   $S$ can transform the basic state $\vert \uparrow \rangle \otimes \vert i \rangle $ to $ \vert \uparrow \rangle \otimes \vert i+1\rangle$ and $\vert \downarrow\rangle\otimes \vert i\rangle$ to $\vert \downarrow\rangle\otimes\vert i-1\rangle$. 

   $C$ is a unitrary transformation to rotate the spin in $\mathcal{H_{c}}$.  A frequently used unitrary transformation is called Hadamard coin $H$.  Here is an example of $H$. 

   $$\vert \uparrow \rangle \otimes \vert 0\rangle\xrightarrow{H} \frac{1}{\sqrt{2}} (\vert \uparrow\rangle + \vert\downarrow\rangle)\otimes\vert0\rangle $$

   The single quantum walk transforamtion can be defined as follows.

   $ U = S\cdot(C\otimes I)$

   Here is a example of single step transformation.

   ####  $\vert \uparrow \rangle \otimes \vert 0\rangle \xrightarrow{U} \frac{1}{\sqrt{2}}(\vert \uparrow\rangle\otimes\vert1\rangle+\vert\downarrow\rangle\otimes\vert-1\rangle)$

   The $T$ steps of tansformation can be represented by $U^{T}$. 

2. continuous time quantum walk

   The original purpose of  continuous time quantum walk is  to speed up many a algorithm using classic random walks. The concept of continuous time quantum walk was first presented by Farhi et al. in 1997.[Quantum computation and Decision tree] The authors exploit quantum walk in the decision tree algorithm instead of classic random walk . Different from discrete time quantum walk, continuous time quantum walk don't need a coin space $\mathcal{Hc}$, taking place entirely in the _Hilbert_ space $\mathcal{Hp}$.[quantum random walks - an introductory overvew] . The idea of continuous time quantum walk is from continuous random walk.  The continuous time random walk can be defined as $P(t) = exp(-Ht)P(0)$. Similarly, the unitary time evolution operator of continuous time quantum walk is 

   $\hat{U}(t)=exp(-i\hat{H}t) $ . 

3. some articles of quantum walk 

   __Quantum Computation and Decision Trees__(1998):

   the author devise a quantum algorithm for decision tree. 

   conclusions :

   - random walk and quantum walk both can reach n level in polymial time in n.
   - some examples that quantum walk is faster than classical counterpart.

   Introduction:

   - brief introduction to decision tree
   - introduce the method of quantum decision tree
     1. consider nodes of the decision tree correspond to quantum states, which give a basis
        for the Hilbert space. 
     2. constructing a Hamiltonian ˆH with nonzero
        off-diagonal matrix elements only between states that are connected in the corresponding
        decision tree.
     3. exploring the whole tree is to move through the tree with a probabilistic rule. 
     4. ​

   __One-Dimensional Quantum Walks__(2003):

   First present the idea of Hadamard walk---a quantum analog of the symmetric random walk.  the authors found some differences of classical random walk.  

   - the author recommend some compter science application of  __classical random walk__ .
   - the author use direct anoloy to random walk to introduce one dimensional quantum walk. 
   - study some __properties__ of quantum walk

   __One-Dimensional Three-State Quantum Walk__(2005):

   study the Hadamard walk with three inner state. 

   __Google in a quantum network__(2012):

   present a quantum page rank algorithm and compared with classical counterpart

   give a defination of quantum computer pagerank,

   conclusions:

   - outperforms the classical random walk 
   - may break the classical hierarchy of the webpage depending on the  topology of the web.

   introduction:

   Give us a backgroud of quantum network. 

   ​

   ​

   There are __many literature __ of quantum networks\cite{The DARPA quantum network}\cite{Outline of the SECOQC quantum-keydistribution
   network in Vienna}\cite{Tokyo Quantum Network 2010}\cite{Swiss Quantum Network}\cite{QKD in standard optical telecommunications networks}\cite{Standardization of quantum key distribution. and the ETSI standardization initiative}. In order to study the behavior of pagerank algorithm on the quantum network, the authors present the quantum page rank algorithm\cite{Google in a quantum network}. However, the authors don't give a specific defination of quantum page rank algorithms, but give a admissible class shown as follows.

   P1: The classical PageRank must be embedded into the quantum class with its undirected graph structure preserved. 
   P2: The sum of all quantum PageRanks must equal to 1.
   P3: The quantum PageRank obey a quantized Markov Chain (MC) rules.
   P4: The classical algorithm to compute the quantum PageRank is also feasible.

   The author exploit the idea of discrete time quantum walk. Hence we have to define the coin space $\mathcal{H_{c}}$and hilbert space $\mathcal{H_{p}}$ which are memtioned in the section of dicrete time quantum walk. The defination of coin space is similar to the one dimension quantum walk.

   $\mathcal{H_{c}} = span\{\vert L\rangle ,\vert R\rangle\}$

   However the hilbert space $\mathcal{H_{p}}$ here is a little tricky. Since the page rank algorithm is on a graph, the author define the Hilbert space as the space of oriented edges.  

   $\mathcal{H_{p}} = span\{ \vert i \rangle_{1},\vert j\rangle_{2} \quad\vert \quad i,j \in N\}$

   where N denotes the all the  vertices of the graph. 

   With these defination and the method of Szegedy’s Quantization of Markov Chains \cite{Quantization of Markov Chains} We can present the unitatry step operator of quantum walk as follows. 

   $U =S(2\prod - \mathbb{1})$

   $S=\sum_{i,k=1}^{N} \vert j,k\rangle \langle  k,j\vert $

   $\prod := \sum_{j=1}^{N} \vert \psi_{j} \rangle \langle \psi_{j}\vert$

   $\vert\psi_{j}\rangle = \vert j\rangle_{1} \otimes \sum_{k=1}^{N} \sqrt{G_{kj}}\vert k\rangle_{2} $

   Where $G_{ij}$ means the weight of edge ij.

   __Quantum Google in a Complex Network__(2013):

   Apply the quantum walk algorithm to the real-world network,and find some interesting properties of the quantum page rank algorithms.

   - We find that the algorithm is able to univocally reveal the underlying topology of the network and
     to identify and order the most relevant nodes.
   - Furthermore, it is capable to clearly highlight the structure of
     secondary hubs and to resolve the degeneracy in importance of the low lying part of the list of ranking
   - ​

