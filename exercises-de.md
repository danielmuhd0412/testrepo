# git Übungsaufgaben

### 1\. Git Basics

a\. Erstellen Sie ein neues Verzeichnis auf ihrem Computer. 
Das Verzeichnis sollte folgende Dateien enthalten:

- `README.md`
- `main.py`

b\. Wandeln Sie das Verzeichnis in einen Git Repository um.

> Hinweis: `.md` und `.py` Dateien sind einfache Text-Dateien. Sie können daher mit Text-Editors wie Notepad erstellt, geöffnet, und geändert werden.


### 2\. Adding & Committing 

a\. Fügen Sie folgende Code im `main.py` hinzu.
```py
print("Hello World!")
```
b\. Fügen Sie folgende Text im `README.md` hinzu.
```
# README

This is a README.
```
c\. Committen Sie diese Änderungen mit dem Commit-Message `Initial commit`

### 3\. Branches & Merging
a\. Erstellen Sie einen neuen Branch namens `test`,

b\. Verändern Sie `main.py` im `test` Branch so, dass anstelle von `Hello World!`, `Bonjour` ausgegeben wird.

c\. Committen Sie diese Änderungen.

d\. Erstellen Sie einen weiteren Branch `another`, **welcher von „test“ abstammt**. 

e\. Verändern Sie `main.py` im `another` Branch so, dass `Good Morning` ausgegeben wird.

f\. Committen Sie diese Änderungen.

g\. Mergen Sie den `main` Branch mit dem `test` Branch.

### 4\. Merge Conflicts

a\. Verändern Sie `main.py` im `test` Branch so, dass `Goodnight` ausgegeben wird.

b\. Verändern Sie `main.py` im `main` Branch so, dass `Goodbye` ausgegeben wird.

c\. Mergen Sie den `main` Branch mit dem `test` Branch.

d\. Lösen Sie den Merge Konflikt, sodass am Ende `Goodbye` ausgegeben wird.

### 5\. Remotes & Issues (OPTIONAL)
a\. Laden Sie das Repository auf einen Remote-Server. Sie haben die Wahl zwischen GitHub oder GitLab.

b\. Erzeugen Sie für das Remote-Repository einen neuen Issue 

