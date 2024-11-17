#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#define MAX 100

// Structure to represent a patient
typedef struct {
    char name[50];
    int age;
    int priority;
} Patient;

Patient priorityQueue[MAX];
int size = 0;

// Function to insert a patient based on priority
void enqueue(char name[],int age, int priority) {
    if (size >= MAX) {
        printf("Queue is full, cannot register more patients.\n");
        return;
    }
    int i;
    for (i = size - 1; (i >= 0 && priorityQueue[i].priority > priority); i--) {
        priorityQueue[i + 1] = priorityQueue[i];
    }

    strcpy(priorityQueue[i + 1].name, name);
    priorityQueue[i + 1].priority = priority;
    priorityQueue[i + 1].age = age;
    size++;
}

// Function to remove the patient with the highest priority
void dequeue() {
    if (size == 0) {
        printf("No patients to treat.\n");
        return;
    }
    printf("Patient to be treated: %s, Age: %d (Severity: %d)\n", priorityQueue[0].name, priorityQueue[0].age, priorityQueue[0].priority);
    for (int i = 0; i < size - 1; i++) {
        priorityQueue[i] = priorityQueue[i + 1];
    }
    size--;
}

// Function to display the patients
void displayPatients() {
    if (size == 0) {
        printf("No patients in the queue.\n");
        return;
    }
    printf("Current queue of patients:\n");
    for (int i = 0; i < size; i++) {
        printf("Name: %s, Age: %d (Severity: %d)\n",priorityQueue[i].name, priorityQueue[i].age, priorityQueue[i].priority);
    }
}

int main() {
    int choice;
    char name[50];
    int age;
    int priority;

    while (1) {
        printf("\nHospital Management System\n");
        printf("1. Add a patient\n");
        printf("2. Treat a patient\n");
        printf("3. View Patient Queue\n");
        printf("4. Exit\n");
        printf("Enter your choice : ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter patient name : ");
                scanf("%s", name);
                printf("Enter patient age : ");
                scanf("%d", &age);
                printf("Enter condition severity (1-5, 1 is most severe) : ");
                scanf("%d", &priority);
                enqueue(name, age, priority);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                displayPatients();
                break;
            case 4:
                printf("------THANKYOU------");
                exit(0);
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }
    return 0;
}
