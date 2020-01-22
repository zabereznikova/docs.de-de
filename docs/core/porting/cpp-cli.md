---
title: Migrieren von C++/CLI-Projekten in .NET Core
description: Informationen zum Portieren von C++/CLI-Projekten zu .NET Core
author: mjrousos
ms.date: 01/10/2020
ms.openlocfilehash: eb03f2a5ff42e8279fd3ebd6ee6fb6d955f6798d
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964860"
---
# <a name="how-to-port-a-ccli-project-to-net-core"></a>Portieren eines C++/CLI-Projekts zu .NET Core

Ab .NET Core 3.1 und Visual Studio 2019, Version 16.4 sind [C++/CLI-Projekte](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp) mit .NET Core kompatibel. Dadurch können Windows-Desktopanwendungen mit C++/CLI-Interopebenen zu .NET Core portiert werden. In diesem Artikel wird beschrieben, wie Sie C++/CLI-Projekte von .NET Framework zu .NET Core 3.1 portieren können.

## <a name="ccli-net-core-limitations"></a>C++/CLI-Einschränkungen für .NET Core

Im Vergleich zu anderen Sprachen gibt es einige wichtige Einschränkungen beim Portieren von C++/CLI-Projekten zu .NET Core:

* C++/CLI wird nur unter Windows für .NET Core unterstützt.
* C++/CLI-Projekte sind nicht mit .NET Standard kompatibel, sondern nur mit .NET Core (oder .NET Framework).
* C++/CLI-Projekte unterstützen nicht das neue SDK-Format für Projektdateien. Stattdessen wird für C++/CLI-Projekte das etablierte VCXPROJ-Dateiformat verwendet, auch wenn sie auf .NET Core ausgerichtet sind.
* C++/CLI-Projekte können nicht mit mehreren .NET-Plattformen kompatibel sein. Wenn Sie ein C++/CLI-Projekt erstellen möchten, dass sowohl unter .NET Framework als auch unter .NET Core verwendet werden kann, müssen Sie separate Projektdateien verwenden.
* .Net Core unterstützt keine `-clr:pure`- oder `-clr:safe`-Kompilierung, sondern nur die neue `-clr:netcore`-Option, die `-clr` für .NET Framework entspricht.

## <a name="port-a-ccli-project"></a>Portieren eines C++/CLI-Projekts

Wenn Sie ein C++/CLI-Projekt zu .NET Core portieren möchten, sollten Sie die folgenden Änderungen an der VCXPROJ-Datei vornehmen. Der Ablauf dieser Migration unterscheidet sich vom Ablauf bei anderen Projekttypen, da bei C++/CLI-Projekten keine SDK-Projektdateien verwendet werden.

1. Ersetzen Sie `<CLRSupport>true</CLRSupport>`-Eigenschaften durch `<CLRSupport>NetCore</CLRSupport>`. Diese Eigenschaft ist häufig in konfigurationsspezifischen Eigenschaftengruppen enthalten. Deshalb müssen Sie sie möglicherweise an mehreren Stellen ersetzen.
2. Ersetzen Sie `<TargetFrameworkVersion>`-Eigenschaften durch `<TargetFramework>netcoreapp3.1</TargetFramework>`.
3. Entfernen Sie alle .NET Framework-Verweise (z. B. `<Reference Include="System" />`). Wenn `<CLRSupport>NetCore</CLRSupport>` verwendet wird, wird automatisch auf .NET Core SDK-Assemblys verwiesen.
4. Aktualisieren Sie ggf. die API-Verwendung in CPP-Dateien, um APIs zu entfernen, die nicht für .NET Core verfügbar sind. Da es sich bei C++/CLI-Projekten in der Regel um relativ dünne Interopebenen handelt, müssen oft nur wenige Änderungen vorgenommen werden. [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) kann verwendet werden, um verwaltete Binärdateien und nicht unterstützte .NET-APIs zu ermitteln, die von C++/CLI-Binärdateien verwendet werden. Im [Leitfaden zum Portieren von Bibliotheken](./libraries.md#determine-portability) finden Sie Anweisungen dazu, wie Sie die Portabilität von Code bestimmen und Projekte aktualisieren können, sodass sie mit .NET Core-APIs verwendet werden können.

### <a name="wpf-and-windows-forms-usage"></a>Nutzung von WPF und Windows Forms

C++/CLI-Projekte für .NET Core können Windows Forms- und WPF-APIs verwenden. Damit Sie diese Windows-Desktop-APIs verwenden können, müssen Sie explizite Frameworkverweise auf die Benutzeroberflächenbibliotheken hinzufügen. SDK-Projekte, die Windows-Desktop-APIs verwenden, verweisen automatisch unter Verwendung des `Microsoft.NET.Sdk.WindowsDesktop` SDK auf die erforderlichen Frameworkbibliotheken. Da C++/CLI-Projekte nicht das SDK-Projektformat verwenden, müssen explizite Frameworkverweise hinzugefügt werden, wenn ein Projekt auf .NET Core ausgerichtet ist.

Damit Sie Windows Forms-APIs verwenden können, sollten Sie den folgenden Verweis zur VCXPROJ-Datei hinzufügen:

```xml
<!-- Reference all of Windows Forms -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WindowsForms" />
```

Damit Sie WPF-APIs verwenden können, sollten Sie den folgenden Verweis zur VCXPROJ-Datei hinzufügen:

```xml
<!-- Reference all of WPF -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WPF" />
```

Wenn Sie sowohl Windows Forms- als auch WPF-APIs verwenden möchten, fügen Sie den folgenden Verweis zu Ihrer VCXPROJ-Datei hinzu:

```xml
<!-- Reference the entirety of the Windows desktop framework:
     Windows Forms, WPF, and the types that provide integration between them -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App" />
```

Derzeit ist es nicht möglich, diese Verweise mithilfe des Verweis-Managers von Visual Studio hinzuzufügen. Aktualisieren Sie die Projektdatei stattdessen manuell. Sie können dieses Update in Visual Studio durchführen, indem Sie das Projekt entladen und anschließend die Projektdatei bearbeiten. Sie können auch einen anderen Editor verwenden, z. B. Visual Studio Code.

## <a name="build-without-msbuild"></a>Build ohne MSBuild

Es ist auch möglich, C++/CLI-Projekte ohne MSBuild zu erstellen. Führen Sie die folgenden Schritte aus, um direkt mithilfe der Dateien *cl.exe* und *link.exe* ein C++/CLI-Projekt für .NET Core zu erstellen:

1. Übergeben Sie bei der Kompilierung `-clr:netcore` an *cl.exe*.
2. Verweisen Sie auf erforderliche Referenzassemblys für .NET Core.
3. Geben Sie bei der Verknüpfung das Verzeichnis für den .NET Core-App-Host als `LibPath` an, damit die Datei *ijwhost.lib* gefunden werden kann.
4. Kopieren Sie *ijwhost.dll* aus dem Verzeichnis des .NET Core-App-Hosts in das Ausgabeverzeichnis des Projekts.
5. Stellen Sie sicher, dass für die erste Komponente der Anwendung, die verwalteten Code ausführt, eine [runtimeconfig.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)-Datei vorhanden ist. Wenn die Anwendung über einen verwalteten Einstiegspunkt verfügt, wird automatisch eine `runtime.config`-Datei erstellt und kopiert. Wenn die Anwendung allerdings über einen nativen Einstiegspunkt verfügt, müssen Sie eine `runtimeconfig.json`-Datei erstellen, damit die erste C++/CLI-Bibliothek die .NET Core-Runtime verwenden kann.

## <a name="known-issues"></a>Bekannte Probleme

Es gibt zwei bekannte Probleme, die bei der Arbeit mit C++/CLI-Projekten entstehen können, die auf .NET Core ausgerichtet sind.

* Ein WPF-Frameworkverweis in C++/CLI-Projekten für .NET Core löst derzeit einige unwesentliche Warnungen aus, weil der Import von Symbolen nicht möglich ist. Sie können diese Warnungen bedenkenlos ignorieren. Dieses Problem sollte bald behoben sein.
* Wenn die Anwendung über einen nativen Einstiegspunkt verfügt, benötigt die C++/CLI-Bibliothek, die zuerst verwalteten Code ausführt, eine [runtimeconfig.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)-Datei. Diese Konfigurationsdatei wird verwendet, wenn die .NET Core-Runtime gestartet wird. C++/CLI-Projekte erstellen nicht automatisch zur Buildzeit `runtimeconfig.json`-Dateien. Deshalb müssen diese Dateien manuell erstellt werden. Wenn eine C++/CLI-Bibliothek über einen verwalteten Einstiegspunkt aufgerufen wird, benötigt die C++/CLI-Bibliothek keine `runtimeconfig.json`-Datei, weil die Einstiegspunktassembly bereits über eine verfügt, die beim Start der Runtime verwendet wird. Nachfolgend finden Sie ein Beispiel für eine `runtimeconfig.json`-Datei. Weitere Informationen finden Sie in der [Spezifikation auf GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).

    ```json
    {
          "runtimeOptions": {
             "tfm": "netcoreapp3.1",
             "framework": {
                "name": "Microsoft.NETCore.App",
                "version": "3.1.0"
             }
          }
    }
    ```
