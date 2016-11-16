---
title: "Verwenden von MSBuild für die Erstellung von .NET Core-Projekten"
description: "Verwenden von MSBuild für die Erstellung von .NET Core-Projekten"
keywords: .NET, .NET Core
author: dsplaisted
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 13c66464-4f14-4db6-aa8b-06f25e7ba894
translationtype: Human Translation
ms.sourcegitcommit: a04755da6417bb28bad5f28a18ead9feeba2d957
ms.openlocfilehash: 5d37e78be88828d6c82777f96b6334903aecbe53

---

# <a name="using-msbuild-to-build-net-core-projects"></a>Verwenden von MSBuild für die Erstellung von .NET Core-Projekten

Die .NET Core-Tools werden [von „project.json“ zu MSBuild-basierten Projekten](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) verschoben.
Wir erwarten, dass die erste Version der .NET Core-Tools, die MSBuild verwenden, zusammen mit der nächsten Version von Visual Studio versendet wird.  Allerdings ist es möglich, MSBuild für .NET Core-Projekte schon heute zu nutzen, und diese Seite zeigt Ihnen, wie.

Es wird empfohlen, dass die meisten Personen, die heute .NET Core mit *neuen* Projekten verwenden, die Standardtoolumgebung mit „project.json“ verwenden, weil:

- MSBuild noch nicht viele der Vorteile von „project.json“ unterstützt
- ein Großteil der auf ASP.NET basierenden Tools derzeit nicht für MSBuild-Projekte funktioniert
- wenn wir die .NET Core-Tools freigeben, die MSBuild verwenden, es möglich sein wird, automatisch von „project.json“ zu MSBuild-Projekten zu konvertieren. 

Möglicherweise möchten Sie MSBuild verwenden, um .NET Core für vorhandene Projekte auszurichten, die bereits die MSBuild-Plattform verwenden, die Sie zu .NET Core portieren möchten, oder wenn Sie die Erweiterungen von MSBuild in Ihrem Build für Szenarios verwenden, die nicht gut für „project.json“-Projekte unterstützt werden.

## <a name="prerequisites"></a>Erforderliche Komponenten

- [Visual Studio 2015 Update 3](https://www.visualstudio.com/en-us/news/releasenotes/vs2015-update3-vs) oder höher
- [.NET Core-Tools für Visual Studio](https://www.visualstudio.com/downloads/download-visual-studio-vs)
- NuGet Visual Studio-Erweiterung [v3.5.0-beta](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) oder höher

## <a name="creating-a-library-targeting-net-core"></a>Erstellen einer Bibliothek, die auf .NET Core abzielt

1. Wählen Sie in der Visual Studio-Menüleiste **Datei** | **Neu** | **Projekt** aus, und wählen Sie anschließend **Klassenbibliothek (portabel)** aus.

  ![Neues Projekt](./media/target-dotnetcore-with-msbuild/new-project-dialog-class-library-portable.png)

2. Wählen Sie einen Namen und Speicherort für Ihre Projekte, und klicken Sie auf **OK**.

3. Das Dialogfeld „Portable Klassenbibliothek hinzufügen“ erscheint daraufhin.  Wählen Sie **.NET Framework 4.6** und **ASP.NET Core 1.0** als Ziele aus, und klicken Sie auf **OK**.

  ![Dialogfeld, das portable Ziele zeigt](./media/target-dotnetcore-with-msbuild/pcl-targets-dialog-net46-aspnetcore10.png)

4. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt, und wählen Sie **Eigenschaften** aus.
5. Klicken Sie auf der Registerkarte **Bibliothek** der Projekteigenschaften auf den Link **Target.NET Platform Standard**, und klicken Sie, wie im dargestellten Dialogfeld, auf **Ja**.
6. Öffnen Sie die Datei `project.json` in Ihrem Projekt, und führen Sie die folgenden Änderungen durch:
    - Ändern Sie die Versionsnummer des `NETStandard.Library`-Pakets zu `1.6.0` (dies ist die .NET Core 1.0-Version des Pakets).
    - Fügen Sie die nachstehende `imports`-Definition innerhalb der `netstandard1.6`-Frameworkdefinition hinzu.  Dadurch kann Ihr Projekt auf .NET Core-kompatible NuGet-Pakete verweisen, die noch nicht aktualisiert wurden, um auf .NET Standard abzuzielen.

        ```json
        "netstandard1.6": {
            "imports": [ "dnxcore50", "portable-net452" ]
        }
        ```

## <a name="creating-a-net-core-console-application"></a>Erstellen einer -NET Core-Konsolenanwendung
Das Erstellen einer Konsolenanwendung für .NET Core erfordert einige Anpassungen des MSBuild-Buildprozesses.  Sie können ein Beispielprojekt für eine .NET Core-Konsolenanwendung namens [CoreApp](https://github.com/dotnet/corefxlab/tree/master/samples/NetCoreSample/CoreApp) im [corefxlab](https://github.com/dotnet/corefxlab)-Repository finden.  Eine weitere gute Option ist es, mit der Vorlage [coretemplate](https://github.com/mellinoe/coretemplate) zu starten, die separate MSBuild-Ziele verwendet, um es für .NET Core zu verwenden, anstatt die Änderungen direkt in der Projektdatei abzulegen.  

Sie können auch damit beginnen, indem Sie ein Projekt in Visual Studio erstellen und es anpassen, sodass Sie es für .NET Core verwenden können.  Die folgenden Anweisungen zeigen die minimalen Schritte, die Sie befolgen müssen, damit all dies funktioniert.  Im Gegensatz zu [CoreApp](https://github.com/dotnet/corefxlab/tree/master/samples/NetCoreSample/CoreApp) oder [coretemplate](https://github.com/mellinoe/coretemplate) enthält ein Projekt, das auf diese Weise erstellt wurde, keine Konfigurationen für die Verwendung auf Linux und macOS.

1. Wählen Sie in der Visual Studio-Menüleiste **Datei** | **Neu** | **Projekt** aus, und wählen Sie anschließend **Konsolenanwendung** aus.
2. Wählen Sie einen Namen und Speicherort für Ihre Projekte, und klicken Sie auf **OK**.
3. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt, wählen Sie **Eigenschaften** aus, und wählen Sie anschließend die Registerkarte **Erstellen** aus.
4. Wählen Sie aus der Dropdownliste **Konfiguration** (ganz oben auf der Seite „Eigenschaften“) **Alle Konfigurationen** aus, und ändern Sie dann **Zielplattform** in **x64**.
5. Löschen Sie die Datei `app.config` aus dem Projekt.
6. Fügen Sie dem Projekt eine `project.json`-Datei mit dem folgenden Inhalt hinzu:

    ```json
    {
        "dependencies": {
            "Microsoft.NETCore.App": "1.0.0-rc2-3002702"
        },
        "runtimes": {
            "win7-x64": { },
            "ubuntu.14.04-x64": { },
            "osx.10.10-x64": { }
        },
        "frameworks": {
            "netcoreapp1.0": {
                "imports": [ "dnxcore50", "portable-net452" ]
            }
        }
    }
    ```

7. Klicken Sie im Projektmappenexplorer mit der rechten Maustaste auf das Projekt, wählen Sie **Projekt entladen** aus, klicken Sie dann erneut rechts, und wählen Sie **Bearbeiten _MyProj.csproj_** aus, und führen Sie die folgenden Änderungen durch:
    - Entfernen sie alle Standard-`Reference`-Elemente (auf `System`, `System.Core` usw.).
    - Fügen Sie die folgenden Eigenschaften der ersten `PropertyGroup` im Projekt hinzu:

        ```xml
        <TargetFrameworkIdentifier>.NETCoreApp</TargetFrameworkIdentifier>
        <TargetFrameworkVersion>v1.0</TargetFrameworkVersion>
        <BaseNuGetRuntimeIdentifier>win7</BaseNuGetRuntimeIdentifier>
        <NoStdLib>true</NoStdLib>
        <NoWarn>$(NoWarn);1701</NoWarn>
        ```

    - Fügen Sie Folgendes an das Dateiende hinzu (nach dem Importieren von `Microsoft.CSharp.Targets`):

        ```xml
        <PropertyGroup>
            <!-- We don't use any of MSBuild's resolution logic for resolving the framework, so just set these two
                    properties to any folder that exists to skip the GetReferenceAssemblyPaths task (not target) and
                    to prevent it from outputting a warning (MSB3644).
                -->
            <_TargetFrameworkDirectories>$(MSBuildThisFileDirectory)</_TargetFrameworkDirectories>
            <_FullFrameworkReferenceAssemblyPaths>$(MSBuildThisFileDirectory)</_FullFrameworkReferenceAssemblyPaths>

            <!-- MSBuild thinks all EXEs need binding redirects, not so for CoreCLR! -->
            <AutoUnifyAssemblyReferences>true</AutoUnifyAssemblyReferences>
            <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>

            <!-- Set up debug options to run with host, and to use the CoreCLR debug engine -->
            <StartAction>Program</StartAction>
            <StartProgram>$(TargetDir)dotnet.exe</StartProgram>
            <StartArguments>$(TargetPath)</StartArguments>
            <DebugEngines>{2E36F1D4-B23C-435D-AB41-18E608940038}</DebugEngines>
        </PropertyGroup>
        ```

    - Schließen Sie die CSPROJ-Datei, und laden Sie das Projekt erneut in Visual Studio.

8. Sie sollten Ihr Programm mit F5 in Visual Studio ausführen können, oder von der Befehlszeile aus im Ausgabeordner mit `dotnet MyApp.exe` 



<!--HONumber=Nov16_HO1-->


