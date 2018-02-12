---
title: .NET Core-CLI-Tools-Telemetrie
description: "Entdecken Sie die Telemetriefunktionen der .NET Core-Tools, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden und wie sie deaktiviert werden."
keywords: .NET, .NET Core, telemetrie
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.workload:
- dotnetcore
ms.openlocfilehash: 9a78ec370fd53260f26a5d8c15707a5d611e458f
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="net-core-cli-tools-telemetry"></a>.NET Core-CLI-Tools-Telemetrie

Das [.NET Core-SDK](index.md) beinhaltet eine [Telemetriefunktion](https://github.com/dotnet/cli/pull/2145), die Benutzerinformationen sammelt. Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit sie verbessert werden können. Weitere Informationen finden Sie unter [What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core SDK Telemetrie gelernt haben)](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).

Die gesammelten Daten sind anonym und werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form für die Verwendung sowohl von Microsoft als auch von der Community veröffentlicht. 

## <a name="scope"></a>Bereich

Der `dotnet`-Befehl wird zum Starten von sowohl Apps als auch .NET Core-CLI verwendet. Der `dotnet`-Befehl selbst sammelt keine Telemetrie. Die .NET Core-CLI-Befehle, die vom Befehl `dotnet` ausgeführt werden, sammeln die Telemetrie.

Die Telemetrie wird durch die Verwendung des Befehls `dotnet` allein *nicht aktiviert*, wenn kein Befehl angefügt ist:

- `dotnet`
- `dotnet [path-to-app]`

Die Telemetrie wird *aktiviert*, wenn Sie die [.NET Core-CLI-Befehle](index.md) verwenden, zum Beispiel:

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`


## <a name="behavior"></a>Verhalten

Die Telemetriefunktion der .NET Core-CLI ist standardmäßig aktiviert. Deaktivieren Sie die Telemetriefunktion, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.

## <a name="data-points"></a>Datenpunkte

Die Funktion sammelt die folgenden Daten:

- Den Zeitstempel des Aufrufs&#8224;
- Den aufgerufenen Befehl (zum Beispiel „build“)&#8224;
- Die aus drei Oktetten bestehende IP-Adresse, die zur Bestimmung des geografischen Standorts verwendet wird
- `ExitCode` des Befehls
- Test Runner (für Testprojekte)
- Betriebssystem und Version&#8224;
- Ob Runtime-IDs im Knoten „Laufzeiten“ vorhanden sind
- Die .NET Core SDK-Version&#8224;

&#8224;Diese Metrik wird veröffentlicht.

Ab dem .NET Core SDK 2.0 werden neue Datenpunkte gesammelt:

- Argumente und Optionen des Befehls `dotnet`: nur bekannte Argumente und Optionen werden gesammelt (keine beliebigen Zeichenfolgen).
- Ob das SDK in einem Container ausgeführt wird.
- Zielframeworks.
- MAC-Adresse mit Hash: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer. Diese Metrik wird nicht veröffentlicht.
- Das derzeitige Arbeitsverzeichnis mit Hash.

Die Funktion sammelt keine Daten wie z.B. Benutzernamen oder E-Mail-Adressen. Es scannt Ihren Code nicht und extrahiert keine vertraulichen Daten auf Projektebene, zum Beispiel Name, Repository oder Autor. Die Daten werden mithilfe der Technologie [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) veröffentlicht.

Wir würden gern wissen, wie die Tools verwendet werden und ob sie gut funktionieren, nicht was Sie mit den Tools erstellen. Wenn Sie vermuten, dass durch die Telemetrie vertrauliche Daten gesammelt werden oder wir die Daten nicht sicher oder ordnungsgemäß behandeln, [file an issue in the dotnet/cli repo issues (melden Sie ein Problem in den dotnet- oder CLI-Repository-Problemen)](https://github.com/dotnet/cli/issues) zur Überprüfung.

## <a name="published-data"></a>Veröffentlichte Daten

Veröffentlichte Daten sind vierteljährlich verfügbar und werden unter [.NET Core SDK Usage Data (.NET Core SDK Nutzungsdaten)](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md) aufgelistet. Die Spalten der Datendatei sind:
- Zeitstempel
- Occurrences&#8224;
- Befehl
- Geography&#8225;
- OSFamily
- RuntimeID
- OSVersion
- SDKVersion

Die Spalte *Occurences* zeigt die Gesamtanzahl der Verwendung dieses Befehls für die Metriken dieser Reihe an diesem Tag an. 

Die Spalte *Geography* zeigt normalerweise den Namen eines Landes an. In einigen Fällen wird der Kontinent Antarktis in dieser Spalte angezeigt. Dies geschieht entweder, weil Experten .NET Core in der Antarktis verwenden oder wegen falschen Standortdaten.

### <a name="example"></a>Beispiel

| Zeitstempel      | Occurrences | Befehl | Geography | OSFamily | RuntimeID     | OSVersion | SDKVersion |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| 4/16/2017 0:00 | 8           | Ausführung     | Uganda    | Darwin   | osx.10.12-x64 | 10.12     | 1.0.1      |

### <a name="datasets"></a>Datasets

[2016 - Q3](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[2016 - Q4](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[2017 - Q1](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[2017 - Q2](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

Zusätzliche Datasets werden mithilfe des Standardformat für URLs bereitgestellt. Ersetzen Sie `<YEAR>` durch das Jahr und `<QUARTER>` durch das Quartal des Jahrs (verwenden Sie `1`, `2`, `3` oder `4`). Die Dateien befinden sich im Format einer durch Tabstopp getrennten Datei (*TSV*). 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a>Lizenz

Die Microsoft-Verteilung von .NET Core ist lizenziert mit den [Lizenzbedingungen der Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula). Diese Lizenz enthält den Abschnitt „DATA“ (Daten) zum Aktivieren von Telemetrie (siehe unten).

[.NET NuGet-Pakete](https://www.nuget.org/profiles/dotnetframework) verwenden die gleiche Lizenz, aktivieren die Telemetrie jedoch nicht (siehe [Bereich](#scope)).

> 2. Daten Die Software sammelt möglicherweise Daten zum Benutzer und zur Nutzung der Software und übermittelt diese an Microsoft. Microsoft kann diese Informationen verwenden, um seine Produkte und -Dienste zu verbessern. Weitere Informationen zur Datenerfassung und -verwendung finden Sie in der Hilfedokumentation und in den Datenschutzbestimmungen unter http://go.microsoft.com/fwlink/?LinkId=528096. Ihre Verwendung der Software gilt als Zustimmung zu diesen Verfahren.

## <a name="disclosure"></a>Offenlegung

In den .NET Core-CLI-Tools wird beim ersten Ausführen einer der Befehle (z.B. `dotnet restore`) der folgende Text angezeigt. Der Text kann abhängig von der von Ihnen ausgeführten Version des SDK leicht variieren. Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.
 
Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience. The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.
```

## <a name="see-also"></a>Siehe auch

[What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core-SDK-Telemetrie gelernt haben)](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)  
[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch) (Verweisquelle der Telemetrie (dotnet-/CLI-Repository, Version 2.0.0 Branch)](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry)   
[.NET Core SDK Usage Data (.NET Core SDK-Nutzungsdaten)](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
