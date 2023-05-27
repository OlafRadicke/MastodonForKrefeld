MISSION
=======

Diese Repository beinhaltet Informationsmaterial mit dem Stadtquartieren erklärt werden soll, wie sie Mastodon für sich nutzen können um ihre Projekte zu pushen.

| ![Postkarte](pics/postkarte.jpg)                           |
|------------------------------------------------------------|
| Das ist eine Postkarte, die man drucken und verteilen kann |

[Hier geht es zu Index-Seite](markdown/00-00-index.md)

Mitarbeit
---------

### Hilfreiche Tools zum Arbeiten mit Markdown

Die IDE Visual Studio Code mit dem Plugin "Markdown All in One" hilft euch, mit den Markdown-Dokumenten zu arbeiten. Wenn du Verbesserungen hasst, freue ich mich über ein Pull request von dir.

Der Inhalt der Dokumentation in MarkDown-Format ist in dem Verzeichnis ***hugo-docu/content*** zu
finden.

Erstellen von statischem HTML für die Website
---------------------------------------------

Installiere dir [Hugo](https://gohugo.io/).

Als themes wurde [Ace documentation
More from us](https://docs.vantage-design.com/ace/) verwendet.

Wechsle in das Verzeichnis

```bash
$ cd ./hugo-docu
```
Rufe

```
$ hugo
```

auf. Danach hast du im Verzeichnis /public statischen HTML-Code der auf den Webserver übertragen werden
muss. Jedesmal wenn der Inhalt in /hug-docu/content angepasst wurde, muss der Schritt wiederholt
werden.

Wenn der HTML-Code unter einer alternativen URL gehostet werden soll, muss diese beim generieren mitgegeben werden. Z.B wenn sie hier aug GitHub als Preview gehostet werden soll:

```bash
hugo -b https://olafradicke.github.io/MastodonForKrefeld/ \
--destination ../docs
```

Der generierte HTML-Code muss unter /docs liegen mit github pages die Seietn ausliefert. Nach dem commit und push ist die preview hier zu sehen: [https://olafradicke.github.io/MastodonForKrefeld/](https://olafradicke.github.io/MastodonForKrefeld/)

Für eine Vorschau, kann der eingebaute Webserver verwendet werden: In dem man

```bash
$ hugo server
```

aufruft.


Lizenz
------

![cc logo](pics/cc-by-sa.png)

Alle Texte und Werke in diesem Repository sind lizenziert unter einer Creative Commons Namensnennung - Weitergabe unter gleichen Bedingungen 4.0 International Lizenz.

Deteils siehe [LICENSE.txt](LICENSE.txt)
