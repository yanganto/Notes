# python setup tool
 ```
from setuptools import find_package, setup  
distutils.core import setup, Extension
```

---

# Tools

- Distutils is still the standard tool for packaging in Python. It is included in the standard library (Python 2 and Python 3.0 to 3.4). It is useful for simple Python distributions, but lacks features. It introduces the distutils Python package that can be imported in your setup.py script. 
- Setuptools was developed to overcome Distutils' limitations, and is not included in the standard library. It introduced a command-line utility called easy_install. It also introduced the setuptools Python package that can be imported in your setup.py script, and the pkg_resources Python package that can be imported in your code to locate data files installed with a distribution. One of its gotchas is that it monkey-patches the distutils Python package. It should work well with pip. It sees regular releases.

- **Setuptools is recommend**

- ref: [StackOverFlow](http://stackoverflow.com/questions/6344076/differences-between-distribute-distutils-setuptools-and-distutils2)
---
