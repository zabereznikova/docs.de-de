---
title: Portieren auf .NET Core - verwenden das Windows Compatibility Pack
description: "Erfahren Sie mehr über das Windows Compatibility Pack und wie können sie vorhandene .NET Framework-Code Portieren zu .NET Core"
keywords: ".NET, .NET Core, Windows, Kompatibilität"
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 5094baee77aba4d1e148f807d842a4a2d3405cf7
ms.sourcegitcommit: 86cf9b4c7104485a9870645705b9a1a4b6ca8e2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2017
---
# <a name="using-the-windows-compatibility-pack"></a>Verwenden das Windows Compatibility Pack

Eine der am häufigsten auftretenden Probleme, die Entwickler stoßen, wenn Sie ihren vorhandenen Code zu .NET Core Portieren ist, dass sie hängen von APIs und -Technologien, die nur in .NET Framework vorhanden sind. Die *Windows Compatibility Pack* wird zum Bereitstellen von viele dieser Technologien so, dass .NET Core-Anwendungen als auch .NET Standardbibliotheken erstellen größerer für vorhandenen Code gültig wird.

Dieses Paket ist eine logische [Erweiterung der Standard 2.0 .NET](../whats-new/index.md#api-changes-and-library-support) , dass erheblich erhöht API-Satz und den vorhandenen Code mit fast keine Änderungen kompiliert wird. Aber um das Versprechen der standardmäßigen .NET halten ("Es ist der Satz von APIs, die alle .NET Implementierungen bereitstellen"), dazu haben nicht Technologien, die auf allen Plattformen, wie z. B. der Registrierung, Windows Management Instrumentation (WMI), nicht funktionieren oder Reflektionsausgabe APIs.

Die *Windows Compatibility Pack* befindet sich auf .NET Standard und bietet Zugriff auf Technologien, die nur Windows sind. Er ist besonders nützlich für Kunden, die zu .NET Core jedoch Plan auf Windows als ersten Schritt bleiben verschoben werden soll. In diesem Szenario ist nicht nur-Windows-Technologien verwenden nur eine Migration Hürde mit 0 (null) architektonische Vorteile.

## <a name="package-contents"></a>Paketinhalt

Die *Windows Compatibility Pack* wird bereitgestellt, über das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) von Projekten für .NET Core "oder" Standard ".NET verwiesen werden kann.

Es stellt ca. 20.000 APIs, die nur für Windows als auch über Plattformen hinweg APIs aus den folgenden Technologiebereichen einschließlich:

* Codepages
* CodeDom
* Konfiguration
* Verzeichnisdienste
* Zeichnen
* ODBC
* Berechtigungen
* Ports
* Windows-Zugriffssteuerungslisten (ACL)
* Windows Communication Foundation (WCF)
* Windows-Kryptografie
* Windows-Ereignisprotokoll
* Windows Management Instrumentation (WMI)
* Windows-Leistungsindikatoren
* Windows-Registrierung
* Zwischenspeichern von Windows-Runtime
* Windows-Dienste

Weitere Informationen finden Sie unter der [des Compatibility Pack Spec](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Erste Schritte

1. Vor dem portieren, sollten Sie einen Blick auf die [Portieren Prozess](index.md).

2. Beim Portieren von vorhandenen Codes zu .NET Core "oder" Standard ".NET installiert das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

3. Wenn Sie auf Windows bleiben möchten, sind alle festgelegt werden.

4. Wenn Sie die .NET Core-Anwendung oder .NET Standardbibliothek unter Linux oder MacOS ausführen möchten, verwenden Sie die [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) Verwendung von APIs zu suchen, die plattformübergreifende funktioniert nicht mehr.

5. Entfernen Sie die Verwendung dieser APIs, plattformübergreifende alternativen ersetzt, oder schützen Sie sie mithilfe einer Platform-Überprüfung, wie:

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

Sehen Sie sich für eine Demo der [Channel 9-Video Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).

