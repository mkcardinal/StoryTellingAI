# AI_StoryTeller

Story narration using an AI chatbot with memory and vocal narration capability.

## Description

This application implements storytelling using generative AI.
A stable difussion server communicates with the backend via websockets to receives images
encoded as binary packets which are then sent via websockets to the frontend. Vocal narration is added using Piper and 
an agentic AI with memory is used for a customized chatbot.


# Configuration

1. Install Comfyui server and download darksushimix stable diffusion model.
   ```
   wget https://civitai.com/api/download/models/56071
   ```
2. Start Comfyui server and confirm by opening http://127.0.0.1:8188
3. Install Ollama and llama3.1 or mistral/phi3.
   
  ```
  ollama run llama3.1
  ollama run phi3
  ollama run mistral
  ```
Edit the selected model under langgraph_agent.py

4. Install app requirements

  Install Pytorch with GPU support. This depends on the type of graphic card on the system (Nvidia / AMD ).
 
  ```
  conda activate aistory
  pip3 install -r requirements.txt
  pip3 install --upgrade requests
  pip3 install numexpr
  pip3 install piper-tts
  python main.py 
  python3 main.py  --disable-smart-memory --listen 0.0.0.0  #alternate options for starting ComfyUI
  ```

5. Start fastapi server

```
python app.py
```

6. Linux version supports voice narration while Windows does not.



