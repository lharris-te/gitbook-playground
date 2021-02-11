# DITA import test

### author: $Author: Julian $

## Eigenschaften von SAP®-Anbindungen

Eigenschaften für die Verbindungen zu verfügbaren SAP®-Systemen.

Die folgenden Eigenschaften stellen Sie in der Konfiguration des SAP®-Plug-ins ein:

\|Name\|Beliebiger Name, unter dem dieses SAP®-System in der Verbindungsprojektierung erscheint.\| \|Anmeldeverfahren\|Wählen Sie das gewünschte Anmeldeverfahren aus.\| \|Benutzer\|Benutzername zur Anmeldung am SAP®-System.\| \|Passwort\|Kennwort zur Anmeldung am SAP®-System.\| \|Mandant\|Mandant \(Buchungskreis für den SAP®-Nutzer\).\| \|Sprache\|Geben Sie hier die Sprache ein, die Sie nutzen möchten. Z.B. „de“ steht für Deutsch, „en“ für Englisch usw.\| \|Client-Protokoll\|Auswahl des Client-Protokolls aus dem Drop-Down-Menü. Muss beim Aufbau einer R3-Connection und beim Erstellen eines RFC-Servers gesetzt werden.\|

**Direkte Anmeldung**

\|Host/IP\|Server \(Name oder IP\) mit dem SAP®-Anwendungssystem. Es ist eine explizite Anmeldung an einem System erforderlich \(Kein Load-Balancing-Verfahren\).\| \|System-Nummer\|Nummer des SAP®-Systems.\|

**Load Balancing**

\|Message-Server\|Name oder IP des SAP®-Message-Servers.\| \|Log-on-Gruppe\|Log-on-Gruppe des SAP®-Systems.\| \|System-Nummer\|Nummer des SAP®-Systems.\|

**RFC-Trigger registrieren als**

\|Unicode\|RFC-Trigger registrieren als Unicode\| \|Non-Unicode\|RFC-Trigger registrieren als Non-Unicode\|

**IDocHandling**

\|IDocHandling\|Auswahl, ob ein leeres IDoc erstellt werden soll oder eine Vorlage aus dem SAP®-System genutzt werden soll.\| \|IDoc Kultur\|Auswahl der IDocSprache \(Culture\) deutsch oder englisch, um einen Absturz zu verhindern, wenn eine Instanz im SAP®-Plugin eine ungültige IDoc-Kultur enthält. Die Datums-Schreibweise ist z. B. unterschiedlich:1. Februar im Deutschen 01.02.2018, im Englischen 02.01.2018\|

Über den Button „Test“ können Sie überprüfen, ob Ihre Verbindung erfolgreich ist.

Wenn Sie unter Anmeldeverfahren Secure Network Communications \(SNC\) ausgewählt haben, dann nehmen Sie bitte darunter die SNC Einstellungen vor:

**SNC Einstellungen**

| Name des SNC Partners | Eintrag des SNC Partners. |
| :--- | :--- |
| Sicherheitsstufe | Auswahl der Sicherheitsstufe aus dem Drop-down-Menü z. B. Maximal oder Standard. |
| Authentifizierungsverfahren | Auswahl zwischen NTLM Authentifizierung oder Kerberos5 Authentifizierung. |
| Sicherheitszertifikat | Auswahl eines Sicherheitszertifikates aus der Drop-down-Liste. Über das Pluszeichen können Sie ein weiteres Zertifikat hinzufügen, mit dem Minuszeichen eines entfernen. Ein weiterer Button dient Ihnen dazu, sich die Eigenschaften eines vorhandenen Zertifikats anzeigen zu lassen. |

**Anmerkung:** Um die bevorzugten Einstellungen des verwendeten SAP Nutzers verwenden zu können, benötigt der OPC Router Lesezugriff auf die SAP Tabelle USR01

### Anpassen des verwendeten Ports

Standardmäßig nutzt der OPC Router den Port „33“ zur Kommunikation mit dem SAP-System, also z. B. „3301“, wenn System-Nummer = 01 gesetzt ist. Wenn das SAP®-System einen anderen Port benutzt und das SAP®-GUI nicht installiert ist, muss der Port angepasst werden:

1. Legen Sie eine Sicherungskopie der Datei C:\Windows\System32\drivers\etc\services an.
2. Öffnen Sie die Datei C:\Windows\System32\drivers\etc\services mit einem Text-Editor \(nicht die Kopie\).
3. Ändern oder ergänzen Sie den Eintrag „sapgw00“, wobei die Portnummer im Format „XX00“ anzugeben ist, also z. B. „3600“.

   ```text
   sapgw00 <Portnummer>/tcp
   ```

4. Speichern Sie die Datei.

Der OPC Router benutzt dann die angegebene Nummer.

