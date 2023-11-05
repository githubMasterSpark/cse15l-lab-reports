PART 1:

1. FAILURE
```
  public void testReverseInPlace2() {
    int[] input1 = { 3, 6 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 6, 3 }, input1);
	}
```
2. SUCCESS
```
   public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```
3. SYMPTOM
   ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/0643db6c-329b-4299-9ae7-d0c787156994)

4. CODE
   
BEFORE
```
for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
AFTER
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < Math.floor(arr.length/2); i++) {
      int tmp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = tmp;
    } 
  }
```
Explanation:

The following fix resolves this issue by changing the code for reverseInPlace() to iterate until the halfway point. This addresses the issue by preemptively stopping the loop from fully iterating and overwriting all values before reversing the array.

-----

PART 2:

COMMAND: ```find```

1. ```--maxdepth```
   
   ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/953b35f8-ac49-427f-8404-7545afba6639)

   This command caps the amount of levels ```find``` descends before terminating the search. This is useful for checking if certain files or documents have the specfied input without listing every single matching file.

   ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/412d4956-d369-4a02-9916-12f195361734)
   
   Attempting to use ```--maxdepth 0``` reuslts in only listing the current level.

2. ```--files0-from [input]```

   ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/73c41afc-cc14-4554-8637-f13a4e597729)

   This command gets the starting point of ```find``` from the ```[input]``` as opposed to the command line. This is useful if you want to pass an arbitrary amount of starting points, as opposed to being limited by command line limitations. If the file is too large, then the name will terminate early.

   ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/515f12f5-aad5-4d2c-a496-faf49bf0dd67)

   Attempting to use this command with a directory brings an error.

3. ```--mindepth```

   ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/740f2dfe-fe04-4a75-9fb0-3af305f48aaa)

   This command processes ```find``` for all levels excluding levels less than the minimum value given. This is useful for checking if certain files or documents have the specified input within a certain amount of nested directories.

   ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/0147e2e3-bf8e-4065-9949-2970fa680d91)

   Using ```--maxdepth 1``` lists all outputs excluding the input.

4. ```--help```

   ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/a2944a0a-b822-436a-8049-88d867c2f3b8)

   This command lists all possible options you can use with ```find```. This is useful if you do not know what options are available to you.

   ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/ce35df02-1577-4c1b-844a-fdc4dde5f3f7)

   This command supercedes all other commands given. For example, attempting to use ```find``` with an argument will only bring up the output from ```find --help```.

-----

SOURCES:

https://man7.org/linux/man-pages/man1/find.1.html



