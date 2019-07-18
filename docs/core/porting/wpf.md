---
title: Portieren einer WPF-App zu .NET Core 3.0
description: Erfahren Sie, wie Sie eine .NET Framework Windows Presentation Foundation-Anwendung zu .NET Core 3.0 für Windows portieren.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 5c7e3aca0a473abb831693244d1b194985f2ef7f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342205"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a>Vorgehensweise: Portieren einer WPF-Desktop-App zu .NET Core

Dieser Artikel beschreibt, wie Sie Ihre WPF-basierte (Windows Presentation Foundation) Desktop-App von .NET Framework zu .NET Core 3.0 portieren. Das .NET Core 3.0 SDK bietet Unterstützung für WPF-Anwendungen. WPF ist immer noch ein ausschließlich für Windows bestimmtes Framework und kann nur unter Windows ausgeführt werden. In diesem Beispiel verwenden Sie das .NET Core SDK-CLI, um ein Projekt zu erstellen und zu verwalten.

In diesem Artikel werden verschiedene Namen zum Identifizieren der für die Migration verwendeten Dateitypen verwendet. Weil Ihre Dateien anders benannt werden, wenn Sie Ihr Projekt migrieren, gleichen Sie sie mit den unten aufgeführten Versionen ab:

| Datei | Beschreibung |
| ---- | ----------- |
| **MyApps.sln** | Der Name der Projektmappendatei. |
| **MyWPF.csproj** | Der Name des zu portierenden .NET Framework WPF-Projekts. |
| **MyWPFCore.csproj** | Der Name des neuen .NET Core-Projekts, das Sie erstellen. |
| **MyAppCore.exe** | Die ausführbare Datei der .NET Core WPF-App. |

## <a name="prerequisites"></a>Erforderliche Komponenten

- [Visual Studio-2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) für alle Designerarbeiten, die Sie durchführen möchten.

  Installieren Sie die folgenden Visual Studio-Workloads:
  - .NET-Desktopentwicklung
  - Plattformübergreifende .NET-Entwicklung

- Ein funktionierendes WPF-Projekt in einer Projektmappe, die ohne Probleme erstellt und ausgeführt wird.
- Ihr Projekt muss in C# codiert werden. 
- Installieren Sie die neueste [.NET Core 3.0](https://aka.ms/netcore3download)-Vorschau.

>[!NOTE]
>**Visual Studio 2017** unterstützt .NET Core 3.0-Projekte nicht. **Visual Studio 2019** unterstützt .NET Core 3.0-Projekte, aber noch nicht den Visual Designer für .NET Core 3.0-WPF-Projekte. Ihre Projektmappe muss ein .NET-WPF-Projekt enthalten, das seine Dateien gemeinsam mit dem .NET Core-Projekt verwendet, um den Visual Designer verwenden zu können.

### <a name="consider"></a>Consider

Wenn Sie eine .NET Framework WPF-Anwendung portieren, müssen Sie ein paar Dinge berücksichtigen.

01. Überprüfen Sie, ob Ihre Anwendung ein guter Kandidat für die Migration ist.

    Verwenden Sie den [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md), um zu bestimmen, ob Ihr Projekt zu .NET Core 3.0 migriert werden kann. Wenn bei Ihrem Projekt Probleme mit .NET Core 3.0 vorliegen, können Sie diese Probleme mit dem Analyzer identifizieren.

01. Sie verwenden eine andere Version von WPF.

    Als .NET Core 3.0 Preview 1 veröffentlicht wurde, wurde WPF als Open Source auf GitHub zur Verfügung gestellt. Der Code für .NET Core-WPF ist ein Fork der .NET Framework-WPF-Codebasis. Es ist möglich, dass einige Unterschiede bestehen, und Ihre App nicht portiert wird.

01. Das [Windows Compatibility Pack][compat-pack] könnte Ihnen bei der Migration helfen.

    Einige APIs, die in .NET Framework verfügbar sind, sind nicht in .NET Core 3.0 verfügbar. Das [Windows Compatibility Pack][compat-pack] fügt viele dieser APIs hinzu und könnte die Kompatibilität Ihrer WPF-App mit .NET Core ermöglichen.

01. Aktualisieren Sie die NuGet-Pakete, die von Ihrem Projekt verwendet werden.

    Es hat sich bewährt, vor jeder Migration die neuesten Versionen der NuGet-Pakete zu verwenden. Wenn Ihre Anwendung auf NuGet-Pakete verweist, aktualisieren Sie sie auf die neueste Version. Stellen Sie sicher, dass die Anwendung erfolgreich erstellt wird. Wenn nach dem Upgrade Paketfehler auftreten, stufen Sie das Paket auf die neueste Version herab, die Ihren Code nicht beschädigt.

01. Visual Studio 2019 unterstützt noch nicht den WPF-Designer für .NET Core 3.0.

    Derzeit müssen Sie Ihre vorhandene .NET Framework-WPF-Projektdatei beibehalten, wenn Sie den WPF-Designer in Visual Studio verwenden möchten.

## <a name="create-a-new-sdk-project"></a>Erstellen eines neues SDK-Projekts

Das neue .NET Core 3.0-Projekt, das Sie erstellen, muss sich in einem anderen Verzeichnis als das .NET Framework-Projekt befinden. Wenn beide sich im gleichen Verzeichnis befinden, können Konflikte mit den Dateien auftreten, die im **obj**-Verzeichnis generiert werden. In diesem Beispiel erstellen Sie ein Verzeichnis namens **MyWPFAppCore** im Verzeichnis **SolutionFolder**:

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

Als Nächstes müssen Sie das **MyWPFCore.csproj**-Projekt im Verzeichnis **MyWPFAppCore** erstellen. Sie können diese Datei manuell mit dem Text-Editor Ihrer Wahl erstellen. Fügen Sie folgende XML-Datei ein:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

Wenn Sie die Projektdatei nicht manuell erstellen möchten, können Sie Visual Studio oder .NET Core SDK zum Generieren des Projekts verwenden. Allerdings müssen Sie alle anderen von der Projektvorlage generierten Dateien mit Ausnahme der Projektdatei löschen. Um das SDK verwenden zu können, führen Sie den folgenden Befehl im Verzeichnis **SolutionFolder** aus:

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

Nach der Erstellung von **MyWPFCore.csproj** sollte Ihre Verzeichnisstruktur wie folgt aussehen:

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

Verwenden Sie entweder Visual Studio oder die .NET Core-CLI aus dem Verzeichnis **SolutionFolder**, um das **MyWPFCore.csproj**-Projekt zu **MyApps.sln** hinzuzufügen:

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a>Beheben des Generierens von Assemblyinformationen

Windows Presentation Foundation-Projekte, die mit .NET Framework erstellt wurden, enthalten eine `AssemblyInfo.cs`-Datei, die Assemblyattribute wie z. B. die Version der zu generierenden Assembly enthält. Projekte im SDK-Stil generieren diese Informationen auf Grundlage der SDK-Projektdatei automatisch für Sie. Beide Typen von „Assemblyinformationen“ zu haben verursacht einen Konflikt. Um dieses Problem zu lösen, deaktivieren Sie die automatische Generierung, sodass das Projekt Ihre vorhandene `AssemblyInfo.cs`-Datei verwenden muss.

Drei Einstellungen müssen dem `<PropertyGroup>`-Hauptknoten hinzufügt werden. 

- **GenerateAssemblyInfo**\
Wenn Sie für diese Eigenschaft `false` festlegen, generiert sie die Assemblyattribute nicht. Dadurch wird der Konflikt mit der vorhandenen `AssemblyInfo.cs`-Datei aus dem .NET Framework-Projekt vermieden.

- **AssemblyName**\
Der Wert dieser Eigenschaft ist die binäre Ausgabe, die erstellt wird, wenn Sie kompilieren. Dem Namen muss keine Erweiterung hinzugefügt werden. Bei Verwendung von `MyCoreApp` entsteht beispielsweise `MyCoreApp.exe`.

- **RootNamespace**\
Der Standardnamespace, der von Ihrem Projekt verwendet wird. Dies sollte dem Standardnamespace des .NET Framework-Projekts entsprechen.

Fügen Sie diese drei Elemente dem `<PropertyGroup>`-Knoten in der `MyWPFCore.csproj`-Datei hinzu:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a>Hinzufügen von Quellcode
Momentan kompiliert das **MyWPFCore.csproj**-Projekt keinen Code. .NET Core-Projekte enthalten standardmäßig automatisch sämtlichen Quellcode im aktuellen Verzeichnis und allen untergeordneten Verzeichnissen. Sie müssen das Projekt so konfigurieren, dass Code aus dem .NET Framework-Projekt mit einem relativen Pfad einbezogen wird. Wenn Ihr .NET Framework-Projekt **RESX**-Dateien für Symbole und Ressourcen für Ihre Fenster und Steuerelemente verwendete, müssen Sie diese ebenfalls einbeziehen. 

Der erste `<ItemGroup>`-Knoten, den Sie zu Ihrem Projekt hinzufügen müssen, enthält die Datei **App.xaml**, die die von Ihrer App verwendete Startkonfiguration sowie die verwendeten Startressourcen darstellt. Die Datei **App.xaml** verfügt auch über die Begleitdatei **App.xaml.cs**, die jedoch automatisch in eine andere `<ItemGroup>` aufgenommen wird.

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

Fügen Sie als Nächstes den folgenden `<ItemGroup>`-Knoten zu Ihrem Projekt hinzu. Jede Anweisung enthält ein Dateiglobmuster, das untergeordnete Verzeichnisse enthält. Es enthält den Quellcode für Ihr Projekt, alle Einstellungsdateien und Ressourcen. Das Verzeichnis **obj** wird explizit ausgeschlossen.

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

Schließen Sie als Nächstes einen weiteren `<ItemGroup>`-Knoten ein, der einen `<Page>`-Eintrag für jede **XAML**-Datei in Ihrem Projekt enthält, mit Ausnahme der Datei **App.xaml**. Diese enthalten alle Fenster, Seiten und Ressourcen im **XAML**-Format. Sie können hier kein Globmuster verwenden und müssen für jede Datei einen Eintrag hinzufügen und den verwendeten `<Generator>` angeben.

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a>Hinzufügen von NuGet-Paketen

Fügen Sie alle NuGet-Pakete, auf die das .NET Framework-Projekt verweist, dem .NET Core-Projekt hinzu. 

In den meisten Fällen verfügt Ihre .NET Framework-WPF-App über eine **packages.config**-Datei, die eine Liste aller NuGet-Pakete enthält, auf die Ihr Projekt verweist. Bestimmen Sie anhand dieser Liste, welche NuGet-Pakete Sie dem .NET Core-Projekt hinzufügen. Wenn das .NET Framework-Projekt beispielsweise auf das NuGet-Paket `MahApps.Metro` verweist, fügen Sie es mithilfe von Visual Studio zum Projekt hinzu. Sie können den Paketverweis auch mit der .NET Core-CLI vom **SolutionFolder**-Verzeichnis hinzufügen:

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

Der vorherige Befehl würde dem **MyWPFCore.csproj**-Projekt den folgenden NuGet-Verweis hinzufügen:

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a>Probleme beim Kompilieren

Wenn beim Kompilieren Ihrer Projekte Probleme auftreten, verwenden Sie möglicherweise einige nur für Windows geeignete APIs, die in .NET Framework, aber nicht in .NET Core verfügbar sind. Sie können versuchen, das [Windows Compatibility Pack][ compat-pack] NuGet-Paket Ihrem Projekt hinzuzufügen. Dieses Paket kann nur auf Windows ausgeführt werden und fügt .NET Core- und .NET Standard-Projekten ungefähr 20.000 Windows-APIs hinzu.

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

Der vorherige Befehl fügt dem **MyWPFCore.csproj**-Projekt Folgendes hinzu:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a>WPF-Designer

Wie in diesem Artikel ausführlich beschrieben unterstützt Visual Studio 2019 in .NET Framework-Projekten nur den WPF-Designer. Durch Erstellen eines parallelen .NET Core-Projekts können Sie Ihr Projekt mit .NET Core testen, während Sie das .NET Framework-Projekt zum Entwerfen von Formularen verwenden. Die Projektmappendatei enthält sowohl die .NET Framework- als auch die .NET Core-Projekte. Führen Sie das Hinzufügen und Entwerfen Ihrer Formulare und Steuerelemente im .NET Framework-Projekt durch, und auf der Basis der Dateiglobmuster, die wir den .NET Core-Projekten hinzugefügt haben, wird jede neue oder geänderte Datei automatisch in die .NET Core-Projekte einbezogen.

Sobald Visual Studio 2019 den WPF-Designer unterstützt, können Sie den Inhalt Ihrer .NET Core-Projektdatei kopieren und in die .NET Framework-Projektdatei einfügen. Löschen Sie dann die Dateiglobmuster, die mit dem `<Source>`- und `<EmbeddedResource>`-Element hinzugefügt wurden. Stellen Sie die Pfade zu jedem von Ihrer App verwendeten Projektverweis wieder her. Damit wird effektiv das .NET Framework-Projekt zu einem .NET Core-Projekt heraufgestuft.
 
## <a name="next-steps"></a>Nächste Schritte

* Lesen Sie mehr über das [Windows Compatibility Pack][compat-pack].
* Sehen Sie sich ein [Video zum Portieren](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) Ihres .NET Framework-WPF-Projekts zu .NET Core an.

[compat-pack]: windows-compat-pack.md
