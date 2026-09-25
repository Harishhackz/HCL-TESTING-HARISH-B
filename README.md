# Manual-testing-Uber
https://docs.google.com/spreadsheets/d/1Nbdeo5XLXlpiTFXkPR99xj5NcoLVVxs5RtZ5DX9vkt8/edit?gid=0#gid=0

# EPtesting(22-09-2026)
https://docs.google.com/spreadsheets/d/1bcG3XZDY_872SiQvgOr-OMZtFsUcZEUz/edit?usp=sharing&ouid=114707436565712301551&rtpof=true&sd=true

# python(23-09-2026)
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
# Test metrics analysis

https://docs.google.com/spreadsheets/d/1OOVj0NTxNtLnHiNSCBFPtutVy5l4r0em/edit?usp=sharing&ouid=114707436565712301551&rtpof=true&sd=true

# Python scenario qns
1. Student Attendance Analysis
A college maintains the daily attendance details of its students in the form of a list containing student IDs. Some students may have attended multiple sessions on the same day. The administration wants to identify the longest continuous sequence of sessions in which no student ID is repeated. Develop a solution that determines the maximum length of such a sequence.
```
student_ids = [1, 2, 3, 1, 4, 5]
seen = set()
left = 0
maximum = 0
for right in range(len(student_ids)):
    while student_ids[right] in seen:
        seen.remove(student_ids[left])
        left += 1
    seen.add(student_ids[right])
    maximum = max(maximum, right - left + 1)
print("Maximum length:", maximum)
```
2. Online Shopping Price Analysis
An online shopping application stores the prices of products viewed by a customer during a browsing session. The customer wants to identify a continuous range of products that provides the maximum possible total discount value. Given the discount values, determine the maximum value that can be obtained from any continuous range.
```
dis=[-2,3,6,-7,4,2]
current=dis[0]
maximum=dis[0]
for i in range (1,len(dis)):
    current=max(dis[i],current+dis[i])
    maximum=max(maximum,current)
print(maximum)
```
3. Rainwater Collection System
A city installs buildings of different heights along a straight road. During rainfall, water gets collected between taller buildings. The engineering team needs to calculate the total amount of water that can remain trapped after heavy rainfall based on the heights of the buildings.
```
heights = [0, 1, 0, 2, 1, 0, 1, 3]
left = 0
right = len(heights) - 1
left_max = 0
right_max = 0
water = 0
while left < right:
    if heights[left] <= heights[right]:
        if heights[left] >= left_max:
            left_max = heights[left]
        else:
            water += left_max - heights[left]
        left += 1
    else:
        if heights[right] >= right_max:
            right_max = heights[right]
        else:
            water += right_max - heights[right]
        right -= 1
print("Trapped water:", water)
```
4. Employee Performance Analysis
A company stores the monthly performance scores of an employee for several months. The scores may contain both positive and negative values depending on the employee's performance. Management wants to identify the continuous period during which the employee achieved the highest overall performance.
```
scores = [-2, 5, -1, 3, -4]
current = scores[0]
maximum = scores[0]
for i in range(1, len(scores)):
    current = max(scores[i], current + scores[i])
    maximum = max(maximum, current)
print("Highest performance:", maximum)
```
5. Product Sales Analysis
A retail company stores the daily sales quantity of a product for several consecutive days. Due to seasonal changes, some days may have negative adjustments. The company wants to identify the period that produced the highest multiplication of sales-related values. Develop a solution to determine this maximum product.
```
num=[2,3,-2,4]
minimum=num[0]
maximum=num[0]
ans=num[0]
for i in range (1,len(num)):
    if num[i]<0:
        maximum,minimum=minimum,maximum
    minimum=min(num[i],minimum*num[i])
    maximum=max(num[i],maximum*num[i])
    ans=max(ans,maximum)
print(ans)
```
6. Customer Purchase History
An e-commerce application stores the product IDs purchased by a customer in chronological order. The same product may appear multiple times. The system needs to determine the longest sequence of consecutive purchases in which every product ID is unique.
```
purchases = ["A", "B", "C", "A", "D", "E"]
seen = set()
left = 0
maximum = 0
for right in range(len(purchases)):
    while purchases[right] in seen:
        seen.remove(purchases[left])
        left += 1
    seen.add(purchases[right])
    maximum = max(maximum, right - left + 1)
print("Longest unique sequence:", maximum)
```
7. Bank Transaction Analysis
A bank stores transaction amounts for a customer's account. A continuous group of transactions may add up to a specific target amount. The auditing system needs to determine how many different continuous transaction groups produce exactly the specified amount.
```
transactions = [1, 2, 3, -2, 5]
target = 3
count = 0
prefix_sum = 0
frequency = {0: 1}
for value in transactions:
    prefix_sum += value
    required = prefix_sum - target
    if required in frequency:
        count += frequency[required]
    frequency[prefix_sum] = frequency.get(prefix_sum, 0) + 1
print("Number of groups:", count)
```
8. Employee Skill Grouping
A company receives a list of employee skill codes represented as strings. Employees having the same set of characters in their skill codes belong to the same skill category, even if the characters appear in a different order. The HR system needs to organize employees into appropriate skill groups.
```
skills = ["eat", "tea", "tan", "ate", "nat", "bat"]
groups = {}
for skill in skills:
    key = "".join(sorted(skill))
    if key not in groups:
        groups[key] = []
    groups[key].append(skill)
print(list(groups.values()))
```
9. Network Packet Analysis
A network monitoring system receives packet identifiers in chronological order. The system must determine the longest sequence of consecutive packets whose identifiers form a continuous numerical sequence, regardless of their original order in the incoming data
```
packets = [100, 4, 200, 1, 3, 2]
numbers = set(packets)
maximum = 0
for number in numbers:
    if number - 1 not in numbers:
        current = number
        length = 1
        while current + 1 in numbers:
            current += 1
            length += 1
        maximum = max(maximum, length)
print("Longest consecutive sequence:", maximum)
```
10. Hospital Appointment Scheduling
A hospital receives appointment requests represented by starting and ending times. Some appointments overlap with each other. The scheduling system needs to combine overlapping appointment periods so that the final schedule contains only non-overlapping time ranges
```
appointments = [[1, 3], [2, 6], [8, 10], [9, 12]]
appointments.sort()
merged = []
for appointment in appointments:
    if not merged or appointment[0] > merged[-1][1]:
        merged.append(appointment)
    else:
        merged[-1][1] = max(merged[-1][1], appointment[1])
print("Merged appointments:", merged)
```





