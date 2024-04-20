# P5 "Toys" reproducibility experiment

This repository contains the *train* and *eval* jupyter notebooks used to perform the reproducibility experiment of the
[*"Recommendation as Language Processing (RLP): A Unified Pretrain, Personalized Prompt & Predict Paradigm (P5)"*](https://arxiv.org/pdf/2203.13366.pdf).

The official repository of the above paper, where the **P5** model is implemented, 
can be found [here](https://github.com/jeykigung/P5) 


## Instructions

- Run the following pytorch docker image: [`pytorch/pytorch:2.0.1-cuda11.7-cudnn8-runtime`](https://hub.docker.com/layers/pytorch/pytorch/2.0.1-cuda11.7-cudnn8-runtime/images/sha256-82e0d379a5dedd6303c89eda57bcc434c40be11f249ddfadfd5673b84351e806)
- Run all cells of `Bash_train_toys.ipynb` with the `bash` kernel
- Move `test_toys_small.ipynb` to the newly created *P5/notebooks* directory
- Open `test_toys_small.ipynb` from the *P5/notebooks* directory and run all its cells with the `3.9.7` kernel

## Changes to the source code:

**No change** has been applied to the source code, since scripts provided by the author's have been used, both for the 
training phase and the evaluation phase.

### Changes to the training script
 
* The script `pretrain_P5_small_beauty.sh` is used, where occurrences of "beauty" have been replaced with 
  "toys", since the Amazon "toys" dataset is used

### Changes to the evaluation notebook

* "test_toys_small.ipynb" is an **exact copy** of `test_beauty_small.ipynb`, where:
  * All occurrences of *beauty* have been replaced by *toys*
  * The working directory is set correctly to the root of P5 repo, since in the original notebook provided the code crashes
  * The path to the model to load is set accordingly to the output of the training phase
  * For the sequential task evaluation, `user_4429` is skipped since no valid recommendations are generated for it and the code crashes otherwise
