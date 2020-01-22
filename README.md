# Pickle
Proofs of concepts using Pickle and Dill through Jupiter notebooks

### [Dill](https://pypi.org/project/dill/) extends python’s pickle module for serializing and de-serializing python objects to the majority of the built-in python types. 
### Serialization is the process of converting an object to a byte stream, and the inverse of which is converting a byte stream back to on python object hierarchy.

If you don't have Dill installed yet, please run the following command:


```python
pip install dill
```

    Requirement already satisfied: dill in /home/ced/anaconda3/lib/python3.7/site-packages (0.3.1.1)
    Note: you may need to restart the kernel to use updated packages.



```python
import dill
```

## I) Save your entire Jupyter notebook session


```python
favorite_color = {"lion":"yellow", "kitty":"red"}

dill.dump_session('save-dill-notebook_env.db')
```


```python
print(favorite_color)
```

    {'lion': 'yellow', 'kitty': 'red'}


### Try to restart the Jupiter local server using Jupyter > Kernel > Restart Kernel


```python
print(favorite_color)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-1-9fd5ad14973e> in <module>
    ----> 1 print(favorite_color)
    

    NameError: name 'favorite_color' is not defined


### The error above is what we are trying to solve using Dill
## II) Load the dictionary back from the Dill file.


```python
import dill
dill.load_session('save-dill-notebook_env.db')
```

### favorite_color is now:


```python
print(favorite_color)
```

    {'lion': 'yellow', 'kitty': 'red'}



```python

```



### This Pickle exemple have been made using [Python UsingPickle doc](https://wiki.python.org/moin/UsingPickle) 


```python
import pickle
```

## I) Save a dictionary into a pickle file


```python
favorite_color = {"lion":"yellow", "kitty":"red"}

pickle.dump( favorite_color, open( "save-pickle.p", "wb"))
```


```python
print(favorite_color)
```

    {'lion': 'yellow', 'kitty': 'red'}


### Try to restart the Jupiter local server


```python
print(favorite_color)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-1-9fd5ad14973e> in <module>
    ----> 1 print(favorite_color)
    

    NameError: name 'favorite_color' is not defined


### The error above is what we are trying to solve using Pickle
## II) Load the dictionary back from the pickle file.


```python
import pickle
favorite_color = pickle.load( open("save-pickle.p", "rb"))
```

### favorite_color is now:


```python
print(favorite_color)
```

    {'lion': 'yellow', 'kitty': 'red'}



```python

```
