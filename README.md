# General-Relativity-Tensor-Calculations

Calculating the Christoffel Symbol, Riemann Curvature Tensor, Ricci Tensor, Ricci Scalar, Traceless Ricci Tensor, and Einstein Tensor from the given metric

### Required packages
sympy, numpy, itertools

## Getting Started

1. Define the coordinate system (cartesian, spherical, etc.) 
2. Define the diagonal components of the metric tensor

The first few lines of the code should look like this.

```
from GR_full_curv import *
from IPython.display import Latex, display
from sympy import *

init_printing()

coord_sys = symbols("t r theta phi") # Coordinate system that we will work on 

G, m, c, a = symbols("G, m, c, a") # Defining some extra symbols

diag_comp = [-1, 1, coord_sys[1]**2, coord_sys[1]**2 * sin(coord_sys[2])**2] # Defining the diagonal components of the metric tensor
```

3. To add a different symbol, use [symbols](https://docs.sympy.org/latest/tutorial/basic_operations.html)

## Getting Tensors and Index Lowering/Raising

1. After defining the diagonal components of the metric tensor, we can calculate/obtain the tensors by just assigning them into a variable and using the `get_tensorname()` method.

For instance, to obtain the Christoffel Symbol, it is sufficient to write this line of code in Jupyter Notebook.

```
cs = ChristoffelSymbol(diag_comp, coord_sys)
chris_symbol = cs.get_christoffelsymbol()
chris_symbol
```

2. In order to access the type of the Christoffel Symbol one can write,

`cs.get_type()`

3. `(1,0)` (Contravariant) type tensor will be denoted by a string `"u"` and `(0,1)`ncovariant type tensor will be denoted by `"d"`. In order to change the type of the Christoffel Symbol, just type the desired tensor in terms of `"u"``and `"d"`.

`cs.vary_type(chris_symbol, 'ddd')`

The code above will convert the `(1,2)` tensor into `(0,3)`

4. In order to obtain the non-zero components of the Christoffel Symbols, one can write.

`cs.nonzero_christoffelsymbol(chris_symbol)`

These examples can be further studied on `example1.ipynb` and `example2.ipynb` files.

Note: It is recommended to use Jupyter Notebook to see a better output.
 
