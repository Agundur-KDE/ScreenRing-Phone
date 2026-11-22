# Handy-App einrichten

Die Handy-App ist der Android-Begleiter für **[KFritz ab Version 0.5.0](https://github.com/Agundur-KDE/kfritz/releases/tag/v0.5.0)**
auf dem KDE-Plasma-Desktop. **KFritz 0.4.1 oder älter reicht dafür nicht aus.**
Die Handy-APK gibt es separat unter **[Releases](https://github.com/Agundur-KDE/ScreenRing-Phone/releases)**.
Die TV-App wird
separat über Google Play angeboten; sie ist hier nicht enthalten.

Der Handy-Download ist zunächst eine **Alpha zum Testen**. Die passenden
KFritz-Pakete und die signierte Handy-APK sind in den verlinkten Releases verfügbar.

## Installation

Android 8 oder neuer und für Anrufmeldungen ein Handy mit Mobiltelefonie werden
benötigt. Handy und Empfänger müssen sich im lokalen Netzwerk erreichen können.

1. Die signierte Handy-APK und `SHA256SUMS` aus demselben Release herunterladen.
   Die Prüfsumme kontrollieren. `SIGNER.txt` enthält den Fingerabdruck des
   öffentlichen Signaturzertifikats. Eine gemeinsam heruntergeladene Prüfsumme
   allein beweist nicht die Identität des Herausgebers.
2. Im Browser oder Dateimanager die Installation aus dieser Quelle erlauben,
   die APK installieren und die Freigabe anschließend bei Bedarf wieder entziehen.
3. In KFritz unter **Einstellungen → Handyanrufe** den Empfang einschalten,
   Verbindungsschlüssel erzeugen und speichern. In der Handy-App das **KFritz-/
   Desktop-Ziel** einschalten, lokale Rechneradresse, Port (standardmäßig **10123**)
   und Schlüssel übernehmen. Den Schlüssel nicht veröffentlichen oder an Dritte geben.
4. Telefonstatus erlauben. Rufnummer/Kontaktname sind optional; nur bei aktivierten
   Anruferdetails werden die zusätzlichen Berechtigungen angefordert.
5. Weitergabe starten und eine Testmeldung senden. TEST pausiert keinen Film.

Erwarteter SHA-256-Fingerabdruck des öffentlichen Handy-Signaturzertifikats:

```text
e126db475859e63617676ac0030acb3ee3b87242779b26cdced241f1a7405d86
```

Dies ist kein Verbindungsschlüssel. Der Fingerabdruck muss mit dem
APK-Signaturzertifikat und `SIGNER.txt` des Downloads übereinstimmen.

Entwicklerversionen mit Debug-Signatur können nicht einfach durch eine anders
signierte Release-APK ersetzt werden. Eine Deinstallation löscht Einstellungen
und Kopplung. Vor diesem Wechsel die Einrichtung planen.

## Betrieb und Datenschutz

Eine dauerhafte Benachrichtigung zeigt den Hintergrunddienst an. Nach einem
Neustart das Handy einmal entsperren. Hersteller-Energiesparregeln und ein
erzwungenes Beenden können den Dienst blockieren; dann App öffnen und starten.

Anruferdetails werden bei aktivierter Funktion und erteilten Rechten lokal
ermittelt und verschlüsselt an die gekoppelten Empfänger gesendet. Geräte- und
Anrufkennungen sowie die Ereignisart stehen im Protokollkopf. Die Empfänger
verarbeiten die Meldung und können sie für Personen vor ihrem Bildschirm anzeigen.
Die App benötigt kein Entwickler-Cloudkonto und enthält keine Werbe- oder
Analyse-SDKs. Einstellungen und Schlüssel bleiben im privaten App-Speicher;
Android-Backup und Geräteübertragung sind deaktiviert.

Bei Problemen prüfen, ob Rechner und KFritz laufen und sich Handy und Rechner
im Heimnetz erreichen können. Gast-WLAN, Client-Isolation und eine Firewall
können den Empfang blockieren. Den Empfangsport nur im vertrauenswürdigen
Heimnetz freigeben. Eine FRITZ!Box ist für den Transport der Handymeldung nicht nötig.

Keine Zusage für WhatsApp/VoIP, ausgehende Anrufe, Gesprächsübertragung oder
automatisches Fortsetzen. Festnetzanrufe von der FRITZ!Box empfängt die TV-App
auch ohne Handy-App. Handy und TV können direkt gekoppelt werden; KFritz ist
kein erforderlicher Vermittler für diesen Weg.

[Datenschutz und Berechtigungen](PRIVACY.md) ·
[Hilfe und Fehlermeldungen](https://github.com/Agundur-KDE/ScreenRing-Phone/issues)

Keine echten Anruferdaten, Schlüssel oder unbereinigten Logs in öffentliche
Fehlermeldungen einfügen. Dieses Repository veröffentlicht die fertige Handy-APK,
nicht deren Quellcode. KFritz selbst bleibt ein separates GPL-Projekt.
