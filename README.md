# Git (mit GitHub)

## Einführung

Git ist ein verteiltes Versionskontrollsystem, das für Projekte unterschiedlicher Größe entwickelt wurde, um diese schnell und effizient abzuwickeln.

* Download Git: https://git-scm.com/downloads
* GitHub Account anlegen: https://github.com/signup

## Erste Schritte

Die wichtigsten Funktionen für Git sind in diesem [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf) zusammengefasst.

* Initial das Repository von GitHub auf die eigene Entwicklerumgeben klonen:
```
git clone https://github.com/johannes-b/teaching-2023.ws.prse.braeuer.team-x.git
```

## Git Flow

Git Flow ist eine beliebte Git-Branching-Strategie, um das Releasemanagement eines Projektes zu vereinfachen. Es erlaubt und unterstützt: 

* *Parallele Entwicklung*: Isoliert neue Entwicklung von fertiger Arbeit.
* *Zusammenarbeit*: Erleichtert die Zusammenarbeit von zwei oder mehr Entwicklern an derselben Funktion.
* *Veröffentlichungs- und Staging-Prozess*: Sobald die Entwicklung eines Features abgeschlossen ist, wird die Änderung in den `main` Branch integriert, der ein Staging-Bereich für alle abgeschlossenen Funktionen darstellt.
* *Bug-Fixes*: Unterstützt Hotfixes–Branches, die aus einer getaggten Version erstellt wurden, die nur den Bug-Fix enthält.

Man unterscheidet zwischen unterschiedlichen Branche Typen, die basierend auf ihren Namen eine unterschiedliche Bedeutung haben.

* `main` - Repräsentiert den aktuellen Entwicklungsstand und existiert bis zum Löschen des Repositories.
* `feature/1234/name` - Wird für die Entwicklung eines Features angelegt und nach Integration in den `main` Branch gelöscht.
* `bug/4321/name` - Wird für die Umsetzung eines Bug-Fixes angelegt und nach Integration in den `main` Branch gelöscht. 
* `release-0.x.x` - Repräsentiert einen funktionsfähigen Zustand des Produktes. 

### Feature entwickeln

Die folgenden Schritte zeigen einen Feature Entwicklung in einem separaten Branch und bezogen zu einem Ticket mit der ID: *4711*

* Den `main` Branch aktualisieren:
```
git checkout main
git pull
```

* Einen Feature Branch basierend auf dem letzten Commit erzeugen. Dabei die dem Branch-Namen das Prefix (`feature` / `bug`) voranstellen, gefolgt von der Ticket ID und einer beschreibenden Bezeichnung:
```
git branch feature/4711/add-button
git checkout feature/4711/add-button
```

* Änderungen in einer Datei speichern und auf den Branch committen. Dabei auch die Ticket ID mit `#` referenzieren:
```
git add .
git commit -m "#4711 Commit message"
```

* Den Feature Branch auf GitHub bereitstellen:
```
git push --set-upstream origin feature/4711/add-button
```

* Nachdem die Entwicklung abgeschlossen ist, mit einem Pull Request (PR) auf GitHub die Änderung integrieren. Dabei einen sprechenden Namen wählen und eine kurze Beschreibung bereitstellen.

* Den Pull Request (PR) mit **Squash and merge** in den `main` Branch integrieren. 

* Danach im Arbeitsverzeichnis wieder auf den `main` Branch wechseln und den letzten Stand abrufen:
```
git checkout main
git pull
```

### Release Branch erzeugen

Ein Release Branch startet mit dem Namen `release` gefolgt von der Versionsnummer. Die Versionsnummer leitet sich aus dem [Semantic-Versioning](https://semver.org/) ab. 

```
git checkout main
git create -b release-0.1.0
git push --set-upstream origin release-0.1.0
```

# GitHub Markdown

Um Dokumentation auf GitHub zu verwalten, muss diese in Markdown geschrieben werden. Eine gute Quelle um sich mit der Markdown Syntax für die Formattierung vertraut zu machen ist hier verfügbar: [Grundlegende Schreib- und Formatierungssyntax](https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

Neben den Standardfunktionalitäten wie Überschriften, Textformatierungen, Code-Beispiele und Links sind Relative Links eine wichtige Funktionalität um Struktur in die Dokumentation zu bringen. 

## Relative Links

Es können relative Links und Bildpfade in deinen gerenderten Dateien definiert werden, um Leser dabei zu unterstützen, in deinem Repository zu anderen Dateien zu navigieren.

Ein relativer Link ist ein Verknüpfung, die relativ zur aktuellen Datei ist. Wenn sich beispielsweise eine README-Datei im Root deines Repositorys und eine andere Datei in docs/CONTRIBUTING.md befindet, sieht der relative Link zu CONTRIBUTING.md in deiner README-Datei wie folgt aus:

```
[Contribution guidelines for this project](docs/CONTRIBUTING.md)
```

[Contribution guidelines for this project](docs/CONTRIBUTING.md)

## Bilder

Bilder können angezeigt werden, indem man ein `!` hinzufügst und den Alternativtext mit [ ] umschließt. Alternativtext ist ein kurzer Text, der den Informationen im Bild entspricht. Umschließe dann den Link für das Bild mit Klammern ().

![Screenshot of a comment on a GitHub issue showing an image, added in the Markdown, of an Octocat smiling and raising a tentacle.](https://myoctocat.com/assets/images/base-octocat.svg)

## Emojis 

Emojis können dem Text hinzugefügt werden, indem der :EMOJICODE:, einen Doppelpunkt gefolgt vom Namen des Emojis, eingegeben wird.

```
:+1: This PR looks great - it's ready to merge! :shipit:
```

:+1: This PR looks great - it's ready to merge! :shipit:

Eine vollständige Liste der verfügbaren Emojis und Codes findest ist hier verfügbar: [Emojis](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md).

# Zusammenfassung

