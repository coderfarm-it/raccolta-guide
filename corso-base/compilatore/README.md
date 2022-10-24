# Come compilare da riga di comando

Lista degli argomenti:
* [Cos'è un compilatore?](#cosè-un-compilatore)
* [Quanti compilatori esistono?](#quanti-compilatori-esistono)
* [Come installo un compilatore?](#come-installo-un-compilatore)
* [Come faccio a compilare un programma in c++?](#come-faccio-a-compilare-un-programma-in-c)
* [Come scelgo il nome dell'eseguibile?](#come-scelgo-il-nome-delleseguibile)
* [Se ho più di un file da compilare come faccio?](#se-ho-più-di-un-file-da-compilare-come-faccio)
* [Quali altre opzioni posso usare?](#quali-altre-opzioni-posso-usare)

## Cos'è un compilatore?
Sicuramente saprete che il processore del vostro computer legge istruzioni in codice binario, interpretando una
sequenza di 0 e 1. È quindi necessario che ci sia un programma che converta il codice che scriviamo
in un linguaggio comprensibile al computer, ed è proprio qui che entra in gioco il compilatore.
Il compilatore è un programma che prima di tutto controlla che il codice sia sintatticamente corretto,
e, se è effettivamente così, procede a creare un eseguibile contenente il programma. Gli eseguibili
sono dei file che contengono istruzioni e dati e ogni sistema operativo rappresenta quest'ultimi in maniera e in formati diversi (ad esempio su windows hanno l'estensione *.exe*).

## Quanti compilatori esistono?
Tanti.

Noi vi consigliagmo di usare GCC (GNU Compiler Collection), ma esistono altre alternative come ad esempio Clang, Microsoft Visual C++ ecc.
Da questo punto in avanti la maggior parte dei comandi proposti saranno validi solo per GCC.
Se desiderate usare Clang, molti comandi sono simili a GCC, ma alcune cose cambiano (come ad esempio le ottimizzazioni), quindi vi consigliamo di consultare la [documentazione](https://clang.llvm.org/docs/UsersManual.html) di Clang.
MSVC è un compilatore proprietario, quindi non potete usarlo se non avete un sistema operativo Windows, questo compilatore \`e incluso nel pacchetto di Visual Studio, quindi se volete usarlo \`e comodo installare Visual Studio (da non confondere con Visual Studio Code, che \`e un editor di testo).

## Come installo un compilatore?
Innanzitutto controlliamo se GCC \`e gi\`a installato, aprite un terminale e
digitate

```g++```

se l'output è simile a

```g++: fatal error: no input files```

allora il compilatore \`e gi\`a installato. Altrimenti seguite i passaggi
in base al vostro sistema operativo:
* [Windows](#windows)
* [MacOs](#macos)
* [GNU/Linux](#linux)

### Windows
Sul nostro canale youtube trovate un [video](https://youtu.be/UJJqdmyGGYA) che vi aiuterà a installare GCC su Windows.
Il link per scaricare la cartella compressa è [questo](https://github.com/brechtsanders/winlibs_mingw/releases/download/12.2.0-14.0.6-10.0.0-ucrt-r2/winlibs-x86_64-posix-seh-gcc-12.2.0-mingw-w64ucrt-10.0.0-r2.zip).
In alternativa potete installare WSL (Windows Subsystem for Linux) e avere a disposizione
un sistema Linux all'interno di Windows, ma dovrete imparare
ad usare la shell di Linux.

### MacOS
Se avete installato XCode dovreste aver disponibile nel sistema clang e potete tranquillamente usarlo
per compilare i vostri codici. Se invece preferite avere GCC esistono dei metodi per ottenerlo, il più
facile è probabilmente [Homebrew](https://brew.sh/), una volta installato basta digitare

```brew install gcc```

### Gnu / Linux
Installate gcc usando il vostro package manager da terminale.

#### Debian / Ubuntu / Linux Mint
```sudo apt install build-essential```

#### Fedora
```sudo dnf install gcc```

#### Arch Linux
```sudo pacman -S gcc```

## Come faccio a compilare un programma in c++?
Supponiamo (con molta fantasia) di voler compilare il codice nel file
*esercizio.cpp*. Il comando per farlo è:

```g++ esercizio.cpp```

se non avete ricevuto errori di compilazione allora dovreste trovare nella cartella
un file chiamato *a.out* oppure *a.exe*. A questo punto scrivendo 

```./a.out```

oppure per chi usa windows

```.\a.exe```

il programma viene eseguito.

Questo metodo funziona ma vi consigliamo di leggere la prossima sezione per scoprire come scegliere il nome
del file eseguibile.

## Come scelgo il nome dell'eseguibile?

Supponiamo di voler compilare il file *esercizio.cpp* ma scegliendo il nome dell'eseguibile.
Ogni nome va bene, ma la convenzione è la seguente:

* su windows si usa il nome del file sorgente con estensione *.exe*, ad esempio *esercizio.exe*
* su linux e mac si usa il nome del file sorgente senza estensione, ad esempio *esercizio*

per specificare il nome dell'eseguibile basta aggiungere alla fine del comando:

```g++ esercizio.cpp -o nome_eseguibile```

sostituendo a *nome_eseguibile* il nome desiderato.

## Se ho più di un file da compilare come faccio?
Spesso dovrete risolvere esercizi con il codice diviso tra vari file,
uno dei quali probabilmente chiamato *grader.cpp*. Supponiamo di voler compilare insieme
i file *esercizio.cpp* e *grader.cpp* producendo l'eseguibile *esercizio.exe*,
il comando è il seguente:

```g++ esercizio.cpp grader.cpp -o esercizio.exe```

## Quali altre opzioni posso usare?

Il compilatore offre un sacco di opzioni di compilazione diverse per modificare il file
eseguibile in base alle nostre necessità, da aggiungere alla fine del comando.
Le più utili quando si risolvono esercizi sono:

* ```-Wall``` - attiva i cosìdetti "warnings", cioè avvisi per farti notare parti di codice
che rischiano di produrre risultati sbagliati o imprevedibili, nonostante siano istruzioni
comprensibili e quindi eseguibili. È una buona idea usare sempre questa opzione.
* ```-Wextra``` - attiva altri warnings oltre a quelli di ```-Wall```.
* ```-pedantic``` - attiva ancora più warnings.
* ```-O2```, ```-O3``` - il compilatore cerca di ottimizzare il codice per renderlo
più veloce. In generale non serve se usate input medio / piccoli.
* ```-fsanitize=address,undefined``` - se il vostro programma si interrompe durante l'esecuzione
per qualche errore detto di *runtime* (spesso sono errori di memoria), attivando questa opzione
otterrete delle informazioni sulla riga del codice che ha causato il problema. Opzione molto
utile se state impazzendo per qualche errore di memoria insidioso, ma rallenta di molto l'esecuzione
del programma.
