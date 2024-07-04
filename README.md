### Password Validation Rules:

1. **Minimum Length**:
   - The password must be at least 8 characters long.
   - If the password is shorter than 8 characters, the program will print "Not Allowed | Minimum length not followed".

2. **Starting Character**:
   - The password must not start with an alphabetic character (either uppercase or lowercase).
   - If the password starts with an alphabetic character, the program will print "Not Allowed | Should not start with an alphabet".

3. **Character Types**:
   - The password must contain at least one digit (0-9).
     - If the password does not contain any digits, the program will print "Not Allowed | Does not contain any number".
   - The password must contain a mix of lowercase and uppercase alphabetic characters.
     - If the password does not contain both lowercase and uppercase characters, the program will print "Not Allowed | Does not contain mix of lowercase and uppercase alphabets".
   - The password must contain at least one of the following special characters: `?`, `,`, `.`, `#`, `$`, `*`, `_`.
     - If the password does not contain any of these special characters, the program will print "Not Allowed | Does not contain required special characters".

4. **Allowed Special Characters**:
   - The allowed special characters are specifically defined as `?`, `,`, `.`, `#`, `$`, `*`, `_`.
   - If the password contains any other special characters not in this list, the program will print "Not Allowed | Special character not allowed".

### Program Structure:

- **Function `isSpecialChar(char ch)`**:
  - This helper function checks if a character is one of the allowed special characters. It returns `1` if the character is allowed and `0` otherwise.

- **Function `validatePassword(char *password)`**:
  - This is the main validation function. It takes the password as input and performs the following checks:
    1. **Length Check**: Verifies that the password is at least 8 characters long.
    2. **Starting Character Check**: Ensures the password does not start with an alphabet.
    3. **Character Type Checks**: Ensures the presence of at least one digit, a mix of lowercase and uppercase letters, and at least one allowed special character.
  - The function prints appropriate error messages if any of these conditions are not met and returns `0`. If all conditions are met, it returns `1`.

- **`main` Function**:
  - The `main` function prompts the user to enter a password.
  - It then calls the `validatePassword` function to check the password.
  - If the password passes all validations, it prints "Allowed". Otherwise, it prints the relevant error message provided by the `validatePassword` function.

### Example Test Cases:

1. **Input**: `1?rtyu$A`
   - **Output**: Allowed
   - **Reason**: Meets all criteria (length, mix of characters, special character, does not start with an alphabet).

2. **Input**: `$qwertY`
   - **Output**: Not Allowed | Minimum length not followed
   - **Reason**: Less than 8 characters long.

3. **Input**: `$qwertys`
   - **Output**: Not Allowed | Does not contain any number
   - **Reason**: No digit present.

4. **Input**: `$qwerty4`
   - **Output**: Not Allowed | Does not contain mix of lowercase and uppercase alphabets
   - **Reason**: Only lowercase letters and a digit, no uppercase letter.

5. **Input**: `%qwerTY4`
   - **Output**: Not Allowed | Special character not allowed
   - **Reason**: Contains `%`, which is not an allowed special character.

6. **Input**: `Alp2#tyu`
   - **Output**: Not Allowed | Should not start with an alphabet
   - **Reason**: Starts with an uppercase letter.

7. **Input**: `###1aAbB`
   - **Output**: Allowed
   - **Reason**: Meets all criteria (length, mix of characters, special character, does not start with an alphabet).
