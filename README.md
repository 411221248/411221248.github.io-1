chess
411221248

```c=
#include<stdio.h>
char chess[8][8];
char input;
void check(short y,short x){
    int c=0;
    int d=0;
    for (int k = -1; k <2; k++){
        for (int m = -1; m <2; m++){
            int xt,yt;
            c=0;
            xt=(k==-1)?-1:8;
            yt=(m==-1)?-1:8;
            for (int i = x+k,j=y+m; i !=xt &&j!=yt; i+=k,j+=m){
                if(chess[j][i]==input)  break;
                if(chess[j][i]!=input&&chess[j][i]!='0')    c=1;
                if(chess[j][i]=='0'){
                    if(c==1){
                        chess[j][i]='x';
                    }
                    break;
                }
            }
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

