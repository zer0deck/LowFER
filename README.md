# LowFER.RuWordNet

Testing the algorithm proposed in the article ["LowFER: Low-rank Bilinear Pooling for Link Prediction", ICML 2020](https://www.semanticscholar.org/paper/LowFER%3A-Low-rank-Bilinear-Pooling-for-Link-Amin-Varanasi/0126fce30b412d583f8e33714908dd09b86293d1) on the Russian-language thesaurus of the [WN](https://wordnet.princeton.edu/) format - ***[RuWordNet](https://ruwordnet.ru/ru)*** for 2021.

## Table of content

- [LowFER.RuWordNet](#lowferruwordnet)
  - [Table of content](#table-of-content)
  - [Launch](#launch)
  - [Results](#results)
  - [Requirements](#requirements)
  - [Authors](#authors)
  - [Licences](#licences)
  - [Citing](#citing)

## Launch

1. Original WN18 data launch with hyperparams tuned by [Saadullah Amin](https://github.com/suamin):

    ```bash
    python main.py --dataset WN18 --num_iterations 30 --batch_size 128 --lr 0.005 --dr 0.995 --edim 200 --rdim 30 --input_dropout 0.2 --hidden_dropout1 0.1 --hidden_dropout2 0.2 --label_smoothing 0.1 --k 10
    ```

2. Our RuWordNet-2021 data launch:

    ```bash
    python main.py --dataset rwn-2021 --num_iterations 30 --batch_size 128 --lr 0.005 --dr 0.995 --edim 200 --rdim 30 --input_dropout 0.2 --hidden_dropout1 0.1 --hidden_dropout2 0.2 --label_smoothing 0.1 --k 10
    ```

## Results

<table>
    <thead>
        <tr>
            <th>Dataset</th>
            <th>MRR</th>
            <th>Hits@10</th>
            <th>Hits@3</th>
            <th>Hits@1</th>
        </tr>
    </thead>
    <tbody>
        <tr>
          <td colspan=5 style="text-align: center;"><b>Original Data</b></td>
        </tr>
                <tr style="color: green">
            <td><b><em>WN18</em></b></td>
            <td>0.953</td>
            <td>0.958</td>
            <td>0.955</td>
            <td>0.949</td>
        </tr>
        <tr style="color: 	#819F00">
            <td><b><em>FB15k</em></b></td>
            <td>0.795</td>
            <td>0.892</td>
            <td>0.833</td>
            <td>0.741</td>
        </tr>
        <tr style="color: #FF7400">
            <td><b><em>WN18RR</em></b></td>
            <td>0.470</td>
            <td>0.526</td>
            <td>0.482</td>
            <td>0.443</td>
        </tr>
        <tr style="color: #A60000">
            <td><b><em>FB15k-237</em></b></td>
            <td>0.358</td>
            <td>0.544</td>
            <td>0.394</td>
            <td>0.266</td>
        </tr>
        <tr>
          <td colspan=5 style="text-align: center;"><b>Our Data</b></td>
        </tr>
        <tr>
            <td><b><em>RuWN21*</em></b></td>
            <td>0.91</td>
            <td>0.94</td>
            <td>0.94</td>
            <td>0.92</td>
        </tr>
    </tbody>
</table>

> *after 30 iterations
## Requirements

The original codebase was implemented in Python 3.6.6. Required packages are:

```bash
python     3.6.6
numpy      1.15.1
pytorch    1.0.1
```

## Authors

2022,
Grandilevskii Aleksei, software engineer,
github: [@zer0deck](https://github.com/zer0deck),
email: zer0deck.work@icloud.com,
website: zer0deck.com

2022,
Sorokin Mikhail, ML engineer,
github: [@Mikha1lSorokin](https://github.com/Mikha1lSorokin),
email: 338347@niuitmo.ru


## Licences

1. RuWordNet is licensed as CCANSA 3.0 Licence

    <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/3.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/">Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License</a>.

2. LowFER itself is licenced as [MIT License](LICENSE).

## Citing

**This project is provided by [LowFER model](https://github.com/suamin/LowFER).**

1. ```bibtex
    @inproceedings{pmlr-v119-amin20a,
      title ={{L}ow{FER}: Low-rank Bilinear Pooling for Link Prediction},
      author = {Amin, Saadullah and Varanasi, Stalin and Dunfield, Katherine Ann and Neumann, G{\"u}nter},
      booktitle = {Proceedings of the 37th International Conference on Machine Learning},
      pages = {257--268},
      year = {2020},
      editor = {III, Hal Daumé and Singh, Aarti},
      volume = {119},
      series = {Proceedings of Machine Learning Research},
      month = {13--18 Jul},
      publisher = {PMLR},
      pdf = {http://proceedings.mlr.press/v119/amin20a/amin20a.pdf},
      url = {https://proceedings.mlr.press/v119/amin20a.html}
    }
    ```

2. ```bibtex
    @inproceedings{dikeoulias-etal-2022-temporal,
        title = "Temporal Knowledge Graph Reasoning with Low-rank and Model-agnostic Representations",
        author = {Dikeoulias, Ioannis and Amin, Saadullah and Neumann, G{\"u}nter},
        booktitle = "Proceedings of the 7th Workshop on Representation Learning for NLP",
        month = may,
        year = "2022",
        address = "Dublin, Ireland",
        publisher = "Association for Computational Linguistics",
        url = "https://aclanthology.org/2022.repl4nlp-1.12",
        doi = "10.18653/v1/2022.repl4nlp-1.12",
        pages = "111--120",
    }
    ```

3. ```bibtex
   @inproceedings{balazevic2019tucker,
      title={TuckER: Tensor Factorization for Knowledge Graph Completion},
      author={Bala\v{z}evi\'c, Ivana and Allen, Carl and Hospedales, Timothy M},
      booktitle={Empirical Methods in Natural Language Processing},
      year={2019}
    }
    ```
