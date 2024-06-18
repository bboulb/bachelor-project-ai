# Generating Super Mario Bros Levels using Large Language Models

**Bilal Boulbarss**  
Email: bilalboulbarss@gmail.com  

Bachelor Project AI -- VU Amsterdam

---

## Introduction

In this repository, you can find all the code, data, and levels used for my bachelor project AI called **"Generating Super Mario Bros levels using Large Language Models"**.

---

## Acknowledgements

I did not write all the code myself:
- Everything from the directory `ECS7002P-MarioAI-master` is from this [GitHub repository](https://github.com/GAIGResearch/ECS7002P-MarioAI). There were some changes made to accommodate this project, especially in `RunLevels.java`.
- Everything from the directory `mario_levels` is from the [Video Game Level Corpus](https://github.com/TheVGLC/TheVGLC).
- A lot of the code in `main.ipynb` (the training loop, dataset class, generation code) was taken from this [example notebook](https://colab.research.google.com/drive/13dZVYEOMhXhkXWfvSMVM1TTtUDrT6Aeh?usp=sharing#scrollTo=NKGBoVwuhM4H).

---

## Project Structure and Usage

### `main.ipynb`

This notebook was used to fine-tune the transformers and generate the levels. Since I used a pre-trained model from HuggingFace, you are required to make a HuggingFace account and get an access token if you want to run it yourself. It is completely free.

- You need to change the directories that lead to the training data and the directory for output after generating.
- I did everything in Google Colab, so I put all the training data in Google Drive and also stored the generated levels there. Another reason to use Google Colab is free (limited) access to a GPU if you don't have one. It makes a big difference in training time compared to a CPU.

### `mario_levels`

This directory contains all the training data used in this project.

### `ECS7002P-MarioAI-master`

This code was mainly used to run A* agents on the generated levels. `RunLevels.java` is the most important file.

### `self/experiment_data` + `self/experiment_levels`

These directories contain all the data and generated levels for the experiment. `average_data` was used for the thesis report.

### `self/evaluation.ipynb`

This was the main notebook used for evaluating the generated levels. It starts off with code for the A* agent. I tried to build a Python wrapper around `RunLevels.java`, but it is not perfect. 

- To use `RunLevels.java`, you need to manually change the path to the levels you want to evaluate.
- To use the Python wrapper, you also need to change the paths to accommodate your machine.
- To evaluate the levels further, you also need to change some paths.

### `self/level_visualization.ipynb`

This notebook was used to transform the generated levels from text format to PNG format.

### `self/play_run.ipynb`

This is the code to play any generated level yourself or let an A* agent play it for you. Note:
- The A* agent that evaluated the levels is not the same A* agent that you will see play. 
- The A* agent you will see play provides no feedback (whether the level was completed, etc.), so this one was unusable to evaluate, but it is very easy to implement.
- The A* agent used to evaluate was more complex but provides good feedback on the generated levels. That is why there are two separate agents.

---

Feel free to reach out if you have any questions or need further assistance!

---
