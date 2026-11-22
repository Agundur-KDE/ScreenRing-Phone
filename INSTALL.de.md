# Handy-App einrichten

Der erste öffentliche Download ist in Vorbereitung. Dieses Repository enthält
die Anleitung und später die Handy-APK unter **Releases**. Die TV-App wird
separat über Google Play angeboten; sie ist hier nicht enthalten.

## Installation

Android 8 oder neuer und für Anrufmeldungen ein Handy mit Mobiltelefonie werden
benötigt. Handy und Empfänger müssen sich im lokalen Netzwerk erreichen können.

1. Die signierte Handy-APK und `SHA256SUMS` aus demselben Release herunterladen.
   Die Prüfsumme kontrollieren. `SIGNER.txt` enthält den Fingerabdruck des
   öffentlichen Signaturzertifikats. Eine gemeinsam heruntergeladene Prüfsumme
   allein beweist nicht die Identität des Herausgebers.
2. Im Browser oder Dateimanager die Installation aus dieser Quelle erlauben,
   die APK installieren und die Freigabe anschließend bei Bedarf wieder entziehen.
3. Im Empfänger Handy-Empfang einschalten. Adresse und Verbindungsschlüssel in
   die Handy-App übernehmen. Den Schlüssel nicht veröffentlichen oder an Dritte geben.
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

Keine Zusage für WhatsApp/VoIP, ausgehende Anrufe, Gesprächsübertragung oder
automatisches Fortsetzen. Festnetzanrufe von der FRITZ!Box empfängt die TV-App
auch ohne Handy-App. Öffentliche Support- und endgültige Datenschutzangaben
werden vor dem ersten Release ergänzt.
