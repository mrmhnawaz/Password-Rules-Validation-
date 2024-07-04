#include <stdio.h>
#include <string.h>
#include <ctype.h>

int isSpecialChar(char ch) {
    char specialChars[] = "?.,#$*_";
    for (int i = 0; i < strlen(specialChars); i++) {
        if (ch == specialChars[i]) {
            return 1;
        }
    }
    return 0;
}

int validatePassword(char *password) {
    int length = strlen(password);
    if (length < 8) {
        printf("Not Allowed | Minimum length not followed\n");
        return 0;
    }

    if (isalpha(password[0])) {
        printf("Not Allowed | Should not start with an alphabet\n");
        return 0;
    }

    int hasDigit = 0, hasLower = 0, hasUpper = 0, hasSpecial = 0;
    for (int i = 0; i < length; i++) {
        if (isdigit(password[i])) hasDigit = 1;
        if (islower(password[i])) hasLower = 1;
        if (isupper(password[i])) hasUpper = 1;
        if (isSpecialChar(password[i])) hasSpecial = 1;
    }

    if (!hasDigit) {
        printf("Not Allowed | Does not contain any number\n");
        return 0;
    }

    if (!hasLower || !hasUpper) {
        printf("Not Allowed | Does not contain mix of lowercase and uppercase alphabets\n");
        return 0;
    }

    if (!hasSpecial) {
        printf("Not Allowed | Does not contain required special characters\n");
        return 0;
    }

    return 1;
}

int main() {
    char password[100];
    printf("Enter your password: ");
    scanf("%s", password);

    if (validatePassword(password)) {
        printf("Allowed\n");
    }

    return 0;
}
