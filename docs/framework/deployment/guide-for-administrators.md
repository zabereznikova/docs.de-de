---
title: Handbuch für die Bereitstellung von .NET Framework für Administratoren
description: Lesen Sie das Handbuch für die Bereitstellung von .NET für Administratoren. Stellen Sie anhand dieser Informationen die .NET Version 4.5 und ihre Systemabhängigkeiten in einem Netzwerk bereit.
ms.date: 04/10/2018
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
ms.openlocfilehash: 12076334d3ede0c8ab9b618ba2018f23c9fc6ae4
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817093"
---
# <a name="net-framework-deployment-guide-for-administrators"></a>Handbuch für die Bereitstellung von .NET Framework für Administratoren

In diesem Artikel wird ausführlich beschrieben, wie Systemadministratoren .NET Framework 4.5 und die zugehörigen Systemabhängigkeiten in einem Netzwerk mit Microsoft Endpoint Configuration Manager bereitstellen können. In diesem Artikel wird davon ausgegangen, dass alle Zielclientcomputer die Mindestanforderungen für das .NET Framework erfüllen. Eine Liste mit den Software- und Hardwareanforderungen für die Installation von .NET Framework 4.5 finden Sie unter [Systemanforderungen für .NET Framework](../get-started/system-requirements.md).

> [!NOTE]
> Die Software, auf die in diesem Dokument verwiesen wird (einschließlich .NET Framework 4.5, Configuration Manager und Active Directory), unterliegt ohne Einschränkungen den jeweils geltenden Lizenzbedingungen. In diesen Anweisungen wird vorausgesetzt, dass die Lizenzbestimmungen von den entsprechenden Lizenznehmern der Software gelesen und akzeptiert wurden. Diese Anweisungen bedeuten keinen Verzicht auf die Bestimmungen von Lizenzvereinbarungen.
>
> Informationen zur Unterstützung für das .NET Framework finden Sie unter [Offizielle .NET Framework-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) auf der Supportwebsite von Microsoft.

Dieses Thema enthält folgende Abschnitte:

- [Bereitstellungsprozess](#the_deployment_process)
- [Bereitstellen des .NET Framework](#deploying_in_a_test_environment)
- [Erstellen einer Sammlung](#creating_a_collection)
- [Erstellen eines Pakets und Programms](#creating_a_package)
- [Auswählen eines Verteilungspunkts](#select_dist_point)
- [Bereitstellen des Pakets](#deploying_package)
- [Ressourcen](#resources)
- [Problembehandlung](#troubleshooting)

<a name="the_deployment_process"></a>

## <a name="the-deployment-process"></a>Bereitstellungsprozess

Wenn Sie die unterstützende Infrastruktur eingerichtet haben, stellen Sie das verteilbare .NET Framework-Paket mit Configuration Manager auf Computern im Netzwerk bereit. Der Aufbau der Infrastruktur umfasst das Erstellen und Definieren von fünf primären Bereichen: Sammlungen, ein Paket und ein Programm für die Software, Verteilungspunkte und Bereitstellungen.

- Bei **Sammlungen** handelt es sich um Gruppen von Configuration Manager-Ressourcen (z. B. Benutzer, Benutzergruppen oder Computer), für die das .NET Framework bereitgestellt wird. Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Einführung in Sammlungen in Configuration Manager](/configmgr/core/clients/manage/collections/introduction-to-collections).

- **Pakete und Programme** stellen in der Regel Softwareanwendungen dar, die auf einem Clientcomputer installiert werden, sie können jedoch auch einzelne Dateien, Updates oder sogar einzelne Befehle enthalten. Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Pakete und Programme in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).

- **Verteilungspunkte** sind Configuration Manager-Standortsystemrollen, die zum Ausführen von Software auf Clientcomputern erforderliche Dateien speichern. Wenn der Configuration Manager-Client eine Softwarebereitstellung empfängt und verarbeitet, stellt er eine Verbindung mit einem Verteilungspunkt her, um den mit der Software verbundenen Inhalt herunterzuladen und den Installationsvorgang zu starten. Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Grundlegende Konzepte für die Inhaltsverwaltung in Configuration Manager](/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management).

- **Bereitstellungen** weisen zutreffende Member der angegebenen Zielsammlung an, das Softwarepaket zu installieren.

> [!IMPORTANT]
> Die Prozeduren in diesem Thema enthalten typische Einstellungen für das Erstellen und Bereitstellen eines Pakets und Programms und umfassen möglicherweise nicht alle möglichen Einstellungen. Weitere Bereitstellungsoptionen im Configuration Manager finden Sie in der [Dokumentationsbibliothek zum Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682041(v=technet.10)).

<a name="deploying_in_a_test_environment"></a>

## <a name="deploying-net-framework"></a>Bereitstellen des .NET Framework

Sie können mit Configuration Manager eine automatische Installation von .NET Framework 4.5 bereitstellen, bei der die Benutzer nicht in den Installationsvorgang eingreifen. Führen Sie folgende Schritte aus:

1. [Erstellen Sie eine Sammlung](#creating_a_collection).

2. [Erstellen Sie ein Paket und Programm für das verteilbare .NET Framework-Paket](#creating_a_package).

3. [Wählen Sie einen Verteilungspunkt aus](#select_dist_point).

4. [Stellen Sie das Paket bereit](#deploying_package).

<a name="creating_a_collection"></a>

### <a name="create-a-collection"></a>Erstellen einer Sammlung

In diesem Schritt wählen Sie die Computer aus, auf denen Sie das Paket und Programm bereitstellen, und gruppieren sie in einer Gerätesammlung. Zum Erstellen einer Sammlung im Configuration Manager können Sie Regeln für die direkte Mitgliedschaft verwenden (wobei Sie die Sammlungsmitglieder manuell angeben). Alternativ können Sie Abfrageregeln verwenden (wobei die Sammlungsmitglieder vom Configuration Manager auf der Grundlage von Kriterien bestimmt werden, die Sie angegeben haben). Weitere Informationen zu abfragebezogenen und direkten Mitgliedschaftsregeln finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Einführung in Sammlungen in Configuration Manager](/configmgr/core/clients/manage/collections/introduction-to-collections).

So erstellen Sie eine Sammlung

1. Wählen Sie in der Configuration Manager-Konsole **Bestand und Kompatibilität** aus.

2. Wählen Sie im Arbeitsbereich **Bestand und Kompatibilität** die Option **Gerätesammlungen** aus.

3. Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Erstellen** die Option **Gerätesammlung erstellen** aus.

4. Geben Sie im **Assistent zum Erstellen von Gerätesammlungen** auf der Seite **Allgemein** einen Namen für die Auflistung ein.

5. Wählen **Durchsuchen** aus, um eine begrenzende Sammlung anzugeben.

6. Wählen Sie auf der Seite **Mitgliedschaftsregeln** die Option **Regel hinzufügen** aus, und wählen Sie dann **Direkte Regel** aus, um den **Assistent für die Erstellung von Regeln der direkten Mitgliedschaft** zu öffnen. Wählen Sie **Weiter** aus.

7. Wählen Sie auf der Seite **Ressourcen suchen** in der Liste **Ressourcenklasse** die Option **Systemressource** aus. Wählen Sie in der Liste **Attributname** die Option **Name** aus. Geben Sie im Feld **Wert** das Zeichen `%` ein, und wählen Sie dann **Weiter** aus.

8. Aktivieren Sie auf der Seite **Ressourcen auswählen** das Kontrollkästchen für jeden Computer, für den Sie .NET Framework bereitstellen möchten. Wählen Sie **Weiter** aus, und schließen Sie den Assistenten.

9. Wählen Sie auf der Seite **Mitgliedschaftsregeln** im **Assistent zum Erstellen von Gerätesammlungen** die Option **Weiter** aus, und schließen Sie den Assistenten ab.

<a name="creating_a_package"></a>

### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a>Erstellen eines Pakets und Programms für das verteilbare .NET Framework-Paket

Mit den folgenden Schritten erstellen Sie manuell ein Paket für das verteilbare .NET Framework-Paket. Das Paket enthält die angegebenen Parameter zum Installieren des .NET Framework und zu dem Speicherort, von dem das Paket an die Zielcomputer verteilt wird.

So erstellen Sie ein Paket

1. Wählen Sie in der Configuration Manager-Konsole **Softwarebibliothek** aus.

2. Erweitern Sie im Arbeitsbereich **Softwarebibliothek** den Knoten **Anwendungsverwaltung**, und wählen Sie dann **Pakete** aus.

3. Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Erstellen** die Option **Paket erstellen** aus.

4. Geben Sie auf der Seite **Paket** im **Assistent zum Erstellen von Paketen und Programmen** die folgenden Informationen ein:

    - Name: `.NET Framework 4.5`

    - Hersteller: `Microsoft`

    - Sprache: `English (US)`

5. Wählen Sie **Dieses Paket enthält Quelldateien** aus, und wählen Sie anschließend **Durchsuchen** aus, um den lokalen oder Netzwerkordner mit den .NET Framework-Installationsdateien auszuwählen. Wenn Sie den Ordner ausgewählt haben, wählen Sie **OK** und anschließend **Weiter** aus.

6. Wählen Sie auf der Seite **Programmtyp** des Assistenten **Standardprogramm** und anschließend **Weiter** aus.

7. Geben Sie auf der Seite **Programm** im **Assistent zum Erstellen von Paketen und Programmen** die folgenden Informationen ein:

    1. **Name:** `.NET Framework 4.5`

    2. **Befehlszeile:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (Befehlszeilenoptionen werden in der Tabelle weiter unten beschrieben)

    3. **Ausführen:** Wählen Sie **Ausgeblendet** aus.

    4. **Programmausführung:** Wählen Sie die Option aus, die angibt, dass das Programm unabhängig davon, ob ein Benutzer angemeldet ist, ausgeführt werden kann.

8. Wählen Sie auf der Seite **Anforderungen** zum Übernehmen der Standardwerte **Weiter** aus, und schließen Sie dann den Assistenten ab.

In der folgenden Tabelle werden die in Schritt 7 angegebenen Befehlszeilenoptionen beschrieben.

|Option|Beschreibung|
|------------|-----------------|
|**/q**|Legt den stillen Modus fest. Es sind keine Benutzereingaben erforderlich, und es wird keine Ausgabe angezeigt.|
|**/norestart**|Verhindert, dass das Setupprogramm automatisch erneut gestartet wird. Bei Verwendung dieser Option muss Configuration Manager den Neustart des Computers behandeln.|
|**/chainingpackage** *PackageName*|Gibt den Namen des Pakets an, das das Verketten ausführt. Diese Informationen werden zusammen mit anderen Installationssitzungsinformationen für Personen ausgegeben, die sich beim Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit (Customer Experience Improvement Program, CEIP) registriert haben. Wenn der Paketname Leerzeichen enthält, verwenden Sie als Trennzeichen doppelte Anführungszeichen, z.B. **/chainingpackage "Chaining Product"** .|

Mit diesen Schritten wird ein Paket namens ".NET Framework 4.5" erstellt. Das Programm stellt eine automatische Installation von .NET Framework 4.5 bereit. In einer automatischen Installation greifen Benutzer nicht in den Installationsvorgang ein, und die Verkettungsanwendung muss den Rückgabecode erfassen und den Neustart initiieren. Weitere Informationen finden Sie in der unter [Getting Progress Information from an Installation Package (Abrufen von Statusinformationen aus einem Installationspaket)](/previous-versions/cc825975(v=vs.100)).

<a name="select_dist_point"></a>

### <a name="select-a-distribution-point"></a>Auswählen eines Verteilungspunkts

Um das Paket und Programm von einem Server an Clientcomputer zu verteilen, müssen Sie zuerst ein Standortsystem als Verteilungspunkt festlegen und das Paket dann an den Verteilungspunkt verteilen.

Führen Sie die folgenden Schritte aus, um einen Verteilungspunkt für das im vorherigen Abschnitt erstellte .NET Framework 4.5-Paket auszuwählen:

1. Wählen Sie in der Configuration Manager-Konsole **Softwarebibliothek** aus.

2. Erweitern Sie im Arbeitsbereich **Softwarebibliothek** den Knoten **Anwendungsverwaltung**, und wählen Sie dann **Pakete** aus.

3. Wählen Sie aus der Liste von Paketen das Paket **.NET Framework 4.5** aus, das Sie im vorherigen Abschnitt erstellt haben.

4. Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Bereitstellung** die Option **Inhalt verteilen** aus.

5. Wählen Sie auf der Registerkarte **Allgemein** im **Assistent für die Verteilung von Inhalt** die Option **Weiter** aus.

6. Wählen Sie auf der Seite **Inhaltsziel** des Assistenten **Hinzufügen** und anschließend **Verteilungspunkt** aus.

7. Wählen Sie im Dialogfeld **Verteilungspunkte hinzufügen** mindestens einen Verteilungspunkt aus, von dem das Paket und Programm gehostet werden sollen, und wählen Sie dann **OK** aus.

8. Durchlaufen Sie den Assistenten.

Das Paket enthält jetzt alle Informationen, die Sie für die automatische Bereitstellung von .NET Framework 4.5 benötigen. Überprüfen Sie vor dem Bereitstellen des Pakets und Programms, ob die Installation auf dem Verteilungspunkt ausgeführt wurde. Weitere Informationen finden Sie im Abschnitt „Überwachen des Inhaltsstatus“ unter [Überwachen von mit Configuration Manager verteilten Inhalten](/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) in der Configuration Manager-Dokumentationsbibliothek.

<a name="deploying_package"></a>

### <a name="deploy-the-package"></a>Bereitstellen des Pakets

So stellen Sie das .NET Framework 4.5-Paket und -Programm bereit

1. Wählen Sie in der Configuration Manager-Konsole **Softwarebibliothek** aus.

2. Erweitern Sie im Arbeitsbereich **Softwarebibliothek** den Knoten **Anwendungsverwaltung**, und wählen Sie dann **Pakete** aus.

3. Wählen Sie aus der Liste von Paketen das Paket **.NET Framework 4.5** aus, das Sie erstellt haben.

4. Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Bereitstellung** die Option **Bereitstellen** aus.

5. Wählen Sie auf der Seite **Allgemein** im **Assistent zum Bereitstellen von Software** die Option **Durchsuchen** und anschließend die Sammlung aus, die Sie zuvor erstellt haben. Wählen Sie **Weiter** aus.

6. Überprüfen Sie auf der Seite **Inhalt** des Assistenten, ob der Punkt, von dem Sie die Software verteilen möchten, angezeigt wird. Wählen Sie anschließend **Weiter** aus.

7. Bestätigen Sie auf der Seite **Bereitstellungseinstellungen** des Assistenten, dass **Aktion** auf **Installieren** festgelegt ist und dass **Zweck** auf **Erforderlich** festgelegt ist. Dadurch wird sichergestellt, dass die Installation des Softwarepakets auf den Zielcomputern erforderlich ist. Wählen Sie **Weiter** aus.

8. Geben Sie auf der Seite **Zeitplanung** des Assistenten an, wann das .NET Framework installiert werden soll. Sie können **Neu** auswählen, um eine Installationszeit zuzuweisen, oder die Software anweisen, die Installation bei An- oder Abmeldung des Benutzers oder so schnell wie möglich durchzuführen. Wählen Sie **Weiter** aus.

9. Verwenden Sie auf der Seite **Benutzerfreundlichkeit** des Assistenten die Standardwerte, und wählen Sie **Weiter** aus.

    > [!WARNING]
    > Möglicherweise gelten in Ihrer Produktionsumgebung Richtlinien, die eine andere Auswahl für den Bereitstellungszeitplan erfordern.

10. Verwenden Sie auf der Seite **Verteilungspunkte** des Assistenten die Standardwerte, und wählen Sie **Weiter** aus.

11. Durchlaufen Sie den Assistenten. Sie können den Status der Bereitstellung im Knoten **Bereitstellungen** des Arbeitsbereichs **Überwachung** überwachen.

Das Paket wird nun in der als Ziel festgelegten Sammlung bereitgestellt, und die automatische Installation von .NET Framework 4.5 beginnt. Informationen zu Fehlercodes für die .NET Framework 4.5-Installation finden Sie weiter unten in diesem Thema im Abschnitt [Rückgabecodes](#return_codes).

<a name="resources"></a>

## <a name="resources"></a>Ressourcen

Weitere Informationen zur Infrastruktur zum Testen der Bereitstellung des weitervertreibbaren .NET Framework 4.5-Pakets finden Sie in den folgenden Ressourcen:

**Active Directory, DNS, DHCP:**

- [Active Directory Domain Services](/windows/desktop/ad/active-directory-domain-services)

- [Domain Name System (DNS)](/windows-server/networking/dns/dns-top)

- [Dynamic Host Configuration-Protokoll (DHCP)](/windows-server/networking/technologies/dhcp/dhcp-top)

**SQL Server 2008:**

- [Installieren von SQL Server 2008 (SQL Server-Video)](/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))

- [SQL Server 2008-Sicherheit: Übersicht für Datenbankadministratoren](https://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)

**System Center 2012 Configuration Manager (Verwaltungspunkt, Verteilungspunkt):**

- [Standortverwaltung für System Center 2012 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg681983(v=technet.10))

**System Center 2012 Configuration Manager-Client für Windows-Computer:**

- [Bereitstellen von Clients für System Center 2012 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699391(v=technet.10))

<a name="troubleshooting"></a>

## <a name="troubleshooting"></a>Problembehandlung

### <a name="log-file-locations"></a>Protokolldateispeicherorte

Beim Setup von .NET Framework werden die folgenden Protokolldateien generiert:

- %temp%\Microsoft .NET Framework *version*\*.txt
- %temp%\Microsoft .NET Framework *version*\*.html,

wobei *version* der .NET Framework-Version entspricht, die Sie installieren (z. B. 4.5 oder 4.7.2).

Sie können ebenso das Verzeichnis angeben, in das Protokolldateien geschrieben werden. Verwenden Sie hierzu die Befehlszeilenoption `/log` im Installationsbefehl von .NET Framework. Weitere Informationen finden Sie im [Leitfaden für die Bereitstellung von .NET Framework für Entwickler](deployment-guide-for-developers.md#command-line-options).

Mit dem [Protokollerfassungstool (Log Collection Tool)](https://www.microsoft.com/download/details.aspx?id=12493) können Sie die .NET Framework-Protokolldateien erfassen und eine komprimierte CAB-Datei erstellen, um die Größe der Dateien zu reduzieren.

<a name="return_codes"></a>

### <a name="return-codes"></a>Rückgabecodes

Die folgende Tabelle enthält die gängigsten Rückgabecodes des weitervertreibbaren .NET Framework 4.5-Installationsprogramms. Die Rückgabecodes sind für alle Versionen des Installationsprogramms identisch.

Links zu ausführlichen Informationen finden Sie im nächsten Abschnitt [Downloadfehlercodes](#additional_error_codes).

|Rückgabecode|Beschreibung|
|-----------------|-----------------|
|0|Die Installation wurde erfolgreich abgeschlossen.|
|1602|Der Benutzer hat die Installation abgebrochen.|
|1603|Während der Installation ist ein schwerwiegender Fehler aufgetreten.|
|1641|Ein Neustart ist erforderlich, um die Installation abzuschließen. Diese Meldung zeigt eine erfolgreiche Installation an.|
|3010|Ein Neustart ist erforderlich, um die Installation abzuschließen. Diese Meldung zeigt eine erfolgreiche Installation an.|
|5100|Der Computer des Benutzers erfüllt die Systemanforderungen nicht.|

<a name="additional_error_codes"></a>

### <a name="download-error-codes"></a>Downloadfehlercodes

- [Fehlercodes für BITS (Background Intelligent Transfer Service)](/windows/desktop/Bits/bits-return-values)

- [Fehlercodes für URL-Moniker](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775145(v=vs.85))

- [Fehlercodes für WinHttp](/windows/desktop/WinHttp/error-messages)

Sonstige Fehlercodes

- [Fehlercodes für Windows Installer](/windows/desktop/msi/error-codes)

- [Ergebniscodes für Windows Update Agent](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))

## <a name="see-also"></a>Siehe auch

- [Bereitstellungshandbuch für Entwickler](deployment-guide-for-developers.md)
- [Systemanforderungen](../get-started/system-requirements.md)
