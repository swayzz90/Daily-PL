# Daily Brain PL

Polnische Version von Daily Brain: Wiadomości (Nachrichten), Czytaj (Lesen) und Nauka (Lernen) als Web-App für den Home-Bildschirm. Läuft auf GitHub Pages, Fortschritt bleibt auf dem Gerät.

## Einrichten (neues Repo, nur iPhone nötig)

1. Auf GitHub ein neues, öffentliches Repo anlegen, zum Beispiel `daily-brain-pl`.
2. Alle Dateien aus dem ZIP hochladen (Add file → Upload files). Alles liegt flach im Hauptordner.
3. Den Workflow anlegen: Add file → Create new file, als Name `.github/workflows/deploy.yml` eingeben und den Text der `deploy.yml` aus dem deutschen Repo einfügen. Der Text ist identisch.
4. Settings → Pages → Source auf „GitHub Actions“ stellen.
5. Actions → „Nachrichten holen & veröffentlichen“ → Run workflow. Nach wenigen Minuten ist die Seite unter `https://DEINNAME.github.io/daily-brain-pl/` erreichbar. Der erste Lauf dauert länger, weil die Porträts geholt werden.
6. iPhone: in Safari öffnen, Teilen → Zum Home-Bildschirm. Android: Chrome-Menü → App installieren.

Danach läuft die Action stündlich und aktualisiert Nachrichten und Porträts.

## Was drin ist

- **Wiadomości:** Meldungen aus 48 Quellen (30 polnisch, 18 englisch), Themen, Region (Wszystkie, Polska, Świat), Sprachknopf (Wszystkie, PL, EN), Bezahlartikel-Filter.
- **Czytaj:** Artikel zu Wissenschaft, Psychologie, Geschichte, Philosophie, Gesellschaft und Gesundheit (8 polnische, 13 englische Quellen).
- **Nauka:** Stolice, Który kraj?, Flagi, Znajdź flagę, Mapa, Prawda czy fałsz, Wcześniej czy później?, Zgadnij rok, Oś czasu, Teczka (die Akte), Pojedynek epok, Zagadka cytatów, Powiązania, Twarze, Karty dnia, Album postaci und die Mapa wiedzy.
- **Inhalte (`content.json`):** 99 Ereignisse, 69 Aussagen, 55 Wissenskarten, 73 Personen, 118 Verbindungen mit Begründung, 15 Zitate mit Quelle. Länder und Hauptstädte stehen in `countries.json` (194 Länder mit polnischen Namen), die Karte in `map.json`.
- **Porträts:** `fetch-portraits.mjs` holt über die polnische Wikipedia nur frei lizenzierte Bilder von Wikimedia Commons und zeigt Urheber und Lizenz im Profil.

## Gut zu wissen

- Die Quellen in `feeds.json` sind teils aus dem Gedächtnis eingetragen. Ausfälle stehen im Log der Action; dann die Adresse korrigieren oder die Zeile löschen.
- Die Texte der Personen und Wissenskarten sind selbst geschrieben und können Fehler enthalten.
- Bezahlartikel werden nicht umgangen, nur ausgeblendet.
- Diese App und die deutsche Version liegen auf derselben Domain (`github.io`). Damit sich nichts vermischt, nutzt die polnische App eigene Speicher- und Cache-Namen (`dbpl:`, `dbpl-`).
- GitHub pausiert geplante Läufe nach 60 Tagen ohne Aktivität im Repo. Dann einmal „Run workflow“ drücken.
