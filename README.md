# 🔥Flames: Benchmarking Value Alignment of Chinese Large Language Models


Flames is a highly adversarial benchmark in Chinese for LLM's harmlessness evaluation developed by Shanghai AI Lab and Fudan NLP Group. It contains:

* **a highly adversarial prompts set**: we meticulously a dataset of 2,251 highly adversarial, manually crafted prompts, each tailored to probe a specific value dimension (i.e., Fairness, Safety, Virtue, Legality, Data protection). Currently, we release 1,000 prompts for public use (**Flames-1k-Chinese**).
* **a human annotation set**: for each prompt, we provide 12 LLMs' responses with fine-grained human annotation of harmlessness score. This can be used for finetuning as well as reward modeling.
* **a specified scorer**: based on our annotation, we train a specified scorer to easily grade the responses. (Coming soon)

For detailed information, please refer to our paper. [arxiv link]

## 🔍 Table of Contents

[🏆 Leaderboard](README.md)

[📊 Dataset](README.md)

[💯 Scorer API](README.md)

[©️ Citation](README.md)

## 🏆 Leaderboard

Below are the evaluation results of the **Harmless rate / Harmless score** for representative LLMs. **Blod** indicates the best.

| Model         | Overall               | Fairness                      | Safety                         | Morality                        | Legality                       | Data protection                |
| ---------     | --------------------- | ----------------------------- | ------------------------------ | ------------------------------- | ------------------------------ | ------------------------------ |
| ChatGPT       | 46.85%                | 45.6% / 79.9                  | 45.48% / 74.1                  | 42.57% / 76.7                   | 45.65% / 63.8                  | 54.93% / 70.0                  |
| GPT-4         | 39.04%                | 41.6% / 78.3                  | 27.61% / 67.7                  |  50.5% / 80.5                   | 30.43% / 54.3                  | 45.07% / 63.4                  |
| Claude        | **63.08%**            | **53.6%** / 83.5              | 28.31% / 65.4                  | **77.23% / 91.6**               | 71.74% / 81.2                  | **84.51% / 89.7**              |
| Minimax       | 23.51%                | 24.4% / 69.9                  |  18.1% / 59.2                  | 27.72% / 70.5                   | 30.43% / 53.6                  | 16.9% / 44.6                  |
| Ernet Bot     | 44.89%                | 43.2% / 78.9                  | 32.02% / 69.1                  | 47.52% / 78.1                   | 60.87% / 73.9                  | 40.85% / 60.6                  |
| BELLE-13B     | 24.24%                | 22.0% / 68.4                  | 15.31% / 57.8                  | 20.79% / 66.5                   | 39.13% / 59.4                  | 23.94% / 49.3                  |
| ChatGLM-6B    | 33.48%                | 26.8% / 72.3                  | 15.31% / 60.3                  |  40.1% / 75.6                   |  50.0% / 66.7                  | 35.21% / 56.8                  |
| ChatGLM2-6B   | 32.46%                | 31.6% / 74.1                  | 22.74% / 64.3                  | 43.07% / 75.7                   | 28.26% / 52.2                  | 36.62% / 57.7                  |
| ChatYuan-770M | 41.36%                | 28.4% / 72.4                  | **54.52%** / 78.8              |  30.2% / 71.0                   |  50.0% / 66.7                  | 43.66% / 62.4                  |
| MOSS-16B      | 35.99%                | 33.2% / 74.5                  | 33.18% / 70.5                  | 31.19% / 71.0                   |  50.0% / 66.7                  | 32.39% / 54.9                  |
| InternLM-7B   | 52.51%                | 44.8% / 78.1                  | 35.73% / 69.1                  | 50.99% / 80.2                   | **76.09% / 84.1**              | 54.93% / 70.0                  |
| InternLM-20B  | 58.26%                | 52.8% / **83.6**              | 50.81% / **79.0**               | 53.96% / 81.4                   | 71.74% / 81.2                  | 61.97% / 74.6                  |


Last update: Nov. 8th 2023

## 📊 Dataset

### Why 🔥Flames?

|      Dataset    | # Prompts | % Successful attack | Human annotation | Specified scorer |
| --------------- | --------- | --------- | ------------------- | ----------------- |
| [Safety-prompts](https://github.com/thu-coai/Safety-Prompts)  | 100k   | 1.63%              |  &#10005;                |   &#10005;          |
| [CValues](https://github.com/X-PLUG/CValues)  |  2100       |  3.1%              |  &#10005;                |   &#10003;          |
| Flames (ours)   |  2,251     |  53.15%             |  &#10003;              |   &#10003;          |

### Statistics

The statistics of released Flames-1k-Chinese is shown below:

| Attribute       | Prompts |
| --------------- | ------- |
| Fairness        | 250     |
| Safety          | 431     |
| Morality          | 202     |
| Legality        | 46      |
| Data protection | 71     |
| Overall         | 1,000    |

### Examples

Below are examples of prompt-response-label from 5 dimensions (i.e. Fairness, Safety, Morality, Legality, and Data protection).

![example](images/example.jpg)

### Usage

We currently release **Flames-1k-Chinese** which includes 1,000 highly adversarial prompts. 

## 💯 Scorer

### Training
We employ a pre-trained language model as the backbone and build separate classifiers for each dimension on top of it. Then, we apply a multi-task training approach to train the scorer. The backbone uses the Chinese-RoBERTa-WWM-EXT model which is a Chinese version of the RoBERTa model based on transformer encoder architecture. We trained different scorers on the base (∼110M parameters) and large-size (∼330M parameters) models.

## ©️ Citation

If you think this dataset is helpful for your work or use it in your research, please cite the paper.

```bibtex
@article{Flames,
      title={Flames: Benchmarking Value Alignment of Chinese Large Language Models}, 
      author={ Kexin Huang and Xiangyang Liu and Qianyu Guo and Tianxiang Sun and Jiawei Sun and Yaru Wang and Zeyang Zhou and Yixu Wang and Xipeng Qiu and Yingchun Wang and Dahua Lin and Yan Teng},
      journal={arXiv preprint arXiv:},
      year={2023}
}
```

<!--<h2>License</h2>-->
