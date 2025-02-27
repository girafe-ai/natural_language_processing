#### Lab02: QA system

In this homework your goal is to build the QA system for specific language. The default code is available for English and Russian languages. Russian example using the [SberQuAD dataset](https://arxiv.org/pdf/1912.09723.pdf). The preprocessing code and baseline solution (BiDAF) are the slightly adapted version of the [Stanford CS224n Starter code](https://github.com/chrischute/squad) for the SQuAD dataset.

**To use any other language, please, refer to [this post](https://medium.com/deepset-ai/going-beyond-squad-part-1-question-answering-in-different-languages-8eac6cf56f21) or to the Table 2 in the paper [Deep learning based question answering systemin Bengali](https://www.researchgate.net/publication/346129818_Deep_learning_based_question_answering_system_in_Bengali), where the authors provide an overview of available datasets.**

The available languages are (but not limited to): Korean, Arabic, French, Spanish, Italian, Russian, English, Hindi and Chinese.

The starting point of this assighnment is the `SberQuAD_preprocessing_and_problem_statement.ipynb` notebook.
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github//natural-language-processing/tree/master/homeworks/lab02_qa/SberQuAD_preprocessing_and_problem_statement.ipynb)


You may choose either this assignment or the `homework05` on the Image Captioning. Or do both ;) 

Next comes the original instructions from the https://github.com/chrischute/squad repository.

P.s. Downgrading PyTorch is not required, starter code works fine on PyTorch 1.4
P.p.s. If you are running in Colab, mount your Google Drive and store the checkpoints/word vectors there. [Official instruction (en)](https://colab.research.google.com/notebooks/io.ipynb), [Habr post (ru)](https://habr.com/ru/post/348058/). Restarting the kernel after you finished the preprocessing (and saved the data to your disk) might be a good idea to release the memory.

#### Setup

1. Make sure you have [Miniconda](https://docs.conda.io/en/latest/miniconda.html) installed
    1. Conda is a package manager that sandboxes your project’s dependencies in a virtual environment
    2. Miniconda contains Conda and its dependencies with no extra packages by default (as opposed to Anaconda, which installs some extra packages)

2. cd into src, run `conda env create -f environment.yml`
    1. This creates a Conda environment called `squad`

3. Run `source activate squad`
    1. This activates the `squad` environment
    2. Do this each time you want to write/test your code
  
4. Run `python setup.py`
    1. This downloads SQuAD 2.0 training and dev sets, as well as the GloVe 300-dimensional word vectors (840B)
    2. This also pre-processes the dataset for efficient data loading
    3. For a MacBook Pro on the Stanford network, `setup.py` takes around 30 minutes total  

5. Browse the code in `train.py`
    1. The `train.py` script is the entry point for training a model. It reads command-line arguments, loads the SQuAD dataset, and trains a model.
    2. You may find it helpful to browse the arguments provided by the starter code. Either look directly at the `parser.add_argument` lines in the source code, or run `python train.py -h`.
