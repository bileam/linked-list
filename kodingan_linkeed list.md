
#include<stdio.h>
#include<stdlib.h>
#include<conio.h>
#include<stdbool.h>
#include<ctype.h>
#include<string.h>

struct node {
    int data;
    struct node* next;
};
struct node *head;

void awal()
{
    struct node *ptr;
    int item;

    ptr = (struct node*) malloc(sizeof(struct node*));
    if (ptr==NULL)
    {
        printf("Overflow!");
    }
    else
    {
        printf("Masukan data : ");
        scanf("%d", &item);
        ptr->data = item;
        ptr->next = head;
        head = ptr;
        printf("\nData berhasil disimpan di NODE awal!\n");
    }
}

void akhir()
{
    struct node *ptr, *temp;
    int item;

    ptr = (struct node*) malloc(sizeof(struct node*));
    if (ptr==NULL)
    {
        printf("Overflow!");
    }
    else
    {
        printf("Masukan data : ");
        scanf("%d", &item);
        ptr->data = item;
        if(head==NULL)
        {
            ptr->next = NULL;
            head = ptr;
            printf("Berhasil simpan NODE!\n");
        }
        else
        {
            temp = head;
            while(temp->next != NULL)
            {
                temp = temp->next;
            }
            temp->next = ptr;
            ptr->next = NULL;
            printf("Berhasil simpan NODE akhir !\n");
        }
    }

}

void sembarang()
{
    struct node *ptr, *temp;
    int item, loc, i;

    ptr = (struct node*) malloc(sizeof(struct node*));
    if (ptr==NULL)
    {
        printf("Overflow!");
    }
    else
    {
        printf("Masukan data : ");
        scanf("%d", &item);
        ptr->data = item;
        printf("mau simpan di lokasi berapa ? ");
        scanf("%d", &loc);
        temp = head;
        for(i=0; i<loc; i++)
        {
            temp = temp->next;
            if(temp==NULL)
            {
                printf("Tidak bisa simpan datamu!");
                return;
            }
        }
        ptr->next = temp->next;
        temp->next = ptr;
        printf("NODE berhasil disimpan\n");
    }

}

void cetak()
{
    struct node *ptr;
   // int item,i=0,flag;
    ptr = head;
    if(ptr==NULL)
    {
        printf("Listnya kosong wehhh!!!");
    }
    else
    {
        printf("Cetak isi list .... ");
        while(ptr != NULL)
        {
            printf("\n%d", ptr->data);
            ptr = ptr->next;
        }
    }
}

int main()
{
   int pilihan = 0;


   while(pilihan != 5 )
   {
       system("cls");
       printf("\n***** Menu latihan LINKED LIST *****");
       printf("\n===============================================");
       printf("\n1.Input  data diawal \n2.Input data di akhir \n3.Input data sembarang \n4.lihat data \n5.Keluar");
       printf("\nPilihanmu?: ");
       scanf("%d", &pilihan);

       switch(pilihan)
       {
           case 1 :
           system("cls");
           awal();
           getch();
           break;

           case 2 :
           system("cls");
           akhir();
           getch();
           break;

           case 3 :
        system("cls");
           sembarang();
           getch();
           break;

           case 4 :
        system("cls");
           cetak();
           getch();
           break;

           case 5 :
           exit(0);
           break;

           default:
           printf("Silahkan pilih yang benar");
       }

   }
}
/*
void cetak(node_t *head)
{
node_t *sementara = head;
while(sementara != NULL)
{
printf("%d - ", sementara->data);
sementara = sementara->next;
}
printf("\n");
}*/

