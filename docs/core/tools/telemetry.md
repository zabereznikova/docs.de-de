---
title: .NET Core SDK-Telemetrie
description: Entdecken Sie die Telemetriefeatures des .NET Core SDK, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden. Erfahren Sie außerdem, wie Sie diese Features deaktivieren können.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: 01376cabc4f59f64c59a78dcff061fb6ec11e3c3
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359232"
---
# <a name="net-core-sdk-telemetry"></a>.NET Core SDK-Telemetrie

Das [.NET Core SDK](index.md) umfasst ein Telemetriefeature, das Daten zur Nutzung und zu Ausnahmen erfasst, wenn die .NET Core-CLI abstürzt. Die .NET Core-CLI umfasst das .NET Core SDK und besteht aus mehreren Verben, die es Ihnen ermöglichen, Ihre .NET Core-Apps zu erstellen, zu testen und zu veröffentlichen. Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit diese verbessert werden können. Informationen zu Fehlern helfen dem Team, Probleme und Fehler zu beheben.

Die erfassten Daten sind anonym und werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form veröffentlicht.

## <a name="scope"></a>Bereich

`dotnet` hat zwei Funktionen: das Ausführen von Apps und das Ausführen von CLI-Befehlen. Es werden *keine Telemetriedaten erfasst*, wenn `dotnet` zum Starten einer Anwendung im folgenden Format verwendet wird:

- `dotnet [path-to-app].dll`

Es werden *Telemetrie erfasst*, wenn einer der [.NET Core-CLI-Befehle](index.md) verwendet wird, zum Beispiel:

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a>Deaktivierung der Telemetriefunktion

Die Telemetriefeature des .NET Core SDK ist standardmäßig aktiviert. Sie können das Telemetriefeature deaktivieren, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.

Ebenfalls wird ein einzelner Telemetrieeintrag auch vom .NET Core SDK-Installer gesendet, wenn eine Installation erfolgreich ist. Sie können zur Deaktivierung die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` festlegen, bevor Sie das .NET Core SDK installieren.

## <a name="disclosure"></a>Offenlegung

Das .NET Core SDK zeigt beim ersten Ausführen eines der [.NET Core-CLI-Befehle](index.md) (z.B. `dotnet build`) den folgenden Text an. Der Text kann abhängig von der von Ihnen ausgeführten Version des SDK leicht variieren. Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is anonymous. It is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

Um diese Meldung und die .NET Core-Willkommensmeldung zu deaktivieren, legen Sie die Umgebungsvariable `DOTNET_NOLOGO` auf `true` fest. Beachten Sie, dass mit dieser Variable nicht die Übertragung von Telemetriedaten deaktiviert wird.

## <a name="data-points"></a>Datenpunkte

Das Telemetriefeature erfasst keine personenbezogenen Daten wie Benutzernamen oder E-Mail-Adressen. Es überprüft Ihren Code nicht und extrahiert keine vertraulichen Daten auf Projektebene wie den Namen, das Repository oder den Autor. Die Daten werden mithilfe von [Azure Monitor](https://azure.microsoft.com/services/monitor/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) veröffentlicht.

Der Schutz Ihrer Privatsphäre ist uns wichtig. Wenn Sie vermuten, dass durch die Telemetrie vertrauliche Daten erfasst oder die Daten nicht sicher oder ordnungsgemäß verarbeitet werden, melden Sie ein Problem mit dem [dotnet/sdk](https://github.com/dotnet/sdk/issues)-Repository, oder senden Sie eine E-Mail an [dotnet@microsoft.com](mailto:dotnet@microsoft.com), damit dies überprüft wird.

Das Telemetriefeature erfasst die folgenden Daten:

| SDK-Versionen | Daten |
|--------------|------|
| Alle          | Den Zeitstempel des Aufrufs |
| Alle          | Den aufgerufenen Befehl (zum Beispiel „build“), ab Version 2.1 gehasht |
| Alle          | Die aus drei Oktetten bestehende IP-Adresse, die zur Bestimmung des geografischen Standorts verwendet wird |
| Alle          | Betriebssystem und Version |
| Alle          | Die Runtime-ID (RID), auf der das SDK ausgeführt wird |
| Alle          | Die Version des .NET Core SDK |
| Alle          | Telemetrieprofil: ein optionaler Wert, der nur bei der expliziten Benutzeranmeldung und intern bei Microsoft verwendet wird. |
| Mindestens Version 2.0        | Befehlsargumente und -optionen: Es werden mehrere Argumente und Optionen erfasst (keine beliebigen Zeichenfolgen). Weitere Informationen finden Sie unter [Gesammelte Optionen](#collected-options). Ab Version 2.1.300 gehasht |
| Mindestens Version 2.0         | Ob das SDK in einem Container ausgeführt wird. |
| Mindestens Version 2.0         | Zielframeworks (aus dem Ereignis `TargetFramework`), ab Version 2.1 gehasht |
| Mindestens Version 2.0         | Gehashte Media Access Control-Adresse: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer |
| Mindestens Version 2.0         | Das derzeitige Arbeitsverzeichnis mit Hash. |
| Mindestens Version 2.0         | Erfolgsbericht zur Installation mit gehashtem EXE-Dateinamen |
| Mindestens Version 2.1.300     | Kernelversion |
| Mindestens Version 2.1.300     | Libc-Version |
| Mindestens Version 3.0.100     | Gibt an, ob die Ausgabe umgeleitet wurde (TRUE oder FALSE) |
| Mindestens Version 3.0.100     | Bei einem CLI- bzw. SDK-Absturz der Ausnahmetyp und seine Stapelüberwachung (es ist nur CLI- bzw. SDK-Code in der gesendeten Stapelüberwachung enthalten) Weitere Informationen finden Sie unter [Gesammelte Telemetrie zu einer .NET Core-CLI- bzw. -SDK-Ausnahme](#net-core-clisdk-crash-exception-telemetry-collected). |

### <a name="collected-options"></a>Gesammelte Optionen

Bestimmte Befehle senden zusätzliche Daten. Eine Teilmenge der Befehle sendet das erste Argument:

| Befehl               | Erste Argumentdaten gesendet                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | Die Hilfe für den Befehl wird abgefragt.  |
| `dotnet new <arg>`    | Der Name der Vorlage (gehasht)             |
| `dotnet add <arg>`    | Die Wörter `package` oder `reference`      |
| `dotnet remove <arg>` | Die Wörter `package` oder `reference`      |
| `dotnet list <arg>`   | Die Wörter `package` oder `reference`      |
| `dotnet sln <arg>`    | Die Wörter `add`, `list` oder `remove`    |
| `dotnet nuget <arg>`  | Die Wörter `delete`, `locals` oder `push` |

Eine Teilmenge der Befehle sendet die ausgewählten Optionen, wenn diese zusammen mit ihren Werten verwendet werden:

| Option                  | Befehle                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | Alle Befehle                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`                  |
| `--framework`           | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest` |
| `--runtime`             | `dotnet build`, `dotnet publish`                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

Mit Ausnahme von `--verbosity` und `--sdk-package-version` werden alle anderen Werte ab dem .NET Core SDK, Version 2.1.100 gehasht.

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a>Gesammelte Telemetrie zu einer .NET Core-CLI- bzw. -SDK-Ausnahme

Wenn die .NET Core-CLI bzw. das -SDK abstürzt, sammelt es den Namen der Ausnahme und die Stapelüberwachung des CLI- bzw. SDK-Codes. Diese Informationen werden gesammelt, um Probleme zu bewerten und die Qualität des .NET Core SDK und der -CLI zu verbessern. Dieser Artikel enthält Informationen zu den von uns erfassten Daten. Außerdem erhalten Sie Tipps dazu, wie Benutzer, die ihre eigene Version des .NET Core SDK die unbeabsichtigte Offenlegung von personenbezogenen und vertraulichen Informationen vermeiden können.

### <a name="types-of-collected-data"></a>Gesammelte Datentypen

Die .NET Core-CLI erfasst nur Informationen zu CLI- bzw. SDK-Ausnahmen und nicht zu Ausnahmen in der Anwendung. Die erfassten Daten enthalten den Namen der Ausnahme und die Stapelüberwachung. Diese Stapelüberwachung besteht aus CLI- bzw. SDK-Code.

Im folgenden Beispiel sehen Sie, welche Art von Daten erfasst wird:

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-of-information"></a>Vermeiden der unbeabsichtigten Offenlegung von Informationen

.NET Core-Mitwirkende und jeder andere, der eine Version des .NET Core SDK ausführt, die Sie selbst erstellt haben, sollte den Pfad zu Ihrem SDK-Quellcode berücksichtigen. Wenn ein Absturz bei der Verwendung eines .NET Core SDK auftritt, bei dem es sich um einen benutzerdefinierten Debugbuild handelt oder der mit benutzerdefinierten Buildsymboldateien konfiguriert ist, wird der Pfad der SDK-Quelldatei auf dem Buildcomputer als Teil der Stapelüberwachung zwar erfasst, aber nicht gehasht.

Aus diesem Grund sollten benutzerdefinierte Builds des .NET Core SDK nicht in Verzeichnissen gespeichert werden, deren Pfadnamen persönliche oder vertrauliche Informationen offenlegen.

## <a name="see-also"></a>Siehe auch

- [Telemetriedaten der .NET Core-CLI](https://dotnet.microsoft.com/platform/telemetry)
- [Telemetrieverweisquelle (dotnet/sdk-Repository)](https://github.com/dotnet/sdk/tree/master/src/Cli/dotnet/Telemetry)
