# Ex--5-Rail-Fence-Program
# DATE:08/04/2025

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
#include<stdio.h>
#include<string.h>
int main() {
    int i, j, len, rails, count, code[100][1000];
    char str[1000];
    printf("Enter a Secret Message\n");
    fgets(str, sizeof(str), stdin);
    len = strlen(str);
    if(str[len-1] == '\n') str[len-1] = '\0';
    len = strlen(str);
    printf("Enter number of rails\n");
    scanf("%d", &rails);
    for(i = 0; i < rails; i++)
        for(j = 0; j < len; j++)
            code[i][j] = 0;
    count = 0;
    j = 0;
    while(j < len) {
        if(count % 2 == 0) {
            for(i = 0; i < rails && j < len; i++)
                code[i][j] = (int)str[j++];
        } else {
            for(i = rails - 2; i > 0 && j < len; i--)
                code[i][j] = (int)str[j++];
        }
        count++;
    }
    for(i = 0; i < rails; i++)
        for(j = 0; j < len; j++)
            if(code[i][j] != 0)
                printf("%c", code[i][j]);
    printf("\n");
    return 0;
}
```

# OUTPUT
![image](https://github.com/user-attachments/assets/b0bb99e6-5e76-4018-9377-db16054c337c)



# RESULT
THE ABOVE PROGRAM WAS EXCUTE SUCCESSFULLY
