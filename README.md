# Teacher's Helper
[AI for Connectivity Hackathon](https://lablab.ai/event/ai-for-connectivity-hackathon) 

[Submission Link](https://lablab.ai/event/ai-for-connectivity-hackathon/teachers-helper/teachers-helper)

## Challenge

Teachers worldwide struggle to find high-quality, relevant teaching resources quickly. In low-resource communities, this challenge is amplified by limited internet access, outdated materials, and fragmented repositories. Educators spend hours curating lesson plans, worksheets, and activities instead of focusing on student engagement and innovation.

## Solution:

Teacher's Helper is a smart, adaptable platform that empowers educators to instantly discover and share teaching resources—whether online or stored locally. Designed for flexibility, it can be deployed in the cloud for schools with reliable internet or installed on-premise in underserved communities, ensuring equitable access to educational materials.

## Presentation:

<div style="display: inline-flex; align-items: center;">
  <!-- Play Button -->
  <a href="https://youtu.be/w7rXye8nTuM" target="_blank" style="display: inline-block;">
    <img src="https://upload.wikimedia.org/wikipedia/commons/b/b8/YouTube_play_button_icon_%282013%E2%80%932017%29.svg" 
         style="width: 50px; height: auto; margin-left: 5px;">
  </a>
</div>

## Technologies Used:

* [Onyx](https://github.com/onyx-dot-app/onyx)
* [docker](https://www.docker.com/)
* [ollama](https://ollama.com/)
* [llama3.2](https://www.llama.com/docs/model-cards-and-prompt-formats/llama3_2/)

## Architecture:

![](https://github.com/Takosaga/teachers_helper/blob/main/Architecture.png)

## Example:

![](https://github.com/Takosaga/teachers_helper/blob/main/bot_example.png)

## Lessons Learned:

### 1. Adapting to Tool Limitations
- **API Integration Challenges**: Learned to work with undocumented APIs by using community resources and trial-and-error experimentation.
- **Hardware Constraints**: Discovered a workaround for AMD GPU limitations (ROCM incompatibility with RX 6700 XT by adjusting HSA_OVERRIDE_GFX_VERSION=10.3.0) with Ollama.

### 2. Model Selection & Trade-offs
- Tested more complex models like `deepseek-r1` but prioritized smaller models (e.g., `llama3.2`) for computational costs, as reasoning may not be needed for educational use cases.
- Balanced model size, latency, and accuracy for resource-constrained environments.

### 3. Deployment Flexibility
- Explored Onyx’s Slack integration as a user-friendly alternative to web deployment, prioritizing accessibility for educators.
- Designed hybrid cloud/on-premise architecture to address low-resource communities’ internet limitations.

### 4. Rapid Prototyping
- Dockerized workflows to streamline setup and iteration during the hackathon.
- Modular design (decoupling RAG from LLM) allowed quick pivots between tools like Onyx and Ollama.

### 5. User-Centric Design
- Simplified outputs (e.g., avoiding markdown in Slack) to reduce cognitive load for teachers.
