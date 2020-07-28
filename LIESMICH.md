# biasex

Von Kommandos, die in die Bash eingebaut sind, gibt es teilweise eine zweite externe Implementierung. Das folgende Bild demonstriert dies für mein eigenes Linux-System für das Kommando `echo`.

![Zwei Implementierungen des Kommandos echo](https://i.imgur.com/0i08Cuq.png)

Beide Implementierungen reagieren weitgehend gleich, allerdings erkennt die bash-interne Implementierung ein Escape-Zeichen mehr als die externe Implementierung.

## Wann ist dies relevant? ##

Um im Einzelfall zu entscheiden, ob diese Doppelimplementierung für eine Anwendung relevant ist, muss man feststellen, zu welchen bash-eigenen Kommandos es alternative externe Implementierungen auf dem verwendeten Linux-System gibt. Genau dies ermittelt das Skript `biasex` ("buildins as external").

```bash
BStLinux@linux-sys: ~ $ ./biasex 

Externe Implementierungen auch in die Bash eingebauter Kommandos:

/usr/bin/[
/bin/echo
/bin/false
/bin/kill
/usr/bin/printf
/bin/pwd
/usr/bin/test
/bin/true

BStLinux@linux-sys: ~ $   
```

