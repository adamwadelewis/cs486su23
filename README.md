# CS 486 Summer 2023 

## Setup

We will be using the demo code and utilities from the Hapke text.   As
is the norm, code ages and builds up bit rot.   No different
here... There have been some API changes from the time the text was
published that need to be addressed. The `nlpia` and `pug-nlp` folders
contain patches that addresses those changes.  

Here's the modified install instructions:

```sh
# Do the git stuff to clone the repository and create a branch where we
# can modify config files.
git clone https://github.com/totalgood/nlpia
# Now do same for the class repository
git clone https://github.com/adamwadelewis/cs486su23
cd nlpia  # make sure you're in the nlpia directory that contains `setup.py`
conda env create -n nlpiaenv -f ../cs486su23/nlipia/conda/environment.yml
conda install -y pip  # to get the latest version of pip
conda activate nlpiaenv
pip install -e .
# Now we need to patch the installed versions of the nlpia and pug-nlp
# packages.   You will need to find where the Andaconda stores the files
# the enviornment. This will be in your home folder.  For example, on my
# machine, this will be ~/anaconda3/envs/nlpiaenv.   Go to that folder.
cd ~/anaconda3/envs/nlpiaenv/lib/python3.10
# Now go to the nlpia folder
cd nlpia
cp ~/cs486su23/nlpia/* .
cd ../pug-nlp/pug/nlp
cp ~/cs486su23/pug-nlp/* .

```
