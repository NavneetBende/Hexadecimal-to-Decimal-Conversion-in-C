# Hexadecimal-to-Decimal-Conversion-in-C

Hexadecimal to Decimal Conversion
Here, in this section, we will discuss the C program for Hexadecimal to decimal conversion. A decimal number can be attained by multiplying every digit of binary digit with a power of 16 and adding each multiplication outcome. The power of the integer starts from 0 and counts to n-1 where n is assumed as the overall digits of integers in the HexaDecimal number.

Ex:-  (1C6F)16 = 1 * 163 + 12 * 162 + 6 * 161 + 15 * 160
4096 + 3072 + 96 + 15 = (7279)10
HexaDecimal to Decimal in C new
While loop in C
How Does HexaDecimal Work?
Hexadecimal has numbers in the range of [0, 15]. With (0 – 9) represented as is and the others represented with alphabets.

A – 10
B – 11
C – 12
D – 13
E – 14
F – 15
Method 1
For a user input num. This requires you to know ASCII values, please check the ASCII table here 

The method uses the following – 

Linear iterative loop spanning the character array
Two sub-if-else loops to decide if the current character is a digit or alphabet
Mathematical calculation to convert to decimal
Code in C
Run

#include
#include
#include

int convert(char hex[])
{
    int len = strlen(hex);
    int decimal = 0, pos = 0;
    
    for(int i = len - 1; i >= 0; i--)
    {
        // if given index value is a digit (0 - 9)
        if (hex[i] >= '0' && hex[i] <= '9') { // if character is in range '0' - '9' // can convert char value to its int value // by subtracting 48 (Refer Ascii table) as ASCII val 0 : 48 int digit = hex[i] - 48; decimal += digit * pow(16, pos); pos++; } // if given index is char in range [A, F] else if (hex[i] >= 'A' && hex[i] <= 'F') 
        { 
            // if character is in range 'A' - 'F' 
            // can convert char value to its int value 
            // by subtracting 55 (Refer Ascii table) as 
            // ASCII val A : 65 and A must result 10 as value 
            int digit = hex[i] - 55; 
            decimal += digit * pow(16, pos); 
            pos++; 
        } 
    } 
    return decimal; 
}
int main()
{
char hex[20];
scanf("%[^\n]", &hex);

printf("%d",convert(hex));
return 0;
}
Output
1C
28
