<h1 align="center">🧠 Multi-Tool Visual Reasoning Agent</h1>

<p align="center" style="color:#555; font-size:16px;">
  A unified AI system that performs <strong>Object Detection</strong>, <strong>OCR</strong>, 
  and <strong>Image Captioning</strong>, and then synthesizes all outputs into one 
  human-friendly response using a lightweight reasoning module.
  <br><br>
  Built using <strong>HuggingFace Transformers</strong>, <strong>EasyOCR</strong>,
  and <strong>PyTorch</strong>.  
  Designed for multi-image queries, visual QA, and advanced scene understanding.
</p>

---

<h4 align="center">Core Technology Stack</h4>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11-blue?style=flat&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/HuggingFace-Transformers-ffcc4d?style=flat&logo=huggingface&logoColor=white" />
  <img src="https://img.shields.io/badge/DETR-Object%20Detection-orange?style=flat" />
  <img src="https://img.shields.io/badge/EasyOCR-Text%20Extraction-blueviolet?style=flat" />
  <img src="https://img.shields.io/badge/PyTorch-Vision%20Models-ee4c2c?style=flat&logo=pytorch&logoColor=white" />
</p>

---

<h2 align="center">📌 Table of Contents</h2>

<ul style="list-style:none; text-align:center; line-height:1.9; font-size:16px;">
  <li>🧠 <a href="#overview">Project Overview</a></li>
  <li>🎯 <a href="#objectives">Core Objectives</a></li>
  <li>🛠️ <a href="#architecture">System Architecture</a></li>
  <li>🖼️ <a href="#features">Key Features</a></li>
  <li>🧪 <a href="#workflow">Workflow</a></li>
  <li>📊 <a href="#examples">Visual Examples</a></li>
  <li>⚙️ <a href="#install">Installation</a></li>
  <li>🤝 <a href="#contribute">Contribution</a></li>
  <li>📜 <a href="#license">License</a></li>
</ul>

---

<h2 id="overview" align="center">🧠 Project Overview</h2>

<p>
The <strong>Multi-Tool Visual Reasoning Agent</strong> is a modular AI system that processes images using multiple computer vision tools and automatically decides:
</p>

<ul>
  <li>When to run object detection</li>
  <li>When to extract text using OCR</li>
  <li>When to generate a caption</li>
  <li>How to combine all outputs into one meaningful response</li>
</ul>

<p>
This system mimics the behavior of modern multi-modal agents (e.g., GPT-Vision), but implemented using open-source models and a lightweight reasoning module.
</p>

---

<h2 id="objectives" align="center">🎯 Core Objectives</h2>

<ul>
  <li>Provide a unified pipeline for object detection, OCR, and captioning</li>
  <li>Automatically select the appropriate tools based on the user query</li>
  <li>Support multi-image queries and batch reasoning</li>
  <li>Generate concise, natural-language answers</li>
  <li>Produce annotated visual outputs</li>
</ul>

---

<h2 id="architecture" align="center">🛠️ System Architecture</h2>

<ul>
  <li><strong>DETR (facebook/detr-resnet-50)</strong> → Object detection</li>
  <li><strong>EasyOCR</strong> → Text extraction from regions of interest</li>
  <li><strong>BLIP / Vit-GPT2</strong> → Image captioning</li>
  <li><strong>Planner Module</strong> → Simple rule-based or LLM-based tool selector</li>
  <li><strong>Reasoning Layer</strong> → Synthesizes detection + OCR + captions</li>
  <li><strong>Visualization Layer</strong> → Annotated image outputs</li>
</ul>

---

<h2 id="features" align="center">🖼️ Key Features</h2>

<ul>
  <li>✔️ Multi-tool visual reasoning</li>
  <li>✔️ Automatic tool selection based on query (planner)</li>
  <li>✔️ Multi-image support</li>
  <li>✔️ Annotated images for detection and OCR regions</li>
  <li>✔️ Natural-language response synthesis</li>
  <li>✔️ Modular — easy to swap in new models</li>
</ul>

---

<h2 id="workflow" align="center">🧪 Workflow</h2>

1. **Load image(s)**  
2. **Parse the user query**  
3. **Planner decides which tools to run**  
4. **Run DETR / OCR / Caption models**  
5. **Generate unified final answer**  
6. **Render annotated images**  

<p align="center"><em>A complete multi-modal reasoning pipeline.</em></p>

---

<h2 id="examples" align="center">📊 Visual Examples</h2>

<!-- ========================= -->
<!-- 1. MULTI-TOOL: DETECT + OCR -->
<!-- ========================= -->
<h3 align="center">1. Object Detection + OCR (Planner: Detect=True, OCR=True)</h3>
<p align="center">
  <img src="https://raw.githubusercontent.com/hamaylzahid/automated-defect-detection/main/visuals/Screenshot%202025-11-23%20205903.png" width="600">
</p>

<!-- ========================= -->
<!-- 2. CAPTIONING ONLY -->
<!-- ========================= -->
<h3 align="center">2. Image Captioning Output
  <br><sub>(Planner: Caption=True, Detect=False, OCR=False)</sub>
</h3>
<p align="center">
  <img src="https://raw.githubusercontent.com/hamaylzahid/automated-defect-detection/main/visuals/Screenshot%202025-11-23%20205932.png" width="600">
</p>

<h3 align="center">3. Captioning + Scene Summary
  <br><sub>(Planner: Caption=True, Detect=False, OCR=False)</sub>
</h3>
<p align="center">
  <img src="https://raw.githubusercontent.com/hamaylzahid/automated-defect-detection/main/visuals/Screenshot%202025-11-23%20205939.png" width="600">
</p>

<!-- ========================= -->
<!-- 4. FINAL ANSWER -->
<!-- ========================= -->
<h3 align="center">4. Final Multi-Tool Reasoning Output
  <br><sub>(Planner: Caption=True, Detect=False, OCR=False)</sub>
</h3>
<p align="center">
  <img src="https://raw.githubusercontent.com/hamaylzahid/automated-defect-detection/main/visuals/Screenshot%202025-11-23%20205951.png" width="600">
</p>

<hr>


<h2 id="install" align="center">⚙️ Setup & Installation</h2>

```bash
# Clone repository
git clone https://github.com/hamaylzahid/multi-tool-vision-agent
cd multi-tool-vision-agent

# Install dependencies
pip install -r requirements.txt

For CPU usage:

pip install easyocr torch torchvision transformers pillow opencv-python
```
<h2 align="center">🤝 Contact & Contribution</h2> <p align="center"> Have feedback, want to collaborate, or just say hello?<br> <strong>Let’s connect and improve automated defect detection together.</strong> </p> <p align="center"> 📬 <a href="mailto:maylzahid588@gmail.com">maylzahid588@gmail.com</a> &nbsp; | &nbsp; 💼 <a href="https://www.linkedin.com/in/your-linkedin-profile">LinkedIn</a> &nbsp; | &nbsp; 🌐 <a href="https://github.com/hamaylzahid/automated-defect-detection">GitHub Repo</a> </p> <p align="center"> <a href="https://github.com/hamaylzahid/automated-defect-detection/stargazers"> <img src="https://img.shields.io/badge/Star%20This%20Project-Give%20a%20Star-yellow?style=for-the-badge&logo=github" /> </a> <a href="https://github.com/hamaylzahid/automated-defect-detection/pulls"> <img src="https://img.shields.io/badge/Contribute-Pull%20Requests%20Welcome-2ea44f?style=for-the-badge&logo=github" /> </a> </p> <p align="center"> ⭐ Found this project helpful? Give it a star on GitHub!<br> 🤝 Want to improve it? Submit a PR and join the mission.<br> <sub><i>Your contributions help enhance real-world defect detection systems.</i></sub> </p> <br>
<h2 align="center">📜 License</h2> <p align="center"> <a href="https://github.com/hamaylzahid/automated-defect-detection/commits/main"> <img src="https://img.shields.io/badge/Last%20Commit-Recent-blue" /> </a> <a href="https://github.com/hamaylzahid/automated-defect-detection"> <img src="https://img.shields.io/badge/Repo%20Size-Moderate-lightgrey" /> </a> </p> <p align="center"> This project is licensed under the <strong>MIT License</strong> — free to use, modify, and expand. </p> <p align="center"> ✅ <strong>Project Status:</strong> Complete & Portfolio-Ready<br> 🧾 <strong>License:</strong> MIT — <a href="LICENSE">View License »</a> </p> <p align="center"> <strong>Crafted with deep learning expertise & real-world defect detection applications.</strong> 🧵✨ </p> <p align="center"> <a href="https://github.com/hamaylzahid"> <img src="https://img.shields.io/badge/GitHub-%40hamaylzahid-181717?style=flat-square&logo=github" /> </a> • <a href="mailto:maylzahid588@gmail.com"> <img src="https://img.shields.io/badge/Email-Contact%20Me-red?style=flat-square&logo=gmail&logoColor=white" /> </a> • <a href="https://github.com/hamaylzahid/automated-defect-detection"> <img src="https://img.shields.io/badge/Repo-Link-blueviolet?style=flat-square&logo=github" /> </a> <br> <a href="https://github.com/hamaylzahid/automated-defect-detection/fork"> <img src="https://img.shields.io/badge/Fork%20This%20Project-Contribute%20to%20AI-2ea44f?style=flat-square&logo=github" /> </a> </p> <p align="center"> <sub><i>Designed for real-world fabric defect detection and deep learning showcase.</i></sub> </p> <p align="center"> 🤖 <b>Use this project to demonstrate your expertise in computer vision and AI.</b><br> 🧵 Clone it, modify it, expand it — and build real-world automated defect detection solutions. </p>
