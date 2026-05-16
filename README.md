# Persentage-calculator-
I am make this calculator for my teacher's.

#include <stdio.h>
#include <string.h>

void s1() { printf("\nEnter DS marks:"); }
void s2() { printf("\nenter OS marks:"); }
void s3() { printf("\nEnter DBMS marks:"); }
void s4() { printf("\nEnter IT marks:"); }
void s5() { printf("\nEnter Ic Marks:"); }
void s6() { printf("\nEnter EPA marks:"); }
void s7() { printf("\nEnter MATH marks:"); }

float check(float n) {
    float num;
    char input[100];
    char extra;

    while (1) {
        
        if (n == 1) s1();
    else if (n == 2) s2();
   else if (n == 3) s3();
    else if (n == 4) s4();
      else if (n == 5) s5();
      else if (n == 6) s6();
    else if (n == 7) s7();
    

        fgets(input, sizeof(input), stdin);

        if (sscanf(input, "%f %c", &num, &extra) == 1) {
            
            if (num >= 0 && num <= 100) {
                return num;
            } else {
                printf("Invalid range! (0-100 only)\n");
            }

        } else {
            printf("Wrong input! Only numbers allowed\n");
        }
    }
}

char* g(float a) {
    if (a > 24)
        return "pass";
    else
        return "fail";

}

int main(){
    
    float ds, os, dbms, it, ic, epa, math;

    ds = check(1);
    os = check(2);
     dbms = check(3);
    it = check(4);

    ic = check(5);
    epa = check (6);
    
    math = check (7);
    
    float tmark, p;
    
    tmark = ds+os+it+ic+dbms+epa+math;
    
    p=tmark / 7;
    
    printf("\n--- Marks ---\n");
    printf("DS:  \t%.2f\t%s\nOS:  \t%.2f\t%s\nDBMS:\t%.2f\t%s\nIT:  \t%.2f\t%s\nIC:  \t%.2f\t%s\nEPA: \t%.2f\t%s\nMATH:\t%.2f\t%s\n",
           ds, g(ds), os, g(os), dbms, g(dbms), it,g(it),ic,g(ic), epa,g(epa), math,g(math));
       printf("total marks:%2f  \ntotal percentage:%2f %",tmark,p);

    return 0;
}
