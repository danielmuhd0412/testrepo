# Einführung in Git

- [Einführung in Git](#einführung-in-git)
  - [Was ist ein Git Repository?](#was-ist-ein-git-repository)
  - [Git konfigurieren](#git-konfigurieren)
  - [Ein Repo holen](#ein-repo-holen)
  - [Ein einfaches Git Repo erstellen](#ein-einfaches-git-repo-erstellen)
  - [Best Practices](#best-practices)
  - [Add, Stage, Commit](#add-stage-commit)
  - [Mit Remote Repositories arbeiten](#mit-remote-repositories-arbeiten)
  - [Ein Repo klonen](#ein-repo-klonen)
  - [Zu einem Remote pushen](#zu-einem-remote-pushen)
  - [Von einem Remote pullen](#von-einem-remote-pullen)
  - [Ein lokales Repo mit einem Remote verlinken](#ein-lokales-repo-mit-einem-remote-verlinken)
  - [Branches](#branches)
  - [Merge Konflikte](#merge-konflikte)
  - [Weiterführende Links](#weiterführende-links)

## Was ist ein Git Repository?

Ein Repository verfolgt alle Änderungen an Dateien in einem Verzeichnis, indem es Schnappschüsse des Projektverlaufs speichert.

Man kann das Repo als einen Ordner `.git` im Filesystem finden. Ein Repository wird auch kurz **repo** genannt.

## Git konfigurieren

Bevor man Git verwenden will, muss man erst den **Namen** und die **E-Mail** festlegen.

Dies wird zur Identifizierung verwendet.

```bash
# deinen Namen eingeben
git config --global user.name "your_name"

# deine E-Mail eingeben
git config --global user.email "your_email"

# Ausgabe wird farbig (Lesbarkeit erhöht)
git config --global color.ui auto
```

## Ein Repo holen

1\. Methode: Ein Repo aus einem bestehenden Verzeichnis erstellen

```bash
git init
```

2\. Methode: Ein Repo aus einer anderen Quelle kopieren (siehe [Remotes](TODO))

```bash
git clone
```

## Ein einfaches Git Repo erstellen

```bash
# ein leeres Verzeichnis mit den Namen git-workshop erstellen
mkdir git-workshop

# in Ordner wechseln
cd git-workshop

# ein leeres Repo erstellen
git init

# bestätigen, dass das Repo existiert
git status
```

## Best Practices

Nachdem ein neues Repo erstellt wurde, solltest du Folgendes tun:

a. ein README Datei hinzufügen

- ein README ist eine kurze Beschreibung vom Projekt
- siehe [Make a README](https://www.makeareadme.com/) für Leitfaden, wie man ein gutes README schreibt

b. ein .gitignore Datei hinzufügen

- ein .gitignore Datei sagt Git, bestimmte Dateien nicht zu verfolgen
- siehe [GitHub's .gitignore Templates](https://github.com/github/gitignore) für vorgefertige .gitignore Vorlagen

## Add, Stage, Commit

Wenn du ein Datei hinzufügst (add), Git beginnt es zu verfolgen.

Vergleichbar wäre das Hinzufügen von Artikeln zu einem Paket, dass du später an eine andere Person schicken willst.

```bash
# ein README in UNIX (Mac/Linux) erstellen
touch README
echo "git-workshop" >> README

# ein README in Windows erstellen
# verwende den Explorer um ein txt Datei zu erstellen!

# verfolgt Git schon das README?
git status

# README zum Staging Area hinzufügen, damit Git es verfolgt
git add README

# nochmal den aktuellen Stand prüfen
git status
```

Das geht aber nur bei einem Datei. Wie fügt man mehrere Dateien hinzu?

```bash
# das kann man natürlich auf schmerzhafte Art machen
git add file1
git add folder\file2

...

# es gibt aber einen einfacheren Weg!

# der Punkt sagt Git, *alles* im Verzeichnis hinzuzufügen
git add .

# *alles* ist inklusive Dateien in Unterordner
```

Nachdem du Datein fertig hinzugefügt haben, musst du ein Commit machen.

Ein Commit ist ein Snapshot vom aktuellen Stand des Repos.

Wieder zur Paket-Analogie: Hier packst du das Paket und verschickt es.

```bash
# das -m Flag erlaubt man, das Commit kurz zu berschreiben
git commit -m "added README"

# wie sieht das Repo jetzt aus?
git status

# Commit-Verlauf prüfen
git log
```

## Mit Remote Repositories arbeiten

Wir haben bisher nur am lokalen Rechner gearbeitet.
Diese Repos heißen lokale (local) Repos.

Was wäre, wenn wir an einem Repo von einer anderen Person arbeiten wollen? Oder unser eigenes Repo online hosten, sodass andere Menschen auch daran arbeiten können?

Dies wird durch Remote Repos ermöglicht.

## Ein Repo klonen

Durch das Klonen eines Repos wird ein Repo von einer externen Quelle kopiert.
Nach dem Klonen wird ein Verzeichnis mit allen Dateien vom Projekt erstellt.

Was sind aber externe Quellen?
Diese sind online Repos, die auf Plattformen wie GitHub oder GitLab gehostet werden.

Es gibt zwei Methoden zum Klonen eines Repos: HTTP oder SSH.
Die sind für unsere Zwecke gleich. Wir verwenden HTTP.

Um die URL zu holen, klicke die grüne `CODE` Taste auf ein GitHub Repo (`CLONE` auf GitLab).

Kopiere die URL unter dem HTTPS-Tab.

```bash
# ein Repo klonen
git clone <url_for_remote_repo>

# in Repo-Ordner wechseln
cd folder-name
```

## Zu einem Remote pushen

Pushen = Die lokalen Commits mit dem Remote-Repo synchronisieren.

```bash
git push <remote> <branch>
```

## Von einem Remote pullen

Pullen = Das lokale Repo mit neuen Änderungen aus dem Remote aktualisieren.

Es gibt 2 Methoden zu pullen.

```bash
# alle Änderungen herunterladen
# aber nicht mit der lokalen Kopie zusammenfügen
git fetch

# Änderungen in lokaler Kopie zusammenfügen
git merge

# fetch und merge auf einmal
git pull
```

## Ein lokales Repo mit einem Remote verlinken

Man muss erst ein neues Repo auf GitHub/GitLab erstellen.

```bash
# URL des Remotes zum lokalen Repo hinzufügen
git remote add origin [url]

# du wirst evtl. aufgefordert, sich bei GitHub/GitLab zu authentifizieren

# Commits pushen und entsprechender Branch in Remote erzeugen
git push --set-upstream origin main
```

## Branches

Ein Branch (Zweig) ist eine Kopie des aktuellen Repos, aber mit eigenständigen Commit-Verlauf.
Es wird meistens zum Programmieren neuer Features oder Bug-Fixing verwendet, ohne den ursprünglichen Code zu ändern.

```bash
# alle Branches auflisten
git branch

# ein neuer Branch namens "test" erzeugen
git branch test

# zu test Branch wechseln
git checkout test

# test Branch löschen
git branch -d test

# test Branch auf einmal erzeugen und dazu wechseln
git checkout -b test
```

## Merge Konflikte

Wenn Git die Änderungen im Repo automatisch auflösen kann, nennt man das einen Merge Konflikt.

Diese treten typischerweise auf, wenn:

1\. 2 Branches gemergt werden.

2\. Das Remote-Repo unterscheidet sich zu sehr vom lokalen Repo.

Wenn das passiert, muss man sich in den Dateien schauen und den Konflikt manuell auflösen.

```bash
# versuchen, test branch mit aktuellen Branch zu mergen
git merge test

# welche Dateien haben einen Merge Konflikt?
git status
```

## Weiterführende Links

[Pro Git](https://git-scm.com/book/en/v2) - Ein Buch, das Git im Detail bespricht. Auch auf Deutsch verfügbar.

[Oh Shit, Git!?!](https://ohshitgit.com/) - Wenn man verkackt hat und weiß nicht, was man als Nächstes tut.

[GitHub's .gitignore Templates](https://github.com/github/gitignore) - .gitignore Vorlagen vom Github.
