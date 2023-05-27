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

Einrichten der entwicklungsumgebung
-----------------------------------

### HUGO installieren

Installiere dir [Hugo](https://gohugo.io/) je nachdem welches Betriebssystem du hast nach Anleitung.

### Diese Repo clonen

Mit du an den Code arbeiten kannst, klone das Repo:

```bash
cd ./dein_verzeichnis_deiner_wahl
git clone git@github.com:OlafRadicke/MastodonForKrefeld.git
```

### Das Themes installieren

Als themes wurde [Ace documentation](https://docs.vantage-design.com/ace/) verwendet. Zum installieren:

```bash
cd ./MastodonForKrefeld/hugo-docu/themes/
git clone https://github.com/vantagedesign/ace-documentation
```

Generieren des statischem HTML für die Website
----------------------------------------------


### Lokale Vorschau

Für eine Vorschau, kann der eingebaute Webserver verwendet werden: In dem man

```bash
$ hugo \
    --source ./hugo-docu \
    server
```

aufruft. Danach kannst du die URL http://localhost:1313/ in deinem Browser aufrufen um die Vorschau zu sehen.

### Vorschau per GitHub pages

Wenn du eine Vorschau per GitHub pages erstellen willst, um diese Vorschau mit anderen zu teilen, musst du drei dinge beachten:

- GutHub pages muss eingeschaltet sein [siehe DOKU](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- Der statische HTML-Code mus im dem richtigen Verzeichne abgelegt werden (in meinem Fall ***/docs***)
- Bei dem generieren des HTML-Codes muss HUGO mitgeteilt werden, unter welcher URL der Code gehostet wird. In meinem Fall [https://olafradicke.github.io/MastodonForKrefeld/](https://olafradicke.github.io/MastodonForKrefeld/). Wenn du dieses Repo clones, wird sich die URL aber ändern!

Um die letzten beiden Bedingungen zu erfüllen muss der Hugo-Aufruf wie folgt lauten:

```bash
hugo \
  --source ./hugo-docu \
  --baseURL  https://olafradicke.github.io/MastodonForKrefeld/ \
  --destination ../docs
```

### Code deployment auf den Server "https://start.krefeld.life"

Der statische Code für den Webserver muss ein klein wenig ander generiert werden, da
er unter einer anderen URL gehostet wird:

```bash
hugo \
  --cleanDestinationDir \
  --source ./hugo-docu \
  --baseURL  https://start.krefeld.life \
  --destination ../public
```

Jetzt muss der Code noch auf den Server. Am besten per ssh/rsync:

```bash
rsync \
-r \
-n \
--stats \
--progress \
--update \
--delete  \
./public/ \
  ./public/ \
  user@server:~/doms/start.krefeld.life/htdocs-ssl/
```

Der Parameter "-n" sorgt dafür, das es nur ein Testlauf ist!

Jedesmal wenn der Inhalt in /hug-docu/content angepasst wurde, müssen die Schritt wiederholt
werden.

Lizenz
------

![cc logo](pics/cc-by-sa.png)

Alle Texte und Werke in diesem Repository sind lizenziert unter einer Creative Commons Namensnennung - Weitergabe unter gleichen Bedingungen 4.0 International Lizenz.

Deteils siehe [LICENSE.txt](LICENSE.txt)
