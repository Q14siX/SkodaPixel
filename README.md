# Skoda Pixel

![Skoda Pixel – Ulanzi TC001 und TC002](media/title.png)

[![Buy Me a Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://buymeacoffee.com/q14six)

**Fahrzeugdaten deines Skoda auf Ulanzi TC001 und TC002 mit AWTRIX NG.**

[**Installationsassistent starten**](https://q14six.github.io/SkodaPixel/) · [English instructions](#english)


## Deutsch

### Was ist Skoda Pixel?

Skoda Pixel zeigt ausgewählte Informationen aus der öffentlichen Skoda Connect API auf LED-Pixeluhren mit **AWTRIX NG**. Die Darstellung ist jeweils auf die Auflösung der Uhr abgestimmt:

- **Ulanzi TC001 (32 × 8 Pixel):** kompakte, gut lesbare Einzelwerte.
- **Ulanzi TC002 (52 × 16 Pixel):** größere Symbole, Beschriftungen und Einzelwerte.

Jede installierte **Skoda Pixel**-Anzeige zeigt **genau eine** vom Nutzer ausgewählte Information. Du kannst die App für mehrere unterschiedliche Werte installieren und die Uhr wie gewohnt zwischen diesen Apps wechseln lassen. Es gibt keine zusätzliche interne Rotation.

### Welche Informationen sind möglich?

Je nach Fahrzeug und tatsächlich bereitgestellten API-Daten stehen unter anderem zur Auswahl: Akkustand, elektrische Reichweite, Ladestatus, Ladeleistung, Ladetempo, Restladezeit, Ladeziel, Ladekabel- und Verriegelungsstatus, Türen, Fenster, Schiebedach, Kofferraum, Motorhaube, Licht, Kilometerstand, Parkstatus, Klimatisierung und Solltemperatur. Für geeignete Fahrzeuge sind außerdem Tankfüllstand, Gesamtreichweite und AdBlue-Reichweite vorgesehen. Nicht verfügbare Werte werden nicht als gültige Fahrzeugdaten ausgegeben.

### Voraussetzungen

- Eine **Ulanzi TC001 oder TC002 mit AWTRIX NG** im erreichbaren lokalen Netzwerk.
- Einen **Skoda-API-Key** und die **Fahrgestellnummer (VIN)** deines Fahrzeugs. Beachte die Nutzungsbedingungen der [öffentlichen Skoda API](https://public.api.connect.skoda-auto.cz/docs).
- Einen aktuellen Browser, der Verbindungen zu deiner Uhr im lokalen Netzwerk zulässt.
- Bei einer geschützten Uhr: deren **AWTRIX-Benutzername und Kennwort**.

### Installation mit dem Assistenten

1. **[Installationsassistent öffnen](https://q14six.github.io/SkodaPixel/).** Die Uhrensuche startet erst mit dem Klick auf **„Uhren suchen“**. Voreingestellt ist `192.168.178.0/24`; du kannst den Bereich ändern oder eine Uhr über ihre IP-Adresse ergänzen.
2. **Eine oder mehrere Uhren auswählen.** Der Assistent prüft die Verbindung und erkennt **TC001 oder TC002 automatisch**. Eine Anmeldeseite erscheint nur für Uhren, die Zugangsdaten benötigen.
3. **Fahrzeug und Anzeigen konfigurieren.** Trage VIN und API-Key ein, wähle pro Uhr die gewünschten Informationen und lege das Abfrageintervall fest. **Standard sind 60 Minuten**; der Wert ist änderbar. Mit **„Orangene Statuspunkte anzeigen“** kannst du die Pixel-Warnhinweise vollständig ausblenden. Fehlertexte bleiben erhalten.
4. **Zusammenfassung kontrollieren und Installation starten.** Der Assistent installiert die passenden Komponenten und Einzelanzeigen auf allen ausgewählten Uhren. Bereits installierte Komponenten können auf diesem Weg auch aktualisiert werden. Jede Uhr erhält eine separate Ergebnisanzeige.

Bei erfolgreicher Installation erscheint **„Installation erfolgreich!“**. Danach übernimmt die Uhr die Anzeige im normalen AWTRIX-App-Wechsel.

### Vorschauen

Die vom Installer verwendeten PNG-Vorschauen findest du in [`media/TC001/`](media/TC001/) und [`media/TC002/`](media/TC002/). Die nicht für den Installer benötigten GIF-Animationen sind im vollständigen ZIP-Paket separat im Hauptverzeichnis unter `media/` enthalten.

### Datenabruf und wichtige Hinweise

Die Anzeigen einer Uhr teilen sich **eine gemeinsame Datenquelle über AWTRIX Shared**. Du kannst also mehrere Einzelanzeigen installieren, ohne dass jede Anzeige selbst einen neuen API-Abruf startet. **Jede Uhr fragt jedoch separat ab** – bei zwei Uhren mit 60-Minuten-Intervall normalerweise zweimal pro Stunde insgesamt.

Die Skoda API kann ältere Fahrzeugdaten zurückgeben. Das Projekt kann **nicht garantieren**, dass Abfragen keine Kommunikation mit dem Fahrzeug auslösen oder die 12-V-Batterie niemals beeinflussen. Wähle ein möglichst schonendes Abfrageintervall.

**Sicherheit:** Der HTML-Installer überträgt neu eingegebene API-Keys als normale AWTRIX-App-Einstellung. Diese kann über die Geräte-API auslesbar sein. Die exportierbare Installer-Konfigurationsdatei speichert weder AWTRIX-Kennwörter noch Skoda-API-Keys. Schütze den Zugriff auf deine Uhr und dein Netzwerk.

**Browser-Einschränkungen:** Die Suche wird nur nach einer bewussten Benutzeraktion ausgeführt. Suche und Installation benötigen erlaubten Zugriff des Browsers auf das lokale Netzwerk. Wenn GitHub Pages diesen Zugriff blockiert, kannst du den vollständigen Projektordner herunterladen und `index.html` lokal öffnen. Auch dann muss der Browser die Verbindung zur Uhr gestatten; eine manuelle IP-Eingabe umgeht die Sperre nicht.

---

## English

### Skoda vehicle information on AWTRIX NG

**Skoda Pixel** displays data from the public Skoda Connect API on **Ulanzi TC001 (32 × 8)** and **TC002 (52 × 16)** clocks running **AWTRIX NG**. Each installed Skoda Pixel display shows **one selected value**. You can install separate displays for different values and let the clock's normal app rotation control when they appear.

Depending on vehicle capabilities and available API data, displays include battery percentage, electric range, charging state and power, remaining charge time, charging target, vehicle access and window states, odometer, parking and climate data. Fuel and AdBlue information is available only for applicable vehicles.

### Requirements

You need a TC001 or TC002 running AWTRIX NG, access to the clock from your browser, your **Skoda API key and VIN**, and AWTRIX credentials if the clock is password-protected. See the [public Skoda API](https://public.api.connect.skoda-auto.cz/docs).

### Install or update

1. **[Open the installation wizard](https://q14six.github.io/SkodaPixel/).** Click **“Uhren suchen”** to start discovery manually. The default range is `192.168.178.0/24`; edit it or enter an IP address if needed.
2. **Select one or more clocks.** The wizard checks connections automatically, identifies the TC001/TC002 model, and requests a username and password only for protected devices.
3. **Choose vehicle settings and displays.** Enter the VIN and API key, select a single vehicle value for each display app, and adjust the fetch interval. **The default is 60 minutes.** Disable **“Orangene Statuspunkte anzeigen”** to hide the orange status pixels while keeping error messages available.
4. **Review and confirm installation.** The matching components are installed or updated on the selected clocks, with an individual completion status for each device.

PNG previews used by the installer: [`TC001 previews`](media/TC001/) · [`TC002 previews`](media/TC002/). Animated GIF examples are distributed separately in the full ZIP archive under the top-level `media/` directory.

### Data, security and connectivity

All Skoda Pixel display apps on **one clock** read from a single shared data provider, avoiding a new Skoda request for each display. Separate clocks have separate fetch schedules. The public API may return previously stored vehicle status; the app cannot guarantee that requests never wake the vehicle or affect its 12 V battery.

Newly entered API keys are stored as ordinary AWTRIX app settings, readable through the device API; the exportable installer profile does **not** store API keys or AWTRIX passwords. Protect your devices and network. Browser restrictions can prevent a hosted page from discovering or reaching devices on your LAN. If necessary, open the downloaded `index.html` locally; local network access permissions are still required.
