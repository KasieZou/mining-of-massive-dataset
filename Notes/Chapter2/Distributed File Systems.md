### Distributed File Systems

#### Single Node Architecture

Traditional model for machine learning and statistics: Read the data from disk to memory $\to$ Algorithm access data in memory $\to$ Algorithm runs on CPU

*What if data is to big to load all from disk to memory?*  

$\to$ **"Classical" Data Mining**: Algorithms looks at the disk *and* CPU and memory, bring only a portion of data into memory, process in batches and write back to the disk. <!--could be inefficient: the foundamental problem would be disk read bandwidth. Solution: multiple disk and cpus parallel: cluster computing-->

#### Cluster Architecture

  

