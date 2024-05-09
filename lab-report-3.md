# Lab Report 3

## Part 1
The bug I have chosen is shown in the code below.
1. Failure Inducing Input:
```
public class ArrayTests {
	@Test 
	public void testReverseInPlaceFailure() {
    int[] input1 = {1, 2, 3, 4};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{4, 3, 2, 1}, input1);
	}
}
```
2. Input that Passes:
```
public class ArrayTests {
	@Test 
	public void testReverseInPlacePass() {
    int[] input1 = {1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{1}, input1);
	}
}
```
3. Symptom:

5. Buggy and Fixed Code:
Buggy Code:
```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
}
```
Fixed Code:
```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
  }
}
```
5. Bug Fix Reasoning:
The fix addresses the issue because without the fix, the second half of the array's elements will not be set to the first half, since the first half will have been overwritten by the second half. Instead, the fix stores a copy of the array, so that the reversal can be performed by iterating over the copy and setting the original array to have reversed elements, and this will avoid overwriting the second half of the array.
