# 7queen_problem_-c

//  Copyright © 2020 saurav tanwar. All rights reserved.
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
#define N 5
int Promising(int i);
int col[N]={0};
int count =0;
void queens(int i){
    
    int j;
    int a = Promising(i);
    if(a==1){
        if(i==N){
            for(int k=1; k<=N; k++){

                printf("%d ", col[k]);
            }
            printf("\n");
        }else{
            for(j=1;j<=N;j++){
                col[i+1] =j;
                queens(i+1);
                count++;

            }

        }
    }
}
int Promising(int i){
    int k ;
  bool flag ;
    k= 1;
    flag = 1;
    while(k<i && flag){
        if((col[i] ==col[k])||abs(col[i]-col[k])==i-k)
            flag= 0;
        k++;
    }
    return flag;
}
int main(int argc, const char * argv[]) {
    queens(0);
      printf("\n");
    printf("queen 함수 후출 %d", count);
     printf("\n");
          

    return 0;
}
