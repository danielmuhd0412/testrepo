# git Übungsaufgaben

### 1\. Git Basics

a\. Erstellen Sie ein neues Verzeichnis namens `git-workshop` auf ihrem Computer. Das Verzeichnis sollte folgende Dateien enthalten:

- `README.md`
- `main.py`

b\. In der Kommandozeile, navigieren Sie in das Verzeichnis mit dem `cd` Befehl.

c\. Wandeln Sie das Verzeichnis in einen Git Repository um.

> Hinweis: `.md` und `.py` Dateien sind einfache Text-Dateien. Sie können daher mit Text-Editors wie Notepad oder TextEdit erstellt, geöffnet, und geändert werden.

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

c\. Committen Sie diese Änderungen mit dem Commit-Message `Initial commit`.

### 3\. Branches & Merging

a\. Erstellen Sie einen neuen Branch namens `test`.

b\. Verändern Sie `main.py` im `test` Branch so, dass anstelle von `Hello World!`, `Bonjour` ausgegeben wird.

c\. Committen Sie diese Änderungen.

> Hinweis: Sie sollten schon bemerkt haben, wie der Rhythmus läuft. Files verändern, dann `git add`, dann `git commit`. Das ist der Kern von Git.

d\. Erstellen Sie einen weiteren Branch `another`, **welcher von der `test` Branche abstammt**. 

e\. Verändern Sie `main.py` im `another` Branch so, dass `Good Morning` ausgegeben wird.

f\. Committen Sie diese Änderungen.

g\. Mergen Sie den `main` Branch mit dem `test` Branch.

> Hinweis: `git add .` fügt alle Veränderungen im nächsten Commit hinzu.

### 4\. Merge Conflicts

a\. Verändern Sie `main.py` im `test` Branch so, dass `Goodnight` ausgegeben wird. Committen Sie diese Änderungen.

b\. Verändern Sie `main.py` im `main` Branch so, dass `Goodbye` ausgegeben wird. Committen Sie diese Änderungen.

c\. Mergen Sie den `main` Branch mit dem `test` Branch.

d\. Lösen Sie den Merge Konflikt, sodass am Ende `Goodbye` ausgegeben wird.

### 5\. Remotes & Issues (OPTIONAL)

a\. Laden Sie das Repository auf einen Remote-Server. Sie haben die Wahl zwischen GitHub oder GitLab.

b\. Erzeugen Sie für das Remote-Repository einen neuen Issue 

