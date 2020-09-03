---
title: Portieren einer Windows Forms-App zu .NET Core
description: Hier erfahren Sie, wie Sie eine .NET Framework Windows Forms-Anwendung zu .NET Core für Windows portieren.
author: Thraka
ms.author: adegeo
ms.date: 01/24/2020
ms.openlocfilehash: 71bd5740e1ea380fdde86328a5aed71fded64765
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118545"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a>Portieren einer Windows Forms-Desktop-App zu .NET Core 3.0

Dieser Artikel beschreibt, wie Sie Ihre Desktop-App auf Windows Forms-Basis von .NET Framework zu .NET Core 3.0 oder höher portieren. Das .NET Core 3.0 SDK bietet Unterstützung für Windows Forms-Anwendungen. Windows Forms ist immer noch ein ausschließlich für Windows bestimmtes Framework und kann nur unter Windows ausgeführt. In diesem Beispiel verwenden Sie das .NET Core SDK-CLI, um ein Projekt zu erstellen und zu verwalten.

In diesem Artikel werden verschiedene Namen zum Identifizieren der für die Migration verwendeten Dateitypen verwendet. Weil Ihre Dateien anders benannt werden, wenn Sie Ihr Projekt migrieren, gleichen Sie sie mit den unten aufgeführten Versionen ab:

| Datei | Beschreibung |
| ---- | ----------- |
| **MyApps.sln** | Der Name der Projektmappendatei. |
| **MyForms.csproj** | Der Name des zu portierenden .NET Framework Windows Forms-Projekts. |
| **MyFormsCore.csproj** | Der Name des neuen .NET Core-Projekts, das Sie erstellen. |
| **MyAppCore.exe** | Die ausführbare .NET Core-Windows Forms-App. |

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019, Version 16.5 oder höher](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=16) für beliebige Designerarbeiten, die Sie tätigen möchten Es wird empfohlen, ein Update auf die [neueste Version von Visual Studio](https://visualstudio.microsoft.com/vs/) durchzuführen.

  Installieren Sie die folgenden Visual Studio-Workloads:
  
  - .NET-Desktopentwicklung
  - Plattformübergreifende .NET Core-Entwicklung

- Ein funktionierendes Windows Forms-Projekt in einer Projektmappe, die ohne Probleme erstellt und ausgeführt wird.
- Ein in C# programmiertes Projekt.

> [!NOTE]
> .NET Core-Windows Forms-Projekte werden in Visual Studio 2019 und höheren Versionen unterstützt. Der .NET Core-Windows Forms-Designer wird ab Version 16.5 von Visual Studio 2019 unterstützt.
>
> Um den Designer zu aktivieren, wechseln Sie zu **Extras** > **Optionen** > **Umgebung** > **Vorschaufeatures**, und wählen Sie Option **Use the preview Windows Forms designer for .NET Core apps** (Vorschauversion des Windows Forms-Designers für .NET Core-Apps verwenden) aus.

### <a name="consider"></a>Consider

Wenn Sie eine .NET Framework Windows Forms-Anwendung portieren, müssen Sie ein paar Dinge berücksichtigen.

01. Überprüfen Sie, ob Ihre Anwendung ein guter Kandidat für die Migration ist.

    Verwenden Sie den [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md), um zu bestimmen, ob Ihr Projekt zu .NET Core 3.0 migriert werden kann. Wenn bei Ihrem Projekt Probleme mit .NET Core 3.0 vorliegen, können Sie diese Probleme mit dem Analyzer identifizieren.

01. Sie verwenden eine andere Version von Windows Forms.

    Als .NET Core 3.0 Preview 1 veröffentlicht wurde, wurde Windows Forms als Open Source auf GitHub zur Verfügung gestellt. Der Code für .NET Core-Windows Forms ist ein Fork der .NET Framework-Windows Forms-Codebasis. Es ist möglich, dass einige Unterschiede bestehen, und Ihre App nicht portiert wird.

01. Das [Windows Compatibility Pack][compat-pack] könnte Ihnen bei der Migration helfen.

    Einige APIs, die in .NET Framework verfügbar sind, sind nicht in .NET Core 3.0 verfügbar. Das [Windows Compatibility Pack][compat-pack] fügt viele dieser APIs hinzu und könnte zur Kompatibilität Ihrer Windows Forms-App mit .NET Core beitragen.

01. Aktualisieren Sie die NuGet-Pakete, die von Ihrem Projekt verwendet werden.

    Es hat sich bewährt, vor jeder Migration die neuesten Versionen der NuGet-Pakete zu verwenden. Wenn Ihre Anwendung auf NuGet-Pakete verweist, aktualisieren Sie sie auf die neueste Version. Stellen Sie sicher, dass die Anwendung erfolgreich erstellt wird. Wenn nach dem Upgrade Paketfehler auftreten, stufen Sie das Paket auf die neueste Version herab, die Ihren Code nicht beschädigt.

## <a name="create-a-new-sdk-project"></a>Erstellen eines neues SDK-Projekts

Das neue .NET Core 3.0-Projekt, das Sie erstellen, muss sich in einem anderen Verzeichnis als das .NET Framework-Projekt befinden. Wenn beide sich im gleichen Verzeichnis befinden, können Konflikte mit den Dateien auftreten, die im **obj**-Verzeichnis generiert werden. In diesem Beispiel erstellen wir ein Verzeichnis namens **MyFormsAppCore** im Verzeichnis **SolutionFolder**:

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

Als Nächstes müssen Sie das **MyFormsCore.csproj**-Projekt im Verzeichnis **MyFormsAppCore** erstellen. Sie können diese Datei manuell mit dem Text-Editor Ihrer Wahl erstellen. Fügen Sie folgende XML-Datei ein:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

Wenn Sie die Projektdatei nicht manuell erstellen möchten, können Sie Visual Studio oder .NET Core SDK zum Generieren des Projekts verwenden. Allerdings müssen Sie alle anderen von der Projektvorlage generierten Dateien mit Ausnahme der Projektdatei löschen. Um das SDK verwenden zu können, führen Sie den folgenden Befehl im Verzeichnis **SolutionFolder** aus:

```dotnetcli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

Nach der Erstellung von **MyFormsCore.csproj** sollte Ihre Verzeichnisstruktur wie folgt aussehen:

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

Fügen Sie das **MyFormsCore.csproj**-Projekt zu **MyApps.sln** hinzu, und verwenden Sie entweder Visual Studio oder die .NET Core-CLI aus dem **SolutionFolder**-Verzeichnis:

```dotnetcli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a>Beheben des Generierens von Assemblyinformationen

Windows Forms-Projekte, die mit .NET Framework erstellt wurden, enthalten eine `AssemblyInfo.cs`-Datei, die Assemblyattribute wie z.B. die Version der zu generierenden Assembly enthält. Projekte im SDK-Stil generieren diese Informationen auf Grundlage der SDK-Projektdatei automatisch für Sie. Beide Typen von „Assemblyinformationen“ zu haben verursacht einen Konflikt. Um dieses Problem zu lösen, deaktivieren Sie die automatische Generierung, sodass das Projekt Ihre vorhandene `AssemblyInfo.cs`-Datei verwenden muss.

Drei Einstellungen müssen dem `<PropertyGroup>`-Hauptknoten hinzufügt werden.

- **GenerateAssemblyInfo**\
Wenn Sie für diese Eigenschaft `false` festlegen, generiert sie die Assemblyattribute nicht. Dadurch wird der Konflikt mit der vorhandenen `AssemblyInfo.cs`-Datei aus dem .NET Framework-Projekt vermieden.

- **AssemblyName**\
Der Wert dieser Eigenschaft ist die binäre Ausgabe, die erstellt wird, wenn Sie kompilieren. Dem Namen muss keine Erweiterung hinzugefügt werden. Bei Verwendung von `MyCoreApp` entsteht beispielsweise `MyCoreApp.exe`.

- **RootNamespace**\
Der Standardnamespace, der von Ihrem Projekt verwendet wird. Dies sollte dem Standardnamespace des .NET Framework-Projekts entsprechen.

Fügen Sie diese drei Elemente dem `<PropertyGroup>`-Knoten in der `MyFormsCore.csproj`-Datei hinzu:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a>Hinzufügen von Quellcode

Momentan kompiliert das **MyFormsCore.csproj**-Projekt keinen Code. .NET Core-Projekte enthalten standardmäßig automatisch sämtlichen Quellcode im aktuellen Verzeichnis und allen untergeordneten Verzeichnissen. Sie müssen das Projekt so konfigurieren, dass Code aus dem .NET Framework-Projekt mit einem relativen Pfad einbezogen wird. Wenn Ihr .NET Framework-Projekt **RESX**-Dateien für Symbole und Ressourcen für Ihre Formulare verwendete, müssen Sie diese ebenfalls einbeziehen.

Fügen Sie den folgenden `<ItemGroup>`-Knoten Ihrem Projekt hinzu. Jede Anweisung enthält ein Dateiglobmuster, das untergeordnete Verzeichnisse enthält.

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

Alternativ können Sie einen `<Compile>`- oder `<EmbeddedResource>`-Eintrag für jede Datei in Ihrem .NET Framework-Projekt erstellen.

## <a name="add-nuget-packages"></a>Hinzufügen von NuGet-Paketen

Fügen Sie alle NuGet-Pakete, auf die das .NET Framework-Projekt verweist, dem .NET Core-Projekt hinzu.

In den meisten Fällen verfügt Ihre .NET Framework-Windows Forms-App über eine **packages.config**-Datei, die eine Liste aller NuGet-Pakete enthält, auf die Ihr Projekt verweist. Bestimmen Sie anhand dieser Liste, welche NuGet-Pakete Sie dem .NET Core-Projekt hinzufügen. Wenn das .NET Framework-Projekt z.B. auf die `MetroFramework`-, `MetroFramework.Design`- und `MetroFramework.Fonts`-NuGet-Pakete verwies, fügen Sie entweder mit Visual Studio oder der .NET Core-CLI vom **SolutionFolder**-Verzeichnis aus jede dem Projekt hinzu:

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

Die zuvor eingegebenen Befehle würden die folgenden NuGet-Verweise dem **MyFormsCore.csproj**-Projekt hinzufügen:

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a>Portieren von Steuerelementbibliotheken

Wenn Sie ein Windows Forms-Steuerelemente-Bibliotheksprojekt portieren müssen, sind die Anweisungen mit Ausnahme von ein paar Einstellungen mit dem Portieren eines .NET Framework-Windows Forms-App-Projekts identisch. Anstatt eine ausführbare Datei zu kompilieren, kompilieren Sie in eine Bibliothek. Der Unterschied zwischen dem ausführbaren Projekt und dem Bibliotheksprojekt ist abgesehen von den Pfaden für die Dateiglobs, die Ihren Quellcode enthalten, minimal.

Erweitern Sie mithilfe des vorherigen Schrittbeispiels, mit welchen Projekten und Dateien wir arbeiten.

| Datei | Beschreibung |
| ---- | ----------- |
| **MyApps.sln** | Der Name der Projektmappendatei. |
| **MyControls.csproj** | Der Name des zu portierenden .NET Framework Windows Forms-Steuerelemente-Projekts. |
| **MyControlsCore.csproj** | Der Name des neuen .NET Core-Bibliotheksprojekts, das Sie erstellen. |
| **MyCoreControls.dll** | Die .NET Core-Windows Forms-Steuerelemente-Bibliothek. |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

Betrachten Sie die Unterschiede zwischen dem `MyControlsCore.csproj`-Projekt und dem zuvor erstellten `MyFormsCore.csproj`-Projekt.

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

Die Projektdatei der .NET Core-Windows Forms-Steuerelemente-Bibliothek könnte z.B. folgendermaßen aussehen:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>

    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>

</Project>
```

Wie Sie sehen können, wurde der `<OutputType>`-Knoten entfernt, der standardmäßig anstelle einer ausführbaren Datei der Compiler zum Erstellen einer Bibliothek ist. `<AssemblyName>` und `<RootNamespace>` wurden geändert. Insbesondere der `<RootNamespace>` sollte mit dem Namespace der Windows Forms-Steuerelemente-Bibliothek übereinstimmen, die Sie portieren. Schließlich wurden die Knoten `<Compile>` und `<EmbeddedResource>` so angepasst, dass sie auf den Ordner der Windows Forms-Steuerelemente-Bibliothek verweisen, die Sie portieren.

Fügen Sie als Nächstes im .NET Core-Hauptprojekt **MyFormsCore.csproj** den Verweis auf die neue Windows Forms-Steuerelementebibliothek von .NET Core hinzu. Fügen Sie entweder mit Visual Studio oder der .NET Core-CLI einen Verweis vom **SolutionFolder**-Verzeichnis hinzu:

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

Der vorherige Befehl fügt dem **MyFormsCore.csproj**-Projekt Folgendes hinzu:

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="compilation-problems"></a>Kompilierungsprobleme

Wenn beim Kompilieren Ihrer Projekte Probleme auftreten, verwenden Sie möglicherweise einige nur für Windows geeignete APIs, die in .NET Framework, aber nicht in .NET Core verfügbar sind. Sie können versuchen, das [Windows Compatibility Pack][compat-pack] NuGet-Paket Ihrem Projekt hinzuzufügen. Dieses Paket kann nur auf Windows ausgeführt werden und fügt .NET Core- und .NET Standard-Projekten ungefähr 20.000 Windows-APIs hinzu.

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

Der vorherige Befehl fügt dem **MyFormsCore.csproj**-Projekt Folgendes hinzu:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="3.1.0" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a>Windows Forms-Designer

Wie in diesem Artikel ausführlich beschrieben unterstützt Visual Studio 2019 in .NET Framework-Projekten nur den Forms-Designer. Durch Erstellen eines parallelen .NET Core-Projekts können Sie Ihr Projekt mit .NET Core testen, während Sie das .NET Framework-Projekt zum Entwerfen von Formularen verwenden. Die Projektmappendatei enthält sowohl die .NET Framework- als auch die .NET Core-Projekte. Führen Sie das Hinzufügen und Entwerfen Ihrer Formulare und Steuerelemente im .NET Framework-Projekt durch, und auf der Basis der Dateiglobmuster, die wir den .NET Core-Projekten hinzugefügt haben, wird jede neue oder geänderte Datei automatisch in die .NET Core-Projekte einbezogen.

Sobald Visual Studio 2019 den Windows Forms-Designer unterstützt, können Sie den Inhalt Ihrer .NET Core-Projektdatei kopieren und in die .NET Framework-Projektdatei einfügen. Löschen Sie dann die Dateiglobmuster, die mit dem `<Source>`- und `<EmbeddedResource>`-Element hinzugefügt wurden. Stellen Sie die Pfade zu jedem von Ihrer App verwendeten Projektverweis wieder her. Damit wird effektiv das .NET Framework-Projekt zu einem .NET Core-Projekt heraufgestuft.

## <a name="next-steps"></a>Nächste Schritte

- Weitere Informationen finden Sie unter [Breaking Changes von .NET Framework zu .NET Core](../compatibility/fx-core.md).
- Lesen Sie mehr über das [Windows Compatibility Pack][compat-pack].
- Sehen Sie sich ein [Video zum Portieren](https://www.youtube.com/watch?v=upVQEUc_KwU) Ihres .NET Framework-Windows Forms-Projekts zu .NET Core an.

[compat-pack]: windows-compat-pack.md
