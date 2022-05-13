## params
| data   | model          |        | learning_rate | max_len | batch_size | num_epoch |
| ------ | -------------- | ------ | ------------- | ------- | ---------- | --------- |
| Ruddit | Deberta-base4  | warmup | 0.00003       | 192     | 32         | 3         |
|        |                | train  | 0.00003       | 192     | 32         | 6         |
|        |                | valid  | -             | 192     | 96         | -         |
|        | Deberta-large4 | warmup | 0.00003       | 192     | 32         | 3         |
|        |                | train  | 0.00003       | 192     | 32         | 5         |
|        |                | valid  | -             | 192     | 96         | -         |
|        | Roberta-base4  | warmup | 0.00005       | 192     | 32         | 4         |
|        |                | train  | 0.00005       | 192     | 32         | 4         |
|        |                | valid  | -             | 192     | 96         | -         |
|        | Roberta-large4 | warmup | 0.00005       | 192     | 32         | 3         |
|        |                | train  | 0.00005       | 192     | 32         | 3         |
|        |                | valid  | -             | 192     | 96         | -         |




| data     | model                         |        | learning_rate | max_len | batch_size | num_epoch |
| -------- | ----------------------------- | ------ | ------------- | ------- | ---------- | --------- |
| Jigsaw18 | Deberta-base1/Deberta-base2   | warmup | 0.00005       | 384     | 32         | 1         |
|          |                               | train  | 0.00003       | 384     | 32         | 3         |
|          |                               | valid  | -             | 384     | 96         | -         |
|          | Deberta-large1/Deberta-large2 | warmup | 0.00005       | 320     | 32         | 2         |
|          |                               | train  | 0.00003       | 320     | 32         | 2         |
|          |                               | valid  | -             | 320     | 96         | -         |
|          | Roberta-base1/Roberta-base2   | train  | 0.000025      | 256     | 32         | 1         |
|          |                               | valid  | -             | 256     | 96         | -         |
|          | Roberta-large1/Roberta-large2 | train  | 0.000025      | 256     | 32         | 1         |
|          |                               | valid  | -             | 256     | 96         | -         |




| data     | model          |       | learning_rate | max_len | batch_size | num_epoch |
| -------- | -------------- | ----- | ------------- | ------- | ---------- | --------- |
| Jigsaw19 | Deberta-base3  | train | 0.000025      | 256     | 32         | 1         |
|          |                | valid | -             | 256     | 96         | -         |
|          | Roberta-base3  | train | 0.000025      | 256     | 32         | 1         |
|          |                | valid | -             | 256     | 96         | -         |
|          | Roberta-large3 | train | 0.000025      | 256     | 32         | 1         |
|          |                | valid | -             | 256     | 96         | -         |


## score
| model           | data     | me_validation | validation   | public LB | private LB |
| --------------- | -------- | ------------- | ------------ | --------- | ---------- |
| roberta-base    | jigsaw18 | -             | 0.7023       | 0.7815    | 0.8052     |
| roberta-large   | jigsaw18 | -             | 0.7035       | 0.7788    | 0.8064     |
| deberta-base    | jigsaw18 | 0.7008/bs=8   | 0.7040/bs=32 | 0.7598    | 0.8030     |
| deberta-large   | jigsaw18 | -             | 0.7050       | 0.7906    | 0.8139     |
| roberta-base-l  | jigsaw18 | -             | 0.7028       | 0.7690    | 0.8070     |
| roberta-large-l | jigsaw18 | -             | 0.7027       | 0.7737    | 0.8013     |
| deberta-base-l  | jigsaw18 | 0.7021/bs=8   | 0.7030/bs=32 | 0.7474    | 0.8013     |
| deberta-large-l | jigsaw18 | -             | 0.7044       | 0.7716    | 0.8085     |
| roberta-base    | jigsaw19 | 0.6971/bs=8   | 0.7008/bs=32 | 0.7617    | 0.8020     |
| roberta-large   | jigsaw19 | 0.6971/bs=4   | 0.6991/bs=32 | 0.7468    | 0.7968     |
| deberta-base    | jigsaw19 | 0.6982/bs=8   | 0.7026/bs=32 | 0.7403    | 0.7958     |
| roberta-base    | ruddit   | 0.6855/bs=32  | 0.6859/bs=32 | 0.8108    | 0.7845     |
| roberta-large   | ruddit   | 0.6904/bs=4   | 0.6865/bs=32 | 0.8132    | 0.7955     |
| deberta-base    | ruddit   | 0.6883/bs=32  | 0.6880/bs=32 | 0.7903    | 0.7880     |
| deberta-large   | ruddit   | 0/bs=2        | 0.6942/bs=32 | 0.8296    | 0.7989     |
| ensemble        | jigsaw18 |               |              | 0.7763    | 0.8103     |
| ensemble        | jigsaw19 |               |              | 0.7509    | 0.8012     |
| ensemble        | ruddit   |               |              | 0.8235    | 0.7983     |
| ensemble        | all15    |               |              | 0.7879    | 0.8139     |