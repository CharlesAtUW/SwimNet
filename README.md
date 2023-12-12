# Handwritten IM2LATEX preprocessing

Code in `scripts` and `third_party` are not ours, but are from Deng et al. They are from https://github.com/harvardnlp/im2markup/tree/master. Some small modifications may have been made to make their code run correctly.

## To preprocess the data

1. Get the handwritten `IM2LATEX-100K-HANDWRITTEN.tgz` file and put it in the top-level directory of this repository. It can be obtained from https://im2markup.yuntiandeng.com/data/ or from https://github.com/harvardnlp/im2markup/tree/master.
2. Run the cells of the `preprocess_handwritten.ipynb` notebook to generate the `handwritten_dataset.h5` file, which is one file that contains all the train/test/validation data. For us, this was not done on Google Colab, since Google Drive doesn't like having ~100k images in one folder (it will delete some of them).
3. Run the cells of `LatexCharacterRecognition.ipynb` to finetune a pretrained model or a saved model on the handwritten IM2LATEX dataset, and to evaluate the model on the dataset.

## Environment

- To run the `preprocess_handwritten.ipynb` notebook properly, `numpy`, `h5py`, and `Pillow` (`PIL`) need to be installed. Python version 3.10.2 was used, but some earlier versions might work. Perl will also need to be installed, in order to properly run some of Deng et al.'s scripts.
- The `LatexCharacterRecognition.ipynb` notebook was ran on Google Colab, with data and models being in the `data` and `models` folders relative to the notebook, respectively.
