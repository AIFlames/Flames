# 🔥FLAMES: Benchmarking Value Alignment of LLMs in Chinese
🎉 **[2024-05-22] News: Flames is now available on [OpenCompass!](https://flames.opencompass.org.cn/leaderboard)**  
🎉 **[2024-03-13] News: We have been accepted to the NAACL 2024 Main Conference!**

Flames is a highly adversarial benchmark in Chinese for LLM's value alignment evaluation developed by Shanghai AI Lab and Fudan NLP Group. We offer:

* **a highly adversarial prompts set**: we meticulously design a dataset of 2,251 highly adversarial, manually crafted prompts, each tailored to probe a specific value dimension (i.e., Fairness, Safety, Morality, Legality, Data protection). Currently, we release 1,000 prompts for public use (**Flames_1k_Chinese**).
* **a specified scorer**: based on our annotation, we train a specified scorer to easily grade the responses (available at [Huggingface](https://huggingface.co/CaasiHUANG/flames-scorer)).

For detailed information, please refer to our paper: [FLAMES: Benchmarking Value Alignment of LLMs in Chinese](https://arxiv.org/abs/2311.06899)

## 🔍 Table of Contents

[🏆 Leaderboard](README.md)

[📊 Dataset](README.md)

[💯 Scorer](README.md)

[©️ Citation](README.md)

## 🏆 Leaderboard

Below are the evaluation results of the **Harmless rate / Harmless score** for representative LLMs. **Blod** indicates the best.


| Model           | Overall   | Fairness                   | Safety                     | Morality                   | Legality                   | Data protection             |
|-----------------|-----------|----------------------------|----------------------------|----------------------------|----------------------------|-----------------------------|
| ChatGPT         | 46.91%    | 45.38% / 79.8              | 45.45% / 74.1              | 42.79% / 76.8              | 45.65% / 63.8              | 55.26% / 70.2               |
| GPT-4           | 40.01%    | 41.37% / 78.2              | 27.51% / 67.7              | 50.75% / 80.6              | 30.43% / 53.6              | 50.0% / 66.7                |
| Claude          | **63.77%**| **53.41%** / 83.4          | 28.44% / 65.5              | **77.11%** / **91.5**      | 71.74% / 81.2              | **88.16%** / **92.1**       |
| Minimax         | 23.66%    | 24.5% / 69.9               | 18.41% / 59.6              | 27.86% / 70.5              | 30.43% / 53.6              | 17.11% / 44.7               |
| Ernie Bot       | 45.96%    | 42.97% / 78.8              | 32.17% / 69.2              | 47.76% / 78.1              | 60.87% / 73.9              | 46.05% / 64.0               |
| InternLM-20B    | 58.56%    | 52.61% / 83.5              | 51.05% / 79.2              | 54.23% / 81.4              | 71.74% / 81.2              | 63.16% / 75.4               |
| MOSS-16B        | 36.18%    | 33.33% / 74.6              | 33.33% / 70.6              | 31.34% / 71.0              | 50.0% / 66.7               | 32.89% / 55.3               |
| Qwen-14B        | 41.97%    | 30.92% / 72.2              | 36.83% / 74.7              | 54.23% / 82.3              | 32.61% / 55.1              | 55.26% / 70.2               |
| Baichuan2-13B   | 43.16%    | 38.55% / 76.4              | 53.85% / 81.7              | 44.78% / 77.9              | 39.13% / 59.4              | 39.47% / 59.6               |
| BELLE-13B       | 24.76%    | 22.09% / 68.4              | 15.38% / 57.8              | 20.9% / 66.5               | 39.13% / 59.4              | 26.32% / 50.9               |
| InternLM-7B     | 53.93%    | 44.58% / 78.0              | 35.9% / 69.1               | 51.24% / 80.3              | **76.09%** / **84.1**      | 61.84% / 74.6               |
| Qwen-7B         | 36.45%    | 36.14% / 77.2              | 31.93% / 69.2              | 40.3% / 76.1               | 30.43% / 53.6              | 43.42% / 62.3               |
| Baichuan2-7B    | 46.17%    | 42.17% / 79.4              | **56.41%** / 81.6          | 39.3% / 76.0               | 52.17% / 68.1              | 40.79% / 60.5               |
| ChatGLM-6B      | 33.1%     | 26.91% / 72.3              | 15.38% / 60.4              | 40.3% / 75.6               | 50.0% / 66.7               | 32.89% / 55.3               |
| ChatGLM2-6B     | 33.86%    | 31.73% / 74.2              | 22.61% / 64.3              | 43.28% / 75.8              | 28.26% / 52.2              | 43.42% / 62.3               |
| ChatGLM3-6B     | 36.32%    | 37.75% / 77.8              | 32.63% / 70.0              | 44.78% / 77.1              | 28.26% / 52.2              | 38.16% / 58.8               |
| ChatYuan-770M   | 41.07%    | 28.11% / 72.3              | 54.78% / 79.1              | 30.35% / 71.0              | 50.0% / 66.7                | 42.11% / 61.4              |








Last update: Dec. 11th 2023

## 📊 Dataset

### Why 🔥Flames?

|      Dataset    | # Prompts | % Successful attack | Human annotation | Specified scorer |
| --------------- | --------- | --------- | ------------------- | ----------------- |
| [Safety-prompts](https://github.com/thu-coai/Safety-Prompts)  | 100k   | 1.63%              |  &#10005;                |   &#10005;          |
| [CValues](https://github.com/X-PLUG/CValues)  |  2,100       |  3.1%              |  &#10005;                |   &#10003;          |
| **Flames (ours)**   |  2,251     |  **53.09%**             |  &#10003;              |   &#10003;          |

### Statistics

The statistics of released Flames-1k-Chinese is shown below:

| Attribute       | Prompts |
| --------------- | ------- |
| Fairness        | 249     |
| Safety          | 429     |
| Morality          | 201     |
| Legality        | 46      |
| Data protection | 75     |
| **Overall**         | 1,000    |

### Examples

Below are examples of prompt-response-label from 5 dimensions (i.e. Fairness, Safety, Morality, Legality, and Data protection).

![example](images/example.jpg)

### Usage

We currently release **Flames-1k-Chinese** which includes 1,000 highly adversarial prompts. 

## 💯 Scorer
The Flames-scorer is now available at [huggingface](https://huggingface.co/CaasiHUANG/flames-scorer).

The environment can be set up as:
```shell
$ pip install -r requirements.txt
```
And you can use `infer.py` to evaluate your model:
```shell
python infer.py --data_path YOUR_DATA_FILE.jsonl
```
Please note that:
1. Ensure each entry in `YOUR_DATA_FILE.jsonl` includes the fields: "dimension", "prompt", and "response".
2. The predicted score will be stored in the "predicted" field, and the output will be saved in the same directory as `YOUR_DATA_FILE.jsonl`.
3. The accuracy of the Flames-scorer on out-of-distribution prompts (i.e., prompts not included in the Flames-prompts) has not been evaluated. Consequently, its predictions for such data may not be reliable.
## ©️ Citation

If you think this dataset is helpful, please cite the paper.

```bibtex
@misc{huang2023flames,
      title={Flames: Benchmarking Value Alignment of Chinese Large Language Models}, 
      author={Kexin Huang and Xiangyang Liu and Qianyu Guo and Tianxiang Sun and Jiawei Sun and Yaru Wang and Zeyang Zhou and Yixu Wang and Yan Teng and Xipeng Qiu and Yingchun Wang and Dahua Lin},
      year={2023},
      eprint={2311.06899},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

<!--<h2>License</h2>-->
