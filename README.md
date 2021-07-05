# Technical Interview
- Use Node.js 

# Part #1
Write a string templating engine in Javascript. You need to replicate the functionality of Javascript's backtick strings that allow you inject arbitrary data into a string \`${variable}\`, but instead use the popular handlebars format "{{variable}}"
- Create a function that accepts a string template and an object of replacement data. 
- The function should map the keys from the object and look for corresponding replacements inside the template string. For example, the template "Hello {{name}}!" with the replacement data {name: "Kyle"} should return the result "Hello Kyle!".
- If a key exists more than once in the template, it should be replaced in all instances. For example "Hello {{name}}! '{{name}}' is a great name." with the replacement data {name: "Kyle"}, should return "Hello Kyle! 'Kyle' is a great name."
- Write tests for your function. Use the above examples as tests and write 1 additional test that tests a longer string with a few replacement keys of different data types.

# Part #2
Process the template replacement data for a custom formatted output.
- If the replacement is a string, limit the length to 20 characters, remove anything after the 20th character and replace it with ellipsis '...'.
- If the replacement is an integer, don't add any additional formatting. 
- If the replacement is a float, limit the float precision to 2 decimal places. 
- If the replacement is a boolean, when true replace it with "Yes", and when false replace it with "No".
- If the replacement is an object or an array, format so that all the object data is readable in the output string. 
- If the replacement is a function, replace it with the string of the function code, but limit the length of the string representation to 10 characters, remove anything after the 10th character and replace it with ellipsis '...'.
- Write tests.

# Bonus
Write a recursive function that converts an object or an array to a string, but automatically limits the length of any array to a maximum of 2 items and limits the overall depth of the object to a maximum of 2 levels. If data is trimmed off, add ellipsis '...' to indicate that data was trimmed. Note that a new level is only entered into when the recursive function encouters an object.

For example, the input:
```js
{
    // Depth Level 1
    a: [ 
        { 
            // Depth Level 2
            b: [1, 2, 3, 4, 5] 
        }, 
        { 
            c: { 
                // Depth Level 3
                d:true 
            },
        },
        { 
            // Depth Level 2
            e: true 
        },
        { 
            // Depth Level 2
            f: true 
        },
    ] 
}
```

Should result in the output string:
```js
`{
    a: [ 
        { 
            b: [ 1, 2, ... ] 
        }, 
        { 
            c: { ... } 
        },
        ...
    ] 
}`
```
- Include this function in your template string engine to process any objects or arrays that are included as replacement data.
- Ensure correct newline and tabspaces for "pretty" output.
- Write tests.
