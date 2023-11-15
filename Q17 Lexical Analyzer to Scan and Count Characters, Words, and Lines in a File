#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *file;
    char filename[30];
    char ch;
    int charCount = 0, wordCount = 0, lineCount = 0, inWord = 0;

    printf("Enter the filename: ");
    scanf("%s", filename);

    file = fopen(filename, "r");

    if (file == NULL) {
        printf("Error: Could not open the file.\n");
        exit(EXIT_FAILURE);
    }

    while ((ch = fgetc(file)) != EOF) {
        charCount++;

        if (ch == '\n') {
            lineCount++;
        }

        if (ch == ' ' || ch == '\t' || ch == '\n') {
            inWord = 0;
        } else if (inWord == 0) {
            inWord = 1;
            wordCount++;
        }
    }

    fclose(file);

    printf("Character count: %d\n", charCount);
    printf("Word count: %d\n", wordCount);
    printf("Line count: %d\n", lineCount);

    return 0;
}
