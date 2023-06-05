#include <stdio.h>
#include <conio.h>  //getch()
#include <ctype.h>  //toupper
#include <stdlib.h> //system("cls") exit(1)
#include <string.h>
int main()
{
    char choice;
mainhome:
    system("cls");
    printf("        Welcome to Yuan's Health Check!\n");
    printf("                on\n");
    printf("Finding          the         TREASURE!\n");
    printf("Press A to see the information about the software!\n");
    printf("Press T to start the test!\n");
    printf("Press Q to QUIT the program!\n");
    choice = toupper(getch());
    if (choice == 'A')
    {
        goto aboutsw;
    }
    else if (choice == 'T')
    {
        goto test;
    }
    else if (choice == 'Q')
    {
        exit(0);
    }
    else
    {
        goto mainhome;
    }
aboutsw:
    system("cls");
    printf("This software is free software: you can redistribute it and/or modify.\n");
    printf("The original author is Yuan\n");
    choice = toupper(getch());
    if (choice == 'A')
    {
        goto mainhome;
    }
    else
    {
        exit(0);
    }
test:
    system("cls");
    int count = 0;
    int score = 0;
    while (count < 2)
    {
        system("cls");
        switch (count)
        {
        case 0:
            printf("A.You do exercise every day\nB.You do exercise 2 times a week.\nC.You do exercise 1 time a week.\nD.You don't usually do exercise.\n");
            printf("Press Q to quit.\n");
            choice = toupper(getch());
            if (choice == 'A')
            {
                score += 3;
            }
            else if (choice == 'B')
            {
                score += 2;
            }
            else if (choice == 'C')
            {
                score += 1;
            }
            else if (choice == 'D')
            {
                score += 0;
            }
            else if (choice == 'Q')
            {
                goto mainhome;
            }
            else
            {
                printf("Please enter a valid answer!");
                getch();
                continue;
            }
            count++;
            break;
        case 1:
            printf("A.You eat healthy food.\nB.You eat normal food.\nC.You eat junk food.\nD.You eat rubbish.\n");
            printf("Press Q to quit.\n");
            choice = toupper(getch());
            if (choice == 'A')
            {
                score += 3;
            }
            else if (choice == 'B')
            {
                score += 2;
            }
            else if (choice == 'C')
            {
                score += 1;
            }
            else if (choice == 'D')
            {
                score += 0;
            }
            else if (choice == 'Q')
            {
                goto mainhome;
            }
            else
            {
                printf("Please enter a valid answer!");
                getch();
                continue;
            }
            count++;
            break;
        case 2:
            goto score;
        default:
            break;
        }
    }
score:
    system("cls");
    printf("Your score is %d.\n", score);
    getch();
    goto mainhome;
}