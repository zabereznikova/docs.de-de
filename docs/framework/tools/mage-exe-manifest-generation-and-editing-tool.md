---
title: Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)
ms.date: 12/06/2018
helpviewer_keywords:
- Manifest Generation and Editing tool
- Mage.exe
ms.assetid: 77dfe576-2962-407e-af13-82255df725a1
ms.openlocfilehash: 3752ac7108a9fcd55b61b32b889a717ef7c0faff
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714474"
---
# <a name="mageexe-manifest-generation-and-editing-tool"></a>Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)

Bei Manifest Generation and Editing Tool (*Mage.exe*) handelt es sich um ein Befehlszeilentool, das Sie beim Erstellen und Bearbeiten von Anwendungs- und Bereitstellungsmanifesten unterstützt. Als Befehlszeilentool kann *Mage.exe* von Batchskripten und anderen Windows-basierten Anwendungen ausgeführt werden, beispielsweise ASP.NET-Anwendungen.

Sie können statt *Mage.exe* auch die grafische Anwendung *MageUI.exe* verwenden. Weitere Informationen finden Sie unter [MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).

Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio, um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

Zwei Versionen von *Mage.exe* und *MageUI.exe* sind in Visual Studio enthalten. Die Versionsinformationen können Sie anzeigen, indem Sie *MageUI.exe* ausführen und auf **Hilfe** und **Info** klicken. In dieser Dokumentation wird Version 4.0.x.x von *Mage.exe* und *MageUI.exe* beschrieben.

## <a name="syntax"></a>Syntax

```console
Mage [commands] [commandOptions]
```

## <a name="parameters"></a>Parameter

In der folgenden Tabelle werden die von *Mage.exe* unterstützten Befehle angezeigt. Weitere Informationen zu den Optionen, die diese Befehle unterstützen, finden Sie unter [Befehlsoptionen für "New" und "Update"](#new-and-update-command-options) und ["Sign"-Befehlsoptionen](#sign-command-options).

|Befehl|BESCHREIBUNG|
|-------------|-----------------|
|**-cc, ClearApplicationCache**|Löscht den heruntergeladenen Anwendungscache aller Anwendungen, die nur online ausgeführt werden.|
|**-n, -New** *Dateityp [neue Optionen]*|Erstellt eine neue Datei des angegebenen Typs. Gültige Typen sind:<br /><br /> -   `Deployment`: Erstellt ein neues Bereitstellungsmanifest.<br />-   `Application`: Erstellt ein neues Anwendungsmanifest.<br /><br /> Wenn Sie mit diesem Befehl keine weiteren Parameter angeben, wird eine Datei des entsprechenden Typs mit den zugehörigen Standardtags und Attributwerten erstellt.<br /><br /> Verwenden Sie die Option **-ToFile** (siehe folgende Tabelle), um den Dateinamen und den Pfad der neuen Datei anzugeben.<br /><br /> Verwenden Sie die Option **-FromDirectory** (siehe folgende Tabelle), um ein Anwendungsmanifest mit allen Assemblys für eine dem \<dependency>-Abschnitt des Manifests hinzugefügte Anwendung zu erstellen.|
|**-u, -Update** *[filePath] [updateOptions]*|Nimmt mindestens eine Änderung an einer Manifestdatei vor. Es ist nicht erforderlich, den Typ der Datei anzugeben, die Sie bearbeiten. "Mage.exe" analysiert die Datei mithilfe von Heuristiken und ermittelt, ob es sich um ein Bereitstellungsmanifest oder ein Anwendungsmanifest handelt.<br /><br /> Wenn Sie eine Datei bereits mit einem Zertifikat signiert haben, entfernt **-Update** den Block mit der Schlüsselsignatur. Der Grund hierfür liegt darin, dass die Schlüsselsignatur einen Hash für die Datei enthält und der Hash durch die Änderung der Datei ungültig wird.<br /><br /> Verwenden Sie die Option **-ToFile** (siehe folgende Tabelle), um einen neuen Dateinamen und Pfad anzugeben, anstatt die vorhandene Datei zu überschreiben.|
|**-s, -Sign** `[signOptions]`|Verwendet ein Schlüsselpaar oder ein X509-Zertifikat, um eine Datei zu signieren. Signaturen werden als XML-Elemente in die Dateien eingefügt.<br /><br /> Beim Signieren eines Manifests, das einen **-TimestampUri** -Wert angibt, müssen Sie mit dem Internet verbunden sein.|
|**-Ver-stellen Sie sicher** *[Manifest-Dateiname]*|Überprüft, ob das Manifest ordnungsgemäß signiert ist. Kann nicht mit anderen Befehlen kombiniert werden. <br/><br/>**Verfügbar in NET Framework 4.7 und neueren Versionen.**|
|**-h, -?, -Help** *[ausführlich]*|Beschreibt alle verfügbaren Befehle und die zugehörigen Optionen. Geben Sie `verbose` an, um ausführliche Hilfe aufzurufen.|

## <a name="new-and-update-command-options"></a>Befehlsoptionen für "New" und "Update"

In der folgenden Tabelle werden die Optionen aufgeführt, die von den Befehlen `-New` und `-Update` unterstützt werden:

|Optionen|Standardwert|Gilt für|BESCHREIBUNG|
|-------------|-------------------|----------------|-----------------|
|**-a, -Algorithm**|sha1RSA|Anwendungsmanifeste,<br /><br /> Bereitstellungsmanifeste|Gibt den Algorithmus an, mit dem Abhängigkeitsdigests generiert werden sollen. Der Wert muss "sha256RSA" oder "sha1RSA" lauten.<br /><br /> Verwenden Sie diese Option mit dem Befehl "-Update". Diese Option wird bei der Verwendung des Befehls "-Sign" ignoriert.|
|**-appc, -AppCodeBase** `manifestReference`||Bereitstellungsmanifeste|Fügt einen URL- oder Dateipfadverweis in die Anwendungsmanifestdatei ein. Dieser Wert muss der vollständige Pfad zum Anwendungsmanifest sein.|
|**-appm, -AppManifest** `manifestPath`||Bereitstellungsmanifeste|Fügt einen Verweis auf das Anwendungsmanifest einer Bereitstellung in das Bereitstellungsmanifest ein.<br /><br /> Die mit `manifestPath` angegebene Datei muss vorhanden sein, andernfalls gibt *Mage.exe* einen Fehler aus. Wenn die Datei, auf die mit `manifestPath` verwiesen wird, kein Anwendungsmanifest ist, gibt *Mage.exe* einen Fehler aus.|
|**-cf, -CertFile** `filePath`||Alle Dateitypen|Gibt den Speicherort eines digitalen X509-Zertifikats zum Signieren eines Manifests oder einer Lizenzdatei an. Diese Option kann in Verbindung mit der Option **-Password** verwendet werden, wenn ein Zertifikat ein Kennwort für Personal Information Exchange (PFX)-Dateien erfordert. Ab .NET Framework 4.7 ist, wenn die Datei keinen privaten Schlüssel enthält, eine Kombination der Optionen **-CryptoProvider** und **-KeyContainer** erforderlich.<br/><br/>Ab .NET Framework 4.6.2 signiert *Mage.exe* Manifeste mit CNG- sowie CAPI-Zertifikaten.|
|**-ch, -CertHash** `hashSignature`||Alle Dateitypen|Der Hash eines im persönlichen Zertifikatspeicher des Clientcomputers gespeicherten digitalen Zertifikats. Dieser entspricht der Zeichenfolge des Fingerabdrucks eines digitalen Zertifikats, das in der Zertifikatkonsole von Windows angezeigt wird.<br /><br /> `hashSignature` kann groß oder klein geschrieben werden und als einzelne Zeichenfolge oder so angegeben werden, dass die einzelnen Oktette des Fingerabdrucks durch Leerzeichen getrennt sind und der vollständige Fingerabdruck in Anführungszeichen eingeschlossen ist.|
|**-csp, -CryptoProvider** `provider-name`||Alle Dateitypen|Gibt den Namen eines Kryptografiedienstanbieters (Cryptographic Service Provider,CSP) an, der den privaten Schlüsselcontainer enthält. Diese Option erfordert die Option **-KeyContainer**.<br/><br/>Diese Option ist ab .NET Core 4.7 verfügbar.|
|**-fd, -FromDirectory** `directoryPath`||Anwendungsmanifeste,|Füllt das Anwendungsmanifest mit Beschreibungen aller Assemblys und Dateien im `directoryPath`, einschließlich aller Unterverzeichnisse, wobei `directoryPath` das Verzeichnis ist, das die bereitzustellende Anwendung enthält. Bei jeder Datei im Verzeichnis stellt *Mage.exe* fest, ob es sich bei der Datei um eine Assembly oder eine statische Datei handelt. Bei einer Assembly wird der Anwendung ein `<dependency>` -Tag und ein `installFrom` -Attribut mit dem Assemblynamen, der CodeBase und der Version hinzugefügt. Bei einer statischen Datei wird ein `<file>` -Tag hinzugefügt. *Mage.exe* verwendet zudem einige einfache Heuristiken zum Ermitteln der zentralen ausführbaren Datei für die Anwendung und kennzeichnet diese als Einstiegspunkt der ClickOnce-Anwendung im Manifest.<br /><br /> *Mage.exe* markiert nie automatisch eine Datei als „Datendatei“. Sie müssen dies manuell durchführen. Weitere Informationen finden Sie unter [Vorgehensweise: Einschließen einer Datendatei in eine ClickOnce-Anwendung](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application).<br /><br /> *Mage.exe* generiert zudem einen Hash für jede Datei auf Grundlage ihrer Größe. ClickOnce verwendet diese Hashes, um sicherzustellen, dass die Dateien der Bereitstellung seit Erstellung des Manifests nicht manipuliert wurden. Falls sich Dateien in der Bereitstellung ändern, können Sie *Mage.exe* mit dem Befehl **-Update** und der Option **-FromDirectory** ausführen. Auf diese Weise werden die Hashes und die Assemblyversionen aller Dateien, auf die verwiesen wird, aktualisiert.<br /><br /> **-FromDirectory** schließt alle Dateien in allen Unterverzeichnissen ein, die im `directoryPath`gefunden werden.<br /><br /> Wenn Sie **-FromDirectory** mit dem Befehl **-Update** verwenden, entfernt *Mage.exe* alle Dateien im Anwendungsmanifest, die im Verzeichnis nicht mehr vorhanden sind.|
|**-if, -IconFile**  `filePath`||Anwendungsmanifeste,|Gibt den vollständigen Pfad zu einer ICO-Symboldatei an. Dieses Symbol wird neben dem Anwendungsnamen im Startmenü und im zugehörigen Eintrag unter "Software" angezeigt. Wenn kein Symbol angegeben wird, wird ein Standardsymbol verwendet.|
|**-ip, -IncludeProviderURL**  `url`|true|Bereitstellungsmanifeste|Gibt an, ob das Bereitstellungsmanifest den von **-ProviderURL**festgelegten Wert für den Updatespeicherort enthält.|
|**-i, -Install** `willInstall`|true|Bereitstellungsmanifeste|Gibt an, ob die ClickOnce-Anwendung auf dem lokalen Computer installiert oder ob sie über das Web ausgeführt werden soll. Wenn eine Anwendung installiert wird, wird diese im **Startmenü** von Windows angezeigt. Gültige Werte sind "true" oder "t" und "false" oder "f".<br /><br /> Wenn Sie die Option **-MinVersion** angeben und ein Benutzer eine ältere Version als jene installiert hat, die **-MinVersion** entspricht, wird die Anwendung zur Installation gezwungen, unabhängig von dem Wert, den Sie an **-Install**übergeben.<br /><br /> Diese Option kann nicht mit der Option **-BrowserHosted** verwendet werden. Wenn Sie beide Optionen für das gleiche Manifest angeben, wird ein Fehler ausgelöst.|
|**-kc, -KeyContainer** `name`||Alle Dateitypen|Gibt den Schlüsselcontainer an, der den Namen für den privaten Schlüssel enthält. Diese Option erfordert die Option **CryptoProvider**.<br/><br/>Diese Option ist ab .NET Core 4.7 verfügbar.|
|**-mv, -MinVersion**  `[version]`|Die im ClickOnce-Bereitstellungsmanifest aufgeführte Version, wie im Flag **-Version** angegeben.|Bereitstellungsmanifeste|Die Version dieser Anwendung, die ein Benutzer mindestens ausführen muss. Dieses Flag macht die genannte Version der Anwendung zu einem erforderlichen Update. Wenn Sie eine Version Ihres Produkts mit einer wichtigen Änderung oder einer Korrektur eines schwerwiegenden Sicherheitsmangels freigeben, können Sie mithilfe dieses Flags angeben, dass das Update installiert werden muss und der Benutzer keine früheren Versionen mehr ausführen kann.<br /><br /> `version` weist dieselbe Semantik wie das Argument für das Flag **-Version** auf.|
|**-n, -Name** `nameString`|Bereitstellen|Alle Dateitypen|Der Name, der zum Angeben der Anwendung verwendet wird. ClickOnce verwendet diesen Namen zum Identifizieren der Anwendung im **Startmenü** (wenn die Anwendung so konfiguriert ist, dass sie sich selbst installiert) und in Dialogfeldern zum Erweitern von Berechtigungen. **Hinweis**:  Wenn Sie ein vorhandenes Manifest aktualisieren und keinen Herausgebernamen mit dieser Option angeben, aktualisiert *Mage.exe* das Manifest mit dem auf dem Computer definierten Organisationsnamen. Zur Verwendung eines anderen Namens müssen Sie diese Option verwenden und den gewünschten Herausgebernamen angeben.|
|**-pwd, -Password** `passwd`||Alle Dateitypen|Das Kennwort, das zum Signieren eines Manifests mit einem digitalen Zertifikat verwendet wird. Muss zusammen mit der Option **-CertFile** verwendet werden.|
|**-p, Processor** `processorValue`|MSIL|Anwendungsmanifeste,<br /><br /> Bereitstellungsmanifeste|Die Mikroprozessorarchitektur, auf der diese Verteilung ausgeführt wird. Dieser Wert muss angegeben werden, wenn Sie eine oder mehrere Installationen vorbereiten, deren Assemblys für einen bestimmten Mikroprozessor vorkompiliert wurden. Gültige Werte sind u.a. `msil`, `x86`, `ia64`und `amd64`. `msil` steht für Microsoft Intermediate Language. Alle Ihre Assemblys sind daher plattformunabhängig und werden bei der ersten Ausführung der Anwendung von der Common Language Runtime (CLR) just in time kompiliert.|
|**-pu,** **-ProviderURL** `url`||Bereitstellungsmanifeste|Gibt die URL an, die ClickOnce auf Anwendungsupdates überprüft.|
|**-pub, -Publisher** `publisherName`||Anwendungsmanifeste,<br /><br /> Bereitstellungsmanifeste|Fügt den Herausgebernamen zum Beschreibungselement des Bereitstellungs- oder Anwendungsmanifests hinzu. Bei Verwendung mit einem Anwendungsmanifest muss **-UseManifestForTrust** zudem mit dem Wert TRUE oder T angegeben werden. Andernfalls verursacht dieser Parameter einen Fehler.|
|**-s, -SupportURL**  `url`||Anwendungsmanifeste,<br /><br /> Bereitstellungsmanifeste|Gibt den Link an, der unter "Software" für die ClickOnce-Anwendung angezeigt wird.|
|**-ti, -TimestampUri** `uri`||Anwendungsmanifeste,<br /><br /> Bereitstellungsmanifeste|Die URL eines digitalen Zeitstempeldiensts. Der Zeitstempel für Manifeste verhindert, dass Sie ein Manifest neu signieren müssen, wenn das digitale Zertifikat abläuft, bevor Sie die nächste Version der Anwendung bereitstellen. Weitere Informationen finden Sie unter [Mitglieder des Windows-Programms für Stammzertifikate](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265983(v=ws.11)).|
|**-t, -ToFile** `filePath`|-   New:<br />-   Deployment: deploy.application<br />-   Application: application.exe.manifest<br />-   Update:<br />-   Die Eingabedatei.|Alle Dateitypen|Gibt den Ausgabepfad der Datei an, die erstellt oder geändert wurde.<br /><br /> Wenn **-ToFile** bei Verwendung von **-New**nicht angegeben wird, wird die Ausgabe in das aktuelle Arbeitsverzeichnis geschrieben. Wenn **-ToFile** bei Verwendung von **-Update** nicht angegeben wird, schreibt *Mage.exe* die Datei zurück in die Eingabedatei.|
|**-tr, -TrustLevel** `level`|Auf Grundlage der Zone, in der sich die Anwendungs-URL befindet|Anwendungsmanifeste,|Die Vertrauensebene, die der Anwendung auf Clientcomputern gewährt wird. Zu den gültigen Werten zählen "Internet", "Intranet" und "FullTrust".|
|**-um, -UseManifestForTrust** `willUseForTrust`|False|Anwendungsmanifeste,|Gibt an, ob für Entscheidungen über die Vertrauenswürdigkeit die digitale Signatur des Anwendungsmanifests verwendet wird, wenn die Anwendung auf dem Client ausgeführt wird. Wenn Sie "true" oder "t" angeben, wird das Anwendungsmanifest für Entscheidungen über die Vertrauenswürdigkeit verwendet. Bei Angabe von "false" oder "f" wird die Signatur des Bereitstellungsmanifests verwendet.|
|**-v, -Version** `versionNumber`|1.0.0.0|Anwendungsmanifeste,<br /><br /> Bereitstellungsmanifeste|Die Version der Bereitstellung. Das Argument muss eine gültige Versionszeichenfolge im Format „*N.N.N.N*“ sein, wobei „*N*“ eine ganze 32-Bit-Zahl ohne Vorzeichen sein muss.|
|**-wpf, -WPFBrowserApp**  `isWPFApp`|False|Anwendungsmanifeste,<br /><br /> Bereitstellungsmanifeste|Verwenden Sie dieses Flag nur für Windows Presentation Foundation-Anwendungen (WPF), die in Internet Explorer gehostet werden, nicht für eigenständig ausführbare Dateien. Gültige Werte sind "true" oder "t" und "false" oder "f".<br /><br /> Fügt für Anwendungsmanifeste das `hostInBrowser` -Attribut unter dem `entryPoint` -Element des Anwendungsmanifests ein.<br /><br /> Legt für Bereitstellungsmanifeste für das `install` -Attribut im `deployment` -Element den Wert "false" fest und speichert das Bereitstellungsmanifest mit der Erweiterung ".xbap". Wenn dieses Argument zusammen mit dem Argument **-Install** angeben wird, wird ein Fehler ausgelöst, da eine im Browser gehostete Anwendung keine installierte Offlineanwendung sein darf.|

## <a name="sign-command-options"></a>Sign-Befehlsoptionen

In der folgenden Tabelle werden die Optionen angezeigt, die von dem Befehl `-Sign` unterstützt werden und für alle Dateitypen gelten.

|Optionen|BESCHREIBUNG|
|-------------|-----------------|
|**-cf, -CertFile** `filePath`|Gibt den Speicherort eines digitalen Zertifikats zum Signieren eines Manifests an. Diese Option kann in Verbindung mit der Option **-Password** verwendet werden, wenn ein Zertifikat ein Kennwort für Personal Information Exchange (PFX)-Dateien erfordert. Ab .NET Framework 4.7 ist, wenn die Datei keinen privaten Schlüssel enthält, eine Kombination der Optionen **-CryptoProvider** und **-KeyContainer** erforderlich.<br/><br/>Ab .NET Framework 4.6.2 signiert *Mage.exe* Manifeste mit CNG- sowie CAPI-Zertifikaten.|
|**-ch, -CertHash** `hashSignature`|Der Hash eines im persönlichen Zertifikatspeicher des Clientcomputers gespeicherten digitalen Zertifikats. Dieser entspricht der Eigenschaft "Fingerabdruck" eines digitalen Zertifikats, das in der Zertifikatkonsole von Windows angezeigt wird.<br /><br /> `hashSignature` kann groß oder klein geschrieben werden und als einzelne Zeichenfolge oder so angegeben werden, dass die einzelnen Oktette des Fingerabdrucks durch Leerzeichen getrennt sind und der vollständige Fingerabdruck in Anführungszeichen eingeschlossen ist.|
**-csp, -CryptoProvider** `provider-name`|Gibt den Namen eines Kryptografiedienstanbieters (Cryptographic Service Provider,CSP) an, der den privaten Schlüsselcontainer enthält. Diese Option erfordert die Option **-KeyContainer**.<br/><br/>Diese Option ist ab .NET Core 4.7 verfügbar.|
|**-kc, -KeyContainer** `name`|Gibt den Schlüsselcontainer an, der den Namen für den privaten Schlüssel enthält. Diese Option erfordert die Option **CryptoProvider**.<br/><br/>Diese Option ist ab .NET Core 4.7 verfügbar.|
|**-pwd, -Password** `passwd`|Das Kennwort, das zum Signieren eines Manifests mit einem digitalen Zertifikat verwendet wird. Muss zusammen mit der Option **-CertFile** verwendet werden.|
|**-t, -ToFile** `filePath`|Gibt den Ausgabepfad der Datei an, die erstellt oder geändert wurde.|

## <a name="remarks"></a>Anmerkungen

Bei allen Argumenten für *Mage.exe* wird nicht zwischen Groß- und Kleinschreibung unterschieden. Befehlen und Optionen kann ein Strich (-) oder ein Schrägstrich (/) als Präfix vorangestellt werden.

Alle mit dem Befehl **-Sign** verwendeten Argumente können jederzeit auch mit den Befehlen **-New** und **-Update** verwendet werden. Folgende Befehle sind gleichwertig.

```console
mage -Sign c:\HelloWorldDeployment\HelloWorld.deploy -CertFile cert.pfx
mage -Update c:\HelloWorldDeployment\HelloWorld.deploy -CertFile cert.pfx
```

> [!NOTE]
> Ab Version 4.6.2 von .NET Framework werden auch CNG-Zertifikate unterstützt.

 Das Signieren sollte zum Schluss erfolgen, da ein signiertes Dokument einen Hash der Datei verwendet, um zu überprüfen, ob die Signatur für das Dokument gültig ist. Wenn Sie Änderungen an einer signierten Datei vornehmen, müssen Sie sie erneut signieren. Wenn Sie ein Dokument signieren, das bereits signiert wurde, ersetzt *Mage.exe* die alte Signatur durch die neue Signatur.

 Wenn Sie ein Bereitstellungsmanifest mithilfe der Option **-AppManifest** füllen, geht *Mage.exe* davon aus, dass sich das Anwendungsmanifest im selben Verzeichnis wie das Bereitstellungsmanifest befindet, und zwar in einem Unterverzeichnis, das nach der aktuellen Bereitstellungsversion benannt ist. Das Bereitstellungsmanifest wird entsprechend konfiguriert. Wenn sich das Anwendungsmanifest in einem anderen Verzeichnis befinden soll, verwenden Sie die Option **-AppCodeBase** , um das alternative Verzeichnis festzulegen.

 Das Bereitstellungs- und das Anwendungsmanifest müssen signiert werden, bevor Sie die Anwendung bereitstellen. Einen Leitfaden zum Signieren von Manifesten finden Sie unter [Trusted Application Deployment Overview](/visualstudio/deployment/trusted-application-deployment-overview).

 Die Option **-TrustLevel** für Anwendungsmanifeste beschreibt den Berechtigungssatz, der für eine Anwendung erforderlich ist, damit sie auf dem Clientcomputer ausgeführt werden kann. Standardmäßig wird Anwendungen auf Grundlage der *Zone* , in der sich die zugehörige URL befindet, eine Vertrauensebene zugewiesen. Anwendungen, die über ein Unternehmensnetzwerk bereitgestellt werden, werden in der Regel in der Intranetzone platziert. Anwendungen, die über das Internet bereitgestellt werden, werden in der Internetzone platziert. In beiden Sicherheitszonen wird der Zugriff der Anwendung auf lokale Ressourcen eingeschränkt, wobei für die Intranetzone etwas geringere Einschränkungen der Berechtigungen gelten als für die Internetzone. Anwendungen in der FullTrust-Zone wird vollständiger Zugriff auf die lokalen Ressourcen eines Computers gewährt. Wenn Sie mithilfe der Option **-TrustLevel** eine Anwendung in dieser Zone platzieren, fordert die Trust-Manager-Komponente der CLR den Benutzer auf, anzugeben, ob diese höhere Vertrauensebene gewährt werden soll. Bei Bereitstellung der Anwendung über ein Unternehmensnetzwerk können Sie die Vertrauensebene der Anwendung mithilfe der Bereitstellung vertrauenswürdiger Anwendungen erhöhen, ohne dazu den Benutzer auffordern zu müssen.

 Anwendungsmanifeste unterstützen zudem benutzerdefinierte Trust-Abschnitte. Auf diese Weise kann die Anwendung das Sicherheitsprinzip der geringsten Berechtigung einhalten, da Sie das Manifest so konfigurieren können, dass nur genau die Berechtigungen angefordert werden, die zum Ausführen der Anwendung erforderlich sind. *Mage.exe* bietet keine direkte Unterstützung für das Hinzufügen eines benutzerdefinierten Trust-Abschnitts. Sie können einen solchen Abschnitt mit einem Text-Editor, einem XML-Parser oder dem grafischen Tool *MageUI.exe* hinzufügen. Weitere Informationen zum Hinzufügen benutzerdefinierter Trust-Abschnitte mit *MageUI.exe* finden Sie unter [MageUI.exe (Manifest Generation and Editing Tool, grafischer Client)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).

Visual Studio 2017 enthält Version 4.6.1 von *Mage.exe*. Manifeste, die mit dieser Version von *Mage.exe* erstellt werden, sind an .NET Framework 4 ausgerichtet. Für die Verwendung früherer Versionen von .NET Framework verwenden Sie eine frühere Version von *Mage.exe*.

Beim Hinzufügen oder Entfernen von Assemblys aus einem vorhandenen Manifest oder beim erneuten Signieren eines vorhandenen Manifests wird das Manifest nicht von *Mage.exe* für die Verwendung von .NET Framework 4 aktualisiert.

In den folgenden Tabellen werden diese Funktionen und Einschränkungen aufgeführt:

|Manifestversion|Vorgang|Mage v2.0|Mage v4.0|
|----------------------|---------------|---------------|---------------|
|Manifest für Anwendungen, für die als Ziel Version 2.0 oder 3.x von .NET Framework verwendet wird|Öffnen|OK|OK|
||Schließen|OK|OK|
||Speichern|OK|OK|
||Erneut signieren|OK|OK|
||Neu|OK|Nicht unterstützt|
||Aktualisieren (siehe unten)|OK|OK|
|Manifest für Anwendungen, für die als Ziel Version 4 von .NET Framework verwendet wird|Öffnen|OK|OK|
||Schließen|OK|OK|
||Speichern|OK|OK|
||Erneut signieren|OK|OK|
||Neu|Nicht unterstützt|OK|
||Aktualisieren (siehe unten)|Nicht unterstützt|OK|

|Manifestversion|Details zum Aktualisierungsvorgang|Mage v2.0|Mage v4.0|
|----------------------|------------------------------|---------------|---------------|
|Manifest für Anwendungen, für die als Ziel Version 2.0 oder 3.x von .NET Framework verwendet wird|Ändern einer Assembly|OK|OK|
||Hinzufügen einer Assembly|OK|OK|
||Entfernen einer Assembly|OK|OK|
|Manifest für Anwendungen, für die als Ziel Version 4 von .NET Framework verwendet wird|Ändern einer Assembly|Nicht unterstützt|OK|
||Hinzufügen einer Assembly|Nicht unterstützt|OK|
||Entfernen einer Assembly|Nicht unterstützt|OK|

 MageUI.exe erstellt neue Manifeste, die als Zielversion das .NET Framework 4 Client Profile haben. ClickOnce-Anwendungen, die .NET Framework 4 Client Profile als Ziel verwenden, können sowohl mit .NET Framework 4 Client Profile als auch mit der Vollversion von .NET Framework 4 ausgeführt werden. Wenn für die Anwendung als Ziel die Vollversion von .NET Framework 4 verwendet wird und eine Ausführung unter dem .NET Framework 4 Client Profile nicht möglich ist, entfernen Sie das Clientelement `<framework>` mit einem Text-Editor, und signieren Sie das Manifest erneut.

Es folgt ein Beispiel eines `<framework>`-Elements mit dem .NET Framework 4 Client Profile als Ziel:

```xml
<framework targetVersion="4.0" profile="client" supportedRuntime="4.0.20506" />
```

## <a name="examples"></a>Beispiele

Im folgenden Beispiel wird die Benutzeroberfläche von Mage (*MageUI.exe*) geöffnet.

```console
mage
```

In den folgenden Beispielen werden ein Standardbereitstellungsmanifest und ein Standardanwendungsmanifest erstellt. Diese Dateien werden alle im aktuellen Arbeitsverzeichnis unter den Namen deploy.application bzw. application.exe.manifest erstellt.

```console
mage -New Deployment
mage -New Application
```

Im folgenden Beispiel wird ein mit allen Assemblys und Ressourcendateien aus dem aktuellen Verzeichnis gefülltes Anwendungsmanifest erstellt.

```console
mage -New Application -FromDirectory . -Version 1.0.0.0
```

Im folgenden Beispiel wird das vorherige Beispiel fortgesetzt, indem der Bereitstellungsname und der Zielmikroprozessor angegeben werden. Zudem wird eine URL angegeben, unter der ClickOnce nach Updates sucht.

```console
mage -New Application -FromDirectory . -Name "Hello, World! Application" -Version 1.0.0.0 -Processor "x86" -ProviderUrl http://internalserver/HelloWorld/
```

Das folgende Beispiel veranschaulicht, wie Sie ein Manifestpaar für die Bereitstellung einer WPF-Anwendung erstellen, die in Internet Explorer gehostet wird.

```console
mage -New Application -FromDirectory . -Version 1.0.0.0 -WPFBrowserApp true
mage -New Deployment -AppManifest 1.0.0.0\application.manifest -WPFBrowserApp true
```

Im folgenden Beispiel wird ein mit allen Assemblys und Ressourcendateien aus dem aktuellen Verzeichnis gefülltes Anwendungsmanifest erstellt und signiert.

```console
mage -New Application -FromDirectory . -Version 1.0.0.0 -KeyContainer keypair.snk -CryptoProvider "Microsoft Enhanced Cryptographic Provider v1.0"
```

Im folgenden Beispiel wird ein Bereitstellungsmanifest mit Informationen aus einem Anwendungsmanifest aktualisiert. Dann wird die CodeBase für den Speicherort des Anwendungsmanifests festgelegt.

```console
mage -Update HelloWorld.deploy -AppManifest 1.0.0.0\application.manifest -AppCodeBase http://internalserver/HelloWorld.deploy
```

Im folgenden Beispiel wird das Bereitstellungsmanifest so bearbeitet, dass ein Update der installierten Version des Benutzers erzwungen wird.

```console
mage -Update c:\HelloWorldDeployment\HelloWorld.deploy -MinVersion 1.1.0.0
```

Im folgenden Beispiel wird das Bereitstellungsmanifest angewiesen, das Anwendungsmanifest aus einem anderen Verzeichnis abzurufen.

```console
mage -Update HelloWorld.deploy -AppCodeBase http://anotherserver/HelloWorld/1.1.0.0/
```

Im folgenden Beispiel wird ein vorhandenes Bereitstellungsmanifest mithilfe eines digitalen Zertifikats im aktuellen Arbeitsverzeichnis signiert.

```console
mage -Sign deploy.application -CertFile cert.pfx -Password <passwd>
```

Im folgenden Beispiel wird ein vorhandenes Bereitstellungsmanifest mithilfe eines digitalen Zertifikats und eines privaten Schlüssels im aktuellen Arbeitsverzeichnis signiert.

```console
mage -Sign deploy.application -CertFile cert.pfx -KeyContainer keyfile.snk -CryptoProvider "Microsoft Enhanced Cryptographic Provider v1.0"
```

## <a name="see-also"></a>Siehe auch

- [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)
- [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)
- [Überblick über die Bereitstellung vertrauenswürdiger Anwendungen](/visualstudio/deployment/trusted-application-deployment-overview)
- [MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
