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
   
   ```
   $ find technical/ -maxdepth 1
   technical/
   technical/911report
   technical/biomed
   technical/government
   technical/plos
   ```

   This command caps the amount of levels ```find``` descends before terminating the search. This is useful for checking if certain files or documents have the specfied input without listing every single matching file.

   ```
   $ find technical/ -maxdepth 0
   technical/
   ```
   
   Attempting to use ```--maxdepth 0``` reuslts in only listing the current level, as the amount of levels ```-maxdepth``` descends would be 0. This could be useful in order to check that the directory exists without using a ```ls``` command that would require one to search manually.

2. ```--files0-from [input]```

   ```
   $ find -files0-from technical/plos/journal.pbio.0020112.txt
   find: ‘\r\n  \r\n    \r\n      \r\n        \r\n        For the estimated 800 million people, living largely in developing countries, without\r\n        enough food to eat, the main food risk is starvation.
   ```

(output shortened due to length)

   This command gets the starting point of ```find``` from the ```[input]``` as opposed to the command line. This is useful if you want to pass an arbitrary amount of starting points, as opposed to being limited by command line limitations. If the file is too large, then the name will terminate early.

   ```
$ find -files0-from technical/government/About_LSC/CONFIG_STANDARDS.txt
	within the state promote the system's ability and capacity to\r\ndevelop, nurture, promote, recruit and retain strong and effective\r\nstaff and leaders who are diverse and culturally\r\ncompetent?\r\n\r\n\r\n\r\n\r\n\r\n\r\n\r\n’: File name too long
   ```

   Due to the nature of how the output is displayed, this could also be used to view Markdown formatting. This could be useful if you're trying to scan through in order to check for errors in formatting, though it is limited by the output having a character limit.

3. ```--mindepth```

   ```
   $ find technical/ -mindepth 3
   technical/government/About_LSC/Comments_on_semiannual.txt
   technical/government/About_LSC/commission_report.txt
   technical/government/About_LSC/conference_highlights.txt
   technical/government/About_LSC/CONFIG_STANDARDS.txt
   technical/government/About_LSC/diversity_priorities.txt
   technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
   ```

(output shortened due to length)

   This command processes ```find``` for all levels excluding levels less than the minimum value given. This is useful for checking if certain files or documents have the specified input within a certain amount of nested directories.

   ```
   $ find technical/plos  -mindepth 1
technical/plos/journal.pbio.0020001.txt
technical/plos/journal.pbio.0020010.txt
technical/plos/journal.pbio.0020012.txt
technical/plos/journal.pbio.0020013.txt
technical/plos/journal.pbio.0020019.txt
technical/plos/journal.pbio.0020028.txt
   ```

(output shortened due to length)

   Using ```--mindepth 1``` lists all outputs excluding the input. This is useful for checking for any nested files and directories without listing the parent directory.

4. ```--mtime```

   ```
   $ find technical/plos -mtime 0
   technical/plos
   technical/plos/journal.pbio.0020001.txt
   technical/plos/journal.pbio.0020010.txt
   technical/plos/journal.pbio.0020012.txt
   technical/plos/journal.pbio.0020013.txt
   technical/plos/journal.pbio.0020019.txt
   technical/plos/journal.pbio.0020028.txt
   technical/plos/journal.pbio.0020035.txt
   ```

   This command lists all files and directories modified within the specified time divided by 24, tracking days. This is useful for checking any files and directories that have been changed.

   ```
   $ find technical/biomed -mindepth 1 -mtime 0
   technical/biomed/1468-6708-3-1.txt
   technical/biomed/1468-6708-3-10.txt
   technical/biomed/1468-6708-3-3.txt
   technical/biomed/1468-6708-3-4.txt
   technical/biomed/1468-6708-3-7.txt
   technical/biomed/1471-2091-2-10.txt
   ```

   This command can also be combined with other commands in order to refine listing. This can be useful to check specific conditions that may overlap without having to do each command seperatetly.

-----

SOURCES:

https://man7.org/linux/man-pages/man1/find.1.html

All four commands found were provided from this source.



