# A simple module

- test.c
- module.h
- module.c

---

# module.h

only claim things not implement

Example
```
#ifndef AD_HHH______ // avoid two file include the same module
#define AD_HHH______

#include <stdio.h>
#define DEBUG_VERSION

// Public funciton
float module_function(int param);

// Privat function 
float use_in_module_only(int param);

#endif

```

---

# test.c
Write a __main__ function here, for testing

Example
```
#include "AD.h"

//int main(int argc, chcr *argv[]){
int main(){
	// writing test here
	int test_input = 1;
	float output;
	output = module_function(test_input);
}

```

---

# module.c
Implement the functions in module have no __main__ function

Example
```
#include <stdio.h>
#include "AD.h"

float module_function(int param){
	//implement the function
}


float use_in_module_only(int param){
	//implement the function
}

```

---
#Complile
- simple way  
`gcc module.c test.c `


- In detail way  
`gcc -c module.c`
`gcc module.o test.c`


