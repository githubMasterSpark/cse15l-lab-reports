Part 1:

Subpart 1. I've been having some weird issues with my code. The program is supposed to reverse an array's contents. For some reason, it's stopping near the middle of the array and not properly iterating through the entire array. I think there's an issue with my reverseInPlace method, particularly the for loop, but I'm not sure what's going on with the loop to cause such an issue.

![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/80848f1a-bc74-4147-a76c-c762f14bd11f)
![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/cc563dd2-81ee-438a-ad79-6cf412989bed)
![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/c232bda0-ecff-456f-917b-0213d39bb719)
   
Subpart 2. Hello. There could be several different reasons behind why it is seemingly stopping in the middle. You could implement some temporary debugging lines to check what's wrong, such as `System.out.println(<your arguments here>)` along with an implementation of a `toString()` method in order to determine the potential issue. Have you also attempted to manually draw out what your code is doing?
 
Subpart 3. This was helpful in discerning what exactly was going on, and I can tell that the data being called was already overwritten previously, causing attempts to grab information from the original array to fail. In this scenario, since `arr[0]` and `arr[1]` were already overwritten, `arr[3]` and `arr[4]` would attempt to grab the new `arr[0]` and `arr[1]` values as opposed to the original values.

![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/ee6ba052-3fa6-4593-af85-a5c8499e62df)

   
Subpart 4. 

Directory Structure: ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/feb95e02-4e76-4f49-8de5-2575cbb58197)

Contents: seen in Subpart 1.

Command Line: `bash test.sh` (Contents found in Subpart 1).

Fix: The part that should be edited should be Line 7; where `int i` should only loop until `i < arr.length / 2`. In addition, there should be a line before that copies the original element to a temporary variable and a line after that overwrites the element that overwrote `arr[i]` with the temporary variable. 

![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/b3c21b4d-3854-4371-bb3e-8b786930f4c4)


----------

Part 2:

Something I learned in the second half of the quarter that I did not know before was how useful Vim was. Despite being rather inconveient to learn, it is a very helpful tool in order to make changes without the use of an interface such as VSCode, and enables quick traversal of files without having to open any external programs. While I initially (and in a way, still do) saw it as a glorified notepad app, I understand how Vim can be valuable in the workplace, especially in scenarios where you can't normally access a dedicated app in order to fix errors. What I still don't understand, however, is how one would use this without a guide, as there are a lot of unintuitive parts to Vim that would not be something one would think of upon first using Vim.
