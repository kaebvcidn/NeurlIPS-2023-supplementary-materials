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
    
- Test on one level-5 problem from each category (except geometry):
```python
python main.py -ptype default --folder ./default --categories 0 1 3 4 5 6 --samples_per_category 1
```
Note: `default` is the default prompt for MathChat, other choices are `python` and `two_tools`.


- Test on all problems from each category (except geometry):
```python
python main.py -ptype default --folder ./default --categories 0 1 3 4 5 6 --samples_per_category 400
```

## Main Results

Accuracy on all the problems with difficulty level-5 from different categories of the MATH dataset with different methods.
|                   | Algebra | C.Prob | I.Alg | N.Theory | Prealg | Precalc | Total |
|-------------------|---------|--------|-------|----------|--------|---------|-------|
| Problem Count     | 307     | 123    | 280   | 154      | 193    | 135     | 1192  |
| **MathChat**     | **59.93%** | **52.03%** | 17.85%  | 60.39% | **60.10%** | **19.26%**  | **44.71%** |
| PoT              | 42.67% | 50.41% | 17.50%  | 54.55% | 52.33% | 16.30% | 37.67% |
| PS               | 43.32% | 44.71% | **20.36%**  | **61.03%** | 55.96% | 18.52% | 39.60% |
| Vanilla          | 46.58% |25.20%  | 2.86% |28.57%  |54.92%  | 7.41% |  28.69%|




