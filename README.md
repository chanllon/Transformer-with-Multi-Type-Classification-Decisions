# [Transformer Model with Multi-Type Classification Decisions for Intrusion Attack Detection of Track Traffic and Vehicle]([https://example.com](https://ieeexplore.ieee.org/abstract/document/10447002))


## Drawing

This is the official implementation for our paper KG4Ex: An Explainable Knowledge Graph-Based Approach for Exercise Recommendation, accepted by CIKM'23.

## Requirements

The code is built on Pytorch and the pyKT benchmark library. Run the following code to satisfy the requirements by pip: `pip install -r requirements.txt`

## Datasets

Download the three public datasets we use in the paper at:

- ASSISTments 2009
- Algebra 2005
- Statics 2011

Preprocess the dataset using pyKT to obtain the student's mastery level of knowledge concepts (MLKC), the probability of knowledge concepts appearing in the next exercise (PKC), and the forgetting rate of knowledge concepts (FRKC).

We provide an example of a CSV file obtained after pyKT processing using the Algebra 2005 dataset (top 10 rows), located in `KG4Ex/pyKT_example/Algebra2005_head_10.csv`.

## Run KG4Ex

1. Construct the knowledge graph: use pyKT preprocessed files, for example, Algebra2005_head_10.csv, to construct entities.dict (entity dictionaries), relations.dict (relationship dictionaries), triples.txt (triples required for knowledge graphs) and Q.txt (Q-matrix). Place the three generated files in folder `KG4Ex/data/algebra2005`.

2. Embedding learning: `python run.py --do_train --cuda --data_path ../data/algebra2005 --model TransE -b 1024 -d 1000 -g 12.0 -a 1.0 -lr 0.001 -adv -save models/algebra2005/TransE_adv`.

3. Recommendation and evaluation: the embedding vectors of entities and relations are saved in `KG4Ex/codes/models/algebra2005/TransE_adv`. Run `test_TransE.py` to obtain corresponding indicator results.

## The interpretability of KG4Ex

To validate the interpretability of KG4Ex and the rationality of exercise recommendations, we conducted real interviews with 250 real students. The student interviews were conducted through questionnaire surveys. We are making the questionnaire content public here `questionnaire.txt`.

## Citation

If you find our work helpful, please kindly cite our research paper:





## Citation

If you find our work helpful, please kindly cite our research paper:

@INPROCEEDINGS{10447002,
  author={Guan, Quanlong and Zhang, Tian and Qin, Yu and Zhou, Yuyu and Zhu, Yangguang and Zhong, Yuansheng and Huang, Xiujie and Duan, Zhifei and Li, Zhefu and Liu, Changjiang and Wu, Xiaofeng},
  booktitle={ICASSP 2024 - 2024 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)}, 
  title={Transformer Model with Multi-Type Classification Decisions for Intrusion Attack Detection of Track Traffic and Vehicle}, 
  year={2024},
  volume={},
  number={},
  pages={4510-4514},
  keywords={Dimensionality reduction;Neural networks;Intrusion detection;Signal processing;Transformers;Data models;Security;Vehicle intrusion detection;Temporal attributes;Transformer;Multi-head Self-attention;Track traffic},
  doi={10.1109/ICASSP48485.2024.10447002}}
