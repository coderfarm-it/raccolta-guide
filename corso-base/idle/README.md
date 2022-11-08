# che programmi usare per scrivere codice in c++?

Questa vuole essere una lista di programmi
che vi vconsigliamo di usare per risolvere gli esercizi,
sentitevi liberi di sperimentare e usare l'opzione
più adatta a voi.

Indice:
* [repl.it](#replit)
* [godbolt.org](#godboltorg)
* [Visual Studio Code](#visual-studio-code)
* [Codeblocks](#codeblocks)
* [XCode](#xcode)
* [DevC++](#devc)

## repl.it
[repl.it](replt.it) è un editor online, molto vantaggioso
perchè non dovete installare nessun programma in locale.
Inoltre vi permette di utillizzare una riga di comando
per navigare tra i file e compilare i vostri progetti,
come accade nelle gare di alto livello. L'unico
svantaggio è che gli editor online spesso non sono ammessi
alle gare ufficiali.

## [godbolt.org](https://godbolt.org/)
Come [repl.it](#replit) è un editor online, con la differenza
di essere più leggero ma ha una grafica vecchio stile e non
permette di utillizare una riga di comando.

## Visual Studio Code
Editor molto famoso e diffuso, probabilmente il migliore.
Per usare VsCode dovrete però installare da soli un compilatore.

## Codeblocks
Disponibile per tutti i sistemi operativi, Codeblocks è facile da installare
e usare. Ha una grafica molto vecchia e non offre particolari vantaggi,
ma molto spesso è installato sui pc per le gare.

## XCode
Disponibile solo su MacOs, XCode è il programma consigliato da Apple per programmare.
Offre come vantaggio che una volta installato avrete disponibile anche il compilatore
clang, non dovrete quindi preoccuparvi di installarne uno manualmente.

## DevC++
Programma molto vecchio e datato solo per Windows, ha il vantaggio che
è incluso un compilatore ed è molto facile usarlo.
Bisogna però tenere a mente che la versione del compilatore è molto vecchia,
quindi alcune funzionalità recenti potrebbero non essere disponibili.

Per attivare le funzionalità di C++11 su DevC++ è necessario andare
nel menu tools -> compiler options -> settings -> code generation e impostare
la voce "Language standard" all'ultima versione disponibile (probabilmente ISO C++11).
Se non trovare i menu [questo thread](https://stackoverflow.com/questions/64371274/how-to-enable-c11-or-c14-in-dev-c-ide) contiene delle immagini che potrebbero aiutarvi.
