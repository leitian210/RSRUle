# RSRule

## Requirements

The dependencies required to run the code are specified in [`pyproject.toml`](https://github.com/liu-yushan/TLogic/blob/main/pyproject.toml). Run `poetry install` to install the dependencies from [`poetry.lock`](https://github.com/liu-yushan/TLogic/blob/main/poetry.lock). For more information about Poetry, a tool for dependency management and packaging in Python, see https://python-poetry.org/docs/.

## Reproducing the Reported Results

We used NVIDIA RTX A6000, NVIDIA GeForce RTX 2080 Ti, and NVIDIA GeForce RTX 3090 for all our experiments.

The command to reproduce the results in our paper:

```
cd codes

python learn.py -d icews14 -l 1 2 3 -n 200 -p 16 -s 12

python apply.py -d icews14 -r 101221144026_r[1,2,3]_n200_exp_s12_rules.json -l 1 2 3 -w 0 -p 8

python evaluate.py -d icews14 -c 101221144026_r[1,2,3]_n200_exp_s12_cands_r[1,2,3]_w0_score_12[0.1,0.5].json
```


## Our work are based on
@inproceedings{ingram,
	author={Jaejun Lee and Chanyoung Chung and Joyce Jiyoung Whang},
	title={{I}n{G}ram: Inductive Knowledge Graph Embedding via Relation Graphs},
	booktitle={Proceedings of the 40th International Conference on Machine Learning},
	year={2023},
	pages={18796--18809}
}

@inproceedings{tlogic,
  title={Tlogic: Temporal logical rules for explainable link forecasting on temporal knowledge graphs},
  author={Liu, Yushan and Ma, Yunpu and Hildebrandt, Marcel and Joblin, Mitchell and Tresp, Volker},
  booktitle={Proceedings of the AAAI conference on artificial intelligence},
  volume={36},
  number={4},
  pages={4120--4127},
  year={2022}
}
