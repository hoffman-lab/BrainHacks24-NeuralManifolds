# Project Description
What are the meaningful changes in the brain with experience, that allows for adaptive behavior? When we look at the coordinated activity across spiking networks of neuronal ensembles, we see a delicate balance of stability and flexibility, as needed for a system that can both learn and remember. In this project, we present a population of simultaneously-recorded neurons from the non-human primate during learning of a complex sequence memory task, and in sleep afterwards. These data are exceptionally rich for exploration, but also to address three fundamental questions: 1. can we decode behavioral states from the ensemble dynamics, 2. what is the core representational geometry of the ensembles (what factors are best preserved/differentiated in low-dimensional spaces, and how does the geometry constrain the computations and dynamics of the network), and finally, 3. Does the ensemble activity drift with time and experience, and if so, how?

Here's a cool illustration of [neural ensembles in macaque hippocampus](https://www.youtube.com/watch?v=PVLZRPLcwW4) which we are interested in studying. 

# Getting started 
Make sure that you have Python installed onto your computer as well as the code editor that you prefer (we would recommend Visual Studio Code for Github copilot and integrated git access). 

Start by creating and activating a virtual environment. 
```bash
# Create a virtual environment
python3 -m venv env

# Activate the virtual environment
# On Windows
env\Scripts\activate

# On Unix or MacOS
source env/bin/activate
```

Clone this repository onto your local machine:
```bash
git clone https://github.com/hoffman-lab/BrainHacks24-NeuralManifolds.git
```
Ensure that you have all the dependencies installed: 
```bash
pip install -r requirements.txt
```
 Everything you will need to get started is in the brainhack_example.ipynb notebook. Click through the notebook to see how our data is formatted, and how we can implement various neural manifold learning algorithms (e.g. PCA, tSNE, and UMAP) to represent the neural ensembles in a low dimensional space. 

# Open Research Themes 
1. Experiment on neural manifold creation with using different hyperparameters (e.g. n_neighbors or min_dist in UMAP). Different parameters can greatly change the shape of the manifold and thus can affect the ability to decode different behaviors. Afterwards, consider creating UI to visualize neural manifolds across different hyperparameters. [Here](https://pair-code.github.io/understanding-umap/) is a great example.
2. Parallelize dimensionality reduction across a set of hyperparameters
3. Experiment with which behavioral parameters are most separated in low dimensional space (block type, trial number, time, head position, angular velocity, etc.). Feel free to use the dimensionality reduction methods that are referred to in this notebook, or any other ones that you may be familiar with (e.g. MDS, CEBRA, etc). 
4. See if you can analyze the [structural index](https://github.com/PridaLab/structure_index) within our data. Briefly, this is a method to quantify representational structure in a neural manifold. 
5. We are also interested in a new, supervised dimensionality reduction algorithm called [CEBRA](https://cebra.ai/docs/index.html). CEBRA uses neural networks to create a latent space representation of neural data, minimizing the distance between neural activity points that share similar behavioral labels. We're interested to see if CEBRA is able to create neural manifolds with underlying task-dependent structure even if the behavioral labels are scrambled. For example, if you scramble timepoints across the data, is there still continuous drift? You can try comparing structural index of a CEBRA generated manifold with and without timepoint scrambling. 

# Data:

Data can be downloaded from this google drive:
https://drive.google.com/drive/folders/1k0v689KtANodxuhu436aghavizu3keBk?usp=drive_link

# Acknowledgements 
The data come from recordings described [in this paper](https://www.biorxiv.org/content/10.1101/2023.12.06.570369v1) (Abbaspoor and Hoffman, bioRxiv, 2023).

The task is described [in this paper](https://www.biorxiv.org/content/10.1101/2023.12.11.571113v1) (Abbaspoor, Rahman, Zinke and Hoffman, bioRxiv, 2023).

Funding: Whitehall Foundation and NINDS R01 NS127128

The lab has some limited openings for students and postdoctoral fellows. If interested, reach out to Richard Song (richard.w.song@vanderbilt.edu) during BrainHack, or contact Kari Hoffman (kari.hoffman@vanderbilt.edu) aftewards for more info.
