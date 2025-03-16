#include <stdio.h>

int main() {
    int n, i, wt = 0, tat = 0;
    printf("Enter number of processes: ");
    scanf("%d", &n);
    int bt[n];
    
    printf("Enter Burst Time for each process:\n");
    for (i = 0; i < n; i++) {
        printf("P%d: ", i + 1);
        scanf("%d", &bt[i]);
    }
    
    printf("\nProcess\tBT\tWT\tTAT\n");
    for (i = 0; i < n; i++) {
        printf("P%d\t%d\t%d\t%d\n", i + 1, bt[i], wt, wt + bt[i]);
        tat += wt + bt[i];
        wt += bt[i];
    }
    
    printf("\nAvg WT: %.2f", (float)tat / n - (float)wt / n);
    printf("\nAvg TAT: %.2f\n", (float)tat / n);
    return 0;
}
