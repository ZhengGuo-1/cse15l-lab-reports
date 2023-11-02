# Blog Post for Bugs and Commands
**I am Zheng Guo, and this is the third lab report.**
**In this report, I will introduce a bug from week 4's lab and explain the failure-inducing input, symptom and code fixing. Also I will introduce a specific command find and gives several examples.**
# Part 1 Bugs(reverseInPlace in ArrayExamples.java)
The code for the reverseInPlace method: 
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```

---

The code for the test with inputs that induces bugs: 
```
@Test
public void testReverseInPlace2() {
    int[] input1 = {1,2,3,4,5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{5,4,3,2,1}, input1);
}
```
Failure-inducing input:{1,2,3,4,5}

---

The code for the test with inputs that does not induce bugs: 
```
@Test 
public void testReverseInPlace() {
    int[] input1 = {3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3}, input1);
}
```
An input that doesn’t induce a failure: {3}

---

The symptom, as the output of running the tests:
![image](截屏2023-11-02 下午3.56.47.png)

---

Code before:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```

Code after:
```
static void reverseInPlace(int[] arr) {
    int[]temporary = Arrays.copyOf(arr, arr.length);
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = temporary[arr.length - i - 1];
    }
}
```
Reason why the fix addresses the issues:
The problem for the reverseInPlace is that the method directly change value in the list, changing the value for index 0 to the last element, and value for index 1 to the second last element, when iterates the value for index 3, it should replace this value with the original 2 in the index 1. However, value for index 1 is not 2 anymore. The reason why the fix addresses the issues is becasue it introduces a copy of the original array, and change the array itself based on the reverse order of the copy. Since the copy version is not changed, the issues occured in the original code will not happen. 

