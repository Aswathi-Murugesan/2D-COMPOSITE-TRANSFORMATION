#include<stdio.h>
#include<conio.h>
#include<math.h>
#include<graphics.h>
int i,pt[8]={50,50,150,50,150,100,50,50};
int p[8];void trans();
void scale();
void invtrans();
void main()
{
int gd=DETECT,gm;
initgraph(&gd,&gm,"c:\\tc\\bgi");
setbkcolor(WHITE);
setcolor(BLUE);
for(i=0;i<=7;i++)
{
drawpoly(4,pt);
}
getch();
trans();
closegraph();
}
void trans()
{
int i,tx=50,ty=50;
printf("Translation");
for(i=0;i<8;i=i+1)
{
p[i]=pt[i]+tx;
}
drawpoly(4,p);
getch();
scale();
}
void scale()
{
int i;
float sx=2.0,sy=2.0;
printf("\t Scaling ");
for(i=0;i<8;i=i+1)
{
p[i]=pt[i]*sx;
}
drawpoly(4,p);
getch();
invtrans();
cleardevice();
}
void invtrans()
{
int i,tx=50,ty=50;
printf("Inverse Translation");
for(i=0;i<8;i=i+1)
{
p[i]=p[i]-tx;
}
drawpoly(4,p);
getch();
}
