# LEETCODE-Strings-884
Let's walk through a dry run of your solution to the problem `uncommonFromSentences` using an example. This function is supposed to return the words that appear exactly once in the concatenation of two sentences, A and B.

### Example Input:

```
A = "apple orange banana"
B = "banana orange grape"
```

### Dry Run:
1. **Concatenate A and B**:  
   The strings `A` and `B` are concatenated with a space between them, resulting in:  
   ```
   A + ' ' + B = "apple orange banana banana orange grape"
   ```

2. **Split concatenated string into words**:  
   The concatenated string is split by spaces into an array of words:
   ```
   ["apple", "orange", "banana", "banana", "orange", "grape"]
   ```

3. **Create a frequency map (count)**:
   A `Map<String, Integer>` called `count` is created, where each word's frequency in the array is stored:
   - "apple" appears 1 time
   - "orange" appears 2 times
   - "banana" appears 2 times
   - "grape" appears 1 time
   
   So, the map would look like this:
   ```
   {
     "apple": 1,
     "orange": 2,
     "banana": 2,
     "grape": 1
   }
   ```

4. **Identify words with frequency 1**:
   We then iterate through the keys of the `count` map, adding words that have a frequency of 1 to the result list (`ans`):
   - "apple" (frequency = 1) → added to `ans`
   - "orange" (frequency = 2) → skipped
   - "banana" (frequency = 2) → skipped
   - "grape" (frequency = 1) → added to `ans`

   After this step, `ans` contains:
   ```
   ["apple", "grape"]
   ```

5. **Return result as an array**:
   Finally, the `ans` list is converted into a string array and returned:
   ```
   return new String[] {"apple", "grape"};
   ```

### Output:
For the input `A = "apple orange banana"` and `B = "banana orange grape"`, the output will be:
```
["apple", "grape"]
```

Your code works correctly by using a frequency map to determine which words are uncommon between two sentences.
