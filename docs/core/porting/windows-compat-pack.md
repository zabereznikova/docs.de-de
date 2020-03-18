---
title: Verwenden des Windows Compatibility Pack zum Portieren auf .NET Core
description: Erfahren Sie mehr über Windows Compatibility Pack und die Verwendungsmöglichkeiten, um vorhandenen .NET Framework-Code in .NET Core zu portieren.
author: terrajobst
ms.date: 12/07/2018
ms.openlocfilehash: 91a653b2345d414c18ebdb6e8b7d6d49bbdbb83e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733607"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a>Verwenden des Windows Compatibility Pack zum Portieren auf .NET Core

Einige der beim Portieren von vorhandenem Code in .NET Core am häufigsten auftretenden Probleme sind Abhängigkeiten von APIs und Technologien, die nur in .NET Framework vorhanden sind. Das *Windows Compatibility Pack* bietet viele dieser Technologien, daher ist es viel einfacher, .NET Core-Anwendungen und .NET Standard-Bibliotheken zu erstellen.

Das Compatibility Pack ist eine logische [Erweiterung von .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support), die den API-Satz erheblich erhöht. Vorhandener Code wird mit fast allen Änderungen kompiliert. Damit das Versprechen („der API-Satz, den alle .NET-Implementierungen bereitstellen“) eingehalten werden kann, enthält .NET-Standard keine Technologien, die nicht auf allen Plattformen funktionieren können, wie z. B. die Registrierung, die Windows-Verwaltungsinstrumentation (WMI) oder APIs für die Reflektionsausgabe. Windows Compatibility Pack basiert auf .NET Standard und stellt diese Technologien bereit, die nur unter Windows verfügbar sind. Für Kunden, die zu .NET Core wechseln, aber Windows beibehalten möchten, ist dies zumindest ein nützlicher erster Schritt. In diesem Szenario wird die Migrationshürde durch die Möglichkeit beseitigt, ausschließlich Windows-Technologien zu verwenden.

## <a name="package-contents"></a>Paketinhalt

Windows Compatibility Pack wird über das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) bereitgestellt. Projekte, die .NET Core oder .NET Standard als Ziel verwenden, können darauf verweisen.

Es werden über 20.000 APIs aus folgenden Technologiebereichen bereitgestellt, darunter befinden sich sowohl Windows-APIs als auch plattformübergreifende APIs:

- Codepages
- CodeDom
- Konfiguration
- Verzeichnisdienste
- Zeichnung
- ODBC
- Berechtigungen
- Ports
- Windows-Zugriffssteuerungslisten (Access Control List, ACL)
- Windows Communication Foundation (WCF)
- Windows-Kryptografie
- Windows-EventLog
- Windows Management Instrumentation (WMI)
- Windows-Leistungsindikatoren
- Windows-Registrierung
- Zwischenspeichern von Windows-Runtime
- Windows-Dienste

Weitere Informationen finden Sie in den Angaben zum [Windows Compatibility Pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Erste Schritte

1. Machen Sie sich vor dem Portieren mit dem [Portiervorgang](index.md) vertraut.

2. Wenn Sie vorhandenen Code in .NET Core oder .NET Standard portieren, installieren Sie das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

   Wenn Sie Windows beibehalten möchten, können Sie sofort beginnen.

3. Wenn Sie die .NET Core-Anwendung oder die .NET Standard-Bibliothek unter Linux oder macOS ausführen möchten, verwenden Sie [API Analyzer](../../standard/analyzers/api-analyzer.md), um die Verwendungen der APIs zu ermitteln, die nicht plattformübergreifend funktionieren.

4. Entfernen Sie die Verwendungen dieser APIs, ersetzen Sie diese durch plattformübergreifende Alternativen, oder schützen Sie diese folgendermaßen mithilfe einer Plattformüberprüfung:

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

Eine Demo finden Sie in diesem [Channel 9 video of the Windows Compatibility Pack (Video von Channel 9 über Windows Compatibility Pack)](https://channel9.msdn.com/Events/Connect/2017/T123).
