# Datasets 
### Queries

The [diamond.tsv](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/queries/diamond.tsv) , [platinum.tsv](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/queries/platinum.tsv) and [gold.tsv](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/queries/gold.tsv) contains the initial query and destination query and their corresponding MAP value when retrieved wth BM25 in the following format: 

```qid \t initial query \t Map (initial query) \t Target Query \t MAP (Target Query)```

For Retrieveing purposes you can use the following query files in the tsv format i..e, ```qid \t query```

- [Diamond_initial.tsv](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/queries/Diamond_initial.tsv)
- [Diamond_Target.tsv](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/queries/Diamond_target.tsv)
- [Platinum_initial.tsv](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/queries/Platinum_initial.tsv)
- [Platinum_Target.tsv](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/queries/Platinum_target.tsv)
- [Gold_initial.tsv](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/queries/Gold_initial.tsv)
- [Gold_Target.tsv](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/queries/Gold_target.tsv)

### qrels

You can find the relevant judged documents per dataset in 
 - [qrels for Diamond dataset ](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/qrels/qrels.diamond.train.tsv)
 - [qrels for Platinum dataset ](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/qrels/qrels.platinum.train.tsv)
 - [qrels for Gold dataset ](https://github.com/Narabzad/msmarco-query-reformulation/blob/main/datasets/qrels/qrels.gold.train.tsv)
