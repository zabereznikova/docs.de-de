---
title: .NET Core-Tools-Telemetrie
description: "Entdecken Sie die Telemetriefunktionen der .NET Core-Tools, die Informationen zur Verwendung für die Analyse erfassen."
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1816b9fbad1f671820c9f970674c8af2147a230e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-tools-telemetry"></a>.NET Core-Tools-Telemetrie

Die .NET Core-Tools beinhalten eine [Telemetriefunktion](https://github.com/dotnet/cli/pull/2145), die Benutzerinformationen sammelt. Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit sie verbessert werden können.

Die gesammelten Daten sind anonym und werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form für die Verwendung sowohl von Microsoft als auch von Community-Entwicklern veröffentlicht.

## <a name="scope"></a>Bereich

Der `dotnet`-Befehl wird zum Starten von sowohl Apps als auch .NET Core-Tools verwendet. Der `dotnet`-Befehl selbst sammelt keine Telemetrie. Es sind die .NET Core-Tools, die über den `dotnet`-Befehl ausgeführt werden, der Telemetrie sammelt.

.NET Core-Befehle (Telemetrie ist nicht aktiviert):

- `dotnet`
- `dotnet [path-to-app]`

.NET Core-Tools-[Befehle](index.md) (Telemetrie ist aktiviert), wie z.B.:

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="behavior"></a>Verhalten

Die Telemetriefunktion der .NET Core-Tools ist standardmäßig aktiviert. Sie können die Telemetriefunktion deaktivieren, indem Sie eine Umgebungsvariable DOTNET_CLI_TELEMETRY_OPTOUT (z.B. `export` unter Mac OS/Linux, `set` unter Windows) auf TRUE festlegen (z.B. „TRUE“, 1).

## <a name="data-points"></a>Datenpunkte

Die Funktion sammelt die folgenden Daten:

- Der Befehl, der verwendet wird (z.B. „build“, „restore“)
- Der ExitCode des Befehls
- Der für Testprojekte verwendete Test Runner
- Der Zeitstempel des Aufrufs
- Das verwendete Framework
- Ob Runtime-IDs im Knoten „Laufzeiten“ vorhanden sind
- Die verwendete CLI-Version

Die Funktion sammelt keine personenbezogenen Daten wie z.B. Benutzernamen oder E-Mails. Sie scannt Ihren Code nicht und extrahiert auch keine Daten auf Projektebene, die als sensibel gelten können, wie z.B. Name, Repository oder Autor (wenn Sie diese in Ihrer „project.json“-Datei festlegen). Wir würden gern wissen, wie die Tools verwendet werden, nicht was Sie mit den Tools erstellen. Wenn Sie bemerken, dass sensible Daten gesammelt werden, handelt es sich dabei um einen Fehler. Bitte [melden Sie ein Problem](https://github.com/dotnet/cli/issues), und der Fehler wird behoben.

## <a name="license"></a>Lizenz

Die Microsoft-Verteilung von .NET Core ist lizenziert mit den [Lizenzbedingungen der Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula). Dies umfasst den Abschnitt „Data“ (Daten), der nachstehend abgebildet ist, um die Telemetrie zu aktivieren.

[.NET NuGet-Pakete](https://www.nuget.org/profiles/dotnetframework) verwenden die gleiche Lizenz, aktivieren die Telemetrie jedoch nicht (siehe [Bereich](#scope) weiter oben).

> 2. Daten Die Software sammelt möglicherweise Daten zum Benutzer und zur Nutzung der Software und übermittelt diese an Microsoft. Microsoft kann diese Informationen verwenden, um seine Produkte und -Dienste zu verbessern. Weitere Informationen zur Datenerfassung und -verwendung finden Sie in der Hilfedokumentation und in den Datenschutzbestimmungen unter http://go.microsoft.com/fwlink/?LinkId=528096. Ihre Verwendung der Software gilt als Zustimmung zu diesen Verfahren.

## <a name="disclosure"></a>Offenlegung

In den .NET Core-Tools wird beim ersten Ausführen einer der Befehle (z.B. `dotnet restore`) der folgende Text angezeigt. Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung. Bei dieser Aktion wird außerdem Ihr NuGet-Cache mit den Bibliotheken im .NET Core SDK gefüllt, und Anfragen an NuGet.org (oder ein anderes NuGet-Feed) für diese Bibliotheken werden vermieden.

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.

Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience.
The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.

Configuring...
-------------------
A command is running to initially populate your local package cache, to improve restore speed and enable offline access. This command will take up to a minute to complete and will only happen once.
```

