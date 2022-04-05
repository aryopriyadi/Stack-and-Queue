#include <stdio.h>
#include <stdlib.h>
//#include <string.h>

int front=0, back=0, maxQueue=5, i, backTemp = 0;
char dataQueue[5][100];
char tempQueue[5][100];

int isFull(){
	if(back == maxQueue){
		return 1;
	} else {
		return 0;
	}
}

int isEmpty(){
	if(front <= 0 && back <= 0){
		return 1;
	} else {
		return 0;
	}
}

void displayQueue(){
	printf("Data Antrian\n");
	for(i=0;i<maxQueue; i++){
		if(strcmp(dataQueue[i],"") == 0){
			printf("%d. (Kosong)\n",i+1);
		} else {
			printf("%d. %s\n",i+1, dataQueue[i]);
		}
	}
}

void enQueue(){
	char data[100];
	if(isFull()){
		printf("Antrian Penuh\n");
	} else {
		printf("Masukkan Data : "); scanf(" %[^\n]", &data);
		if(isEmpty()){
			strcpy(dataQueue[back],data);
			front = 1;
			back++;
		} else {
			strcpy(dataQueue[back],data);
			back++;
		}
		printf("Data berhasil dimasukkan\n");
	}
}

void deQueue(){
	if(isEmpty()){
		printf("Antrian Kosong\n");
	} else {
		for(i=0; i< back; i++){
			strcpy(dataQueue[i], dataQueue[i+1]);
		}
		
		if(back<= 1){ // data tinggal 1
			front = 0;
		}
		
		back--;
		printf("Antrian berhasil dihapus");
	}
}

void countQueue(){
	printf("Jumlah antrian adalah sebanyak %d data", back);
}

void destroyQueue(){
	if(isEmpty()){
		printf("Antrian sudah kosong\n");
	} else {
		for(i=0; i< back; i++){
			strcpy(tempQueue[i], dataQueue[i]);
			strcpy(dataQueue[i], "");
		}
		backTemp = back;
		front = 0;
		back = 0;
	}
	printf("Antrian berhasil direset\n");
}

void restoreQueue(){
	if(isEmpty()){
		for(i=0; i< backTemp; i++){
			strcpy(dataQueue[i], tempQueue[i]);
			strcpy(tempQueue[i], "");
			//strcpy(dataTujuan, dataAsal)
			//strcmp(dataA,dataB) -> kalau true -> return 0
		}
		back = backTemp;
		if(backTemp != 0){
			front = 1;
		}
		backTemp = 0;
		printf("Antrian berhasil dikembalikan\n");
	} else {
		printf("Antrian belum kosong\n");
	}
}

int main(){
	//Queue -> Antrian
	// Queue -> FIFO (First in First out)
	
	int pilihan;
	
	do{
		system("cls");
		printf("MENU Queue\n");
		printf("+========================+\n");
		printf("1. Lihat Data (Display Queue)\n");
		printf("2. Tambah Data (Enqueue)\n");
		printf("3. Hapus Data (DeQueue)\n");
		printf("4. Menghitung Data (Count Queue)\n");
		printf("5. Reset Data (Destory Queue)\n");
		printf("6. Restore Data (Restore Queue)\n");
		printf("7. Exit\n");
		printf("Masukkan Pilihan : "); scanf("%d", &pilihan);
		
		switch(pilihan){
			case 1: system("cls"); displayQueue(); getch(); break;
			case 2: system("cls"); enQueue(); getch(); break;
			case 3: system("cls"); deQueue(); getch(); break;
			case 4: system("cls"); countQueue(); getch(); break;
			case 5: system("cls"); destroyQueue(); getch(); break;
			case 6: system("cls"); restoreQueue(); getch(); break;
			case 7: exit(EXIT_SUCCESS); break;
			default: printf("PILIHAN SALAH !!\n");
		}
	} while (pilihan != 7);
	return 0;
}
