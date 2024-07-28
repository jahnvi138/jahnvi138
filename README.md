#include <stdio.h>
double bal = 0;
double amt;
int choice;
void option()
{
    printf("1.CHECKBAL\n2.WITHDRAW\n3.DEPOSIT\n4.FOR EXIT\n\nchoose any one option\n");
    scanf("%d", &choice);
}
void checkbal()
{
    printf("YOUR CURRENT BALANCE IS: %0.2lf\n", bal);
    option();
}
 
void withdraw()
{
    printf("HOW MUCH MONEY DO YOU WANT TO WITHDRAW\n");
    scanf("%lf", &amt);
    printf("BEFORE WITHDRAW:%0.2lf\n", bal);

    double current_bal = bal - amt;
    if (amt > bal)
    {
        printf("OVERDRAFT!\n");
    }
    else
    {
        printf("AFTER WITHDRAW: %0.2lf\n ", current_bal);
    }
    option();
}

void deposit()
{
    printf("HOW MUCH MONEY DO YOU WANT TO DEPOSIT\n ");

    scanf("%lf", &amt);
    printf("BEFORE DEPOSIT YOUR BALANCE IS:%0.2lf\n\n", bal);
    printf("NOW YOUR UPDATED BALANCE IS:%0.2lf\n", amt);

    option();
}
void for_exit()
{
    printf("THANKS FOR VISIT!!");
}

int main()
{
    option();

    switch (choice)
    {
    case 1:
        checkbal();
        break;
    case 2:
        withdraw();
        break;
    case 3:
        deposit();
        break;
    case 4:
        for_exit();
        break;
    default:
        printf("YOU CHOOSE WRONG OPTION...TRY AGAIN!!!\n");
    }

    return 0;
}
