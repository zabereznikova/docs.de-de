---
title: MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)
ms.date: 03/30/2017
helpviewer_keywords:
- Manifest Generation and Editing tool
- MageUI.exe
ms.assetid: f9e130a6-8117-49c4-839c-c988f641dc14
ms.openlocfilehash: 99f522181232d16b9913ba3c55f34274b75d8966
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449417"
---
# <a name="mageuiexe-manifest-generation-and-editing-tool-graphical-client"></a>MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)

"MageUI.exe" unterstützt dieselbe Funktionalität wie das Befehlszeilentool "Mage.exe", verwendet jedoch eine Windows-basierte Benutzeroberfläche. Mit diesem Tool können Sie Bereitstellungs- und Anwendungsmanifeste erstellen, bearbeiten und signieren. Für neue Manifeste, die mit "MageUI.exe" erstellt werden, wird als Zielversion [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] festgelegt. Voherige Versionen von "MageUI.exe" sollten verwendet werden, um ältere .NET Framework-Versionen als Ziel festzulegen. Beim Hinzufügen oder Entfernen von Assemblys aus einem Manifest oder beim erneuten Signieren von vorhandenen Manifesten wird das Manifest von "MageUI.exe" nicht aktualisiert, um als Zielversion [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] festzulegen. Weitere Informationen finden Sie unter [„Mage.exe“ (Tool zum Generieren und Bearbeiten von Manifesten)](mage-exe-manifest-generation-and-editing-tool.md).

 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

 Zwei Versionen von Mage.exe und MageUI.exe sind als Komponenten von Visual Studio inbegriffen. Die Versionsinformationen können Sie anzeigen, indem Sie "MageUI.exe" ausführen, zunächst **Hilfe**und anschließend **Info**auswählen. In dieser Dokumentation wird Version 4.0.x.x von "Mage.exe" und "MageUI.exe" beschrieben.

> [!NOTE]
> „MageUI.exe“ unterstützt nicht das Element [compatibleFrameworks](/visualstudio/deployment/compatibleframeworks-element-clickonce-deployment), wenn es ein Anwendungsmanifest speichert, das bereits mithilfe von „MageUI.exe“ mit einem Zertifikat signiert wurde. Stattdessen müssen Sie [Mage.exe](mage-exe-manifest-generation-and-editing-tool.md) verwenden.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 Die folgende Tabelle gibt einen Überblick über die verfügbaren Menü- und Symbolleistenelemente.  
  
|Befehl|Menü|Verknüpfung|BESCHREIBUNG|  
|-------------|----------|--------------|-----------------|  
|**Anwendungsmanifest**|**Datei, Neu**||Erstellt ein neues Anwendungsmanifest.|  
|**Bereitstellungsmanifest**|**Datei, Neu**||Erstellt ein neues Bereitstellungsmanifest.|  
|**Öffnen**|**Datei**|STRG+O|Öffnet ein vorhandenes Bereitstellungsmanifest, Anwendungsmanifest oder eine Vertrauenslizenz zum Bearbeiten.|  
|**Schließen**|**Datei**|STRG+F4|Schließt eine geöffnete Datei.<br /><br /> Wenn Sie eine Datei vor dem Schließen bearbeiten, fordert "MageUI.exe" Sie auf, die Datei mit einem öffentlichen Schlüssel, einem Schlüsselpaar oder einem gespeicherten Zertifikat erneut zu signieren.|  
|**Speichern**|**Datei**|STRG+S|Speichert das Dokument, das den Benutzereingabefokus hat, auf einen Datenträger.|  
|**Speichern unter**|**Datei**||Speichert eine Datei auf einen Datenträger unter Angabe eines neues Dateinamens und/oder Speicherorts.|  
|**Alle speichern**|**Datei**||Speichert die an allen in "MageUI.exe" geöffneten Dateien vorgenommenen Änderungen.|  
|**Einstellungen**|**Datei**||Öffnet das Dialogfeld **Einstellungen**. Weitere Informationen finden Sie in folgendem Abschnitt.|  
|**Beenden**|**Datei**|ALT+F4|Beendet "MageUI.exe".|  
|**Ausschneiden**|**Bearbeiten**|STRG+X|Entfernt den momentan markierten Text aus der Anwendung und verschiebt ihn in die Zwischenablage des Systems.|  
|**Kopieren**|**Bearbeiten**|STRG+C|Kopiert den aktuell ausgewählten Text in die Zwischenablage des Systems.|  
|**Einfügen**|**Bearbeiten**|STRG+V|Fügt den Text aus der Zwischenablage des Systems in das momentan aktive Textelement ein.|  
|**Löschen**|**Bearbeiten**||Löscht ein aktuell in einer Liste ausgewähltes Element, z.B. eine Vertrauenslizenz, auf der Registerkarte **Bereitstellungsmanifest**.|  
|**Alle schließen**|**Fenster**||Schließt alle aktuell in "MageUI.exe" geöffneten Dateien. Wenn mindestens eine Datei gespeichert werden muss, fordert Sie "MageUI.exe" dazu auf. "MageUI.exe" fordert Sie zudem auf, für jede nicht signierte oder geänderte Datei einen Signaturschlüssel auszuwählen.|  
|**Info**|**Hilfe**||Zeigt Versions- und Copyrightinformationen zu "MageUI.exe" an.|  
  
## <a name="preferences-dialog-box"></a>Dialogfeld "Einstellungen2  
 Das Dialogfeld **Einstellungen** enthält die folgenden Elemente.  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Beim Speichern signieren**|Fordert Sie beim Speichern der vorgenommenen Änderungen zum Signieren der Datei auf.|  
|**Standardsignaturzertifikat verwenden**|Verwendet den im Textfeld **Zertifikatsdatei** eingegebenen Schlüssel zum Signieren aller Dateien. Auf diese Weise wird die Aufforderung zum Signieren entfernt, die i.d.R. angezeigt wird, wenn Sie eine Datei speichern und **Beim Speichern signieren** aktiviert ist. Verwenden Sie die Schaltfläche mit den Auslassungspunkten ( **…** ) neben dem Textfeld **Zertifikatdatei**, um eine Schlüsseldatei auszuwählen.|  
|Hashwertalgorithmus|Gibt den Algorithmus an, mit dem Abhängigkeitsdigests generiert werden sollen. Der Wert muss "sha256RSA" oder "sha1RSA" sein. Als Standard wird SHA1 verwendet. Wird sowohl im Anwendungs- als auch im Bereitstellungsmanifest verwendet. Wenn der Benutzer beim Speichern des Manifests ein Zertifikat angibt, werden die Algorithmen im Zertifikat verwendet, um damit Abhängigkeitsdigests zu generieren.|  
  
## <a name="signing-options-dialog-box"></a>Dialogfeld "Signaturoptionen"  
 Das Dialogfeld **Signaturoptionen** wird angezeigt, wenn Sie ein Manifest oder eine Vertrauenslizenz zum ersten Mal speichern, oder wenn Sie Änderungen daran vornehmen. Das Dialogfeld wird nur dann angezeigt, wenn die Option **Beim Speichern signieren** im Dialogfeld **Einstellungen** aktiviert ist. Beim Signieren eines Manifests, das einen Wert im Textfeld **Zeitstempel-URI** angibt, müssen Sie mit dem Internet verbunden sein.  
  
 Dieses Dialogfeld enthält die folgenden Elemente:  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Mit Zertifikatsdatei signieren**|Signiert das Manifest mit einem im Dateisystem gespeicherten digitalen Zertifikat.|  
|**Datei**|Stellt einen Bereich für die Eingabe des Pfads zur PFX-Datei bereit, die das Zertifikat darstellt.|  
|**...**|Öffnet das Dialogfeld **Datei auswählen** zum Auswählen einer vorhandenen PFX-Datei.|  
|**Neu**|Generiert eine neue PFX-Datei, die nicht durch eine Zertifizierungsstelle überprüft wird. Weitere Informationen zu den Zertifikattypen, die zum Signieren von ClickOnce-Bereitstellungen verwendet werden, finden Sie unter [Trusted Application Deployment Overview (Übersicht über die Bereitstellung vertrauenswürdiger Anwendungen)](/visualstudio/deployment/trusted-application-deployment-overview).|  
|**Kennwort**|Stellt einen Bereich für die Eingabe des Kennworts zum Signieren mit diesem Zertifikat bereit. Kann leer bleiben, wenn kein Kennwort verwendet wird.|  
|**Mit gespeichertem Zertifikat signieren**|Zeigt eine Liste für die Auswahl aus im Zertifikatsspeicher des Computers gespeicherten digitalen Zertifikaten an.|  
|**Zeitstempel-URI**|Zeigt den Uniform Resource Locator (URI) eines digitalen Zeitstempeldiensts an. Der Zeitstempel verhindert, dass Sie ein Manifest neu signieren müssen, wenn das digitale Zertifikat abläuft, bevor Sie die nächste Version der Anwendung bereitstellen. Weitere Informationen finden Sie unter [Mitglieder des Windows-Programms für Stammzertifikate](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265983(v=ws.11)) und [ClickOnce und Authenticode](/visualstudio/deployment/clickonce-and-authenticode).|  
|**Nicht signieren**|Ermöglicht das Speichern des Manifests, ohne eine Signatur aus einem digitalen Zertifikat hinzuzufügen.|  
  
## <a name="tab-and-panel-descriptions"></a>Beschreibungen von Registerkarten und Bereichen  
 Wenn Sie ein Dokument mit "MageUI.exe" öffnen, wird es in einer eigenen Registerkarte geöffnet. Jede Registerkarte enthält mehrere Eigenschaftenbereiche. Die Bereiche enthalten gruppierte Teilmengen der Dokumentdaten.  
  
### <a name="application-manifest-tab"></a>Registerkarte "Anwendungsmanifest"  
 Auf der Registerkarte **Anwendungsmanifest** werden die Inhalte eines Anwendungsmanifests angezeigt. Das Anwendungsmanifest beschreibt alle in einer Bereitstellung enthaltenen Dateien sowie die für die Anwendung zum Ausführen des Clients erforderlichen Berechtigungen.  
  
 Die Registerkarte **Anwendungsmanifest** enthält die folgenden Registerkarten.  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Name**|Gibt bezeichnende Informationen zur Bereitstellung an.|  
|**Beschreibung**|Gibt Herausgeber-, Produkt- und Supportinformationen an.|  
|**Anwendungsoptionen**|Gibt an, ob dies eine Browseranwendung und das Manifest die Quelle der vertrauenswürdigen Informationen ist.|  
|**Dateien**|Gibt alle Dateien an, aus denen die Bereitstellung besteht.|  
|**Erforderliche Berechtigungen**|Gibt den minimalen Berechtigungssatz an, der von der Anwendung für die Ausführung auf einem Client erforderlich ist.|  
  
### <a name="name-tab"></a>Registerkarte "Name"  
 Die Registerkarte **Name** wird angezeigt, wenn Sie ein Anwendungsmanifest erstmalig erstellen oder öffnen. Sie identifiziert die Bereitstellung eindeutig und gibt optional eine gültige Zielplattform an.  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Name**|Erforderlich. Der Name des Anwendungsmanifests. In der Regel identisch mit dem Dateinamen.|  
|**Version**|Erforderlich. Die Versionsnummer der Bereitstellung im Format *N.N.N.N*. Nur die erste Hauptbuildnummer ist erforderlich. Für Version 1.0 einer Anwendung sind z.B.`1`, `1.0`, `1.0.0` und `1.0.0.0` gültige Werte.|  
|**Prozessor**|Optional. Die Computerarchitektur, auf der diese Bereitstellung ausgeführt werden kann. Der Standardwert ist `msil` oder Microsoft Intermediate Language, das Standardformat für alle verwalteten Assemblys. Ändern Sie dieses Feld, wenn Sie die Assemblys in der Anwendung für eine bestimmte Architektur vorkompiliert haben. Weitere Informationen zur Vorkompilierung finden Sie unter [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md).|  
|**Kultur**|Optional. Der zweiteilige ISO-Land- und Regionscode, in dem die Anwendung ausgeführt wird. Die Standardeinstellung ist `neutral`.|  
|**Öffentliches Schlüsseltoken**|Optional. Der öffentliche Schlüssel, mit dem dieses Anwendungsmanifest signiert wurde. Wenn es sich um ein neues oder unsigniertes Manifest handelt, wird dieses Feld als `Unsigned` angezeigt.|  
  
### <a name="description-tab"></a>Registerkarte "Beschreibung"  
 Diese Informationen werden normalerweise im Bereitstellungsmanifest bereitgestellt. Diese Felder können nur geändert werden, wenn das Kontrollkästchen **Anwendungsmanifest für Vertrauensinformationen verwenden** auf der Registerkarte **Anwendungsoptionen** aktiviert ist.  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Publisher**|Der Name der Person oder Organisation, die für die Anwendung verantwortlich ist. Dieser Wert wird als Ordnername für das Startmenü verwendet.|  
|**Produkt**|Der vollständige Produktname. Wenn Sie **Lokal installieren** für das Element **Anwendungstyp** auf der Registerkarte **Bereitstellungsoptionen** des Bereitstellungsmanifests ausgewählt haben, wird dieser Name im Menülink **Start** und unter **Programme hinzufügen oder entfernen** für diese Anwendung angezeigt.|  
|**Supportstandort**|Die URL, über die Kunden Hilfe und Unterstützung für die Anwendung erhalten können.|  
  
### <a name="application-options-tab"></a>Registerkarte "Anwendungsoptionen"  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Windows Presentation Foundation-Browseranwendung**|Gibt an, ob es sich um eine WPF-Anwendung handelt, die im Browser als XAML-Browseranwendung (XBAP) ausgeführt wird.|  
|**Anwendungsmanifest für Vertrauensinformationen verwenden**|Gibt an, ob dieses Manifest Vertrauensinformationen enthält.|  
  
### <a name="files-tab"></a>Registerkarte "Dateien"  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Anwendungsverzeichnis**|Das Verzeichnis, in dem sich die Dateien der Anwendung befinden. Verwenden Sie die Schaltfläche mit den Auslassungszeichen ( **...** ), um das Verzeichnis auszuwählen.|  
|**Auffüllen**|Fügt alle Dateien im Anwendungsverzeichnis und in den Unterverzeichnissen zum Anwendungsmanifest hinzu. Wenn "MageUI.exe" im Verzeichnis eine einzelne ausführbare Datei findet, wird diese automatisch als Einstiegspunkt gekennzeichnet. Hierbei handelt es sich um die Datei, die zuerst ausgeführt wird, wenn die ClickOnce-Anwendung auf dem Client gestartet wird.|  
|**Anwendungsdateien**|Zeigt eine Liste aller Dateien in der Anwendung an. Jede Datei verfügt über drei bearbeitbare Attribute, die unten erläutert werden.|  
|**Dateityp**|Der Dateityp kann einen von vier Werten aufweisen:<br /><br /> –  Keine.<br />– Einstiegspunkt. Die primäre ausführbare Datei der Anwendung. Nur eine ausführbare Datei kann als Einstiegspunkt markiert werden.<br />– Datendatei. Eine Datei, z. B. eine XML-Datei, die Daten für die Anwendung bereitstellt.<br />– Symboldatei. Ein Anwendungssymbol, das auf dem Desktop oder in der Ecke des Anwendungsfensters angezeigt wird.|  
|**Optional**|Als "optional" markierte Dateien werden nicht bei der ersten Installation oder Aktualisierung heruntergeladen, aber werden möglicherweise zur Laufzeit mithilfe der bedarfsabhängigen API "System.Deployment" heruntergeladen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Herunterladen von Assemblys bei Bedarf mit der API für die ClickOnce-Bereitstellung unter Verwendung des Designers](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer).|  
|**Gruppieren**|Eine Bezeichnung für einen Satz optionaler Dateien. Sie können einem Satz von Dateien die Bezeichnung "Gruppieren" zuweisen und einen Batch von Dateien mithilfe der bedarfsabhängigen API in einem einzigen API-Aufruf herunterladen.|  
  
### <a name="permissions-required-tab"></a>Registerkarte "Erforderliche Berechtigungen"  
 Verwenden Sie die Registerkarte **Erforderliche Berechtigungen**, wenn Sie der Anwendung umfassenderen Zugriff auf den lokalen Computer gewähren müssen, als ihr standardmäßig erteilt wird. Weitere Informationen finden Sie unter [Sichern von ClickOnce-Anwendungen](/visualstudio/deployment/securing-clickonce-applications).  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Berechtigungssatztyp**|Der minimale Berechtigungssatz, der von der Anwendung für die Ausführung auf dem Client erforderlich ist. Eine Beschreibung dieser Berechtigungssätze und der erforderlichen Berechtigungen finden Sie unter [Named Permission Sets](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)) (Benannte Berechtigungssätze).|  
|**Details**|Die für das Anwendungsmanifest erstellte XML-Datei zum Darstellen des Berechtigungssatzes. Sie sollten diesen XML-Code nicht manuell bearbeiten, sofern Sie nicht mit dem XML-Format des Anwendungsmanifests vertraut sind. Weitere Informationen finden Sie unter [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest).|  
  
### <a name="deployment-manifest-tab"></a>Registerkarte "Bereitstellungsmanifest"  
 Die Registerkarte **Bereitstellungsmanifest** enthält die folgenden Registerkarten.  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Name**|Gibt bezeichnende Informationen zur Bereitstellung an.|  
|**Beschreibung**|Gibt Herausgeber-, Produkt- und Supportinformationen an.|  
|**Bereitstellungsoptionen**|Gibt zusätzliche Informationen zur Bereitstellung an, z. B. den Anwendungstyp und die Startposition.|  
|**Aktualisierungsoptionen**|Gibt an, wie oft ClickOnce nach Anwendungsupdates suchen soll.|  
|**Anwendungsverweis**|Gibt das Anwendungsmanifest für diese Bereitstellung an.|  
  
### <a name="name-tab"></a>Registerkarte "Name"  
 Die Registerkarte **Name** wird angezeigt, wenn Sie ein Bereitstellungsmanifest erstmalig erstellen oder öffnen. Sie identifiziert die Bereitstellung eindeutig und gibt optional eine gültige Zielplattform an.  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Name**|Erforderlich. Der Namen des Bereitstellungsmanifests. In der Regel identisch mit dem Dateinamen.|  
|**Version**|Erforderlich. Die Versionsnummer der Bereitstellung im Format *N.N.N.N*. Nur die erste Hauptbuildnummer ist erforderlich. Für Version 1.0 einer Anwendung sind z.B.`1`, `1.0`, `1.0.0` und `1.0.0.0` gültige Werte.|  
|**Prozessor**|Optional. Die Computerarchitektur, auf der diese Bereitstellung ausgeführt werden kann. Der Standardwert ist `msil` oder Microsoft Intermediate Language, das Standardformat für alle verwalteten Assemblys. Ändern Sie dieses Feld, wenn Sie die Assemblys in der Anwendung für eine bestimmte Architektur kompiliert haben.|  
|**Kultur**|Optional. Der zweiteilige ISO-Land-/Regionscode, in dem die Anwendung ausgeführt wird. Die Standardeinstellung ist `neutral`.|  
|**Öffentliches Schlüsseltoken**|Optional. Der öffentliche Schlüssel, mit dem dieses Bereitstellungsmanifest signiert wurde. Wenn es sich um ein neues oder unsigniertes Manifest handelt, wird dieses Feld als `Unsigned` angezeigt.|  
  
### <a name="description-tab"></a>Registerkarte "Beschreibung"  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Publisher**|Erforderlich. Der Name der Person oder Organisation, die für die Anwendung verantwortlich ist. Dieser Wert wird als Ordnername für das Startmenü verwendet.|  
|**Produkt**|Erforderlich. Der vollständige Produktname. Bei Auswahl von **Lokal installieren** für das Element **Anwendungstyp** auf der Registerkarte **Bereitstellungsoptionen** wird dieser Name im Menülink **Start** und unter **Programme hinzufügen oder entfernen** für diese Anwendung angezeigt.|  
|**Supportstandort**|Optional. Die URL, über die Kunden Hilfe und Unterstützung für die Anwendung erhalten können.|  
  
### <a name="deployment-options-tab"></a>Registerkarte "Bereitstellungsoptionen"  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Anwendungstyp**|Optional. Gibt an, ob sich diese Anwendung auf dem Clientcomputer selbst installiert (**Lokal installieren**), ob sie online ausgeführt wird (**Nur online**), oder ob es sich um eine WPF-Anwendung handelt, die im Browser ausgeführt wird (**WPF-Browseranwendung**). Der Standardwert ist **Lokal installieren**.|  
|**Startposition**|Optional. Die URL, über die die Anwendung eigentlich gestartet werden soll. Hilfreich beim Bereitstellen einer Anwendung von einer CD, die sich über das Internet selbst aktualisieren soll.|  
|**Startposition (ProviderURL) im Manifest einschließen**|Optional. Gibt die URL an, die ClickOnce auf Anwendungsupdates überprüft.|  
|**Anwendung nach dem Installieren automatisch ausführen**|Erforderlich. Gibt an, dass die ClickOnce-Anwendung unmittelbar nach der ersten Installation über eine URL ausgeführt werden soll. Dieses Kontrollkästchen ist standardmäßig aktiviert.|  
|**Übergeben von URL-Parametern an die Anwendung zulassen**|Erforderlich. Gestattet die Übertragung der Parameterdaten an die ClickOnce-Anwendung über eine Abfragezeichenfolge, die an die URL des Bereitstellungsmanifests angefügt wird. Das Kontrollkästchen ist standardmäßig deaktiviert.|  
|**Dateierweiterung „.deploy“ verwenden**|Erforderlich. Bei Auswahl dieser Option müssen alle Dateien im Anwendungsmanifest die Erweiterung ".deploy" aufweisen. Das Kontrollkästchen ist standardmäßig deaktiviert.|  
  
### <a name="update-options-tab"></a>Registerkarte "Aktualisierungsoptionen"  
 Die Registerkarte **Aktualisierungsoptionen** enthält die hier genannten Optionen nur, wenn für das Auswahlfeld **Anwendungstyp** auf der Registerkarte **Name** die Option **Lokal installieren** festgelegt ist.  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Diese Anwendung soll nach Updates suchen**|Gibt an, ob ClickOnce nach Anwendungsupdates suchen soll. Wenn dieses Kontrollkästchen nicht aktiviert ist, sucht die Anwendung nicht nach Updates, sofern Sie sie nicht mithilfe der APIs im <xref:System.Deployment.Application>-Namespace programmgesteuert aktualisieren.|  
|**Zeitpunkt für das Prüfen auf Updates auswählen**|Bietet zwei Optionen zum Prüfen auf Updates:<br /><br /> -   **Vor dem Starten der Anwendung**. Das Prüfen auf Updates erfolgt vor der Ausführung der Anwendung.<br />-   **Nach dem Starten der Anwendung**. Das Prüfen auf Updates beginnt, sobald das Hauptformular der Anwendung initialisiert wurde, und wird beim nächsten Starten der Anwendung ausgeführt.|  
|**Häufigkeit des Prüfens auf Updates**|Bestimmt, wie oft ClickOnce auf Updates überprüfen soll:<br /><br /> -   **Bei jedem Ausführen der Anwendung überprüfen**. ClickOnce führt jedes Mal eine Überprüfung auf Updates durch, wenn der Benutzer die Anwendung öffnet.<br />-   **Prüfen alle:** Wählen Sie ein vor der Prüfung auf Updates zu verstreichendes Zeitintervall und eine Einheit (Stunden, Tage oder Wochen) aus.|  
|**Mindestens erforderliche Version für diese Anwendung angeben**|Optional. Gibt an, dass eine bestimmte Version der Anwendung installiert sein muss, wodurch verhindert wird, dass Ihre Benutzer mit einer früheren Version arbeiten.|  
|**Version**|Diese ist erforderlich, wenn das Kontrollkästchen **Mindestens erforderliche Version für diese Anwendung angeben** aktiviert ist. Die Versionsnummer muss im Format *N.N.N.N* bereitgestellt werden. Nur die erste Hauptbuildnummer ist erforderlich. Für Version 1.0 einer Anwendung sind z.B.`1`, `1.0`, `1.0.0` und `1.0.0.0` gültige Werte.|  
  
### <a name="application-reference-tab"></a>Registerkarte "Anwendungsverweis"  
 Die Registerkarte **Anwendungsverweis** enthält die gleichen Felder wie die weiter oben in diesem Thema beschriebene Registerkarte **Name**. Die einzige Ausnahme ist das folgende Feld.  
  
|Benutzeroberflächenelement|BESCHREIBUNG|  
|----------------|-----------------|  
|**Manifest auswählen**|Ermöglicht Ihnen die Auswahl des Anwendungsmanifests. Alle anderen Felder auf dieser Seite werden aufgefüllt, wenn Sie ein Anwendungsmanifest auswählen.|  
  
## <a name="see-also"></a>Siehe auch

- [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)
- [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)
- [Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](mage-exe-manifest-generation-and-editing-tool.md)
