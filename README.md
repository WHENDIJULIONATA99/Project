{
  'mean': [axis1, axis2, flattened],
  'variance': [axis1, axis2, flattened],
  'standard deviation': [axis1, axis2, flattened],
  'max': [axis1, axis2, flattened],
  'min': [axis1, axis2, flattened],
  'sum': [axis1, axis2, flattened]
} 

{
  'mean': [[3.0, 4.0, 5.0], [1.0, 4.0, 7.0], 4.0], 
  'variance': [[6.0, 6.0, 6.0], [0.6666666666666666, 0.6666666666666666, 0.6666666666666666], 6.666666666666667], 
  'standard deviation': [[2.449489742783178, 2.449489742783178, 2.449489742783178], [0.816496580927726, 0.816496580927726, 0.816496580927726], 2.581988897471611],
  'max': [[6, 7, 8], [2, 5, 8], 8],
  'min': [[0, 1, 2], [0, 3, 6], 0],
  'sum': [[9, 12, 15], [3, 12, 21], 36]}
}












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
