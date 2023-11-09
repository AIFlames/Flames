# 🔥Flames: Highly Adversarial Benchmark for LLM's Harmlessness Evaluation

// +++++ 中文版本/论文地址/Scorer API地址

Flames is a highly adversarial benchmark in Chinese for LLM's harmlessness evaluation developed by Shanghai AI Lab and Fudan NLP Group. It contains:

* **a highly adversarial prompts set**: we design a comprehensive framework for harmlessness evaluation, which includes **Fairness, Safety, Virtue, Legality, Data protection** and fine-grained subcomponents. We construct our highly adversarial prompts set based on this framework. Currently, we release **Flames-1k-Chinese** for public use. English ver. is coming soon.
* **a human annotation set**: for each prompt, we provide **10 LLMs' responses with fine-grained human annotation** of harmlessness score. This can be used for finetuning as well as reward modelling.
* **a specified scorer**: based on our annotation, we train a specified scorer to easily grade the responses. We release our scorer API for dev test.

For detailed information, please refer to our paper. [arxiv link]

## 🔍 Table of Contents

[🏆 Leaderboard](README.md)

[📊 Dataset](README.md)

[💯 Scorer API](README.md)

[©️ Citation](README.md)

## 🏆 Leaderboard

Below are the evaluation results of the **Harmless rate / Harmless score** for representative LLMs. **Blod** indicates the best and underline indicates the second.

| Model         | Overall               | Fairness                      | Safety                         | Morality                        | Legality                       | Data protection                |
| ---------     | --------------------- | ----------------------------- | ------------------------------ | ------------------------------- | ------------------------------ | ------------------------------ |
| ChatGPT       | 46.85%                | 45.6% / 79.9                  | 45.48% / 74.1                  | 42.57% / 76.7                   | 45.65% / 63.8                  | 54.93% / 70.0                  |
| GPT-4         | 39.04%                | 41.6% / 78.3                  | 27.61% / 67.7                  |  50.5% / 80.5                   | 30.43% / 54.3                  | 45.07% / 63.4                  |
| Claude        | **63.08%**            | **53.6% / 83.5**              | 28.31% / 65.4                  | **77.23% / 91.6**               | <u>71.74% / 81.2</u>           | **84.51% / 89.7**              |
| Minimax       | 23.51%                | 24.4% / 69.9                  |  18.1% / 59.2                  | 27.72% / 70.5                   | 30.43% / 53.6                  |  16.9% / 44.6                  |
| Ernet Bot     | 44.89%                | 43.2% / 78.9                  | 32.02% / 69.1                  | 47.52% / 78.1                   | 60.87% / 73.9                  | 40.85% / 60.6                  |
| BELLE-13B     | 24.24%                | 22.0% / 68.4                  | 15.31% / 57.8                  | 20.79% / 66.5                   | 39.13% / 59.4                  | 23.94% / 49.3                  |
| ChatGLM-6B    | 33.48%                | 26.8% / 72.3                  | 15.31% / 60.3                  |  40.1% / 75.6                   |  50.0% / 66.7                  | 35.21% / 56.8                  |
| ChatGLM2-6B   | 32.46%                | 31.6% / 74.1                  | 22.74% / 64.3                  | 43.07% / 75.7                   | 28.26% / 52.2                  | 36.62% / 57.7                  |
| ChatYuan-770M | 41.36%                | 28.4% / 72.4                  | **54.52% / 78.8**              |  30.2% / 71.0                   |  50.0% / 66.7                  | 43.66% / 62.4                  |
| MOSS-7B       | 35.99%                | 33.2% / 74.5                  | 33.18% / 70.5                  | 31.19% / 71.0                   |  50.0% / 66.7                  | 32.39% / 54.9                  |
| InternLM-7B   | 52.51%                | 44.8% / 78.1                  | 35.73% / 69.1                  | 50.99% / 80.2                   | **76.09% / 84.1**              | 54.93% / 70.0                  |
| InternLM-20B  | `<u>`58.26%`</u>`     | `<u>`52.8% / 83.6`</u>`       | `<u>`50.81% / 79.0`</u>`       | `<u>`53.96% / 81.4`</u>`        | `<u>`71.74% / 81.2`</u>`       | `<u>`61.97% / 74.6`</u>`       |



Last update: Oct. 18th 2023

## 📊 Dataset

### Why 🔥Flames?

|      Dataset    | Dimension | # Prompts | % Successful attack | # Response/prompt | Response Annotation |
| --------------- | --------- | --------- | ------------------- | ----------------- | ------------------- |
| [COLD](https://github.com/thu-coai/COLDataset)           | 1         | 37,480    |  -                  |  -                |   &#10003;          |
| [Safety-prompts](https://github.com/thu-coai/Safety-Prompts)  | 7         | 70k       |  1.63%              |  1                |   &#10005;          |
| Flames (ours)   | 12        | 2,251     |  56.00%             |  10               |   &#10003;          |

### Statistics

The statistics of released Flames-1k-Chinese is shown below:

| Attribute       | Prompts |
| --------------- | ------- |
| Fairness        | 200     |
| Safety          | 400     |
| Virtue          | 200     |
| Legality        | 50      |
| Data protection | 150     |
| Overall         | 1000    |

### Examples

Below are examples of prompt-response-label from 5 dimensions (i.e. Fairness, Safety, Virtue, Legality, and Data protection).

![example](images/flames-example-ch.png)

### Usage

The annotation set (prompts included) has been uploaded to this respository, which can be found in 'data/flames_public.json' (add link)

## 💯 Scorer API

@lxy

## ©️ Citation

If you think this dataset is helpful for your work or use it in your research, please cite the paper.

```bibtex
@article{VAEC,
      title={Towards Value Alignment Evaluation in Chinese: VAEC Benchmark for Large Language Models}, 
      author={Qianyu Guo and Kexin Huang and Xiangyang Liu and Tianxiang Sun and Jiawei Sun and Yaru Wang and Zeyang Zhou and Xipeng Qiu and Yingchun Wang and Dahua Lin and Yan Teng},
      journal={arXiv preprint arXiv:},
      year={2023}
}
```

<!--<h2>License</h2>-->
