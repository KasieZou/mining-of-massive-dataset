### Chapter 1 - Data Mining

#### What's data mining

Use the most powerful hardware, the most powerful programing systems, and the most efficient algorithms to solve problems in science, commerce, healthcare, goverment, the humanities, and many other fields of human endeavor.

##### Modeling

Generally, the objective of data mining is an algorithm. The hard part is creating the model, and once the model is available, the algorithm to use the model is straightforward.

##### Statistical Modeling

Data mining in statistical view: the construction of a statistical model, an underlying distribution from which the visible data is drawn. 

##### Machine Learning

Some data mining appropriately uses algorithms from machin learning, but ML is not suitable for all data mining problems: 

* Suitable situations: when we have little idea of what the data says about the problem we are trying to solve - we don't know how the data support the outcome. eg. Movie rating.

* Unsuitable situations: when we can describe the goals of the mining more directly. Like searching through pattern matching. 

ML also has some shortcomings:

* Precise but not interpretable. In some cases where exlaninability is important, we can't see why and how the model changes and what it informs. 

##### Computational Approaches to Modeling

A model of the data is simply the answer to a complex query about that data, in contrast to the statistical approach. Instead of monitoring the potential distribution, which requires strict assumptions that are not easy to satisfy, using other approaches such as:

* constructing a random process
* summarizing the data succinctly and approximately
* extracting the most prominent features of the data and ignoring the rest

##### Summarization

* PageRank idea (Web mining): the entire complex structure of the Web is summarized by a single number('PageRank') for each page, which is (oversimplifying somewhat) the probability that a random walker on the graph would be at that page at any given time - reflects the 'importance' of the page. 
* Clustering: form clusters and use the summaries of the cluster to describe the summary of the entire data set. 

##### Feature Extraction

The typical feature-based model (eg. Bayes nets) looks for the most extreme examples of a phenomenon and represents the data by these examples. Feature extraction: 

* Frequent Itemsets: small sets of items that appear together - characterization of the data that we seek. Original application in market baskets, such as hamburger and ketchup.
* Similar Items. When data looks like a collection of set, the objective is to find the pairs of sets that have a relatively large fraction of their elements in common. eg. collaborative filtering in recommendation. 

#### Statistical Limits on Data Mining

A common sort of data-mining problem involves discovering unusual events hidden within massive amounts of data. However, the 'unusual events' that you wish to discover or track may be just a conjecture and not ture. When tracking it, you may need to discover all kinds of data, like TIA program, which often results in privacy problem, and what you are looking for could be 'bogus', occurrences that have no cause other than that random data will always have some number of unusual feature that look significant but aren't. 

##### Total Information Awareness

TIA program was intended to mine all kinds of data including private information to teach terrorist activity. *Information integration* - the idea of relating and combining different data sources to obtain insights that are not available from any one source - is often a key step on the way to solving an important problem.

One particular techinal problem: if you look in your data for too many things at the sme time, you will see things that look interesting, but are in fact simply sttatistical artifacts and have no significance. 

##### Bonferroni's Principle

Bonferroni's principle helps to avoid treating random occureences as if they are real. Calculate the expected number of occurrences of the events that looking for, on the assumption that data is random. If this number is significantly larger than the number of real instances you hope to find, then you must expect almost anything you find to be bogus, i.e., a statistical artifact rather than evidence of what you are looking for. 

#### Things Useful to Know

##### Importance of Words in Documents

In the applications of data mining where the problem is to categorize documents (sequences of words) by their topic, which is identified by finding the special words that characterize documents about that topic. The main idea is to find the rare but frequent words which may be the topic words, using TFIDF.

TFIDF ( Term Frequency times Inverse Document Frequency) with total $N$ documents is computed as follows:

*  $TF_{ij} = \frac{f_{ij}}{\max_kf_{kj}}$, $f_{jk}$ is the frequency of term i in document j.
* $IDF_i=\log_2(N/n_i)$, $n_i$ is number of documents term i appears. 

* $TFIDF=TF_{ij}\times IDF_i$. The higher the closer to the topic. 

##### Hash Functions

Hash function takes a hash-key value as an argument and produces a bucket number as a result. The bucket number is an integer, normally in the range 0 to B − 1, where B is the number of buckets. Hash-keys can be of any type. Intuitive property:  if hash-keys are drawn randomly from a reasonable population of possible hash-keys, then h will send approximately equal numbers of hash-keys to each of the B buckets. 

Different types of hash-keys: (for common $h(x) = x$ mod $B$) 

* Integer: choose B to be a prime
* String: convert each character to ASCII of Unicode and sum before dividing by B
* Record: use algorithm appropriate to convert into integers
* Array, set, or bag of elements of some type: convert into integers. 

##### Indexes

One way to form indexes is to use hash table. Use hash-key to locate the bucket to store the records. The bucket could be a list of records in main-memory or a disk block. It's efficient to search for the desired records. 

![Screen Shot 2021-04-13 at 3.32.50 PM](/Users/kasiezou/Library/Application Support/typora-user-images/Screen Shot 2021-04-13 at 3.32.50 PM.png)

##### Secondary Storage

Where the data is stored cause a differnece in time taken to perform computations, like the data is initially on disk or in main memory. Disks are organized into *blocks*, which are the minimon units that the operating system uses to move data between main memory and disk. Acccessing data (from disk to main memory) would cost far more time than computing, so we can organizing data and put related data on a single *cylinder*, the collection of blocks reachable at a fixed radius from the center of the disk, and therefore accessible without moving the disk head. 

##### The Base of Natural Logarithms

Useful properties:

* $\lim_{x\to\infin}(1+\frac{1}{x})^x = e $ $\Rightarrow (1+a)^b \approx e^{ab}$ When $a$ is small.
* $\lim_{x\to\infin}(1-\frac{1}{x})^x = \frac{1}{e} $ $\Rightarrow (1-a)^b \approx e^{-ab}$ When $a$ is small.
* Taylor expansion: $e_x = \Sigma^\infin_{i=0}\frac{x_i}{i!}$ or $e^x=1+x+\frac{x^2}{2}+\frac{x^3}{6}+\frac{x^4}{24}+\dots$ 

##### Power Laws

Refer to the linear relationship between the logarithms of the variables. The general form of a power law relation $x$ and $y$ is $\log y = b + a\log x$, equals to $y=cx^a$ for some constants $a$ and $c$. 

*The Matthew Effect*: the existence of power laws with values of the exponent higher than 1. "The rich get richer": where getting a high value of some property causes that very property to increase. 

