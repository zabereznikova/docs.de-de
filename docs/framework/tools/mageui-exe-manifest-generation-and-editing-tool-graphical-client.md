---
title: "MageUI.exe (Manifest Generation and Editing Tool, Graphical Client) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Manifest Generation and Editing tool"
  - "MageUI.exe"
ms.assetid: f9e130a6-8117-49c4-839c-c988f641dc14
caps.latest.revision: 38
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 38
---
# MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)
"MageUI.exe" unterstützt dieselbe Funktionalität wie das Befehlszeilentool "Mage.exe", verwendet jedoch eine Windows\-basierte Benutzeroberfläche.  Mit diesem Tool können Sie Bereitstellungs\- und Anwendungsmanifeste erstellen, bearbeiten und signieren.  Für neue Manifeste, die mit "MageUI.exe" erstellt werden, wird als Zielversion [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] festgelegt.  Voherige Versionen von "MageUI.exe" sollten verwendet werden, um ältere .NET Framework\-Versionen als Ziel festzulegen.  Beim Hinzufügen oder Entfernen von Assemblys aus einem Manifest oder beim erneuten Signieren von vorhandenen Manifesten wird das Manifest von "MageUI.exe" nicht aktualisiert, um als Zielversion [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] festzulegen.  Weitere Informationen finden Sie unter [Mage.exe \(Tool zum Generieren und Bearbeiten von Manifesten\)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
 Dieses Tool wird automatisch mit Visual Studio installiert.  Zum Ausführen des Tools verwenden Sie die Developer\-Eingabeaufforderung \(oder die Visual Studio\-Eingabeaufforderung in Windows 7\).  Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Zwei Versionen von "Mage.exe" und "MageUI.exe" werden als Komponenten des [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)]\-Setups bereitgestellt.  Die Versionsinformationen können Sie anzeigen, indem Sie "MageUI.exe" ausführen, zunächst **Hilfe** und anschließend **Info** auswählen.  In dieser Dokumentation wird Version 4.0.x.x von "Mage.exe" und "MageUI.exe" beschrieben.  
  
> [!NOTE]
>  MageUI.exe unterstützt nicht das [compatibleFrameworks](../Topic/%3CcompatibleFrameworks%3E%20Element%20\(ClickOnce%20Deployment\).md)\-Element, wenn es ein Anwendungsmanifest speichert, das bereits mithilfe von "MageUI.exe" mit einem Zertifikat signiert wurde.  Stattdessen müssen Sie [Mage.exe](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md) verwenden.  
  
## UIElement-Liste  
 Die folgende Tabelle gibt einen Überblick über die verfügbaren Menü\- und Symbolleistenelemente.  
  
|Befehl|Menü|Verknüpfung|Beschreibung|  
|------------|----------|-----------------|------------------|  
|**Anwendungsmanifest**|**Datei, Neu**||Erstellt ein neues Anwendungsmanifest.|  
|**Bereitstellungsmanifest**|**Datei, Neu**||Erstellt ein neues Bereitstellungsmanifest.|  
|**Öffnen**|**Datei**|STRG\+O|Öffnet ein vorhandenes Bereitstellungsmanifest, Anwendungsmanifest oder eine Vertrauenslizenz zum Bearbeiten.|  
|**Schließen**|**Datei**|STRG\+F4|Schließt eine geöffnete Datei.<br /><br /> Wenn Sie eine Datei vor dem Schließen bearbeiten, fordert "MageUI.exe" Sie auf, die Datei mit einem öffentlichen Schlüssel, einem Schlüsselpaar oder einem gespeicherten Zertifikat erneut zu signieren.|  
|**Speichern**|**Datei**|STRG\+S|Speichert das Dokument, das den Benutzereingabefokus hat, auf einen Datenträger.|  
|**Speichern unter**|**Datei**||Speichert eine Datei auf einen Datenträger unter Angabe eines neues Dateinamens und\/oder Speicherorts.|  
|**Alle speichern**|**Datei**||Speichert die an allen in "MageUI.exe" geöffneten Dateien vorgenommenen Änderungen.|  
|**Einstellungen**|**Datei**||Öffnet das Dialogfeld **Einstellungen**.  Weitere Informationen finden Sie in folgendem Abschnitt.|  
|**Beenden**|**Datei**|ALT\+F4|Beendet "MageUI.exe".|  
|**Ausschneiden**|**Edit**|STRG\+X|Entfernt den momentan markierten Text aus der Anwendung und verschiebt ihn in die Zwischenablage des Systems.|  
|**Kopieren**|**Edit**|STRG\+C|Kopiert den aktuell ausgewählten Text in die Zwischenablage des Systems.|  
|**Einfügen**|**Edit**|STRG\+V|Fügt den Text aus der Zwischenablage des Systems in das momentan aktive Textelement ein.|  
|**Löschen**|**Edit**||Löscht ein aktuell in einer Liste ausgewähltes Element, z. B. eine Vertrauenslizenz auf der Registerkarte **Bereitstellungsmanifest**.|  
|**Alle schließen**|**Fenster**||Schließt alle aktuell in "MageUI.exe" geöffneten Dateien.  Wenn mindestens eine Datei gespeichert werden muss, fordert Sie "MageUI.exe" dazu auf.  "MageUI.exe" fordert Sie zudem auf, für jede nicht signierte oder geänderte Datei einen Signaturschlüssel auszuwählen.|  
|**Info**|**Hilfe**||Zeigt Versions\- und Copyrightinformationen zu "MageUI.exe" an.|  
  
## Dialogfeld "Einstellungen2  
 Das Dialogfeld **Einstellungen** enthält die folgenden Elemente:  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Beim Speichern signieren**|Fordert Sie beim Speichern der vorgenommenen Änderungen zum Signieren der Datei auf.|  
|**Standardsignaturzertifikat verwenden**|Verwendet den im Textfeld **Zertifikatsdatei** eingegebenen Schlüssel zum Signieren aller Dateien.  Auf diese Weise wird die Aufforderung zum Signieren, die i. d. R. angezeigt wird, nicht mehr angezeigt, wenn Sie eine Datei mit **Beim Speichern signieren** speichern.  Verwenden Sie die Ellipsenschaltfläche \(**…**\) neben dem Textfeld **Zertifikatdatei**, um eine Schlüsseldatei auszuwählen.|  
|Digestalgorithmus|Gibt den Algorithmus an, mit dem Abhängigkeitsdigests generiert werden sollen.  Der Wert muss "sha256RSA" oder "sha1RSA" sein.  Als Standard wird SHA1 verwendet.  Wird sowohl im Anwendungs\- als auch im Bereitstellungsmanifest verwendet.  Wenn der Benutzer beim Speichern des Manifests ein Zertifikat angibt, werden die Algorithmen im Zertifikat verwendet, um damit Abhängigkeitsdigests zu generieren.|  
  
## Dialogfeld "Signaturoptionen"  
 Das Dialogfeld **Signaturoptionen** wird angezeigt, wenn Sie ein Manifest oder eine Vertrauenslizenz zum ersten Mal speichern oder Änderungen daran vornehmen.  Das Dialogfeld wird nur dann angezeigt, wenn die Option **Beim Speichern signieren** im Dialogfeld **Einstellungen** aktiviert ist.  Beim Signieren eines Manifests, das einen Wert im Textfeld **Zeitstempel\-URI** angibt, müssen Sie mit dem Internet verbunden sein.  
  
 Dieses Dialogfeld enthält die folgenden Elemente:  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Mit Zertifikatsdatei signieren**|Signiert das Manifest mit einem im Dateisystem gespeicherten digitalen Zertifikat.|  
|**Datei**|Stellt einen Bereich für die Eingabe des Pfads zur PFX\-Datei bereit, die das Zertifikat darstellt.|  
|**...**|Öffnet das Dialogfeld **Datei auswählen** zum Auswählen einer vorhandenen PFX\-Datei.|  
|**Neu**|Generiert eine neue PFX\-Datei, die nicht durch eine Zertifizierungsstelle überprüft wird.  Weitere Informationen zu den Zertifikatstypen, die zum Signieren von [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]\-Bereitstellungen verwendet werden, finden Sie unter [Überblick über die Bereitstellung vertrauenswürdiger Anwendungen](../Topic/Trusted%20Application%20Deployment%20Overview.md).|  
|**Kennwort**|Stellt einen Bereich für die Eingabe des Kennworts zum Signieren mit diesem Zertifikat bereit.  Kann leer bleiben, wenn kein Kennwort verwendet wird.|  
|**Mit gespeichertem Zertifikat signieren**|Zeigt eine Liste für die Auswahl aus im Zertifikatsspeicher des Computers gespeicherten digitalen Zertifikaten an.|  
|**Zeitstempel\-URI**|Zeigt den Uniform Resource Locator \(URI\) eines digitalen Zeitstempeldiensts an.  Der Zeitstempel verhindert, dass Sie ein Manifest neu signieren müssen, wenn das digitale Zertifikat abläuft, bevor Sie die nächste Version der Anwendung bereitstellen.  Weitere Informationen finden Sie unter [Mitglieder des Windows\-Programms für Stammzertifikate](http://go.microsoft.com/fwlink/?LinkId=159000) und [ClickOnce und Authenticode](../Topic/ClickOnce%20and%20Authenticode.md).|  
|**Nicht signieren**|Ermöglicht das Speichern des Manifests, ohne eine Signatur aus einem digitalen Zertifikat hinzuzufügen.|  
  
## Beschreibungen von Registerkarten und Bereichen  
 Wenn Sie ein Dokument mit "MageUI.exe" öffnen, wird es in einer eigenen Registerkarte geöffnet.  Jede Registerkarte enthält mehrere Eigenschaftenbereiche.  Die Bereiche enthalten gruppierte Teilmengen der Dokumentdaten.  
  
### Registerkarte "Anwendungsmanifest"  
 Auf der Registerkarte **Anwendungsmanifest** werden die Inhalte eines Anwendungsmanifests angezeigt.  Das Anwendungsmanifest beschreibt alle in einer Bereitstellung enthaltenen Dateien sowie die für die Anwendung zum Ausführen des Clients erforderlichen Berechtigungen.  
  
 Die Registerkarte **Anwendungsmanifest** enthält die folgenden Registerkarten.  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Name**|Gibt bezeichnende Informationen zur Bereitstellung an.|  
|**Beschreibung**|Gibt Herausgeber\-, Produkt\- und Supportinformationen an.|  
|**Anwendungsoptionen**|Gibt an, ob dies eine Browseranwendung und das Manifest die Quelle der vertrauenswürdigen Informationen ist.|  
|**Dateien**|Gibt alle Dateien an, aus denen die Bereitstellung besteht.|  
|**Erforderliche Berechtigungen**|Gibt den minimalen Berechtigungssatz an, der von der Anwendung für die Ausführung auf einem Client erforderlich ist.|  
  
### Registerkarte "Name"  
 Die Registerkarte **Name** wird angezeigt, wenn Sie ein Anwendungsmanifest erstmalig erstellen oder öffnen.  Sie identifiziert die Bereitstellung eindeutig und gibt optional eine gültige Zielplattform an.  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Name**|Erforderlich.  Der Name des Anwendungsmanifests.  In der Regel identisch mit dem Dateinamen.|  
|**Version**|Erforderlich.  Die Versionsnummer der Bereitstellung im Format *N.N.N.N*.  Nur die erste Hauptbuildnummer ist erforderlich.  Für Version 1.0 einer Anwendung sind `1`, `1.0`, `1.0.0` und `1.0.0.0` z. B. gültige Werte.|  
|**Prozessor**|Dies ist optional.  Die Computerarchitektur, auf der diese Bereitstellung ausgeführt werden kann.  Der Standardwert ist `msil` oder Microsoft Intermediate Language, das Standardformat für alle verwalteten Assemblys.  Ändern Sie dieses Feld, wenn Sie die Assemblys in der Anwendung für eine bestimmte Architektur vorkompiliert haben.  Weitere Informationen zur Vorkompilierung finden Sie unter [Ngen.exe \(Native Image Generator\)](../../../docs/framework/tools/ngen-exe-native-image-generator.md).|  
|**Kultur**|Dies ist optional.  Der zweiteilige ISO\-Land\- und Regionscode, in dem die Anwendung ausgeführt wird.  Die Standardeinstellung ist `Neutral`.|  
|**Öffentliches Schlüsseltoken**|Dies ist optional.  Der öffentliche Schlüssel, mit dem dieses Anwendungsmanifest signiert wurde.  Wenn es sich um ein neues oder unsigniertes Manifest handelt, wird dieses Feld als `Nicht signiert` angezeigt.|  
  
### Registerkarte "Beschreibung"  
 Diese Informationen werden normalerweise im Bereitstellungsmanifest bereitgestellt.  Diese Felder können nur geändert werden, wenn das Kontrollkästchen **Anwendungsmanifest für Vertrauensinformationen verwenden** auf der Registerkarte  **Anwendungsoptionen** aktiviert ist.  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Herausgeber**|Der Name der Person oder Organisation, die für die Anwendung verantwortlich ist.  Dieser Wert wird als Ordnername für das Startmenü verwendet.|  
|**Produkt**|Der vollständige Produktname.  Bei Auswahl von **Lokal installieren** für das Element **Anwendungstyp** auf der Registerkarte **Bereitstellungsoptionen** des Bereitstellungsmanifests wird dieser Name im Menülink **Start** und in **Software** für diese Anwendung angezeigt.|  
|**Supportstandort**|Die URL, über die Kunden Hilfe und Unterstützung für die Anwendung erhalten können.|  
  
### Registerkarte "Anwendungsoptionen"  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Windows Presentation Foundation\-Browseranwendung**|Gibt an, ob es sich um eine WPF\-Anwendung handelt, die im Browser als XAML\-Browseranwendung \(XBAP\) ausgeführt wird.|  
|**Anwendungsmanifest für Vertrauensinformationen verwenden**|Gibt an, ob dieses Manifest Vertrauensinformationen enthält.|  
  
### Registerkarte "Dateien"  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Anwendungsverzeichnis**|Das Verzeichnis, in dem sich die Dateien der Anwendung befinden.  Verwenden Sie die Schaltfläche mit den Auslassungszeichen \(**...**\), um das Verzeichnis auszuwählen.|  
|**Auffüllen**|Fügt alle Dateien im Anwendungsverzeichnis und in den Unterverzeichnissen zum Anwendungsmanifest hinzu.  Wenn "MageUI.exe" im Verzeichnis eine einzelne ausführbare Datei findet, wird diese automatisch als Einstiegspunkt gekennzeichnet. Hierbei handelt es sich um die Datei, die zuerst ausgeführt wird, wenn die ClickOnce\-Anwendung auf dem Client gestartet wird.|  
|**Anwendungsdateien**|Zeigt eine Liste aller Dateien in der Anwendung an.  Jede Datei verfügt über drei bearbeitbare Attribute, die unten erläutert werden.|  
|**Dateityp**|Der Dateityp kann einen von vier Werten aufweisen:<br /><br /> -   Keine.<br />-   Einstiegspunkt.  Die primäre ausführbare Datei der Anwendung.  Nur eine ausführbare Datei kann als Einstiegspunkt markiert werden.<br />-   Datendatei.  Eine Datei, z. B. eine XML\-Datei, die Daten für die Anwendung bereitstellt.<br />-   Symboldatei.  Ein Anwendungssymbol, das auf dem Desktop oder in der Ecke des Anwendungsfensters angezeigt wird.|  
|**Optional**|Als "optional" markierte Dateien werden nicht bei der ersten Installation oder Aktualisierung heruntergeladen, aber werden möglicherweise zur Laufzeit mithilfe der bedarfsabhängigen API "System.Deployment" heruntergeladen.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bedarfsgerechtes Herunterladen von Assemblys mit der API für die ClickOnce\-Bereitstellung unter Verwendung des Designers](../Topic/Walkthrough:%20Downloading%20Assemblies%20on%20Demand%20with%20the%20ClickOnce%20Deployment%20API%20Using%20the%20Designer.md).|  
|**Gruppieren**|Eine Bezeichnung für einen Satz optionaler Dateien.  Sie können einem Satz von Dateien die Bezeichnung "Gruppieren" zuweisen und einen Batch von Dateien mithilfe der bedarfsabhängigen API in einem einzigen API\-Aufruf herunterladen.|  
  
### Registerkarte "Erforderliche Berechtigungen"  
 Verwenden Sie die Registerkarte  **Erforderliche Berechtigungen**, wenn Sie der Anwendung umfassenderen Zugriff auf den lokalen Computer gewähren müssen, als ihr standardmäßig erteilt wird.  Weitere Informationen finden Sie unter [Sichern von ClickOnce\-Anwendungen](../Topic/Securing%20ClickOnce%20Applications.md).  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Berechtigungssatztyp**|Der minimale Berechtigungssatz, der von der Anwendung für die Ausführung auf dem Client erforderlich ist.  Eine Beschreibung dieser Berechtigungssätze und der erforderlichen Berechtigungen finden Sie unter [NIB: Named Permission Sets](http://msdn.microsoft.com/de-de/08250d67-c99d-4ab0-8d2b-b0e12019f6e3).|  
|**Details**|Die für das Anwendungsmanifest erstellte XML\-Datei zum Darstellen des Berechtigungssatzes.  Sie sollten diesen XML\-Code nicht manuell bearbeiten, sofern Sie nicht mit dem XML\-Format des Anwendungsmanifests vertraut sind.  Weitere Informationen finden Sie unter [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md).|  
  
### Registerkarte "Bereitstellungsmanifest"  
 Die Registerkarte **Bereitstellungsmanifest** enthält die folgenden Registerkarten.  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Name**|Gibt bezeichnende Informationen zur Bereitstellung an.|  
|**Beschreibung**|Gibt Herausgeber\-, Produkt\- und Supportinformationen an.|  
|**Bereitstellungsoptionen**|Gibt zusätzliche Informationen zur Bereitstellung an, z. B. den Anwendungstyp und die Startposition.|  
|**Aktualisierungsoptionen**|Gibt an, wie oft [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] nach Anwendungsupdates suchen soll.|  
|**Anwendungsverweis**|Gibt das Anwendungsmanifest für diese Bereitstellung an.|  
  
### Registerkarte "Name"  
 Die Registerkarte **Name** wird angezeigt, wenn Sie ein Bereitstellungsmanifest erstmalig erstellen oder öffnen.  Sie identifiziert die Bereitstellung eindeutig und gibt optional eine gültige Zielplattform an.  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Name**|Erforderlich.  Der Namen des Bereitstellungsmanifests.  In der Regel identisch mit dem Dateinamen.|  
|**Version**|Erforderlich.  Die Versionsnummer der Bereitstellung im Format *N.N.N.N*.  Nur die erste Hauptbuildnummer ist erforderlich.  Für Version 1.0 einer Anwendung sind `1`, `1.0`, `1.0.0` und `1.0.0.0` z. B. gültige Werte.|  
|**Prozessor**|Dies ist optional.  Die Computerarchitektur, auf der diese Bereitstellung ausgeführt werden kann.  Der Standardwert ist `msil` oder Microsoft Intermediate Language, das Standardformat für alle verwalteten Assemblys.  Ändern Sie dieses Feld, wenn Sie die Assemblys in der Anwendung für eine bestimmte Architektur kompiliert haben.|  
|**Kultur**|Dies ist optional.  Der zweiteilige ISO\-Land\-\/Regionscode, in dem die Anwendung ausgeführt wird.  Die Standardeinstellung ist `Neutral`.|  
|**Öffentliches Schlüsseltoken**|Dies ist optional.  Der öffentliche Schlüssel, mit dem dieses Bereitstellungsmanifest signiert wurde.  Wenn es sich um ein neues oder unsigniertes Manifest handelt, wird dieses Feld als `Nicht signiert` angezeigt.|  
  
### Registerkarte "Beschreibung"  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Herausgeber**|Erforderlich.  Der Name der Person oder Organisation, die für die Anwendung verantwortlich ist.  Dieser Wert wird als Ordnername für das Startmenü verwendet.|  
|**Produkt**|Erforderlich.  Der vollständige Produktname.  Bei Auswahl von **Lokal installieren** für das Element **Anwendungstyp** auf der Registerkarte **Bereitstellungsoptionen** wird dieser Name im Menülink **Start** und in **Software** für diese Anwendung angezeigt.|  
|**Supportstandort**|Dies ist optional.  Die URL, über die Kunden Hilfe und Unterstützung für die Anwendung erhalten können.|  
  
### Registerkarte "Bereitstellungsoptionen"  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Anwendungstyp**|Dies ist optional.  Gibt an, ob sich diese Anwendung auf dem Clientcomputer selbst installiert \(**Lokal installieren**\), ob sie online ausgeführt wird \(**Nur online**\), oder ob es sich um eine WPF\-Anwendung handelt, die im Browser ausgeführt wird \(**WPF\-Browseranwendung**\).  Der Standardwert ist **Lokal installieren**.|  
|**Startposition**|Dies ist optional.  Die URL, über die die Anwendung eigentlich gestartet werden soll.  Hilfreich beim Bereitstellen einer Anwendung von einer CD, die sich über das Internet selbst aktualisieren soll.|  
|**Startposition \(ProviderURL\) im Manifest einschließen**|Dies ist optional.  Gibt die URL an, die [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] auf Anwendungsupdates überprüft.|  
|**Anwendung nach dem Installieren automatisch ausführen**|Erforderlich.  Gibt an, dass die [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]Anwendung unmittelbar nach der ersten Installation über eine URL ausgeführt werden soll.  Dieses Kontrollkästchen ist standardmäßig aktiviert.|  
|**Übergeben von URL\-Parametern an die Anwendung zulassen**|Erforderlich.  Gestattet die Übertragung der Parameterdaten an die [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]\-Anwendung über eine Abfragezeichenfolge, die an die URL des Bereitstellungsmanifests angefügt wird.  Das Kontrollkästchen ist standardmäßig deaktiviert.|  
|**Dateierweiterung ".deploy" verwenden**|Erforderlich.  Bei Auswahl dieser Option müssen alle Dateien im Anwendungsmanifest die Erweiterung ".deploy" aufweisen.  Das Kontrollkästchen ist standardmäßig deaktiviert.|  
  
### Registerkarte "Aktualisierungsoptionen"  
 Die Registerkarte **Aktualisierungsoptionen** enthält die hier genannten Optionen nur, wenn für das Auswahlfeld **Anwendungstyp** auf der Registerkarte **Name** die Option **Lokal installieren** festgelegt ist.  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Diese Anwendung soll nach Updates suchen**|Gibt an, ob [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] nach Anwendungsupdates suchen soll.  Wenn dieses Kontrollkästchen nicht aktiviert ist, sucht die Anwendung nicht nach Updates, sofern Sie sie nicht mithilfe der APIs im <xref:System.Deployment.Application>\-Namespace programmgesteuert aktualisieren.|  
|**Zeitpunkt für Updateüberprüfungen auswählen**|Bietet zwei Optionen zum Prüfen auf Updates:<br /><br /> -   **Vor Start der Anwendung**.  Das Prüfen auf Updates erfolgt vor der Ausführung der Anwendung.<br />-   **Nach dem Starten der Anwendung**.  Das Prüfen auf Updates beginnt, sobald das Hauptformular der Anwendung initialisiert wurde, und wird beim nächsten Starten der Anwendung ausgeführt.|  
|**Häufigkeit der Updateüberprüfung**|Bestimmt, wie oft [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] auf Updates prüfen soll:<br /><br /> -   **Bei jedem Ausführen der Anwendung überprüfen**.  [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] führt jedes Mal eine Prüfung auf Updates durch, wenn der Benutzer die Anwendung öffnet.<br />-   **Überprüfung alle**: Wählen Sie ein vor der Prüfung auf Updates zu verstreichendes Zeitintervall und eine Einheit \(Stunden, Tage oder Wochen\) aus.|  
|**Mindestens erforderliche Version für diese Anwendung angeben**|Dies ist optional.  Gibt an, dass eine bestimmte Version der Anwendung installiert sein muss, wodurch verhindert wird, dass Ihre Benutzer mit einer früheren Version arbeiten.|  
|**Version**|Diese ist erforderlich, wenn das Kontrollkästchen **Mindestens erforderliche Version für diese Anwendung angeben** aktiviert ist.  Die Versionsnummer muss im Format *N.N.N.N* bereitgestellt werden.  Nur die erste Hauptbuildnummer ist erforderlich.  Für Version 1.0 einer Anwendung sind `1`, `1.0`, `1.0.0` und `1.0.0.0` z. B. gültige Werte.|  
  
### Registerkarte "Anwendungsverweis"  
 Die Registerkarte **Anwendungsverweis** enthält dieselben Felder wie die weiter oben in diesem Thema beschriebene Registerkarte **Name**.  Die einzige Ausnahme ist das folgende Feld.  
  
|Benutzeroberflächenelement|Beschreibung|  
|--------------------------------|------------------|  
|**Manifest auswählen**|Ermöglicht Ihnen die Auswahl des Anwendungsmanifests.  Alle anderen Felder auf dieser Seite werden aufgefüllt, wenn Sie ein Anwendungsmanifest auswählen.|  
  
## Siehe auch  
 [ClickOnce Security and Deployment](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [Walkthrough: Manually Deploying a ClickOnce Application](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md)   
 [Mage.exe \(Tool zum Generieren und Bearbeiten von Manifesten\)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)