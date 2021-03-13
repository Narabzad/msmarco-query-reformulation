# Matches Made in Heaven: Toolkit and Large-Scale Datasets forSupervised Query Reformulation

With the increasing importance of the query reformulation task,various researchers have already offered different strategies to collectground-truth query translation pairs. To generate a ground-truth query reformulation dataset, we employ the following strategy. We propose a toolkit to first train a transformer architecture and learn the associations between the relevance judgement documents of each query and the query itself. Then, the trained transformer is exploited to generate queries from theset of relevant judgment documents associated with each query. The generated queries are then evaluated based on their effectiveness, e.g.,map or mrr, and the most effective queries are chosen to be pairedwith the original query. 

## Dataset

 Based on MSMARCO training set, we release three datasets for MSMarco, namely,Diamond,Platinum, and Gold datasets. The details and the corresponding link to queries can be found in this table. Queries were retrieved using [BM25 implementation in Anserini](https://github.com/castorini/anserini/blob/master/docs/experiments-msmarco-passage.md). All the queries have relevant judged documents that can be found in [MSMARCO website](https://microsoft.github.io/msmarco/). 


|                           | Number of Queries | MAP (Source Query) | MAP (Revised Query) | MAP Improvement % | MRR@10 (Source Query) | MRR@10 (Revised Query) | MRR@10 Improvement % |
|---------------------------|:-----------------:|:------------------:|:-------------------:|:-----------------:|:---------------------:|:----------------------:|:--------------------:|
| [Diamond Dataset](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/diamond.tsv)  |      188,398      |        0.139       |        1.000        |       619\%       |         0.126         |          1.000         |         690\%        |
| [Platinum Dataset](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/platinum.tsv)|      429,192      |        0.086       |        0.582        |       576\%       |         0.074         |          0.593         |         693\%        |
| [Gold Dataset](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/gold.tsv)    |      502,939      |        0.179       |        0.603        |       236\%       |         0.169         |          0.612         |         260\%        |
 
For instance , to replicate the numbers in the table (retrieve and evaluate the Diamond Dataset) you need to follow these steps: 

1. Installing [Anserini](https://github.com/castorini/anserini)
2. [Index MSMARCO passage collection](https://github.com/castorini/anserini/blob/master/docs/experiments-msmarco-passage.md#data-prep)
3. you may to may the number of threads and the index directory when following this command
```
sh anserini/target/appassembler/bin/SearchMsmarco -hits 1000 -threads 1 \
 -index indexes/msmarco-passage/lucene-index-msmarco \
 -queries diamond.tsv \
 -output runs/run.diamond.train.tsv
```
4. You may evaluate the results on MRR@10 with the folllowing comand :
```
python anserini/tools/scripts/msmarco/msmarco_passage_eval.py \
 qrels.train.tsv runs/run.diamond.train.tsv
```
and the output should be:
```
#####################
MRR @10: 1
QueriesRanked: 188398 
#####################
```

6. You may evaluate the MAP with the following commands:
```
python anserini/tools/scripts/msmarco/convert_msmarco_to_trec_run.py \
 --input runs/run.diamond.train.tsv \
 --output runs/run.diamond.train.trec

python anserini/tools/scripts/msmarco/convert_msmarco_to_trec_qrels.py \
 --input qrels.train.tsv \
 --output qrels.train.trec
 
anserini/tools/eval/trec_eval.9.0.4/trec_eval -m map qrels.train.trec runs/run.diamond.train.tsv
```
and the output should be:

``` map  all   1 ```
