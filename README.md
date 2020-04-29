# Exercise 6.13 Testing

This directory structure contains two files of interest, an `execise.py` file in the `src` directory and a `test_exercise.py` file in the `tests` directory.

The `exercise.py` file contains two methods, one which calculates the sum of two numbers and one which calculates the division of two numbers. You will not need to edit this file in this exercise.

You will be working with the `test_exercise.py` file. Modify it so that it tests the routine `divide()`. A template is below:

```python
import pytest
from src.exercise import add, divide

def test_exercise():
    assert add(2,3) == 5 # checks if the output of add is correct
    assert add(-2,3) == 1 # it's a good idea to check minus numbers for this routine

    # implement your divide checks here. What happens if you divide by 0?
```

Follow the instructions for setting up a virtual environment and installing `pytest` via `pip` in the [Getting Started](https://scott3142.uk/python-programming/codelabs/getting-started) part of the notes. Once you have `pytest` installed, you can run the following commands from the `root` directory. (The `root` directory is the top level directory containing `README.md` and the folders `src` and `tests`).

```bash
virtualenv testing
source testing/bin/activate
python -m pytest
```

Once you have run these commands you should see the tests either pass or fail. If you would like to learn more about Python testing (and I recommend that you do), you can check out [this great resource](https://realpython.com/python-testing/).

### Exploring the .github/workflows/workflow.yml file

The full description of what this file does is beyond the scope of this course, but the lines of interest to us are

```plaintext
- name: Test with pytest
      run: |
        pip install pytest
        python -m pytest
```

This means that when the code is uploaded to Github, it is `pytest`-ed with the same command you're running locally in this exercise. This has been happening behind the scenes throughout this course, and the Actions panel that you've been using to check your code prints out the results of these tests.
