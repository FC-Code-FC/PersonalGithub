Appendix Table 10. Numeric confusion-matrix counts on the held-out test set. Positive class = default; predicted default corresponds to rejection.

| Model | Threshold regime | Threshold | TN | FP | FN | TP |
| --- | --- | --- | --- | --- | --- | --- |
| LR-C | Naive 0.5 | 0.5 | 27,684 | 193 | 1,660 | 342 |
| LR-C | F1-optimal | 0.19 | 26,121 | 1,756 | 942 | 1,060 |
| LR-C | Cost-optimal (r = 10) | 0.088 | 23,514 | 4,363 | 574 | 1,428 |
| RF-C | Naive 0.5 | 0.5 | 27,661 | 216 | 1,655 | 347 |
| RF-C | F1-optimal | 0.24 | 26,570 | 1,307 | 1,049 | 953 |
| RF-C | Cost-optimal (r = 10) | 0.086 | 23,697 | 4,180 | 557 | 1,445 |
| XGB-C | Naive 0.5 | 0.5 | 27,751 | 126 | 1,747 | 255 |
| XGB-C | F1-optimal | 0.23 | 26,564 | 1,313 | 1,048 | 954 |
| XGB-C | Cost-optimal (r = 10) | 0.084 | 23,005 | 4,872 | 513 | 1,489 |
