# Scipy ivp library for CuPy
This is CuPy-compatilbe initial value problem library in SciPY. 
All the NumPy functions in files of `scipy/integrate/_ivp/` are replaced with CuPy functions and slightly modified for consistency.

I assume that this library will be used as in the following example.
```
prop = DOP853(fun, t0=0.0, y0=y0, t_bound=5.0, rtol=1e-5, atol=1e-8)

y_log = []
i = 0
while not prop.status == "finished":
    if i % 100 == 0:
        y_log.append(cp.copy(prop.y))
        
    prop.step()
    i += 1
    
```
See more in the notebook
Note that `solve_ivp` function in scipy is not inclued in this library.

