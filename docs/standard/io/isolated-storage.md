---
title: Isolierte Speicherung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- data storage using isolated storage
- stores
- storing data using isolated storage
- isolated storage
- location of isolated storage in file system
- standardizing storage systems
- storing data using isolated storage, when not to use
- code, isolated storage
- isolated storage, options
- data storage using isolated storage, when not to use
- storing data using isolated storage, options
- isolated storage, when not to use
- data storage using isolated storage, options
- isolation
ms.assetid: aff939d7-9e49-46f2-a8cd-938d3020e94e
ms.openlocfilehash: f98af970c8827623298fb43cd0653bdaafb20dd3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278881"
---
# <a name="isolated-storage"></a>Isolierte Speicherung
<a name="top"></a> Die isolierte Speicherung ist ein Mechanismus zur Datenspeicherung von Desktop-Apps, der Isolation und Sicherheit gewährleistet, indem er standardisierte Möglichkeiten zur Verknüpfung von Code mit gespeicherten Daten definiert. Die Standardisierung hat weitere Vorteile. Administratoren können spezielle Tools zum Ändern isolierter Speichervorgänge verwenden, um Speicherplätze für Dateien zu konfigurieren, Sicherheitsrichtlinien festzulegen und nicht verwendete Daten zu löschen. Dank isolierter Speicherung benötigt der Code keine eindeutigen Pfade zur Festlegung sicherer Speicherplätze im Dateisystem. Außerdem werden die Daten vor anderen Anwendungen geschützt, die nur über Zugriff auf isolierte Speicherplätze verfügen. Fest codierte Daten, die den Speicherbereich einer Anwendung angeben, sind nicht erforderlich.

> [!IMPORTANT]
> Die isolierte Speicherung ist nicht für Windows 8.x Store-Apps verfügbar. Verwenden Sie stattdessen zum Speichern von lokalen Daten und Dateien die in der Windows-Runtime-API enthaltenen Anwendungsdatenklassen in den `Windows.Storage`-Namespaces. Weitere Informationen finden Sie im Windows Developer Center unter [Anwendungsdaten](https://docs.microsoft.com/previous-versions/windows/apps/hh464917(v=win.10)) .

Dieses Thema enthält folgende Abschnitte:

- [Datendepots und -speicher](#data_compartments_and_stores)

- [Kontingente für isolierte Speicherung](#quotas)

- [Sicherer Zugriff](#secure_access)

- [Zulässige Verwendung und Sicherheitsrisiken](#allowed_usage)

- [Isolierte Speicherorte](#isolated_storage_locations)

- [Erstellen, Auflisten und Löschen von isoliertem Speicher](#isolated_storage_tasks)

- [Szenarien für die isolierte Speicherung](#scenarios_for_isolated_storage)

- [Verwandte Themen](#related_topics)

- [Verweis](#reference)

<a name="data_compartments_and_stores"></a>

## <a name="data-compartments-and-stores"></a>Datendepots und -speicher

Wenn eine Anwendung Daten in einer Datei speichert, müssen Dateiname und Speicherplatz sorgfältig ausgewählt werden, um weitestgehend zu verhindern, dass der Speicherplatz einer anderen Anwendung zugänglich und damit anfällig für Datenbeschädigungen wird. Ohne die Verwendung eines Standardsystems zur Behebung solcher Probleme kann die Entwicklung von Ad-hoc-Techniken zur Minimierung von Speicherkonflikten sehr komplex sein und zu unzuverlässigen Ergebnissen führen.

Bei der isolierten Speicherung werden die Daten immer nach Benutzer oder nach Assembly isoliert. Informationen wie der Ursprung oder der starke Name der Assembly bestimmen die Identität der Assembly. Daten können auch nach Anwendungsdomäne isoliert werden, wobei ähnliche Informationen verwendet werden.

Bei der Verwendung der isolierten Speicherung speichert Ihre Anwendung Daten in einem eindeutigem Datendepot, das einem bestimmten Aspekt der Identität des Codes zugeordnet ist, beispielsweise dem Herausgeber oder der Signatur. Das Datendepot ist abstrakt und stellt keinen spezifischen Speicherplatz dar. Es besteht aus einer oder mehreren Dateien der isolierten Speicherung, so genannten Speichern. Diese enthalten den tatsächlichen Verzeichnisort, an dem die Daten gespeichert sind. So kann z. B. einer Anwendung ein Datendepot zugeordnet sein. In diesem Fall ist es das Verzeichnis im Dateisystem, das den Speicher implementiert. Dort sind die Daten dieser Anwendung gespeichert. In diesem Speicher können beliebige Daten gespeichert werden, z. B. Informationen zur Benutzereinstellung oder der Anwendungszustand. Für den Entwickler ist der Speicherplatz des Datendepots transparent. Speicher befinden sich normalerweise auf dem Client. Eine Serveranwendung könnte jedoch isolierte Speicher zum Speichern von Informationen verwenden, indem sie die Identität des Benutzers annimmt, in dessen Auftrag sie arbeitet. Mit isolierter Speicherung können Daten auf einem Server mit einem Roamingbenutzerprofil gespeichert werden. Dadurch wandern die Daten mit dem Benutzer mit.

<a name="quotas"></a>

## <a name="quotas-for-isolated-storage"></a>Kontingente für isolierte Speicherung

Bei einem Kontingent handelt es sich um eine Begrenzung des Umfangs an isoliertem Speicherplatz, der verwendet werden kann. Das Kontingent umfasst Speicherplatzangaben in Bytes sowie den Mehrbedarf in Verbindung mit dem Verzeichnis und anderen Informationen im Speicher. Bei der isolierten Speicherung werden Berechtigungskontingente verwendet, bei denen es sich um eine mithilfe von <xref:System.Security.Permissions.IsolatedStoragePermission> -Objekten eingestellte Speicherplatzbegrenzung handelt. Versuchen Sie, über das Kontingent hinausgehende Daten zu schreiben, wird eine <xref:System.IO.IsolatedStorage.IsolatedStorageException> -Ausnahme ausgelöst.  In einer Sicherheitsrichtlinie, die mithilfe des .NET Framework-Konfigurationstools (Mscorcfg.msc) geändert werden kann, wird festgelegt, welche Berechtigungen Code erteilt werden. Code, dem <xref:System.Security.Permissions.IsolatedStoragePermission> gewährt wurde, kann nicht mehr Speicherplatz verwenden, als die <xref:System.Security.Permissions.IsolatedStoragePermission.UserQuota%2A> -Eigenschaft zulässt. Da Code allerdings Berechtigungskontingente durch die Angabe verschiedener Benutzeridentitäten umgehen kann, dienen diese lediglich als Richtlinien und nicht als strenge Einschränkungen für das Verhalten des Codes.

Kontingente werden nicht in Roamingspeichern durchgesetzt. Dies ist der Grund, weshalb für ihre Verwendung eine etwas höhere Berechtigungsebene erforderlich ist. Die Enumerationswerte <xref:System.Security.Permissions.IsolatedStorageContainment.AssemblyIsolationByRoamingUser> und <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByRoamingUser> geben eine Berechtigung zur Verwendung von isolierter Speicherung für einen Roamingbenutzer an.

<a name="secure_access"></a>

## <a name="secure-access"></a>Sicherer Zugriff

Durch isolierte Speicherung können Daten von teilweise vertrauenswürdigen Anwendungen so gespeichert werden, dass eine Kontrolle durch die Sicherheitsrichtlinien des Computers gewährleistet ist. Dies ist besonders für heruntergeladene Komponenten von Nutzen, bei deren Ausführung Vorsicht geboten ist. Wenn Sie standardmäßige E/A-Mechanismen zum Zugriff auf das Dateisystem verwenden, lassen die Sicherheitsrichtlinien selten diese Art der Codeberechtigung zu. Code, der vom lokalen Computer, von einem lokalen Netzwerk oder über das Internet ausgeführt wird, erhält jedoch standardmäßig die Berechtigung zur Verwendung von isoliertem Speicher.

Administratoren können auf Basis einer entsprechenden Vertrauensebene festlegen, wie viel isolierter Speicherplatz einer Anwendung oder einem Benutzer zur Verfügung steht. Darüber hinaus können Administratoren die gespeicherten Daten eines Benutzers vollständig löschen. Um isolierten Speicherplatz erstellen oder darauf zugreifen zu können, muss dem Code die entsprechende <xref:System.Security.Permissions.IsolatedStorageFilePermission> -Berechtigung erteilt werden.

Für den Zugriff auf isolierten Speicherplatz muss der Code über alle notwendigen systemeigenen Rechte der Betriebssystemplattform verfügen. Die Bedingungen der Zugriffssteuerungslisten (ACLs, Access Control Lists), die festlegen, welche Benutzer zur Verwendung des Dateisystems berechtigt sind, müssen erfüllt sein. .NET Framework-Anwendungen verfügen bereits über Betriebssystemrechte für den Zugriff auf isolierten Speicherplatz, sofern sie keine (plattformspezifische) Imitation ausführen. In diesem Fall ist die Anwendung dafür zuständig, dass die imitierte Benutzeridentität über die entsprechenden Rechte des Betriebssystems verfügt, um auf den isolierten Speicherplatz zuzugreifen. Mithilfe dieses Zugriffs kann aus dem Web ausgeführter bzw. heruntergeladener Code auf einfache Weise aus dem Speicherbereich, der einem bestimmten Benutzer zugeordnet ist, lesen bzw. in diesen schreiben.

Zur Steuerung des Zugriffs auf isolierte Speicherplätze verwendet Common Language Runtime <xref:System.Security.Permissions.IsolatedStorageFilePermission> -Objekte. Jedes Objekt verfügt über Eigenschaften, die folgende Werte festlegen:

- Zulässige Verwendung, die den erlaubten Zugriffstyp anzeigt. Die Werte sind Member der <xref:System.Security.Permissions.IsolatedStorageContainment> -Enumeration. Weitere Informationen über diese Werte finden Sie in der Tabelle im nächsten Abschnitt.

- Speicherkontingent, wie im vorherigen Abschnitt erläutert.

Beim ersten Versuch des Codes, einen Speicher zu öffnen, fordert die Runtime eine <xref:System.Security.Permissions.IsolatedStorageFilePermission> -Berechtigung an. Sie entscheidet basierend auf der Vertrauenswürdigkeit des Codes, ob diese Berechtigung erteilt wird. Falls die Berechtigung erteilt wird, werden die Werte für die zulässige Verwendung und für das Speicherkontingent durch die Sicherheitsrichtlinien und durch die Anforderung von <xref:System.Security.Permissions.IsolatedStorageFilePermission>durch den Code festgelegt. Die Sicherheitsrichtlinien werden mit dem .NET Framework-Konfigurationstool (Mscorcfg.msc) festgelegt. Alle Aufrufer in der Aufrufliste werden überprüft, um sicherzustellen, dass jeder mindestens über die entsprechende zulässige Verwendung verfügt. Durch die Laufzeit werden auch die Kontingente überprüft, die dem Code auferlegt wurden, durch welchen der Speicher für die zu speichernde Datei geöffnet oder erstellt wurde. Falls diese Bedingungen erfüllt sind, wird die Berechtigung erteilt. Die Überprüfung des Kontingents erfolgt jedes Mal erneut, wenn eine Datei in den Speicher geschrieben wird.

Für Anwendungscode muss keine Berechtigung angefordert werden, da Common Language Runtime jede gemäß den Sicherheitsrichtlinien angemessene <xref:System.Security.Permissions.IsolatedStorageFilePermission> erteilt. Allerdings gibt es gute Gründe, bestimmte Berechtigungen, die für Ihre Anwendung erforderlich sind, einschließlich von <xref:System.Security.Permissions.IsolatedStorageFilePermission>, anzufordern.

<a name="allowed_usage"></a>

## <a name="allowed-usage-and-security-risks"></a>Zulässige Verwendung und Sicherheitsrisiken

Die durch <xref:System.Security.Permissions.IsolatedStorageFilePermission> festgelegte zulässige Verwendung bestimmt, bis zu welchem Grad das Erstellen und Verwenden von isolierter Speicherung durch Code zugelassen wird. Aus der folgenden Tabelle geht hervor, inwiefern die in der Berechtigung festgelegte zulässige Verwendung den Isolationstypen entspricht. Ferner werden die Sicherheitsrisiken zusammengefasst, die jede zulässigen Verwendung mit sich bringt.

|Zulässige Verwendung|Isolationstypen|Sicherheitsrisiko|
|-------------------|---------------------|---------------------|
|<xref:System.Security.Permissions.IsolatedStorageContainment.None>|Es ist keine Verwendung von isolierter Speicherung zulässig.|Es besteht kein Sicherheitsrisiko.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser>|Isolation nach Benutzer, Domäne und Assembly. Jede Assembly verfügt über einen separaten Unterspeicher innerhalb der Domäne. Speicher, die diese Berechtigung verwenden, werden auch implizit nach Computer isoliert.|Diese Berechtigungsebene bietet Ressourcen keinen Schutz vor unbefugter Überbeanspruchung, wobei erzwungene Kontingente allerdings die Funktion haben, dies zu erschweren. Dies wird Denial-of-Service-Angriff genannt.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByRoamingUser>|Wie bei `DomainIsolationByUser`, jedoch befindet sich der Speicher an einem Speicherplatz, für den Roaming möglich ist, sofern Roamingbenutzerprofile aktiviert und Kontingente nicht erzwungen sind.|Da Kontingente deaktiviert sein müssen, sind die Speicherressourcen anfälliger für Denial-of-Service-Angriffe.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.AssemblyIsolationByUser>|Isolation nach Benutzer und Assembly. Speicher, die diese Berechtigung verwenden, werden auch implizit nach Computer isoliert.|Kontingente werden auf dieser Ebene erzwungen, um einen Denial-of-Service-Angriff zu verhindern. Dieselbe Assembly in einer anderen Domäne kann auf diesen Speicher zugreifen, wodurch ein Verlust von Informationen zwischen Anwendungen möglich ist.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.AssemblyIsolationByRoamingUser>|Wie bei `AssemblyIsolationByUser`, jedoch befindet sich der Speicher an einem Speicherplatz, für den Roaming möglich ist, sofern Roamingbenutzerprofile aktiviert und Kontingente nicht erzwungen sind.|Wie bei `AssemblyIsolationByUser`. Allerdings erhöht sich ohne Kontingente das Risiko eines Denial-of-Service-Angriffs.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser>|Isolation nach Benutzer. Normalerweise gilt diese Berechtigungsebene nur für Verwaltungs- oder Debugtools.|Durch den Zugriff mit dieser Berechtigung kann Code jede der Dateien oder Verzeichnisse in isolierten Speicherplätzen anzeigen oder löschen (unabhängig von Assemblyisolation). Es besteht u. a. das Risiko eines Informationslecks und des Datenverlusts.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.UnrestrictedIsolatedStorage>|Isolation nach Benutzern, Domänen und Assemblys. Normalerweise gilt diese Berechtigungsebene nur für Verwaltungs- oder Debugtools.|Durch diese Berechtigung sind sämtliche isolierte Speicher aller Benutzer potenziell gefährdet.|

<a name="isolated_storage_locations"></a>

## <a name="isolated-storage-locations"></a>Isolierte Speicherorte

Gelegentlich sollten Änderungen an isolierten Speicherplätzen mit dem Dateisystem des Betriebssystems überprüft werden. Sie möchten vielleicht auch wissen, wo die Dateien im isolierten Speicherplatz gespeichert sind. Der Speicherort hängt vom Betriebssystem ab. Die folgende Tabelle gibt für einige geläufige Betriebssysteme die Stammorte an, an denen isolierter Speicherplatz erstellt wird. Suchen Sie in diesem Stammspeicherort nach „Microsoft\IsolatedStorage“-Verzeichnissen. Zum Anzeigen versteckter Dateien und Ordner müssen die Ordnereinstellungen geändert werden, sodass isolierte Speicherplätze im Dateisystem angezeigt werden können.

|Betriebssystem|Speicherplatz im Dateisystem|
|----------------------|-----------------------------|
|Windows 2000, Windows XP, Windows Server 2003 (Upgrade von Windows NT 4.0)|Für Roaming aktivierte Speicher =<br /><br /> \<SYSTEMROOT>\Profile\\<Benutzer\>\Anwendungsdaten<br /><br /> Nicht für Roaming eingerichtete Speicher =<br /><br /> \<SYSTEMROOT>\Profile\\<Benutzer\>\Lokale Einstellungen\Anwendungsdaten|
|Windows 2000 – Neuinstallation (und Upgrades von Windows 98 und Windows NT 3.51)|Für Roaming aktivierte Speicher =<br /><br /> \<SYSTEMDRIVE>\Dokumente und Einstellungen\\<Benutzer\>\Anwendungsdaten<br /><br /> Nicht für Roaming eingerichtete Speicher =<br /><br /> \<SYSTEMDRIVE>\Dokumente und Einstellungen\\<Benutzer\>\Lokale Einstellungen\Anwendungsdaten|
|Windows XP, Windows Server 2003 – Neuinstallation (und Upgrades von Windows 2000 und Windows 98)|Für Roaming aktivierte Speicher =<br /><br /> \<SYSTEMDRIVE>\Dokumente und Einstellungen\\<Benutzer\>\Anwendungsdaten<br /><br /> Nicht für Roaming eingerichtete Speicher =<br /><br /> \<SYSTEMDRIVE>\Dokumente und Einstellungen\\<Benutzer\>\Lokale Einstellungen\Anwendungsdaten|
|Windows 8, Windows 7, Windows Server 2008, Windows Vista|Für Roaming aktivierte Speicher =<br /><br /> \<SYSTEMDRIVE>\Benutzer\\<Benutzer\>\AppData\Roaming<br /><br /> Nicht für Roaming eingerichtete Speicher =<br /><br /> \<SYSTEMDRIVE>\Benutzer\\<Benutzer\>\AppData\Local|

<a name="isolated_storage_tasks"></a>

## <a name="creating-enumerating-and-deleting-isolated-storage"></a>Erstellen, Auflisten und Löschen von isoliertem Speicher

Das .NET Framework stellt drei Klassen im <xref:System.IO.IsolatedStorage> -Namespace bereit, um Ihnen bei der Ausführung von Aufgaben im Zusammenhang mit isolierter Speicherung zu helfen:

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>wird von <xref:System.IO.IsolatedStorage.IsolatedStorage?displayProperty=nameWithType> abgeleitet und ermöglicht die Verwaltung von gespeicherten Assembly- und Anwendungsdateien. Eine Instanz der <xref:System.IO.IsolatedStorage.IsolatedStorageFile> -Klasse stellt einen einzelnen Speicher im Dateisystem dar.

- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> wird aus <xref:System.IO.FileStream?displayProperty=nameWithType> abgeleitet und ermöglicht den Zugriff auf Dateien in einem Speicher.

- Bei<xref:System.IO.IsolatedStorage.IsolatedStorageScope> handelt es sich um eine Enumeration, mit der ein Speicher mit einem entsprechenden Isolationstyp erstellt und ausgewählt werden kann.

Mit den Klassen der isolierten Speicherung können Sie isolierte Speicherplätze erstellen, auflisten und löschen. Die Methoden zur Ausführung dieser Aufgaben sind über das <xref:System.IO.IsolatedStorage.IsolatedStorageFile> -Objekt verfügbar. Für einige Operationen benötigen Sie zum Verwalten isolierter Speicher die <xref:System.Security.Permissions.IsolatedStorageFilePermission> -Berechtigung. Für den Zugriff auf die Datei oder das Verzeichnis benötigen Sie gegebenenfalls auch Betriebssystemrechte.

Eine Reihe von Beispielen, die allgemeine isolierte Speicheraufgaben veranschaulichen, finden Sie in den Gewusst-wie-Themen in [Verwandte Themen](#related_topics).

<a name="scenarios_for_isolated_storage"></a>

## <a name="scenarios-for-isolated-storage"></a>Szenarien für die isolierte Speicherung

Isolierte Speicherung kann in vielen Situationen hilfreich sein, zum Beispiel in diesen vier Szenarien:

- Heruntergeladene Steuerelemente. Aus dem Internet heruntergeladene Steuerelemente für verwalteten Code sind nicht berechtigt, über normale E/A-Klassen auf die Festplatte zu schreiben. Allerdings können sie mithilfe von isolierter Speicherung die Einstellungen eines Benutzers sowie den Anwendungszustand speichern.

- Speicher für gemeinsame Komponenten. Von Anwendungen gemeinsam verwendete Komponenten können mithilfe von isolierter Speicherung einen kontrollierten Zugriff auf Datenspeicher bereitstellen.

- Speicher auf dem Server. Serveranwendungen können isolierte Speicherung verwenden, um einzelne Speicher für eine große Zahl von Benutzern bereitzustellen, die Anforderungen an die Anwendung richten. Da isolierte Speicherplätze auf die einzelnen Benutzer verteilt werden, muss der Server den anfordernden Benutzer imitieren. In diesem Fall werden Daten auf Basis der Identität des Prinzipals isoliert, bei der es sich um dieselbe Identität handelt, anhand derer die Anwendung Benutzer voneinander unterscheidet.

- Roaming. Anwendungen können isolierte Speicherplätze auch mit Roamingbenutzerprofilen verwenden. Dadurch können die isolierten Speicher eines Benutzers wie die Profile von überall zugänglich sein.

Sie sollten isolierten Speicher in den folgenden Situationen nicht verwenden:

- Zum Speichern hochsensibler Daten wie unverschlüsselte Schlüssel oder Kennwörter, da isolierte Speicherplätze nicht vor besonders vertrauenswürdigem Code, nicht verwaltetem Code bzw. vor vertrauenswürdigen Benutzern des Computers geschützt sind.

- Zum Speichern von Code.

- Zum Speichern von administratorgesteuerten Konfigurations- und Bereitstellungseinstellungen. (Benutzereinstellungen gelten nicht als Konfigurationseinstellungen, da sie nicht vom Administrator gesteuert werden.)

Viele Anwendungen verwenden Datenbanken zur Speicherung und Isolation von Daten, wobei eine oder mehrere Zeilen einer Datenbank den Speicherplatz für einen bestimmten Benutzer darstellen können. Sie können in folgenden Fällen gegebenenfalls isolierte Speicherung anstelle einer Datenbank verwenden: bei geringer Benutzerzahl, bei beträchtlichem Verwaltungsaufwand durch Verwendung einer Datenbank oder wenn keine Datenbankfunktion zur Verfügung steht. Wenn eine Anwendung zudem Speicherplatz benötigt, der flexibler und komplexer ist als die Zeilen einer Datenbank, bietet isolierte Speicherung eine gute Alternative.

<a name="related_topics"></a>

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Isolationstypen](types-of-isolation.md)|Beschreibt verschiedene Isolationstypen.|
|[How to: Erhalten von Speichern für isolierten Speicher](how-to-obtain-stores-for-isolated-storage.md)|Stellt ein Beispiel für die Verwendung der <xref:System.IO.IsolatedStorage.IsolatedStorageFile> -Klasse bereit, um einen nach Benutzer und Assembly isolierten Speicher abzurufen.|
|[How to: Auflisten von Speichern für isolierten Speicher](how-to-enumerate-stores-for-isolated-storage.md)|Zeigt, wie mithilfe der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> -Methode die Größe des gesamten isolierten Speichers für den Benutzer berechnet wird.|
|[How to: Löschen von Speichern im isolierten Speicher](how-to-delete-stores-in-isolated-storage.md)|Zeigt, wie mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A?displayProperty=nameWithType> -Methode isolierte Speicher auf zwei unterschiedliche Arten gelöscht werden.|
|[How to: Vorhersehen von Speicherengpässen bei isoliertem Speicher](how-to-anticipate-out-of-space-conditions-with-isolated-storage.md)|Zeigt, wie der restliche Speicherplatz in einem isolierten Speicher ermittelt wird.|
|[How to: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher](how-to-create-files-and-directories-in-isolated-storage.md)|Einige Beispiele für das Erstellen von Dateien und Verzeichnissen in einem isolierten Speicher.|
|[How to: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher](how-to-find-existing-files-and-directories-in-isolated-storage.md)|Zeigt, wie die Verzeichnisstruktur und die Dateien bei isolierter Speicherung gelesen werden.|
|[How to: Lesen von bzw. Schreiben in Dateien im isolierten Speicher](how-to-read-and-write-to-files-in-isolated-storage.md)|Beispiel dafür, wie eine Zeichenfolge in eine isolierte Speicherdatei geschrieben und von dort gelesen wird.|
|[How to: Löschen von Dateien und Verzeichnissen in isoliertem Speicher](how-to-delete-files-and-directories-in-isolated-storage.md)|Beschreibt das Löschen von Dateien und Verzeichnissen der isolierten Speicherung.|
|[Datei- und Stream-E/A](index.md)|Erläutert, wie Sie einen synchronen und asynchronen Datei- und Datenstreamzugriff ausführen können.|

<a name="reference"></a>

## <a name="reference"></a>Referenz

- <xref:System.IO.IsolatedStorage.IsolatedStorage?displayProperty=nameWithType>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream?displayProperty=nameWithType>

- <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=nameWithType>
