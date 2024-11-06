# AI dev assignment - News classification

Create a model for text classification based on given data. Make your code available on a public Git repo. Hyperparameter tuning is optional; setting hyperparameters to 'good enough' values manually is OK.

## Data

The data is a subset of News Category Dataset available on Kaggle. It is stored in JSON-per-line (JSONL) format. Important fields:

- `category` - this is the value that should be predicted by the model
- `headline` - headline of the article
- `short_description` - short snippet of text

The data is divided into three files:

- `train.jsonl` - training data
- `dev.jsonl` - validation data; hyperparameter tuning is optional for this assignment, manually coming with 'good enough' values is OK.
- `test.jsonl` - test data for final evaluation

## Deliverables

- `train.py` - training script
  - **inputs**: train data, (optional) validation data, (optional) hyperparameter values
  - **outputs**: serialized model file
- `eval.py` - evaluation script
  - **inputs**: serialized model file, evaluation data (in the JSONL format defined above)
  - **outputs**: accuracy; optionally confusion matrix and precision/recall for each category
- `classify.py` - classification script
  - **inputs**: serialized model file, data to classify (the JSONL without `category` field)
  - **outputs**: the input JSONL with `category` field set to model's predicted value
- `requirements.txt` - list of (direct) dependencies of your scripts in [Pip requirements file format](https://pip.pypa.io/en/stable/reference/requirements-file-format/)
- `README.md`
  - A short summary of your approach.
  - Clear instructions on how to install, train, evaluate, and run the classifier.
  - Bullet points are fine.
- other files at your discretion

## Technical Requirements

- You can use any model type and any publicly available Python library you consider appropriate.
- The scripts should not make API calls through the network (e.g., you cannot call OpenAI API).
- It is ok to download and use pre-trained models for some subtasks. But you cannot use a model created to classify the same data by somebody else.
- The scripts should be able to run on a regular laptop.
- Do not use Jupyter Notebooks for deliverables; write regular production-like code that can be executed from a command line with appropriate parameters.

- Code style and conventions:
  - Use self-explanatory variable and function names.
  - Use type hints for function parameters and return values. Use them at least for basic types
(`str`, `int`, `Iterable`, `tuple`, `Optional`, `Mapping`, ...).
You do not need to use them for complex types of third-party libraries where it is not clear what the type actually is.
  - Document all public functions using docstrings. Add other comments as appropriate.
  - Strictly follow the PEP8 code style (use a linter or IDE to verify this).
  - Use the main function pattern and `argparse` to parse arguments.
  - Use `pathlib.Path` to manipulate files.
  - Use appropriate libraries to handle JSON, XML, CSV, etc. Do not write the code yourself.

## Nice to haves

- Hyperparameter tuning.
- Tests for some of the functions.

## Workflow requirements

- The code must be submitted via a pull request to a Git repository.
- Develop the code on a feature branch, not on the main/master branch. Name the branch any way you want.
- Commit functional parts of the application; ideally, each commit should introduce some value or functionality.
- Use meaningful commit messages, avoiding vague terms like 'WIP' or 'Fix'.
- Once you are done, push the code to the repository, create a pull request, and let us know you are done.
