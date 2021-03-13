# Matches Made in Heaven: Toolkit and Large-Scale Datasets forSupervised Query Reformulation

With the increasing importance of the query reformulation task,various researchers have already offered different strategies to collectground-truth query translation pairs. To generate a ground-truth query reformulation dataset, we employ the following strategy. We propose a toolkit to first train a transformer architecture and learn the associations between the relevance judgement documents of each query and the query itself. Then, the trained transformer is exploited to generate queries from theset of relevant judgment documents associated with each query. Thegenerated queries are then evaluated based on their effectiveness, e.g.,map or mrr, and the most effective queries are chosen to be pairedwith the original query. 

 Based on MSMARCO training set, we release three datasets for MSMarco, namely,Diamond,Platinum, and Gold datasets. The details and the corresponding link to queries can be found in this table.
|                           | Number of Queries | MAP (Source Query) | MAP (Revised Query) | MAP Improvement % | MRR@10 (Source Query) | MRR@10 (Revised Query) | MRR@10 Improvement % |
|---------------------------|:-----------------:|:------------------:|:-------------------:|:-----------------:|:---------------------:|:----------------------:|:--------------------:|
| [Diamond Dataset](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/diamond.tsv)  |      188,398      |        0.139       |        1.000        |       619\%       |         0.126         |          1.000         |         690\%        |
| [Platinum Dataset](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/platinum.tsv)|      429,192      |        0.086       |        0.582        |       576\%       |         0.074         |          0.593         |         693\%        |
| [Gold Dataset](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/gold.tsv)    |      502,939      |        0.179       |        0.603        |       236\%       |         0.169         |          0.612         |         260\%        |
 
