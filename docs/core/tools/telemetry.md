---
title: .NET Core-Tools-Telemetrie
description: .NET Core
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 07/06/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: f2b312bb-f80b-4b0d-9101-93908f06a6fa
translationtype: Human Translation
ms.sourcegitcommit: c53c7d3b5733e15e066fd975bf3fa414ee96bbd1
ms.openlocfilehash: 4717b1f608051dc748ba3f1ceb94d6ddd94250bb

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

##<a name="behavior"></a>Verhalten

Die Telemetriefunktion der .NET Core-Tools ist standardmäßig aktiviert. Sie können die Telemetriefunktion deaktivieren, indem Sie eine Umgebungsvariable DOTNET_CLI_TELEMETRY_OPTOUT (z.B. `export` unter Mac OS/Linux, `set` unter Windows) auf TRUE festlegen (z.B. „TRUE“, 1).

##<a name="data-points"></a>Datenpunkte

Die Funktion sammelt die folgenden Daten:

- Der Befehl, der verwendet wird (z.B. „build“, „restore“)
- Der ExitCode des Befehls
- Der für Testprojekte verwendete Test Runner
- Der Zeitstempel des Aufrufs
- Das verwendete Framework
- Ob Runtime-IDs im Knoten „Laufzeiten“ vorhanden sind
- Die verwendete CLI-Version

Die Funktion sammelt keine personenbezogenen Daten wie z.B. Benutzernamen oder E-Mails. Sie scannt Ihren Code nicht und extrahiert auch keine Daten auf Projektebene, die als sensibel gelten können, wie z.B. Name, Repository oder Autor (wenn Sie diese in Ihrer „project.json“-Datei festlegen). Wir würden gern wissen, wie die Tools verwendet werden, nicht was Sie mit den Tools erstellen. Wenn Sie bemerken, dass sensible Daten gesammelt werden, handelt es sich dabei um einen Fehler. Bitte [melden Sie ein Problem](https://github.com/dotnet/cli/issues), und der Fehler wird behoben.

##<a name="license"></a>Lizenz

Die Microsoft-Verteilung von .NET Core ist lizenziert mit den [Lizenzbedingungen der Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula). Dies umfasst den Abschnitt „Data“ (Daten), der nachstehend abgebildet ist, um die Telemetrie zu aktivieren.

[.NET NuGet-Pakete](https://www.nuget.org/profiles/dotnetframework) verwenden die gleiche Lizenz, aktivieren die Telemetrie jedoch nicht (siehe [Bereich](#scope) weiter oben).

```text
2.      DATA.  The software may collect information about you and your use of
the software, and send that to Microsoft. Microsoft may use this information
to improve our products and services. You can learn more about data collection
and use in the help documentation and the privacy statement at
http://go.microsoft.com/fwlink/?LinkId=528096 . Your use of the software
operates as your consent to these practices.
```

## <a name="disclosure"></a>Offenlegung

In den .NET Core-Tools wird beim ersten Ausführen einer der Befehle (z.B. `dotnet restore`) der folgende Text angezeigt. Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung. Bei dieser Aktion wird außerdem Ihr NuGet-Cache mit den Bibliotheken im .NET Core SDK gefüllt, und Anfragen an NuGet.org (oder ein anderes NuGet-Feed) für diese Bibliotheken werden vermieden.

```text
Welcome to .NET Core!
---------------------

Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to
see available commands or go to https://aka.ms/dotnet-cli-docs.

Telemetry
---------

The .NET Core tools collect usage data in order to improve your experience.
The data is anonymous and does not include commandline arguments. The data is
collected by Microsoft and shared with the community.

You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT
environment variable to 1 using your favorite shell.

You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-
telemetry.

Configuring...
--------------

A command is running to initially populate your local package cache, to
improve restore speed and enable offline access. This command will take up to
a minute to complete and will only happen once. 
```



<!--HONumber=Nov16_HO1-->


