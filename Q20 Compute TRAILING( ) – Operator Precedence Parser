#include <stdio.h>
#include <string.h>

#define MAX_RULES 10
#define MAX_SYMBOLS 10

char rules[MAX_RULES][MAX_SYMBOLS];

int isTerminal(char symbol) {
    return (symbol >= 'a' && symbol <= 'z') || (symbol >= 'A' && symbol <= 'Z');
}

void computeTrailing(char nonTerminal, int index) {
    int length = strlen(rules[index]);
    for (int i = length - 1; i >= 0; i--) {
        char symbol = rules[index][i];
        if (isTerminal(symbol)) {
            printf("Trailing(%c) = %c\n", nonTerminal, symbol);
            break;
        } else if (symbol != nonTerminal) {
            computeTrailing(symbol, i);
        }
    }
}

int main() {
    int numProductions;
    printf("Enter the number of productions: ");
    scanf("%d", &numProductions);

    printf("Enter the productions:\n");
    for (int i = 0; i < numProductions; i++) {
        printf("Production %d: ", i + 1);
        scanf("%s", rules[i]);
    }

    printf("Compute Trailing for:\n");
    for (int i = 0; i < numProductions; i++) {
        computeTrailing(rules[i][0], i);
    }

    return 0;
}
