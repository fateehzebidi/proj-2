# proj-2
les sous programe
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
char *ChargerChaine(int N);
int Longueur(char *ch);
void ChargerTab(char *p, char Tab[]);
void AfficherTab(char Tab[], int m);
void InverserTab(char Tab[], char T[], int m);
int main() {
    char *ch; 
    int n;
    printf("Veuillez saisir la taille maximale de la chaine:\n");
    scanf("%d", &n);
    ch = ChargerChaine(n);
    int m = Longueur(ch);
    char Tab[m], T[m];
    ChargerTab(ch, Tab);
    printf("Tableau original:\n");
    AfficherTab(Tab, m);
    InverserTab(Tab, T, m);
    printf("Tableau inverse:\n");
    AfficherTab(T, m);
    free(ch);

    return 0;
}
char *ChargerChaine(int N) {
    char *chaine = (char *)malloc((N + 1) * sizeof(char));
 
    printf("Veuillez saisir une chaine (max %d caracteres):\n", N);
    scanf(" %s", chaine);

    return chaine;
}
int Longueur(char *ch) {
    int length = 0;
    while (ch[length] != '\0') {
        length++;
    }
    return length;
}
void ChargerTab(char *p, char Tab[]) {
    int i = 0;
    while (p[i] != '\0') {
        Tab[i] = p[i];
        i++;
    }
}
void AfficherTab(char Tab[], int m) {
    for (int i = 0; i < m; i++) {
        printf("%c", Tab[i]);
    }
    printf("\n");
}
void InverserTab(char Tab[], char T[], int m) {
    for (int i = 0; i < m; i++) {
        T[i] = Tab[m - i - 1];
    }
}


