# Puntatori in C

Vediamo ora come questi concetti studiati in teoria si applicano alla programmazione.

Immaginiamo il seguente codice.

```c
#include <stdio.h>

int main() {
    int            a = 4;
    printf ("Il valore di a è %d\n",a);
    return 0;
}
```

```text
Il valore di a è 4
```

È possibile sapere in quale indirizzo di memoria è situata la variabile `a`?

La risposta è sì, ed è possibile farlo attraverso l'operatore `&`, che serve esattamente per sapere l'indirizzo di una variabile.

## Operatore & (indirizzo di)

L'operatore `&` si legge "e commerciale" (oppure in inglese "ampersand" o ancora "operatore di referenziazione") e serve esattamente per sapere l'indirizzo di una variabile.

```c
#include <stdio.h>

int main() {
    int            a = 4;
    printf ("Il valore di a è %d\n",a);
    printf ("L'indirizzo di a è %p\n",&a);
    return 0;
}
```

```text
Il valore di a è 4
L'indirizzo di a è 0x7ffc18dc19cc
```

> Possiamo immaginare il simbolo & come un nodo a cui è legato il filo alla cui estremità opposta c'è la variabile.

Se volessimo invece sapere il valore di un indirizzo di memoria? Esiste anche un operatore per questo scopo, che è l'operatore `*`.

## Operatore * (indirizzamento indiretto)

L'operatore `*` si legge "stella" (oppure in inglese "star" o ancora operatore di "dereferenziazione" o "indirezione") serve per conoscere il valore di un certo indirizzo di memoria.

Le variabili che memorizzano al loro interno un indirizzo di memoria si chiamano puntatori.

Vediamo un esempio di codice in cui dichiariamo un puntatore, gli assegniamo l'indirizzo di 'a' e ne stampiamo sia il valore, sia il valore puntato.

```c
#include <stdio.h>

int main() {
    int            a = 4;
    int* p = &a;

    printf ("Il valore di a è %d\n",a);
    printf ("L'indirizzo di a è %p\n",&a);

    printf ("Il valore di p è %p\n",p);
    printf ("Il valore puntato da p è %d\n",*p);

    return 0;
}
```

```text
Il valore di a è 4
L'indirizzo di a è 0x7ffe344c8874
Il valore di p è 0x7ffe344c8874
Il valore puntato da p è 4
```

Potete sperimentare anche voi con questo esempio a [questo](https://godbolt.org/z/5ezhavErh) link.

Potete inoltre visualizzare graficamente il comportamento dei puntatori con il seguente strumento. Cliccate next per vedere come si comporta la memoria in fase di esecuzione.

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%20%3Cstdio.h%3E%0A%0Aint%20main%28%29%20%7B%0A%20%20%20%20int%20%20%20%20%20%20%20%20%20%20%20%20a%20%3D%204%3B%0A%20%20%20%20int*%20p%20%3D%20%26a%3B%0A%0A%20%20%20%20printf%20%28%22Il%20valore%20di%20a%20%C3%A8%20%25d%5Cn%22,a%29%3B%0A%20%20%20%20printf%20%28%22L'indirizzo%20di%20a%20%C3%A8%20%25p%5Cn%22,%26a%29%3B%0A%0A%20%20%20%20printf%20%28%22Il%20valore%20di%20p%20%C3%A8%20%25p%5Cn%22,p%29%3B%0A%20%20%20%20printf%20%28%22Il%20valore%20puntato%20da%20p%20%C3%A8%20%25d%5Cn%22,*p%29%3B%0A%0A%20%20%20%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=nevernest&origin=opt-frontend.js&py=c_gcc9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>