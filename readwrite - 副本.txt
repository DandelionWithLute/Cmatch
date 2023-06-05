#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <conio.h>
#include <ctype.h>

int filewrite()
{
    FILE *fp;
    char name[1024];
    char major[1024];
    int age;
    scanf("%s %d %s", &name, &age, &major);
    fp = fopen("file.txt", "a");
    fprintf(fp, "%s\t%d\t%s\n", name, age, major);
    fclose(fp);
    getch();
    return (0);
}

int fileread()
{
    FILE *fp;
    int c;

    fp = fopen("file.txt", "r");
    while (1)
    {
        c = fgetc(fp);
        if (feof(fp))
        {
            break;
        }
        printf("%c", c);
    }
    fclose(fp);
    getch();
    return (0);
}

int main()
{
    goto home;
home:
    printf("Press W to write\n");
    printf("Press R to Read\n");
    printf("Press Q to Quit\n");
    char choice = toupper(getch());
    while (1)
    {
        if (choice == 'W')
        {
            goto write;
        }
        else if (choice == 'R')
        {
            goto read;
        }
        else if (choice == 'Q')
        {
            exit(1);
        }
    }
write:
    printf("Please enter your name, age and major(abbr).\n");
    filewrite();
    goto home;
read:
    printf("Name\tAge\tMajor\n");
    fileread();
    goto home;
}