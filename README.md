# hangman-game
# C program
# Let's make a hangman game in c language

#include <stdio.h>
#include <string.h> 
//문자열은 '\0', NUL로  끝나야 한다. 
int check(char s[],char a[],char ch);
int main(void){
	char solution[100]="i love you";
	char answer[100]="_ ____ ___";
	char ch;
	while(1){
	printf("문자열은 다음과 같습니다: %s\n",answer);
	printf("글자를 추측하시오:\n");
	ch=getchar();
	if(check(solution,answer,ch)==1){
		printf("성공하셨습니다!!");
		break; 
	}
	getchar(); //줄바꿈 문자를 제 거  
}
	return 0;	
}
int check(char s[],char a[], char ch){
	int i;
	for(i=0;s[i]!='\0';i++){
		if(s[i]==ch){
			a[i]=ch;
		}
	}
	if(strcmp(s,a)==0){
		return 1;
	}
	else{
		return 0;
	}
}


