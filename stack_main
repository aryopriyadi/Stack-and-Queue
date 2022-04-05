#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int top = 0, maxStack = 5, i, tempTop;
char dataStack[5][100];
char tempStack[5][100];

int isEmpty(){
	if(top == 0){
		return 1;
	} else {
		return 0;
	}
}

int isFull(){
	if(top >= maxStack){
		return 1;
	} else {
		return 0;
	}
}

void displayStack(){
	int no = 1;
	if(isEmpty()){ // cek data kosong
		printf("Data Kosong\n");
	} else {
		for(i = top; i > 0; i--){
			printf("Data - %i : %s\n",no, dataStack[i-1]);
			no++;
		}
	}
}

void pushStack(){
	char data[100];
	
	if(isFull()){
		printf("Data Sudah Penuh\n");
	} else {
		printf("Masukkan Data : "); scanf(" %[^\n]",&data);
		strcpy(dataStack[top], data);
		top++;
		printf("Data berhasil dimasukkan! \n");
	}
}

void popStack(){
	if(isEmpty()){
		printf("Data Kosong\n");
	} else {
		strcpy(dataStack[top-1],"");
		top--;
		printf("Data berhasil dihapus\n");
	}
}

void peekStack(){
	int posisi, index;
	if(isEmpty()){
		printf("Data Kosong\n");
	} else {
		displayStack();
		printf("Masukkan Posisi Data : "); scanf("%d", &posisi);
		if(posisi > top){
			printf("Posisi melampaui data");
		} else {
			index = top;
			for(i = 0; i< posisi; i++){
				index--;
			}
			printf("Posisi ke - %d adalah %s\n", posisi, dataStack[index]);
		}
	}
}

void changeStack(){
	int posisi, index;
	char dataPengganti[100];
	if(isEmpty()){
		printf("Data Kosong\n");
	} else {
		displayStack();
		printf("Masukkan Posisi Data : "); scanf("%d", &posisi);
		printf("Masukkan data pengganti : "); scanf(" %[^\n]", &dataPengganti);
		if(posisi > top){
			printf("Posisi melampaui data");
		} else {
			index = top;
			for(i = 0; i< posisi; i++){
				index--;
			}
			strcpy(dataStack[index], dataPengganti);
			printf("Posisi ke - %d adalah %s\n", posisi, dataStack[index]);
		}
	}
}

void countStack(){
	printf("Jumlah data adalah sebanyak %d data\n", top);
}

void destroyStack(){
	if(isEmpty()){
		printf("Data Stack Sudah Kosong\n");
	} else {
		tempTop = top;
		for(i = top; i> 0; i--){
			strcpy(tempStack[i-1], dataStack[i-1]);
			strcpy(dataStack[i-1],"");
			top--;
		}
		printf("Data berhasil direset /  destroy \n");
	}
}

void restoreStack(){
	if(isEmpty()){
		for(i = tempTop; i> 0; i--){
			strcpy(tempStack[i-1],"");
			strcpy(dataStack[i-1], tempStack[i-1]);
			tempTop--;
			top++;
			printf("Data berhasil direstore \n");
		}
	} else {
		printf("Data gagal di restore\n");
	}
}

int main(){
	
	//Stack
	// Stack -> Tumpukan -> LIFO (last in First out)
	// Display Stack , Push Stack , Pop Stack , Peek Stack, Change Data Stack, Count , Destroy 
	int pilihan;
	
	do{
		system("cls");
		printf("MENU STACK\n");
		printf("+========================+\n");
		printf("1. Lihat Data (Display Stack)\n");
		printf("2. Tambah Data (Push Stack)\n");
		printf("3. Hapus Data (Pop Stack)\n");
		printf("4. Lihat Data berdasarkan Posisi (Peek Stack)\n");
		printf("5. Ubah Data (Change Stack)\n");
		printf("6. Menghitung Data (Count Stack)\n");
		printf("7. Reset Data (Destory Stack)\n");
		printf("8. Restore Data (Destory Stack)\n");
		printf("9. Exit\n");
		printf("Masukkan Pilihan : "); scanf("%d", &pilihan);
		
		switch(pilihan){
			case 1: system("cls"); displayStack(); getch(); break;
			case 2: system("cls"); pushStack(); getch(); break;
			case 3: system("cls"); popStack(); getch(); break;
			case 4: system("cls"); peekStack(); getch(); break;
			case 5: system("cls"); changeStack(); getch(); break;
			case 6: system("cls"); countStack(); getch(); break;
			case 7: system("cls"); destroyStack(); getch(); break;
			case 8: system("cls"); restoreStack(); getch(); break;
			case 9: exit(EXIT_SUCCESS); break;
			default: printf("PILIHAN SALAH !!\n");
		}
	} while (pilihan != 9);
	return 0;
}
