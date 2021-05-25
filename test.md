import numpy as np
from pymoo.algorithms.nsga3 import NSGA3
from pymoo.model.problem import Problem
from pymoo.optimize import minimize
from pymoo.factory import get_reference_directions


class MyProblem(Problem):

    def __init__(self):
        super().__init__(n_var=7,
                         n_obj=2,
                         n_constr=0,
                         xl=np.array([-2, -2, -2, -2, -2, -2, -2]),
                         xu=np.array([2, 2, 2, 2, 2, 2, 2]),
                         elementwise_evaluation=True)

    def _evaluate(self, x, out, *args, **kwargs):
        f1 = -34 * x[0] - 0 * x[1] - 27 * x[2] - 20 * x[3] / 25 * x[4] + 6 * x[5] + 11 * x[6]
        f2 = -54 * x[0] - 55 * x[1] - 27 * x[2] - 48 * x[3] / 53 * x[4] + 20 * x[5] + 16 * x[6]

        # g1 = 2 * (x[0] - 0.1) * (x[0] - 0.9) / 0.18
        # g2 = - 20 * (x[0] - 0.4) * (x[0] - 0.6) / 4.8

        out["F"] = [f1, f2]
        # out["G"] = [g1, g2]


problem = MyProblem()

# create the reference directions to be used for the optimization - just a single one here

# create the reference directions to be used for the optimization
ref_dirs = get_reference_directions("das-dennis", 2, n_partitions=12)

# create the algorithm object
algorithm = NSGA3(pop_size=10,
                  ref_dirs=ref_dirs)

# execute the optimization
res = minimize(problem,
               algorithm,
               ("n_gen", 10),
               verbose=True,
               seed=1)

print("UNSGA3: Best solution found: \nX = %s\nF = %s" % (res.X, res.F))
