# DAT250: Software Technology Experiment Assignment 4

## Experiment 2

### Technical problems with the assignment
I had a problem figuring out how to solve this test case:
```
@Test
    void testNonExistingTodo() {
        final long todoId = 9999L;
        // Execute get request
        String result = doGetRequest(todoId);

        // Expect a appropriate result message.
        assertThat(result, containsString(String.format(TODO_WITH_THE_ID_X_NOT_FOUND, todoId)));

        // Execute delete request
        result = doDeleteRequest(todoId);

        // Expect a appropriate result message.
        assertThat(result, containsString(String.format(TODO_WITH_THE_ID_X_NOT_FOUND, todoId)));
    }
```
### A link to the code
https://github.com/Mamo-00/dat250-expass4.git


but i finally found out how to solve it:
```
return new ResponseEntity<>(String.format(TODO_WITH_THE_ID_X_NOT_FOUND, id), HttpStatus.NOT_FOUND);
```
