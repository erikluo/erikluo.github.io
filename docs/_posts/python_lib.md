## Python Libs
* Flask
* Numpy
* Transformer
* Gradio
    - [github](https://github.com/gradio-app/gradio)
    - [site](https://www.gradio.app/)
    - [create a chatbot](https://gradio.app/creating-a-chatbot/)
    - [mounting-within-another-fastapi-app](https://gradio.app/sharing-your-app/#mounting-within-another-fastapi-app)
    - [theming-guide](https://gradio.app/theming-guide/)
    - [gradio-tutorial](https://www.machinelearningnuggets.com/gradio-tutorial/)
    - [gradio-nginx-conf](https://huggingface.co/spaces/radames/nginx-gradio-reverse-proxy/blob/main/nginx.conf)
    - [gradio 嵌入到html中](https://gradio.app/sharing-your-app/#embedding-hosted-spaces)

## 关于Gradio实现流式输出的几种方法：
* Interface
    - live=true
* Block
    - load函数定时输出
    - submit/click 函数的回调函数返回yield类型时，自动转化为流式。
* Chatbot
     - [create a chatbot](https://gradio.app/creating-a-chatbot/)
   
