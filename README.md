# Git (with GitHub)

## Einführung

Git ist ein kostenloses und quelloffenes verteiltes Versionskontrollsystem, das entwickelt wurde, um Projekte unterschiedlicher größe schnell und effizient abzuwickeln.

* Download Git: https://git-scm.com/downloads
* GitHub Account anlegen: https://github.com/signup

## Funktionen

Die wichtigsten Funktionen vit Git sind hier zusammengefasst: [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

* Initial das Repository von GitHub auf die eigene Entwicklerumgeben klonen:
```
git clone 
```

### Feature in einem Branch entwickeln

Die folgenden Schritte zeigen einen Feature-Entwicklung in einem seperaten Branch und bezogen zu einem Ticket mit der ID: *4711* . 

* Aus dem Arbeitsverzeichnis einen Feature-Branch basierend auf dem letzten Commit erzeugen:
```
git create -b feature/4711/add-button
```

* Änderungen in einer Datei speichern und auf den Branch committen. Dabei auch die Ticket ID referenzieren:
```
git add .
git commit -m "Commit message (#4711)"
```

* Den Feature Branch auf GitHub bereitstellen
```
git push
```

* Nachdem die Entwicklung abgeschlossen ist, einen Pull Request (PR) in GitHub anlegen, um die Änderung zu integrieren. 

* Nachdem der Pull Request (PR) gemerged wurde, im Arbeitsverzeichnis wieder auf den `main` Branch wechseln und den letzten Stand bereistellen:
```
git checkout main
git pull
```

### Release Branch erzeugen

```
git checkout main
git create -b release-0.1.0
git push
```

## Zusammenfassung





