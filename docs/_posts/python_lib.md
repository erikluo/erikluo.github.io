## Python Libs
* Flask
* Numpy
* Transformer

### 低代码
* Gradio
    - [github](https://github.com/gradio-app/gradio)
    - [site](https://www.gradio.app/)
    - [create a chatbot](https://gradio.app/creating-a-chatbot/)
    - [mounting-within-another-fastapi-app](https://gradio.app/sharing-your-app/#mounting-within-another-fastapi-app)
    - [theming-guide](https://gradio.app/theming-guide/)
    - [gradio-tutorial](https://www.machinelearningnuggets.com/gradio-tutorial/)
    - [gradio-nginx-conf](https://huggingface.co/spaces/radames/nginx-gradio-reverse-proxy/blob/main/nginx.conf)
    - [gradio 嵌入到html中](https://gradio.app/sharing-your-app/#embedding-hosted-spaces)
    - [在gradio中嵌入html+js](https://discuss.huggingface.co/t/gradio-html-component-with-javascript-code-dont-work/37316)

* Streamlit
    - [streamlit github](https://github.com/streamlit/streamlit)
 
* Wooey
    - [Wooey](https://github.com/wooey/Wooey)
    - [Wooey实践 用腾讯云 AI 语音合成打造有声书制作工具](https://cloud.tencent.com/document/product/1073/79142)

## 关于Gradio实现流式输出的几种方法：
* Interface
    - live=true
* Block
    - load函数定时输出
    - submit/click 函数的回调函数返回yield类型时，自动转化为流式。
* Chatbot
     - [create a chatbot](https://gradio.app/creating-a-chatbot/)
   
