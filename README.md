# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

### Name:M.Vetrivel
### Register Number: 212225040487
### Date: 28-10-2026

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char PT[100];
    int key[2][2], i, a, b;
    int x, y;

    printf("Enter the plaintext ");
    scanf("%99s", PT);

    for (i = 0; PT[i] != '\0'; i++)
        PT[i] = toupper((unsigned char)PT[i]);

    int len = strlen(PT);

    if (len % 2 != 0)
    {
        printf("Plaintext length must be even.\n");
        return 1;
    }

    printf("Enter the 2x2 key matrix:\n");
    for (i = 0; i < 2; i++)
        for (int j = 0; j < 2; j++)
            scanf("%d", &key[i][j]);

    printf("Encrypted text: ");

    for (i = 0; i < len; i += 2)
    {
        a = PT[i] - 'A';
        b = PT[i + 1] - 'A';

        x = (key[0][0] * a + key[0][1] * b) % 26;
        y = (key[1][0] * a + key[1][1] * b) % 26;

        printf("%c%c", x + 'A', y + 'A');
    }

    printf("\n");

    return 0;
}

```

## OUTPUT

![alt text](OUTPUT.png)

## RESULT

The C program to implement the hill cipher substitution techniques is completed sucessfully. 
