---
title: Entwickeln von Bibliotheken mit der .NET-CLI
description: Hier erfahren Sie, wie Sie mithilfe der .NET-CLI .NET-Bibliotheken erstellen. Sie erstellen damit eine Bibliothek, die mehrere Frameworks unterstützt.
author: cartermp
ms.topic: how-to
ms.date: 12/14/2020
ms.openlocfilehash: 6f4c1feac7630a6a0250e4b0b39ef01152f5a400
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633675"
---
# <a name="develop-libraries-with-the-net-cli"></a>Entwickeln von Bibliotheken mit der .NET-CLI

In diesem Artikel wird erläutert, wie Sie mithilfe der .NET-CLI Bibliotheken für .NET schreiben. Die CLI bietet effiziente Funktionalität auf niedriger Stufe, die auf allen unterstützten Betriebssystemen funktioniert. Sie können trotzdem noch Bibliotheken mit Visual Studio erstellen. Wenn das Ihre bevorzugte Methode ist, finden Sie [weitere Informationen im Handbuch für Visual Studio](library-with-visual-studio.md).

## <a name="prerequisites"></a>Voraussetzungen

[Das .NET SDK und die -CLI](https://dotnet.microsoft.com/download) müssen auf Ihrem Computer installiert sein.

Für die Abschnitte dieses Dokuments, in denen es um .NET Framework-Versionen geht, muss das [.NET Framework](https://dotnet.microsoft.com) auf einem Windows-Computer installiert sein.

Wenn Sie ältere .NET Framework-Ziele unterstützen möchten, müssen Sie außerdem Pakete zum Festlegen von Zielversionen oder Entwicklerpakete von der Seite [.NET-Downloadarchive](https://dotnet.microsoft.com/download/archives) installieren. Weitere Informationen finden Sie in dieser Tabelle:

| .NET Framework-Version | Empfohlene Downloads                                       |
| ---------------------- | ------------------------------------------------------ |
| 4.6.1                  | Paket zur Festlegung von Zielversionen für .NET Framework 4.6.1                    |
| 4.6                    | Paket zur Festlegung von Zielversionen für .NET Framework 4.6                      |
| 4.5.2                  | .NET Framework 4.5.2 Entwicklerpaket                    |
| 4.5.1                  | .NET Framework 4.5.1 Entwicklerpaket                    |
| 4.5                    | Windows Software Development Kit für Windows 8         |
| 4,0                    | Windows SDK für Windows 7 und .NET Framework 4         |
| 2.0, 3.0 und 3.5      | .NET Framework 3.5 SP1-Runtime (oder Windows 8+-Version) |

## <a name="how-to-target-net-50-or-net-standard"></a>Verwenden von .NET 5.0 oder .NET Standard als Ziel

Sie können das Zielframework Ihres Projekts kontrollieren, indem Sie es zu Ihrer Projektdatei hinzufügen ( *.csproj* oder *.fsproj*). Informationen, die Sie bei der Entscheidung zwischen .NET 5.0 oder .NET Standard als Ziel unterstützen sollen, finden Sie unter [.NET 5 und .NET Standard](../../standard/net-standard.md#net-5-and-net-standard).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
  </PropertyGroup>
</Project>
```

Wenn Sie die .NET Framework-Version 4.0 oder niedriger als Ziel festlegen oder eine API verwenden möchten, die in .NET Framework verfügbar ist, aber nicht in .NET Standard (z. B. `System.Drawing`), lesen Sie die folgenden Abschnitte. In ihnen erfahren Sie, wie mehrere Ziele festlegt werden.

## <a name="how-to-target-net-framework"></a>Vorgehensweise: .NET Framework als Ziel

> [!NOTE]
> In diesen Anleitungen wird vorausgesetzt, dass .NET Framework auf Ihrem Computer installiert ist. Informationen zum Installieren von Abhängigkeiten finden Sie unter [Erforderliche Komponenten](#prerequisites).

Bedenken Sie, dass einige der hier verwendeten .NET Framework-Versionen nicht mehr unterstützt werden. Für weitere Informationen über nicht unterstütze Versionen, besuchen Sie [.NET Framework Support Lifecycle Policy FAQ (.NET Framework Support Lifecycle-Richtlinien FAQ)](https://support.microsoft.com/gp/framework_faq/en-us).

Wenn Sie so viele Entwickler und Projekte erreichen möchten wie möglich, verwenden Sie .NET Framework 4.0 als Baselineziel. Um .NET Framework als Ziel festzulegen, müssen Sie zunächst den richtigen Zielframeworkmoniker (Target Framework Moniker, TMF) auswählen, der der .NET Framework-Version entspricht, die Sie unterstützen möchten.

| .NET Framework-Version | TFM      |
| ---------------------- | -------- |
| .NET Framework 2.0     | `net20`  |
| .NET Framework 3.0     | `net30`  |
| .NET Framework 3.5     | `net35`  |
| .NET Framework 4.0     | `net40`  |
| .NET Framework 4.5     | `net45`  |
| .NET Framework 4.5.1   | `net451` |
| .NET Framework 4.5.2   | `net452` |
| .NET Framework 4.6     | `net46`  |
| .NET Framework 4.6.1   | `net461` |
| .NET Framework 4.6.2   | `net462` |
| .NET Framework 4.7     | `net47`  |
| .NET Framework 4.8     | `net48`  |

Sie fügen anschließend TFM in den `TargetFramework`-Abschnitt Ihrer Projektdatei ein. Hier sehen Sie zum Beispiel, wie Sie eine Bibliothek schreiben, die .NET Framework 4.0 als Ziel festlegt:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

Das war’s! Obwohl dieses Beispiel nur für .NET Framework 4 kompiliert wurde, können Sie die Bibliothek für neueren Versionen von .NET Framework verwenden.

## <a name="how-to-multitarget"></a>Vorgehensweise: Festlegen mehrerer Ziele

> [!NOTE]
> In den folgenden Anweisungen wird vorausgesetzt, dass .NET Framework auf Ihrem Computer installiert ist. Im Abschnitt [Erforderliche Komponenten](#prerequisites) finden Sie weitere Informationen darüber, welche Abhängigkeiten Sie installieren müssen, und wo Sie diese herunterladen können.

Sie müssen möglicherweise ältere Versionen des .NET Frameworks als Ziel festlegen, wenn Ihr Projekt sowohl das .NET Framework als auch .NET unterstützt. Wenn Sie neuere APIs und Sprachkonstrukte für die neueren Ziele verwenden möchten, verwenden Sie in diesem Szenario `#if`-Anweisungen in Ihrem Code. Sie müssen möglicherweise auch unterschiedliche Pakete und Abhängigkeiten für jede Zielplattform hinzufügen, um verschiedene APIs einzuschließen, die für jeden Fall benötigt werden.

Nehmen wir z.B. einmal an, dass Sie eine Bibliothek haben, die Netzwerkvorgänge über HTTP ausführt. Für .NET Standard und die .NET Framework-Versionen 4.5 oder höher können Sie die `HttpClient`-Klasse aus dem `System.Net.Http`-Namespace verwenden. Frühere Versionen von .NET Framework verfügen jedoch nicht über die Klasse `HttpClient`, daher können Sie für diese stattdessen die Klasse `WebClient` aus dem Namespace `System.Net` verwenden.

Ihre Projektdatei könnte also Folgendermaßen aussehen:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard2.0;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

Sie sehen hier drei große Veränderungen:

1. Der `TargetFramework`-Knoten wurde durch `TargetFrameworks` ersetzt, und drei TFMs werden darin dargestellt.
1. Es gibt einen `<ItemGroup>`-Knoten für das `net40`-Ziel, der einen .NET Framework-Verweis einbezieht.
1. Es gibt einen `<ItemGroup>`-Knoten für das `net45`-Ziel, der zwei .NET Framework-Verweise einbezieht.

Das Buildsystem beachtet die folgenden Präprozessorsymbole, die in `#if`-Anweisungen verwendet werden:

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

Hier sehen sie ein Beispiel, das die bedingte Kompilierung pro Ziel verwendet:

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "https://www.dotnetfoundation.org/";

            var uri = new Uri(url);

            string result = "";

            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET Framework 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "https://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

Wenn Sie diese Projekt mit `dotnet build` erstellen, bemerken Sie drei Verzeichnisse unter dem `bin/`-Ordner:

```
net40/
net45/
netstandard2.0/
```

Jedes dieser Verzeichnisse enthält die `.dll`-Dateien für jedes Ziel.

## <a name="how-to-test-libraries-on-net"></a>So testen Sie die Bibliotheken unter .NET

Es ist wichtig, über Plattformen hinweg testen zu können. Sie können entweder [xUnit](https://xunit.net/) oder MSTest standardmäßig verwenden. Beide sind bestens für Komponententests für Ihre Bibliothek unter .NET geeignet. Wie Sie Ihre Lösung mit Testprojekten einrichten, hängt von der [Struktur Ihrer Lösung](#structuring-a-solution) ab. Im folgenden Beispiel wird davon ausgegangen, dass Test- und Quellverzeichnisse im gleichen Verzeichnis auf oberster Ebene vorhanden sind.

> [!NOTE]
> Es werden einige [.NET-CLI](../tools/index.md)-Befehle verwendet. Weitere Informationen finden Sie unter [dotnet new](../tools/dotnet-new.md) und [dotnet sln](../tools/dotnet-sln.md).

1. Richten Sie Ihre Projektmappe ein. Verwenden Sie dazu folgende Befehle:

   ```dotnetcli
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   Dadurch werden Projekte erstellt, die zusammen in einer Projektmappe verknüpft werden. Ihr Verzeichnis für `SolutionWithSrcAndTest` sollte in etwa so aussehen:

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. Navigieren Sie zum Verzeichnis des Testprojekts, und fügen Sie einen Verweis zu `MyProject.Test` von `MyProject` hinzu.

   ```dotnetcli
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. So stellen Sie Pakete wieder her und erstellen Projekte:

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

1. Überprüfen Sie, ob xUnit durch Ausführung des `dotnet test`-Befehls ausgeführt wird. Wenn Sie MSTests verwenden möchten, dann muss stattdessen das MSTest-Konsolenausführungsprogramm ausgeführt werden.

Das war’s! Jetzt können Sie Ihre Bibliothek mithilfe der Befehlszeilentools plattformübergreifend testen. Nachdem jetzt alles eingerichtet ist, ist das weitere Testen Ihrer Bibliothek sehr einfach:

1. Nehmen Sie Änderungen an Ihrer Bibliothek vor.
1. Führen Sie mit dem Befehl `dotnet test` in Ihrem Testverzeichnis Tests über die Befehlszeile aus.

Der Code wird automatisch neu erstellt, wenn Sie den Befehl `dotnet test` aufrufen.

## <a name="how-to-use-multiple-projects"></a>So verwenden Sie mehrere Projekte

Eine häufige Anforderung an größere Bibliotheken ist es, Funktionalität in verschiedenen Projekten zu bieten.

Stellen Sie sich vor, Sie möchten eine Bibliothek erstellen, die in idiomatischem C# und F# genutzt werden kann. Das würde bedeuten, dass Benutzer Ihrer Bibliotheken diese auf eine Art nutzen, die natürlich für C# und F# ist. In C# z.B. könnten Sie die Bibliothek wie folgt nutzen:

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

In F# wird wie folgt formuliert:

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

Solche Nutzungsszenarios bedeuten, dass die APIs, auf die zugegriffen wird, eine andere Struktur für C# und F# haben müssen.  Eine gängige Methode, dies zu erreichen ist, die gesamte Logik einer Bibliothek in ein Kernprojekt zu zerlegen, in dem C# und F# Projekte die API-Schichten definieren, die das Kernprojekt aufrufen.  Im übrigen Abschnitt werden die folgenden Namen verwendet:

* **AwesomeLibrary.Core** – Ein Kernprojekt, das die gesamte Logik für die Bibliothek enthält
* **AwesomeLibrary.CSharp** – Ein Projekt mit öffentlichen APIs, die für den Gebrauch in C# vorgesehen sind
* **AwesomeLibrary.FSharp** – Ein Projekt mit öffentlichen APIs, die für den Gebrauch in F# vorgesehen sind

Sie können die folgenden Befehle in Ihrem Terminal ausführen, um die gleiche Struktur wie dieses Handbuch zu erstellen:

```dotnetcli
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang "F#"
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

Dadurch werden die drei oben genannten Projekte und eine Projektmappendatei hinzugefügt, die sie verknüpft. Durch das Erstellen der Projektmappendatei und das Verknüpfen der Projekte können Sie Projekte auf oberster Ebene wiederherstellen und erstellen.

### <a name="project-to-project-referencing"></a>Projekt-zu-Projekt-Verweise

Die beste Möglichkeit, auf ein Projekt zu verweisen, ist die Verwendung der .NET-CLI, um einen Projektverweis hinzuzufügen. Sie können den folgenden Befehl von den Projektverzeichnissen **AwesomeLibrary.CSharp** und **AwesomeLibrary.FSharp** ausführen:

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

Die Projektdateien für **AwesomeLibrary.CSharp** und **AwesomeLibrary.FSharp** verweisen nun auf **AwesomeLibrary.Core** als `ProjectReference`-Ziel.  Sie können dies überprüfen, indem Sie die Projektdateien prüfen und Folgendes darin sehen:

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

Sie können jeder Projektdatei diesen Abschnitt manuell hinzufügen, wenn Sie nicht die .NET-CLI verwenden möchten.

### <a name="structuring-a-solution"></a>Strukturieren einer Projektmappe

Ein weiterer wichtiger Aspekt bei mehreren Projekten in einer Projektmappe ist es, eine gute allgemeine Projektstruktur einzurichten. Sie können den Code beliebig organisieren, solange Sie jedes Projekt mit Ihrer Projektmappendatei mit `dotnet sln add` verknüpfen. Dadurch können Sie `dotnet restore` und `dotnet build` auf Projektmappenebene ausführen.
