
## Transformer 
是HuggingFace开源的自然语言处理库
- [transformer github](https://github.com/huggingface/transformers)
- [transformer 模型仓库](https://huggingface.co/models?sort=downloads&search=chat) 汇集了大量的训练好的模型，可直接使用。

## AIGC
- [AI聚合网站](https://www.futurepedia.io/)
- [LLM组合构建](https://github.com/hwchase17/langchain)

## ChatGpt
- [ChatGPT使用指南](https://www.yuque.com/tomatosauce/sur15w/goqo7v447fs0kfwa)
- [ChatGPT资源汇总](https://github.com/chenweiphd/ChatGPT-Hub) 
- [开源GPT数据标注项目](https://github.com/LAION-AI/Open-Assistant)
- [开源ChatGpt替代方案-ChatRWKV](https://github.com/BlinkDL/ChatRWKV)
- [开源GPT训练-ColossalAI](https://github.com/hpcaitech/ColossalAI)
- [开源对话式人工智能](https://github.com/LAION-AI/Open-Assistant)
- [Auto-CoT: Automatic Chain of Thought Prompting in Large Language Models (ICLR 2023)](https://github.com/amazon-science/auto-cot)
- [ChatGPT 中文调教指南](https://github.com/PlexPt/awesome-chatgpt-prompts-zh)
- [Prompt engineering 课程](https://learnprompting.org/)

## AI绘图
* [disco-diffusion](https://github.com/alembics/disco-diffusion)
* [visual-chatgpt](https://github.com/microsoft/visual-chatgpt)
* [stable-diffusion](https://github.com/CompVis/stable-diffusion)
    - [sygil Stable Diffusion web UI](https://github.com/Sygil-Dev/sygil-webui)
    - [AUTOMATIC1111/stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
    - [InvokeAI](https://github.com/invoke-ai/InvokeAI)
    - [模型](https://huggingface.co/CompVis/stable-diffusion-v1-4)
    - [提示词参考](https://mpost.io/top-50-text-to-image-prompts-for-ai-art-generators-midjourney-and-dall-e/)

## LLM微调
* LoRA
    - [lora-faster-fine-tuning-of-stable-diffusion](https://replicate.com/blog/lora-faster-fine-tuning-of-stable-diffusion)
    - [github](https://github.com/cloneofsimo/lora)
    - [使用 LoRA 进行 Stable Diffusion 的高效参数微调](https://hub.baai.ac.cn/view/24035)

* Textual Inversion（Embedding 嵌入模型）
* Dreambooth
* Checkpoint Merger（检查点合并）
* Hypernetwork（超网络模型）
* Aesthetic Gradient（审美梯度）

## LLM（大语言模型）
* GPT-3
* BLOOM
    - BigScience发布并开源的自然语言模型
    - [huggingface](https://huggingface.co/bigscience/bloom)
    - [Fast Inference Solutions for BLOOM](https://github.com/huggingface/transformers-bloom-inference)
    - [Text Generation Inference](https://github.com/huggingface/text-generation-inference)
    - [BLOOM C++实现](https://github.com/NouamaneTazi/bloomz.cpp)
* GPT-JT
    - [huggingface](https://huggingface.co/togethercomputer)

* LLaMA-脸书大语言模型
    - [llama github](https://github.com/facebookresearch/llama)
    - [泄漏的模型下载地址](https://github.com/shawwn/llama-dl)
    - [如何在本地Macbook M2搭建](https://til.simonwillison.net/llms/llama-7b-m2)
    - [一键搭建基于llama的chatbot](https://github.com/skypilot-org/skypilot/tree/master/examples/llama-llm-chatbots)
    - [Stanford Alpaca，基于LLaMA-7B 和指令微调，仅使用约 5 万条训练数据，就能达到类似 GPT-3.5的效果](https://github.com/tatsu-lab/stanford_alpaca)
    - [Alpaca-Lora (羊驼-Lora)，使用 Lora (Low-rank Adaptation) 在LLaMA 7B 模型上微调，只需要训练很小一部分参数就可以获得媲美 Standford Alpaca 的效果](https://github.com/tloen/alpaca-lora)
    - [开源中文对话大模型-70亿参数-基于 Stanford Alpaca](https://github.com/LianjiaTech/BELLE)
    - [Chinese-alpaca-lora](https://github.com/LC1332/Chinese-alpaca-lora)
    - [LLaMA C++实现版本](https://github.com/ggerganov/llama.cpp)
* GLM (General Language Model)
    - [GLM](https://github.com/THUDM/GLM)
    - [ChatGLM-6B](https://github.com/THUDM/ChatGLM-6B)
    - [GLM-130B](https://github.com/THUDM/GLM-130B)

* SkyText
    - [huggingface](https://huggingface.co/SkyWork)
    - 昆仑天工发布


## 商业化
* [查看使用GPT3实现的AppDemo](https://gpt3demo.com/)
* [奇点智源API文档](https://openapi.singularity-ai.com/index.html#/documentIndex)

## Reference
* 文档
    - [PyTorch-Transformers:最先进的自然语言处理库](https://www.jianshu.com/p/e4ce00a41781)
    - [昆仑天工](https://mp.weixin.qq.com/s/dSwaBbqy5ZKk6SJIg34eWg)
    - [魔咒百科词典](https://aitag.top/)
    - [civitai](https://civitai.com/)
    - [万字长文讲透 AI 艺术：缘起、意义和未来（下篇）](https://foresightnews.pro/article/detail/19449)
* Paper
    - [Training language models to follow instructions with human feedback](https://arxiv.org/abs/2203.02155)
    - [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/pdf/2201.11903.pdf)
    - [Automatic Chain of Thought Prompting in Large Language Models](https://arxiv.org/abs/2210.03493)
    - [Toolformer: Language Models Can Teach Themselves to Use Tools](https://arxiv.org/pdf/2302.04761.pdf)
    - [Alpaca-Lora 的论文地址](https://arxiv.org/abs/2106.09685)
