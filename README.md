# C-Practice-8

#include <stdio.h>
#include <string.h>

long long factorial(int n) {
    long long result = 1;
    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
}

int main() {
    char word[15];
    scanf("%s", word);
    int len = strlen(word);
    long long count = factorial(len);
    for (int i = 0; i < len; i++) {
        int freq[256] = {0};
        for (int j = i; j < len; j++) {
            freq[(int)word[j]]++;
        }
        for (int j = 0; j < 256; j++) {
            if (freq[j] > 1) {
                count /= factorial(freq[j]);
            }
        }
    }
    printf("%lld\n", count);
    return 0;
}
