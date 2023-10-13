chess
411221248

```c=
#include<stdio.h>
char chess[8][8];
char input;
void check(short y,short x){
    int c=0;
    int d=0;
    for (int i = x+1; i < 8; i++){

        if(chess[y][i]==input){
            break;
        }
        if(chess[y][i]!=input&&chess[y][i]!='0'){
            c=1;
        }
        if(chess[y][i]=='0'){
            if(c==1){
                chess[y][i]='x';
            }
            break;

        }
    }
    c=0;
    for (int i = x-1; i >-1; i--){
        if(chess[y][i]==input){
            break;
        }
        if(chess[y][i]!=input&&chess[y][i]!='0'){
            c=1;
        }
        if(chess[y][i]=='0'){
            if(c==1){
                chess[y][i]='x';
            }
            break;
        }
    }
    c=0;
    for (int i = y-1; i >-1; i--){

        if(chess[i][x]==input){
            break;
        }
        if(chess[i][x]!=input&&chess[i][x]!='0'){
            c=1;
        }
        if(chess[i][x]=='0'){
            if(c==1){
                chess[i][x]='x';
            }
            break;
        }
    }
    c=0;
    for (int i = y+1; i <8; i++){

        if(chess[i][x]==input){
            break;
        }
        if(chess[i][x]!=input&&chess[i][x]!='0'){
            c=1;
        }
        if(chess[i][x]=='0'){
            if(c==1){
                chess[i][x]='x';
            }
            break;
        }
    }
    c=0;
    for (int i = y+1,j=x+1; i <8&&j<8; i++,j++){

        if(chess[i][j]==input){
            break;
        }
        if(chess[i][j]!=input&&chess[i][j]!='0'){
            c=1;
        }
        if(chess[i][j]=='0'){
            if(c==1){
                chess[i][j]='x';
            }
            break;
        }
    }
    c=0;
    for (int i = y-1,j=x+1; i >=0&&j<8; i--,j++){

        if(chess[i][j]==input){
            break;
        }
        if(chess[i][j]!=input&&chess[i][j]!='0'){
            c=1;
        }
        if(chess[i][j]=='0'){
            if(c==1){
                chess[i][j]='x';
            }
            break;
        }
    }
    c=0;
    for (int i = y+1,j=x-1; i <8&&j>=0; i++,j--){

        if(chess[i][j]==input){
            break;
        }
        if(chess[i][j]!=input&&chess[i][j]!='0'){
            c=1;
        }
        if(chess[i][j]=='0'){
            if(c==1){
                chess[i][j]='x';
            }
            break;
        }
    }
    c=0;
    for (int i = y-1,j=x-1; i >=0&&j>=0; i--,j--){

        if(chess[i][j]==input){
            break;
        }
        if(chess[i][j]!=input&&chess[i][j]!='0'){
            c=1;
        }
        if(chess[i][j]=='0'){
            if(c==1){
                chess[i][j]='x';
            }
            break;
        }
    }
    for (int i = 0; i < 8; i++){
        for (int j = 0; j < 8; j++){
            if(chess[i][j]=='x'){
                if(d==1){
                    printf(",");
                }else
                    d=1;
                printf("(%d,%d)",i,j);
            }
        }
    }
    printf("can be placed\n");
    for (int i = 0; i < 8; i++){
        for (int j = 0; j < 8; j++){
            printf("%c ",chess[i][j]);
        }printf("\n");
    }
}


int main(){    
    int x,y;
    char haha;
    for (int i = 0; i < 8; i++){
        for (int j = 0; j < 8; ){
            scanf("%c",&chess[i][j]);
            if (chess[i][j]=='\n'||chess[i][j]==' ')
            {
                continue;
            }
            j++;
        }
    }
    printf("input ");
    scanf("%1d%c%1d",&x,&haha,&y);
    input=chess[x][y];
    if (input=='0'){
        return 0;
    }
     printf("color %c\n",input);
    check(x,y);
    
    return 0;
}

```

