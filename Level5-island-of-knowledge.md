# code-fights-solutions
 ## Test 1
Call two arms equally strong if the heaviest weights they each are able to lift are equal.
Call two people equally strong if their strongest arms are equally strong (the strongest arm can be both the right and the left), and so are their weakest arms.
Given your and your friend's arms' lifting capabilities find out if you two are equally strong.

**Example**

    For yourLeft = 10, yourRight = 15, friendsLeft = 15 and friendsRight = 10, the output should be
    areEquallyStrong(yourLeft, yourRight, friendsLeft, friendsRight) = true;
    
    For yourLeft = 15, yourRight = 10, friendsLeft = 15 and friendsRight = 10, the output should be
    areEquallyStrong(yourLeft, yourRight, friendsLeft, friendsRight) = true;
    
    For yourLeft = 15, yourRight = 10, friendsLeft = 15 and friendsRight = 9, the output should be
    areEquallyStrong(yourLeft, yourRight, friendsLeft, friendsRight) = false.

**Input/Output**
   * [time limit] 4000ms (py3)
   * [input] integer yourLeft. A non-negative integer representing the heaviest weight you can lift with your left arm. Guaranteed constraints: 0 ≤ yourLeft ≤ 20.

    * [input] integer yourRight. A non-negative integer representing the heaviest weight you can lift with your right arm. Guaranteed constraints: 0 ≤ yourRight ≤ 20.

    * [input] integer friendsLeft. A non-negative integer representing the heaviest weight your friend can lift with his or her left arm. Guaranteed constraints: 0 ≤ friendsLeft ≤ 20.

    * [input] integer friendsRight. A non-negative integer representing the heaviest weight your friend can lift with his or her right arm. Guaranteed constraints: 0 ≤ friendsRight ≤ 20.

    * [output] boolean. true if you and your friend are equally strong, false otherwise.


```python
def areEquallyStrong(yourLeft, yourRight, friendsLeft, friendsRight):
    if max(yourLeft, yourRight) == max(friendsLeft, friendsRight) and min(yourLeft, yourRight) == min(friendsLeft, friendsRight):
        return True
    else:
        return False
 ```       
    
      
## Test 2
Given an array of integers, find the maximal absolute difference between any two of its adjacent elements.

**Example**
      
    For inputArray = [2, 4, 1, 0], the output should be arrayMaximalAdjacentDifference(inputArray) = 3.

**Input/Output**
    * [time limit] 4000ms (py3)

    * [input] array.integer inputArray. Guaranteed constraints: 3 ≤ inputArray.length ≤ 10, -15 ≤ inputArray[i] ≤ 15.

    * [output] integer. The maximal absolute difference
    
```python
    def arrayMaximalAdjacentDifference(inputArray):
    y=[]
    for i in range(len(inputArray)-1):
        x=abs(inputArray[i]-inputArray[i+1])
        y.append(x)
    return max(y)
    ```
    
## Test 3
An IP address is a numerical label assigned to each device (e.g., computer, printer) participating in a computer network that uses the Internet Protocol for communication. There are two versions of the Internet protocol, and thus two versions of addresses. One of them is the IPv4 address.
IPv4 addresses are represented in dot-decimal notation, which consists of four decimal numbers, each ranging from 0 to 255 inclusive, separated by dots, e.g., 172.16.254.1.
Given a string, find out if it satisfies the IPv4 address naming rules.

**Example**
     
    For inputString = "172.16.254.1", the output should be
    isIPv4Address(inputString) = true;

    For inputString = "172.316.254.1", the output should be
    isIPv4Address(inputString) = false.
    316 is not in range [0, 255].

    For inputString = ".254.255.0", the output should be
    isIPv4Address(inputString) = false.

    There is no first number.
    
  **Input/Output**
  
     * [time limit] 4000ms (py)

     * [input] string inputString. Guaranteed constraints: 1 ≤ inputString.length ≤ 30.

     * [output] boolean
      true if inputString satisfies the IPv4 address naming rules, false otherwise.
      
 ```python 
    def isIPv4Address(inputString):
    s=inputString.split(".")
    if len(s)!=4:
        return False
    for i in s:
        if not i.isdigit():
            return False
        x=int(i)
        if x<0 or x>255:
            return False
    return True

  


   
