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

| Model     | Overall               | Safety                        | Fairness                        | Virtue                    | Data protection                  | Legality                        |
| --------- | --------------------- | ----------------------------- | ------------------------------- | ------------------------- | -------------------------------- | ------------------------------- |
| Minimax   | 49.73%                | 38.67% / 71.3                 | 52.00% /  77.7                 | 68.00% /  85.2           | 56.00% /  67.0                  | 37.00% /  50.5                 |
| Ernie Bot | 56.53%                | 41.33% / 80.3                 | 57.33% /  80.3                 | 66.00% /  84.2           | 66.00% /  74.5                  | 52.00% /  64.0                 |
| Claude    | 42.67%                | 26.00% / 74.7                 | 37.33% /  66.0                 | **76.00% /  90.8** | 54.00% /  65.5                  | 20.00% /  40.0                 |
| BELLE     | 54.13%                | 49.33% / 75.8                 | 57.33% /  79.3                 | 62.00% /  85.2           | 56.00% /  67.0                  | 46.00% /  59.5                 |
| ChatYuan  | `<u>`63.60%`</u>` | `<u>`57.33% / 80.7 `</u>` | **66.67% / 85.3**        | 70.00% /  86.7            | 64.00% /73.0                     | **60.00% /  70.0**       |
| LLMzoo    | 57.60%                | 53.33% / 78.2                 | 58.67%  / 81.0                 | 66.00% /  85.2           | 58.00% /  68.5                  | `<u>`52.00% /  64.0 `</u>` |
| ChatGLM   | 57.60%                | 40.67% / 71.8                 | 57.33% /  81.0                 | 68.00% /  86.2           | `<u>`70.00%  /  77.5 `</u>` | `<u>`52.00% /  64.0 `</u>` |
| MOSS      | **64.80%**      | **58.67% / 81.0**       | `<u>`65.33% /  83.6 `</u>` | `<u>`74.00% /  89.8/u> | **76.00% /  82.0**        | 50.00% /  62.5                 |
| ChatGPT   | 44.00%                | 26.67% / 64.8                 | 37.33% /  70.0                 | 66.00% /  84.7           | 60.00% /  70.0                  | 30.00% /  47.5                 |
| GPT-4     | 53.99%                | 43.33% / 74.0                 | 50.67% /  80.0                 | 72.00% /  87.8           | 68.00% /  76.0                  | 36.00% /  52.0                 |

Last update: Oct. 18th 2023

## 📊 Dataset

### Why 🔥Flames?

|      Dataset    | Dimension | # Prompts | % Successful attack | # Response/prompt | Response Annotation |
| --------------- | --------- | --------- | ------------------- | ----------------- | ------------------- |
| COLD            | 1         | 37,480    |  -                  |  -                |   &#10003;          |
| Safety-prompts  | 7         | 70k       |  1.63%              |  1                |   &#10005;          |
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
