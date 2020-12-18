# 01_matched_substring

### Problem:
- Given two strings, return an array of ever matching substring
- in: "te", "test"
- out: ["t", "te", "e" ]

### Questions:
- Do I need to worry about whitespace?
- Do I need to worry about multiple words?
- Do I need to worry about special characters?
- Do I need to worry about upper or lower cases being different?

### Assumptions:
- Our string is a single word with no whitespace.

- Return Value:
- What should this return?
- Should this return an empty array or a boolean value?
    - Example: "dog", "test"
    - Since there are no substring matches between "dog" and "test" should I return [] or false?


### Notes:
- Before coding walk through the problem and make notes and get a higher view of the problem.

### Planning:
- Set all strings to uppercase or lower case 
    - So I'm dealing with the same values no matter what is passed in.

- Find the substrings
- Compare the sub strings with each other
    - How do I find the substrings?
        - var1 = "te"
            - subStrings: "t", "te", "e"
        - Check for duplicates
            - !arr.includes(subString) => arr.push(subStr)
        - Check the next substring
            - str2.includes(arr[i])
                - If it does include it then we'll push it on to an array called "matched"
                - matched.push(arr[i])
            
- Return the array
- If array is empty then return false.



### Code:
```
function matchingSubstrings(str1, str2) {
    str1 = str1.toLowerCase();
    str2 = str2.toLowerCase();

    let matched = [];

    let subString1 = findSubstrings(str1);

    subString1.forEach(subStr => str2.includes(subStr)? matched.push(subStr: null))



    return matched.length == 0 ? false : matched;
}

function findSubstrings(str) {
    let arr = [];

    for (let i = 0; i < str.length; i++) {
        for (let j = i+1; j < str.length+1, j++) {
            let subString = str.slice(i, j);
            arr.includes(subString) ? null : arr.push(subStr)

        }
    }
    return arr;
}


matchingSubstrings("te", "test")

```