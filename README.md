# 🇮🇹 Italiano 250

Mobile-first Italienisch-Lernapp mit 250 ausgewählten Kernwörtern, 10 Themen, 10 Dialogen, Tagestraining, Quiz, Wiederholungsplan, Browser-Sprachausgabe und optionaler Browser-Spracherkennung.

## GitHub Pages veröffentlichen

1. Auf github.com anmelden und ein **öffentliches** Repository namens `italiano250` erstellen.
2. Alle Dateien **aus diesem Ordner** in das Stammverzeichnis des Repositorys hochladen (nicht den ZIP-Ordner als einzelne Datei).
3. Im Repository **Settings → Pages** öffnen.
4. Unter **Build and deployment** als Source **Deploy from a branch** auswählen; Branch **main**, Ordner **/(root)** auswählen und **Save** drücken.
5. Nach einigen Minuten `https://DEIN-GITHUB-NAME.github.io/italiano250/` öffnen.
6. Auf dem iPhone in **Safari** öffnen → **Teilen** → **Zum Home-Bildschirm**.

Alternativ kann das Repository mit Git lokal verwaltet werden; ein Build-Schritt ist nicht nötig.

## Bedienung

- **Start**: Tagestraining (bis zu 5 fällige + 8 neue Wörter)
- **Lernen**: 10 Themen mit je 25 Wörtern
- **Wiederholen**: 1/3/7/14/30-Tage-Intervalle; Quiz
- **Dialoge**: 10 Alltagsdialoge, Hör- und Sprechübungen
- **Statistik**: Fortschritt, 30-Tage-Übersicht, JSON-Export und -Import

## iPhone/Safari und Audio

Sprachausgabe verwendet die Web Speech Synthesis API (`it-IT`), ohne externe Schlüssel. Verfügbare Stimmen hängen von iOS und den installierten Stimmen ab. Für Spracheingabe wird die Web Speech Recognition API verwendet, **falls** sie im jeweiligen Safari/iOS-Build verfügbar ist. Andernfalls zeigt die App eine verständliche Alternative (Anhören und selbst nachsprechen). Die angezeigte Wortübereinstimmung ist **keine** echte phonetische Aussprachebewertung. Mikrofonberechtigung kann erforderlich sein. Onlinezugang kann für die Spracherkennung nötig sein.

## Offline / Datenschutz

Die App-Shell und Wortliste werden über einen Service Worker zwischengespeichert. Nach dem ersten vollständigen Laden funktionieren Vokabeln, Quiz und lokal gespeicherter Fortschritt weitgehend offline; Audio hängt von Gerät und verfügbarer Stimme ab, Spracherkennung kann online benötigen. Lernstände liegen nur in `localStorage` dieses Browsers/Geräts. Für Backups: **Statistik → Daten exportieren**; für Wiederherstellung **Daten importieren**. Kein Tracking, kein Backend.

## Wartung

Die Inhalte sind in `words.json`; der Browser lädt sie beim Start. Bei Änderungen an statischen Dateien `CACHE` in `sw.js` hochzählen, um alte Offline-Caches zu entfernen. Die 250 Wörter sind eine didaktische Auswahl, keine linguistisch validierte Häufigkeitsrangliste. Beispieltexte können zusätzliche Wörter und Flexionsformen enthalten. Der 30-Tage-Plan ist eine Motivationsstruktur, kein garantierter Spracherfolg.

## Lokal testen

Im Projektordner `python3 -m http.server 8000` ausführen und `http://localhost:8000` öffnen. Nicht `index.html` als `file://` öffnen, da `fetch` sonst blockiert werden kann.
