#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char password[100];
    int length, hasUpper = 0, hasLower = 0;
    int hasDigit = 0, hasSpecial = 0;

    printf("===== Password Strength Checker =====\n");
    printf("Enter your password: ");
    scanf("%s", password);

    length = strlen(password);

    for (int i = 0; i < length; i++) {
        if (isupper(password[i]))
            hasUpper = 1;
        else if (islower(password[i]))
            hasLower = 1;
        else if (isdigit(password[i]))
            hasDigit = 1;
        else
            hasSpecial = 1;
    }

    printf("\nPassword Analysis:\n");

    if (length < 6) {
        printf("❌ Weak Password (Too short)\n");
    } else if (hasUpper && hasLower && hasDigit && hasSpecial) {
        printf("✅ Strong Password\n");
    } else {
        printf("⚠️ Medium Password\n");
        printf("Suggestions:\n");
        if (!hasUpper) printf("- Add uppercase letters\n");
        if (!hasLower) printf("- Add lowercase letters\n");
        if (!hasDigit) printf("- Add digits\n");
        if (!hasSpecial) printf("- Add special characters\n");
    }

    return 0;
}# Password-strength-checker-
Password strength checker
