---
title: Installutil.exe (Installer-Tool)
description: Verwenden des Installationstools „Installutil.exe“. Dieses Tool ermöglicht das Installieren und Deinstallieren von Serverressourcen durch Ausführen der Installationsprogrammkomponenten in bestimmten Assemblys.
ms.date: 03/30/2017
helpviewer_keywords:
- uninstalling server resources
- removing server resources
- status information for installation
- installation progress reports
- installing server resources
- Installer tool
- Installutil.exe
- files, Installer tool
- progress information for installation
- reporting installation progress
ms.assetid: 3f9d0533-f895-4897-b4ea-528284e0241d
ms.openlocfilehash: 042e5f64a7a863173db9c4e601d3152b0df46d97
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164449"
---
# <a name="installutilexe-installer-tool"></a>Installutil.exe (Installer-Tool)

Das Installationsprogrammtool ist ein Befehlszeilen-Hilfsprogramm, mit dem Sie Serverressourcen installieren und deinstallieren können, indem Sie die Komponenten des Installationsprogramms in angegebenen Assemblys ausführen. Dieses Tool funktioniert in Verbindung mit Klassen im <xref:System.Configuration.Install>-Namespace.

Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

Geben Sie an der Eingabeaufforderung Folgendes ein:

## <a name="syntax"></a>Syntax

```console
installutil [/u[ninstall]] [options] assembly [[options] assembly] ...
```

## <a name="parameters"></a>Parameter

|Argument|BESCHREIBUNG|
|--------------|-----------------|
|`assembly`|Der Dateiname der Assembly, in der die Installationsprogrammkomponenten ausgeführt werden sollen. Lassen Sie diesen Parameter aus, wenn Sie den starken Namen der Assembly angeben möchten, indem Sie die `/AssemblyName`-Option verwenden.|

<a name="options"></a>

## <a name="options"></a>Tastatur

|Option|BESCHREIBUNG|
|------------|-----------------|
|`/h[elp]`<br /><br /> - oder -<br /><br /> `/?`|Zeigt Befehlssyntax und Optionen für das Tool an.|
|`/help` *assembly*<br /><br /> - oder -<br /><br /> `/?` *assembly*|Zeigt zusätzliche Optionen, die von einzelnen Installationsprogrammen innerhalb der angegebenen Assembly erkannt werden, zusammen mit der Befehlssyntax und Optionen für "InstallUtil.exe" an. Mit dieser Option wird dem Hilfetext von "InstallUtil.exe" der von der <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>-Eigenschaft aller Installationsprogrammkomponenten zurückgegebene Text hinzugefügt.|
|`/AssemblyName` "*assemblyName*<br /><br /> ,Version=*major.minor.build.revision*<br /><br /> ,Culture=*locale*<br /><br /> ,PublicKeyToken=*publicKeyToken*"|Gibt den starken Namen einer Assembly an, die im globalen Assemblycache registriert werden muss. Der Assemblyname muss mit der Version, Kultur und dem öffentlichen Schlüsseltoken der Assembly vollständig qualifiziert werden. Der vollqualifizierte Name muss in Anführungszeichen stehen.<br /><br /> "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" ist beispielsweise ein vollqualifizierter Assemblyname.|
|`/InstallStateDir=[` *directoryName* `]`|Gibt das Verzeichnis der INSTALLSTATE-Datei an, die die Daten enthält, die verwendet werden, um die Assembly zu deinstallieren. Das Standardverzeichnis ist das Verzeichnis, das die Assembly enthält.|
|`/LogFile=`[*filename*]|Gibt den Namen der Protokolldatei an, in der der Installationsverlauf aufgezeichnet wird. Wenn die Option `/LogFile` fehlt, wird standardmäßig die Protokolldatei „*assemblyname*.InstallLog“ erstellt. Wenn *filename* nicht angegeben wird, wird keine Protokolldatei generiert.|
|`/LogToConsole`={`true`&#124;`false`}|Wenn der Wert `true` ist, wird die Ausgabe in der Konsole angezeigt. Ist der Wert `false` (Standardeinstellung), wird die Ausgabe in der Konsole unterdrückt.|
|`/ShowCallStack`|Gibt die Aufrufliste in der Protokolldatei aus, wenn im Verlauf der Installation eine Ausnahme auftritt.|
|`/u`[`ninstall`]|Deinstalliert die angegebenen Assemblys. Im Gegensatz zu den anderen Optionen wird `/u` auf alle Assemblys angewendet, wobei es unerheblich ist, an welcher Stelle in der Befehlszeile sich die Option befindet.|

<a name="cmdline"></a>

## <a name="additional-installer-options"></a>Zusätzliche Optionen des Installationsprogramms

Einzelne Installationsprogramme, die in einer Assembly verwendet werden, erkennen möglicherweise Optionen zusätzlich zu den im Abschnitt [Optionen](#options) aufgeführten. Um Informationen über diese Optionen zu erhalten, führen Sie "InstallUtil.exe" mit den Pfaden der Assemblys in der Befehlszeile zusammen mit der Option `/?` oder `/help` aus. Um diese Optionen anzugeben, geben Sie sie in der Befehlszeile zusammen mit den Optionen an, die von "InstallUtil.exe" erkannt werden.

> [!NOTE]
> Hilfetext für die Optionen, die von einzelnen Installationsprogrammkomponenten unterstützt werden, wird von der <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben. Auf die einzelnen Optionen, die in der Befehlszeile eingegeben wurden, kann über die <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType>-Eigenschaft programmgesteuert zugegriffen werden.

Alle Optionen und Befehlszeilenparameter werden in die Installationsprotokolldatei geschrieben. Wenn Sie jedoch den `/Password`-Parameter verwenden, der von einigen Installationsprogrammkomponenten erkannt wird, werden die Kennwortinformationen durch acht Sternchen (*) ersetzt und nicht in der Protokolldatei angezeigt.

> [!IMPORTANT]
> In einigen Fällen können an das Installationsprogramm übergebene Parameter vertrauliche oder personenbezogene Informationen enthalten, die standardmäßig in eine Nur-Text-Protokolldatei geschrieben werden. Um dieses Verhalten zu verhindern, können Sie die Protokolldatei unterdrücken, indem Sie `/LogFile=` (ohne *filename*-Argument) nach „Installutil.exe“ in der Befehlszeile angeben.

## <a name="remarks"></a>Hinweise

.NET Framework-Anwendungen bestehen aus herkömmlichen Programmdateien und zugeordneten Ressourcen wie Meldungswarteschlangen, Ereignisprotokollen und Leistungsindikatoren, die beim Bereitstellen der Anwendung erstellt werden müssen. Sie können die Installationsprogrammkomponenten einer Assembly verwenden, um diese Ressourcen beim Installieren der Anwendung zu erstellen und beim Deinstallieren der Anwendung zu entfernen. "Installutil.exe" erkennt diese Installationsprogrammkomponenten und führt sie aus.

Sie können mehrere Assemblys in einer Befehlszeile angeben. Jede Option, die vor einem Assemblynamen steht, bezieht sich auf die Installation dieser Assembly. Mit Ausnahme von `/u` und `/AssemblyName` sind Optionen kumulativ, können jedoch überschrieben werden. Das heißt, dass für eine Assembly angegebene Optionen auf alle nachfolgenden Assemblys angewendet werden, es sei denn, die Option wird mit einem neuen Wert angegeben.

Wenn Sie "Installutil.exe" ohne Angabe von Optionen für eine Assembly ausführen, werden die folgenden drei Dateien im Verzeichnis der Assembly platziert:

- "InstallUtil.InstallLog" - Enthält eine allgemeine Beschreibung des Installationsverlaufs.

- *assemblyname*.InstallLog: Enthält spezielle Informationen, die sich auf die Commitphase des Installationsverlaufs beziehen. Weitere Informationen zur Commitphase finden Sie in den Informationen zur <xref:System.Configuration.Install.Installer.Commit%2A>-Methode.

- *assemblyname*.InstallState: Enthält Daten für die Deinstallation der Assembly.

"Installutil.exe" verwendet Reflektion, um die angegebenen Assemblys zu überprüfen und alle <xref:System.Configuration.Install.Installer>-Typen zu suchen, bei denen das <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType>-Attribut auf `true` festgelegt wurde. Anschließend führt das Tool entweder die <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType>- oder die <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType>-Methode für jede Instanz des <xref:System.Configuration.Install.Installer>-Typs aus. "Installutil.exe" führt die Installation in Form einer Transaktion durch. D. h., wenn die Installation einer Assembly fehlschlägt, wird die Installation aller anderen Assemblys zurückgenommen. Die Deinstallation wird nicht als Transaktion durchgeführt.

Verzögert signierte Assemblys können mit "Installutil.exe" weder installiert noch deinstalliert werden, jedoch kann das Tool Assemblys mit starkem Namen installieren und deinstallieren.

Ab .NET Framework, Version 2.0, ist im Lieferumfang der 32-Bit-Version der Common Language Runtime (CLR) ausschließlich die 32-Bit-Version des Installationstools enthalten. Der Lieferumfang der 64-Bit-Version der Common Language Runtime umfasst hingegen sowohl eine 32-Bit-Version als auch eine 64-Bit-Version des Installationstools. Verwenden Sie in der 64-Bit-Common Language Runtime zur Installation von 32-Bit-Assemblys das 32-Bit-Installationstool und zur Installation von 64-Bit-Assemblys sowie von Microsoft Intermediate Language (MSIL)-Assemblys das 64-Bit-Installationstool. Beide Versionen des Installationstools verhalten sich gleich.

Sie können „Installutil.exe“ nicht verwenden, um einen Windows-Dienst bereitzustellen, der mit C++ erstellt wurde, da „Installutil.exe“ den eingebetteten nativen Code nicht erkennen kann, der vom C++-Compiler erzeugt wird. Wenn Sie versuchen, einen mit C++ erstellten Windows-Dienst mit "Installutil.exe" bereitzustellen, wird eine Ausnahme, z. B. <xref:System.BadImageFormatException>, ausgelöst. Um mit diesem Szenario zu arbeiten, verschieben Sie den Dienstknoten in ein C++-Modul, und schreiben Sie dann das Installationsprogrammobjekt in C# oder Visual Basic.

## <a name="examples"></a>Beispiele

Mit dem folgenden Befehl werden eine Beschreibung der Befehlssyntax und Optionen für "InstallUtil.exe" angezeigt.

```console
installutil /?
```

Mit dem folgenden Befehl werden eine Beschreibung der Befehlssyntax und Optionen für "InstallUtil.exe" angezeigt. Außerdem wird eine Beschreibung und eine Liste der von den Installationsprogrammkomponenten unterstützten Optionen in `myAssembly.exe` angezeigt, wenn Hilfetext der <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>-Eigenschaft des Installationsprogramms zugewiesen wurde.

```console
installutil /? myAssembly.exe
```

Der folgende Befehl führt die Installationsprogrammkomponenten in der Assembly `myAssembly.exe` aus.

```console
installutil myAssembly.exe
```

Der folgende Befehl führt die Installationsprogrammkomponenten in einer Assembly mithilfe des `/AssemblyName`-Schalters und eines vollqualifizierten Namens aus.

```console
installutil /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

Mit dem folgenden Befehl werden die Installationsprogrammkomponenten in einer Assembly, die vom Dateinamen angegeben wird, und in einer Assembly, die mit einem starken Namen angegeben wird, ausgeführt. Beachten Sie, dass alle mit Dateinamen angegebenen Assemblys vor Assemblys stehen müssen, die mit starkem Namen in der Befehlszeile angegeben werden, da die `/AssemblyName`-Option nicht überschrieben werden kann.

```console
installutil myAssembly.exe /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

Der folgende Befehl führt die Komponenten des Deinstallationsprogramms in der Assembly `myAssembly.exe` aus.

```console
installutil /u myAssembly.exe
```

Der folgende Befehl führt die Komponenten des Deinstallationsprogramms in den Assemblys `myAssembly1.exe` und `myAssembly2.exe` aus.

```console
installutil myAssembly1.exe /u myAssembly2.exe
```

Da die Position der `/u`-Option in der Befehlszeile nicht wichtig ist, entspricht diese dem folgenden Befehl.

```console
installutil /u myAssembly1.exe myAssembly2.exe
```

Der folgende Befehl führt die Installationsprogramme in der Assembly `myAssembly.exe` aus und gibt an, dass Verlaufsinformationen in `myLog.InstallLog` geschrieben werden.

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe
```

Der folgende Befehl führt die Installationsprogramme in der Assembly `myAssembly.exe` aus, gibt an, dass Statusinformationen in `myLog.InstallLog` geschrieben werden sollen, und verwendet die benutzerdefinierte `/reg`-Option des Installationsprogramms, um anzugeben, dass Updates in der Systemregistrierung vorgenommen werden sollen.

```console
installutil /LogFile=myLog.InstallLog /reg=true myAssembly.exe
```

Der folgende Befehl führt die Installationsprogramme in der Assembly `myAssembly.exe` aus, verwendet die benutzerdefinierte `/email`-Option des Installationsprogramms zur Angabe der E-Mail-Adresse des Benutzers und unterdrückt die Ausgabe in die Protokolldatei.

```console
installutil /LogFile= /email=admin@mycompany.com myAssembly.exe
```

Der folgende Befehl schreibt den Installationsverlauf für `myAssembly.exe` in `myLog.InstallLog` und den Verlauf für `myTestAssembly.exe` in `myTestLog.InstallLog`.

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe /LogFile=myTestLog.InstallLog myTestAssembly.exe
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Configuration.Install>
- [Extras](index.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
