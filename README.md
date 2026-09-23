# Manual-testing-Uber
https://docs.google.com/spreadsheets/d/1Nbdeo5XLXlpiTFXkPR99xj5NcoLVVxs5RtZ5DX9vkt8/edit?gid=0#gid=0

# EPtesting(22-09-2026)
https://docs.google.com/spreadsheets/d/1bcG3XZDY_872SiQvgOr-OMZtFsUcZEUz/edit?usp=sharing&ouid=114707436565712301551&rtpof=true&sd=true

# python(23-01-2026)
1.Write a Python program which accepts a sequence of comma separated 4 digit
binary numbers as its input and then check whether they are divisible by 5 or not.
The numbers that are divisible by 5 are to be printed in a comma separated
sequence.
Example:
0100,0011,1010,1001
Then the output should be:
1010
```
bin_number=input("Enter a binary number: ").split(",")
result=[]
for bin in bin_number:
    decimal=int(bin,2)
    if decimal %5==0:
        result.append(bin)
print(",".join(result))
```
```
output:
Enter a binary number: 0100,0011,1010,1001
1010
```
2.Write a Python program that accepts a sentence and calculate the number of
letters and digits.
Suppose the following input is supplied to the program:
hello world! 123
Then, the output should be:
LETTERS 10
DIGITS 3
```
sentence=input("Enter a sentence: ")
letter=0
digits=0

for ch in sentence:
    if ('a'<= ch <= 'z') or ('A' <= ch <='Z'):
        letter+=1
    elif('0'<= ch <='9'):
        digits+=1
print("letter",letter)
print("digits",digits)
```
```
output:
Enter a sentence: hello123
letter 5
digits 3
```
3.Write a program which can compute the factorial of a given numbers.The
results should be printed in a comma-separated sequence on a single
line.Suppose the following input is supplied to the program:8
Then, the output should be:40320
```
val=int (input())
fact=1
for i in range(1,val+1):
    fact=fact*i
print(fact)
```
```
output:
8
40320
```
