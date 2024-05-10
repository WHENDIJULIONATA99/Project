Mean-Variance-Standard-Deviation-Calculator
This assignment was set within the Data Analysis with Python Projects on freeCodeCamp.org

Assignment
Create a function named calculate() in mean_var_std.py that uses Numpy to output the mean, variance, standard deviation, max, min, and sum of the rows, columns, and elements in a 3 x 3 matrix.

The input of the function should be a list containing 9 digits. The function should convert the list into a 3 x 3 Numpy array, and then return a dictionary containing the mean, variance, standard deviation, max, min, and sum along both axes and for the flattened matrix.

The returned dictionary should follow this format:

import numpy as np

def calculate(list):
    if len(list) != 9:
        raise ValueError('List must contain nine numbers.')
    else:
        matrix = np.array(list).reshape(3, 3)

    mean = [(matrix.mean(axis=0).tolist()), (matrix.mean(axis=1).tolist()),
            (matrix.flatten().mean())]

    var = [(matrix.var(axis=0).tolist()), (matrix.var(axis=1).tolist()),
           (matrix.flatten().var())]

    std = [(matrix.std(axis=0).tolist()), (matrix.std(axis=1).tolist()),
           (matrix.flatten().std())]

    max = [(matrix.max(axis=0).tolist()), (matrix.max(axis=1).tolist()),
           (matrix.flatten().max())]

    min = [(matrix.min(axis=0).tolist()), (matrix.min(axis=1).tolist()),
           (matrix.flatten().min())]

    sum = [(matrix.sum(axis=0).tolist()), (matrix.sum(axis=1).tolist()),
           (matrix.flatten().sum())]

    calculations = {
        "mean": mean,
        "variance": var,
        "standard deviation": std,
        "max": max,
        "min": min,
        "sum": sum,
    }
    return calculations
