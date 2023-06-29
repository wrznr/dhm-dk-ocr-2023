layout: true
  
<div class="my-header"></div>

<div class="my-footer">
  <table>
    <tr>
      <td style="text-align:right">Sächsische Landesbibliothek – Staats- und Universitätsbibliothek</td>
      <td>Date</td>
      <td style="text-align:right"><a href="https://www.slub-dresden.de/">www.slub-dresden.de</a></td>
    </tr>
    <tr>
      <td style="text-align:right">Referate 2.5 & 4.3</td>
      <td />
    </tr>
  </table>
</div>

<div class="my-title-footer">
  <table>
    <tr>
      <td style="text-align:left"><b>Robert Sachunsky & Kay-Michael Würzner</b></td>
    </tr>
    <tr>
      <td style="text-align:left">Referate 2.5 bzw. 4.3</td>
    </tr>
    <tr>
      <td style="font-size:8pt"><b>30. Juni 2023</b></td>
    </tr>
    <tr>
      <td style="font-size:8pt">Seminar *Datenkompetenz für Digital Humanities*</td>
    </tr>
  </table>
</div>

---

class: title-slide
count: false

# Optical Character Recognition
## Vom Bild zum Text

---

# Überblick

- Kurze Einführung OCR
- Hands-on Web: OCR mit Wikimedia
- Demo Shell: OCR mit Tesseract
- Hands-on Python: OCR mit Tesserocr
- Demo *komplex*: optimierte OCR mit OCR-D

---

class: part-slide
count: false

# Kurze Einführung OCR

---

class: part-slide
count: false

# OCR mit Wikimedia

---

# OCR mit Wikimedia

- einfaches Webinterface zur OCR von Wikimedia-Inhalten

<center>
<img src="img/wikimedia.png" height="300px" />
</center>

→ [ocr-test.wmcloud.org](https://ocr-test.wmcloud.org/)

---

# OCR mit Wikimedia

Aufgabe
- Suchen Sie sich ein [geeignetes Bild](https://upload.wikimedia.org/wikipedia/commons/0/0e/Weisse_Scherzhafte_Lieder_003.jpg) bei Wikimedia.Commons (Tipp: via Wikisource)!
- Führen Sie eine OCR aus!
- Kopieren Sie sich das Textresultat!
- Führen Sie eine zweite OCR mit veränderten Parametern aus!
- Kopieren Sie sich das Textresultat
- Vergleichen Sie die Ergebnisse auf [diffchecker](https://www.diffchecker.com/)! Was fällt Ihnen alles auf?

---

# OCR mit Wikimedia

<center>
<img src="img/diff.png" height="400px" />
</center>


---

class: part-slide
count: false

# OCR mit Tesseract

---

# OCR mit Tesseract

- mit großem Abstand: verbreitetste OCR-Software
    + Einsatz in unzähligen Apps, Forschungsprojekten, privaten Kontexten
- kostenlos verwendbar, quelloffen entwickelt
- Teil praktisch aller **Linux**distributionen
    + Installation auf MacOS per `Homebrew` und `MacPorts` möglich
    + Installation unter Windows per [Installer](https://github.com/UB-Mannheim/tesseract/wiki) möglich
- Zugriff auf Tesseract per
    + Programmierschnittstelle (API)
    + **Kommandozeilenschnittstelle** (CLI)
    + graphische Benutzeroberfläche (GUI, Drittanbieter)
- Erkennunsgmodelle für zahlreiche Sprachen bzw. Schriften vorhanden
    + teilweise als installierbare Pakete
    + empfehlenswert jedoch Download von [GitHub](https://github.com/tesseract-ocr/tessdata_best)

---

# OCR mit Tesseract

- Prinzipielle Kommandostruktur
```
tesseract EINGABEBILD AUSGABE (OPTIONEN) (AUSGABEKONFIGURATION)
```
- einfachster Aufruf
```
$ tesseract sample.png -
```
    + `-` schickt die Ergebnisse nach `stdout`
    + Modell `eng` per default ausgewählt
    + Konfiguration `txt` per default ausgewählt

.cols[
.sixty[
```
The Quick Brown
Fox Jumps Over
The Lazy Dog
```
]
.fourty[
<center>
<img src="img/sample.png" width="300px" />
<p style="font-size:4pt;">Image by Peter J. Acklam, public domain</p>
</center>
]
]

---

# OCR mit Tesseract

- Modellauswahl
    + Option `-l MODELLNAME`, Datei `MODELLNAME.traineddata` nötig
    + eventuell in Kombination mit `--tessdata-dir`
    + Kombination mehrerer Modelle möglich:
      `-l MODELLNAME+MODELLNAME2+MODELLNAME3`
- Segmentierung
    + Option `-psm MODUS` (Liste verfügbarer Optionen via `--help-psm`)
    + Möglichkeit einzelne Absätze, Zeilen oder gar Wörter zu verarbeiten
- Bildauflösung
    + wichtiger Faktor für Ergebnisqualität
    + idealerweise min. 300 dpi
    + unter Umständen Teil der Metadaten, anonsten: `Warning: Invalid resolution 0 dpi. Using 70 instead.`
    + manuell per `--dpi` setzbar

---

class: part-slide
count: false

# OCR mit Tesserocr

---

class: part-slide
count: false

# optimierte OCR mit OCR-D

---

class: part-slide

# Many thanks for your attention!

<center>
<a href="https://wrznr.github.io/dhm-dk-ocr-2023/">wrznr.github.io/dhm-dk-ocr-2023</a>
</center>
