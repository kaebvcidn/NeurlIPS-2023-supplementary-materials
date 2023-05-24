# NeurlIPS-2023-supplementary-materials


## Setup
- Set up env
```
conda env create -f environment.yml
```
- put a valid key that can use GPT-4 in `openai.api_key`.
- If the prompt involves wolfram, an wolfram app_id is needed.
- Customized prompt to use Python or Wolfram can be put in `prompt.py` to be tested.

## Run MathChat 
- Use `--categories` to select category to run, and `--samples_per_category` for number of samples. The problems are randomly selected from level-5 difficulty. 
    
    ID : Category Name
    0 : Algebra     
    1 : Counting & Probability     
    2 : Geometry    
    3 : Intermediate Algebra     
    4 : Number Theory    
    5 : Prealgebra    
    6 : Precalculus    
    
- Test on one sampled level-5 problem from each category (except geometry):
```python
python main.py -ptype v3.9python --folder ./default --categories 0 1 3 4 5 6 --samples_per_category 1
```
Note: `v3.9python` is the default prompt for MathChat.


- Test on all problems from each category (except geometry):
```python
python main.py -ptype v3.9python --folder ./default --categories 0 1 3 4 5 6 --samples_per_category 400
```

## Run baselines

