Part 1:

Subpart 1. I've been having some weird issues with my code. The program is supposed to reverse an array's contents. For some reason, I'm getting an `ArrayIndexOutOfBoundsException`. I think there's an issue with my reverseInPlace method, particularly the for loop, but I'm not sure what's going on with the loop to cause such an issue.

![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/ef16db80-10d9-4672-99ee-c400402aa2cf)

   
Subpart 2. Hello. There could be several different reasons behind the exception. I recommend checking through your `reverseInPlace()` method again in order to determine the potential issue, as the exception being thrown points to there being an issue in line 9. Have you also looked through any `.sh` files you may be running?
 
Subpart 3. This was helpful in discerning what was going on, and I found that I was setting the wrong indices to replace `arr[i]`. By fixing lines 9 and 10, I was able to have it properly go through each index up until the loop ended.

![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/03c4d679-be4b-41f6-b2bc-b5ec87f3ef0d)
   
Subpart 4. 

Directory Structure: ![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/feb95e02-4e76-4f49-8de5-2575cbb58197)

Contents: 
![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/ef16db80-10d9-4672-99ee-c400402aa2cf)
![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/cc563dd2-81ee-438a-ad79-6cf412989bed)
![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/c232bda0-ecff-456f-917b-0213d39bb719)

Command Line: `bash test.sh` (Contents of bash.sh found above).

Fix: The parts that should be edited are lines 9 and 10. These should have `arr[arr.length - i - 1]` as opposed to `arr[arr.length - i]` in order to prevent an ArrayIndexOutOfBoundsException, having `arr[0]` be replaced by `arr[4]` instead of `arr[5]`, an index that doesn't exist.

![image](https://github.com/githubMasterSpark/cse15l-lab-reports/assets/147002814/b3c21b4d-3854-4371-bb3e-8b786930f4c4)


----------

Part 2:

Something I learned in the second half of the quarter that I did not know before was how useful Vim was. Despite being rather inconveient to learn, it is a very helpful tool in order to make changes without the use of an interface such as VSCode, and enables quick traversal of files without having to open any external programs. While I initially (and in a way, still do) saw it as a glorified notepad app, I understand how Vim can be valuable in the workplace, especially in scenarios where you can't normally access a dedicated app in order to fix errors. What I still don't understand, however, is how one would use this without a guide, as there are a lot of unintuitive parts to Vim that would not be something one would think of upon first using Vim.
