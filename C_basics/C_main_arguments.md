## arguments of the main function

basic usage  
```c
void main(int argc, char* argv[])
{
    for(int i=0; i<argc; i++){
        printf("%s\n",argv[i]);
    }
}
```

### executing through cmd:  
go to the path  
write the name of the path and then your arguments
```
C:\>cd "PATH OF THE FILE EXE"

C:\"PATH OF THE FILE EXE"filename.exe string1 string2 string3
filename.exe
string1
stirng2
string3
```

>### Note that 
>All the arguments are treated as strings (you can cast their type or use atoi atof etc.)  
>First argument always should be the file name (so first actual argument is argv[1]  --not argv[0]-) 