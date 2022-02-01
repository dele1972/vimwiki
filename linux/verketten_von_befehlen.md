# Linux - verketten von Befehlen

## `;` ohne Abhängigkeit

```bash
$ command1 ; command2
```

**Beispiel**

```bash
$ false ; echo "This will always run"
This will always run
```


## mit Abhängigkeit

### `&&` - UND: Ausführung wenn vorheriger Befehl mit Status `0` beendet wurde

Der folgende Befehl wird nur ausgeführt, wenn der vorherige Befehl erfolgreich (mit Exit-Code = 0) beendet wurde.

```bash
$ command1 && command2
```

Nach `command1` wird `command2` nur ausgeführt, wenn `command1` erfolgreich war.

**Beispiel**

```bash
$ true && echo "Things went well"
Things went well
```


### `||` - ODER: Ausführung wenn vorheriger Befehl mit Status `1` beendet wurde

Der folgende Befehl wird nur ausgeführt, wenn der vorherige Befehl (mit Exit-Code = 1) fehlgeschlagen ist.

```bash
$ command1 || command2
```

Nach `command1` wird `command2` nur ausgeführt, wenn `command1` fehlgeschlagen ist.

**Beispiel**

```bash
$ false || echo "Oops, fail"
Oops, fail
```


----

## BTW: Exit-Code

Der Exit-Code wird in der Umgebungsvariable `$?` gespeichert und kann mit folgendem Befehl ausgegeben werden:

```bash
$ echo $?
```

- siehe auch: [Bash get exit code of command on a Linux / Unix](https://www.cyberciti.biz/faq/bash-get-exit-code-of-command/)

### `!` negieren des Exit-Codes

Man kann auch den Exit-Code eines Befehls mit vorangestelltem `!` umkehren.

**Beispiel**

```bash
$ echo 23
23

$ echo $?
0

$ ! echo 23
23

$ echo $?
1
```
