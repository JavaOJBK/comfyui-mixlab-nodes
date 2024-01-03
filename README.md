> 适配了最新版comfyui的py3.11 ，torch 2.1.2+cu121

## 🚀🚗🚚🏃 Workflow-to-APP 
- 新增AppInfo节点，可以通过简单的配置，把workflow转变为一个Web APP。
- 支持多个web app 切换
- 发布为app的workflow，可以在右键里再次编辑了
- web app可以设置分类，在comfyui右键菜单可以编辑更新web app


- Support multiple web app switching.
- Add the AppInfo node, which allows you to transform the workflow into a web app by simple configuration.
- The workflow, which is now released as an app, can also be edited again by right-clicking.
- The web app can be configured with categories, and the web app can be edited and updated in the right-click menu of ComfyUI.


![](./assets/0-m-app.png)

![](./assets/appinfo-readme.png)

![](./assets/appinfo-2.png)

Example:
- workflow
![APP info](./workflow/appinfo-workflow.svg)
[text-to-image](./workflow/Text-to-Image-app.json)

APP-JSON:
- [text-to-image](./example/Text-to-Image_3.json)
- [image-to-image](./example/Image-to-Image_2.json)
- text-to-text

> 暂时支持8种节点作为界面上的输入节点：Load Image、CLIPTextEncode、PromptSlide、TextInput_、Color、FloatSlider、IntNumber、CheckpointLoaderSimple、LoraLoader

> 输出节点：PreviewImage 、SaveImage、ShowTextForGPT、VHS_VideoCombine


## 🏃🚗🚚🚀  Real-time Design
> ScreenShareNode & FloatingVideoNode. Now comfyui supports capturing screen pixel streams from any software and can be used for LCM-Lora integration. Let's get started with implementation and design! 💻🌐

![screenshare](./assets/screenshare.png)

https://github.com/shadowcz007/comfyui-mixlab-nodes/assets/12645064/e7e77f90-e43e-410a-ab3a-1952b7b4e7da


<!-- [ScreenShareNode](./workflow/2-screeshare.json) -->
[ScreenShareNode & FloatingVideoNode](./workflow/3-FloatVideo-workflow.json)

!! Please use the address with HTTPS (https://127.0.0.1).


### SpeechRecognition & SpeechSynthesis
![f](./assets/audio-workflow.svg)

[Voice + Real-time Face Swap Workflow](./workflow/语音+实时换脸workflow.json)

### GPT
> Support for calling multiple GPTs.ChatGPT、ChatGLM3 , Some code provided by rui. If you are using OpenAI's service, fill in https://api.openai.com/v1 . If you are using a local LLM service, fill in http://127.0.0.1:xxxx/v1 .  Azure OpenAI:https://xxxx.openai.azure.com 

![gpt-workflow.svg](./assets/gpt-workflow.svg)

[workflow-5](./workflow/5-gpt-workflow.json)


## Prompt
> PromptSlide
![](./assets/prompt_weight.png)

![](./workflow/promptslide-appinfo-workflow.svg)

> randomPrompt

![randomPrompt](./assets/randomPrompt.png)


### Layers
> A new layer class node has been added, allowing you to separate the image into layers. After merging the images, you can input the controlnet for further processing.

![layers](./assets/layers-workflow.svg)

![poster](./assets/poster-workflow.svg)


### 3D
![](./assets/3dimage.png)
[workflow](./workflow/3D-workflow.json)


### LoadImagesFromLocal
> Monitor changes to images in a local folder, and trigger real-time execution of workflows, supporting common image formats, especially PSD format, in conjunction with Photoshop. 

![watch](./assets/4-loadfromlocal-watcher-workflow.svg)

[workflow-4](./workflow/4-loadfromlocal-watcher-workflow.json)

### LoadImagesFromURL
> Conveniently load images from a fixed address on the internet to ensure that default images in the workflow can be executed.


## Utils
> The Color node provides a color picker for easy color selection, the Font node offers built-in font selection for use with TextImage to generate text images, and the DynamicDelayByText node allows delayed execution based on the length of the input text.

- [添加了DynamicDelayByText功能，可以根据输入文本的长度进行延迟执行。](./workflow/audio-chatgpt-workflow.json)

- [Added DynamicDelayByText, enabling delayed execution based on input text length.](./workflow/audio-chatgpt-workflow.json)


## Other Nodes

![main](./assets/all-workflow.svg)
![main2](./assets/detect-face-all.png)

[workflow-1](./workflow/1-workflow.json)



> TransparentImage

![TransparentImage](./assets/TransparentImage.png)


> Consistency Decoder

[openai Consistency Decoder]( https://github.com/openai/consistencydecoder)

![Consistency](./assets/consistency.png)
After downloading the OpenAI VAE model, place it in the "model/vae" directory for use.
https://openaipublic.azureedge.net/diff-vae/c9cebd3132dd9c42936d803e33424145a748843c8f716c0814838bdc8a2fe7cb/decoder.pt


> FeatheredMask、SmoothMask

Add edges to an image.

![FeatheredMask](./assets/FlVou_Y6kaGWYoEj1Tn0aTd4AjMI.jpg)


> LaMaInpainting

from [simple-lama-inpainting](https://github.com/enesmsahin/simple-lama-inpainting)


### Improvement 

- Add "help" option to the context menu for each node.
- Add "Nodes Map" option to the global context menu.

An improvement has been made to directly redirect to GitHub to search for missing nodes when loading the graph.

![help](./assets/help.png)

![node-not-found](./assets/node-not-found.png)


### Update 
v0.8.0 🚀🚗🚚🏃‍ LaMaInpainting
- 新增 LaMaInpainting
- 优化color节点的输出
- 修复高清显示屏上定位节点不准的情况

- Add LaMaInpainting
- Optimize the output of the color node
- Fix the issue of inaccurate positioning node on high-definition display screens


### Models
[Download CLIPSeg](https://huggingface.co/CIDAS/clipseg-rd64-refined/tree/main), move to : models/clipseg


<!-- ### Workflow
[Workflow](./workflow.md) -->


## Installation

manually install, simply clone the repo into the custom_nodes directory with this command:

```
cd ComfyUI/custom_nodes

git clone https://github.com/shadowcz007/comfyui-mixlab-nodes.git

```

Install the requirements:

run directly:
```
cd ComfyUI/custom_nodes/comfyui-mixlab-nodes
install.bat
```

or install the requirements using:
```
../../../python_embeded/python.exe -s -m pip install -r requirements.txt
```

If you are using a venv, make sure you have it activated before installation and use:
```
pip3 install -r requirements.txt
```

#### Chinese community
访问 [www.mixcomfy.com](https://www.mixcomfy.com)，获得更多内测功能，关注微信公众号：Mixlab无界社区


#### Thanks:
[ComfyUI-CLIPSeg](https://github.com/biegert/ComfyUI-CLIPSeg/tree/main)

#### discussions:
[discussions](https://github.com/shadowcz007/comfyui-mixlab-nodes/discussions)

### TODO:
- 音频播放节点：带可视化、支持多音轨、可配置音轨音量
- vector https://github.com/GeorgLegato/stable-diffusion-webui-vectorstudio


<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="
      https://api.star-history.com/svg?repos=shadowcz007/comfyui-mixlab-nodes&type=Date&theme=dark
    "
  />
  <source
    media="(prefers-color-scheme: light)"
    srcset="
      https://api.star-history.com/svg?repos=shadowcz007/comfyui-mixlab-nodes&type=Date
    "
  />
  <img
    alt="Star History Chart"
    src="https://api.star-history.com/svg?repos=shadowcz007/comfyui-mixlab-nodes&type=Date"
  />
</picture>

