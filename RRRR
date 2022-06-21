#include <stdio.h>
#include <ctype.h>
#include<termios.h>
#include<unistd.h>
int getch()
{
    struct termios oldt, newt;
    int c;
    tcgetattr(STDIN_FILENO, &oldt);
    newt = oldt;
    newt.c_lflag &= ~(ICANON | ECHO);
    tcsetattr(STDIN_FILENO, TCSANOW, &newt);
    c = getchar();
                return c;
}
int main()
{
    unsigned char c;
    while (c != 0x50)
    {
        c = getch();
        if (isalnum(c))
            printf("%x ", c);
        else
            printf("%c ", c);
    }
    return 0;
}
