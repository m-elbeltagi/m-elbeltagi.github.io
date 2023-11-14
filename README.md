## Education
- Ph.D., Particle Physics|Carleton University, Canada
- BSc Honours, Theoretical Physics|Carleton University, Canada
  
## Professional Experience

**_Research Assistant/Data Analyst_ @ Carleton University - Physics Department**(_May 2018 - Present_)

- Headed the collection, storage and analysis of laboratory sensor data using **Python** and LabVIEW, enhancing the operational efficiency of particle physics experiment through uninterrupted monitoring and maintenance of a complex detector system.
- Developed a **Python** package for signal processing and time-series analysis (with **visualization** and **reports**), enabling pattern recognition and predictive maintenance that significantly reduced the risk of dielectric breakdowns in HV equipment.
- Applied innovative Monte Carlo methods in **machine learning** to improve probability density estimation for detector events, which sharpened the precision of measurement uncertainty. 


**_NLP Engineer Intern_ @ Advanced Symbolics**(_Summer 2023_)

- Reasearched latest papers to engineer and integrate custom metrics to meticulously evaluate **NLP** tasks, including clustering and summarization, ensuring high-quality model output.
- Actively engaged in **MLOps** practices, orchestrating the seamless operation of **NLP** production pipelines on **AirFlow** (using **Git**), significantly minimizing downtime and bolstering continuous delivery of **ML** solutions.

**_Course Instructor_ @ Carleton University - Math Department**(_Sep 2021 - Present_)

- Led physics courses on mechanics and electrostatics for classes of 20+ high school students, creating and delivering lecture materials, coordinating with TAs for optimal student support.

---
## Applied Projects Highlights
### Twitter Troll Detection: An LLM Approach

<div style="text-align: center;">
  <img src="/resources/TwitterTroll_cover.png?raw=true" width="300" height="300"/>
</div>

<br>
[Project Poster](/resources/TwitterTroll_poster.png)

(_The attached poster won 3rd place at the [Carleton Data Day 9.0](https://science.carleton.ca/dataday9/) competition._)

We apply a transfer learning approach to tweet classification, 3 models were used to compare their performance. 
1. A distilled version of a **pretrained LLM with fixed weights** for encoding the text, and a binary classification head trained on top of it. 
2. A pretrained smaller version of a LLM, now its weights adjustable by the training process to be **fine-tuned**, along with a binary classification head. 
3. A new (at the time this project was underway) few-shot learning (without prompts) technique called [SetFit](https://huggingface.co/blog/setfit) that dramatically decreases the number of examples needed for training by using contrastive learning.

The models were trained using 2 political tweets datasets, one confirmed to be russian-troll tweets, and one containing election-related political tweets, while excluding foreign and non-english language tweets.

[View the project code on my GitHub profile](https://github.com/m-elbeltagi/Twitter_Troll_Detection)

---

### Searching for Signal in a Haystack of Backgrounds

<div style="text-align: center;">
  <img src="/resources/SignalSearch_cover.png?raw=true" width="300" height="300"/>
</div>

<br>
[Project Report](https://github.com/m-elbeltagi/Signal_Hypothesis_Testing/blob/main/MohamedElbeltagi_5002Project.pdf)

This was the final project of a graduate **Computational Physics** course that I took a few years back. The objective was to identify the _mystery_ signal distribution (and number of signal events), given various background events occuring inside a physics detector. **EDA** is performed for the training data (in the context of physics, training data are usually obtained by **Monte Carlo simulations** emulating what we understand about real world physics processes) looking at the distributions, their properties, and correlations between them. Then **dimensionality reduction** is performed by constructing a Fisher discriminant, and cuts are applied to the _mystery_ data distribution by choosing an appropriate **p-value**. 

[View the project code on my GitHub profile (written in Python but utilises Cern **ROOT C++** framework)](https://github.com/m-elbeltagi/Signal_Hypothesis_Testing)

---
### From Randomness to Nature

<div style="text-align: center;">
  <img src="/resources/DCGAN_cover.png?raw=true" width="300" height="300"/>
</div>

In this project I designed and implemented in **PyTorch** a deep convolutional generative adversarial network (**DCGAN**) that I trained to generate images of natural landscapes with 3 color channels. It takes in a vector of random numbers from a latent space, and outputs images of natural landscapes. This is based on the concept of an adversarial network, but with the Generator and Discriminator being convolutional networks, which are better suited for dealing with images.

The loss of the Discriminator is based on whether the input image to it was in the training set, or came from the Generator. The loss of the Generator is based on the Discriminator's output/label, in a sense, the more its able to fool the Discriminator, the less it gets its weight updated via gradient descent because its doing a "good job", but if it gets discovered by the Discriminator, it gets a larger weight update because it doing a bad "job". This process continues in the training loop untill the discriminator can't tell the difference between real and generated images (it picks the label of each with $p=0.5$).


<!--- The following tag is to render equations on GitHub pages using MAthJax --->
<script type="text/javascript" charset="utf-8" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML,
https://vincenttam.github.io/javascripts/MathJaxLocal.js"></script>


$L_D = \mathop{max}_{D} ; \space log(D(x)) + log(1-D(G(z)))$

$L_G = \mathop{min}_{G} ; \space log(1-D(G(z)))$

Where $x$ is an image from the trianing set, $z$ is random noise from the latent space that the Generator uses to produce images, $D$ is the Discriminator, $G$ is the Generator. This is just the **_binary cross entropy loss_**.

[View the project code on my GitHub profile]([https://github.com/m-elbeltagi/ChatDr](https://github.com/m-elbeltagi/Landscape-Convolutional-GAN))

---
### ChatDr

<div style="text-align: center;">
  <img src="/resources/ChatDr_cover.png?raw=true" width="300" height="300"/>
</div>

<br>
This is an extractive question answering (**extractive QA**) medical chat bot, to answer questions given a patient's medical history. It is a version of a language model trained on the [SQuAD_v2 dataset](https://huggingface.co/datasets/squad_v2), further fine-tuned on a medical QA dataset. The fine-tuning was performed on an **NVIDIA RTX 3060ti GPU**, utilising the **Hugging Face Transformers** library (specifically using the [Trainer class](https://huggingface.co/docs/transformers/main_classes/trainer)), after preparing the supervised training dataset using **PyTorch**. Training metrics and performance were logged in real-time, and the different training runs were conveniently versioned using **Tensor Board** which provides interactive graphs/visualizations.

[View the project code on my GitHub profile (Jupyter Notebook)](https://github.com/m-elbeltagi/ChatDr)

---

### CapitaLens

<div style="text-align: center;">
  <img src="/resources/CapitaLens_cover.png?raw=true" width="300" height="300"/>
</div>

This is a web app that aims to provide up-to-date relevant information about assets and stocks, including recent news discussing the asset, the general emotions breakdown of said news, overlayed onto recent stock performance, with the goal of making more informed investment decisions.

Currently building the web app, will post here when it's deployed.
