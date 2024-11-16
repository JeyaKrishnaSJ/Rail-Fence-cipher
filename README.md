# EX.NO: 2 A Rail-Fence-
# AIM:
To implement a program for encryption and decryption using rail fence transposition technique.
# ALGORITHM:
n the rail fence cipher, the plaintext is written downwards and diagonally on successive "rails" of an
imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the
message is written downwards again until the whole plaintext is written out. The message is then
read off in rows.
# PROGRAM:
```
To implement a program for encryption and decryption using rail fence transposition technique.
In the rail fence cipher, the plaintext is written downwards and diagonally on successive "rails" of an
imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the
message is written downwards again until the whole plaintext is written out. The message is then
read off in rows.
Rail-fence-cipher
AIM:
ALGORITHM :
PROGRAM:
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
int main() {
int i, j, len, rails, count, code[100][1000] = {0};
char str[1000];
printf("Enter a Secret Message\n");
fgets(str, sizeof(str), stdin);
len = strlen(str);
if (str[len - 1] == '\n') { // Remove newline from fgets
str[len - 1] = '\0';
len--;
}
printf("Enter number of rails\n");
scanf("%d", &rails);
count = 0;
j = 0;
// Fill the matrix in zig-zag (rail-fence) order
while (j < len) {
if (count % 2 == 0) { // Going down
for (i = 0; i < rails && j < len; i++) {
code[i][j] = str[j];
j++;
}
} else { // Going up
for (i = rails - 2; i > 0 && j < len; i--) {
code[i][j] = str[j];
j++;
}
}
count++;
}
for (i = 0; i < rails; i++) {
for (j = 0; j < len; j++) {
if (code[i][j] != 0) {
printf("%c", code[i][j]);
}
}
}
printf("\n");
return 0;
```
# OUTPUT:
![Screenshot 2024-11-16 112422](https://github.com/user-attachments/assets/6ca59ae0-9bb9-4a9d-a11b-c7f29f97b480)
# RESULT:
Thus the encryption amd decryption using rail fence cipher is implemented.





