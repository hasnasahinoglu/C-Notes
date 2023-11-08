>## Exercise : 
> ### Finding the number of word in the given sentence

```c
#include <stdio.h>
#include <stdlib.h>


int main()
{
    printf("Enter a sentence(no space at the end pls) and I will tell you how many words are there\n");
    char sentence[100]; // defining an array to store the sentence
    gets(sentence); // we will work with the spaces and to do this we use gets, not scanf
    // also scanf is not as safe as gets.

    int i = 0;
    int counter = 0;

    while(sentence[i]) // the loop will be executed as long as there IS to work on
    {
        if (sentence[i] == 32) // if the syllable == space (32 is the ASCII code of space)
            counter++;

        i++;
    }

    printf("Number of the words is %d", counter+1);
    return 0;
}
```

