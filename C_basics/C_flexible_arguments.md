## flexible arguments

basic usage  
```c
void fun1 (int n, ...){
    va_list args; 
    va_start(args, n);

    va_arg(args,int);

    va_end(args);
}

```
