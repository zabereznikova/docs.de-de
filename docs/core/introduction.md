---
title: '.NET: Einführung und Übersicht'
description: Hier erfahren Sie mehr über die kostenlose Open-Source-Entwicklungsplattform .NET zum Entwickeln von vielen verschiedenen Arten von Apps.
author: tdykstra
ms.date: 09/28/2020
ms.custom: updateeachrelease
ms.openlocfilehash: d008fbeabf58a3dddf1ee96fc655b6a685f8edfd
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223585"
---
# <a name="introduction-to-net"></a>Einführung in .NET

.NET ist eine kostenlose Open-Source-Entwicklungsplattform zum Entwickeln von vielen verschiedenen Arten von Apps. Beispiele:

* [Web-Apps, Web-APIs und Microservices](/aspnet/core/introduction-to-aspnet-core#recommended-learning-path)
* [serverlose Funktionen in der Cloud](/azure/azure-functions/functions-create-first-function-vs-code?pivots=programming-language-csharp)
* [Cloudnative Apps](../architecture/cloud-native/index.md)
* [Mobile Apps](https://dotnet.microsoft.com/learn/xamarin/hello-world-tutorial/intro)
* Desktop-Apps
  * [Windows WPF](/dotnet/desktop/wpf/)
  * [Windows Forms](/dotnet/desktop/winforms/)
  * [Universelle Windows-Plattform (UWP)](/windows/uwp/get-started/create-a-hello-world-app-xaml-universal)
* [Spiele](https://dotnet.microsoft.com/learn/games/unity-tutorial/intro)
* [Internet der Dinge (IoT)](https://dotnet.microsoft.com/apps/iot)
* [Maschinelles Lernen](../machine-learning/index.yml)
* [Konsolen-Apps](tutorials/with-visual-studio-code.md)
* [Windows-Dienste](/aspnet/core/host-and-deploy/windows-service)

Verwenden Sie [Klassenbibliotheken](../standard/class-libraries.md), um Funktionen für verschiedene Apps und App-Typen zu verwenden.

Mit .NET sind Ihr Code und Ihre Projektdateien einheitlich, unabhängig davon, welche Art von App Sie entwickeln. Sie haben mit jeder App Zugriff auf die gleiche Runtime, API und die gleichen Sprachfunktionen.

## <a name="cross-platform"></a>Plattformübergreifend

Sie können .NET-Apps für viele Betriebssysteme einschließlich der folgenden erstellen:

* Windows
* macOS
* Linux
* Android
* iOS
* tvOS
* watchOS

Dies sind die unterstützten Prozessorarchitekturen:

* x64
* x86
* ARM32
* ARM64

.NET ermöglicht die Verwendung von plattformspezifischen Funktionen wie Betriebssystem-APIs. Beispiele hierfür sind Windows Forms und WPF unter Windows sowie die nativen Bindungen mit jeder mobilen Plattform von Xamarin.

Weitere Information finden Sie unter [Unterstützte Lebenszyklusrichtlinien für das Betriebssystem](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) und [.NET Core-RID-Katalog](rid-catalog.md).

## <a name="open-source"></a>Open Source

.NET ist ein Open-Source-Angebot und verwendet [MIT- und Apache 2-Lizenzen](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT). .NET ist ein Projekt der [.NET Foundation](https://dotnetfoundation.org/).

Weitere Informationen finden Sie in der [Liste der Projektrepositorys auf github.com](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).

## <a name="support"></a>Support

.NET wird von Microsoft unter Windows, macOS und Linux unterstützt. Es wird regelmäßig jeden zweiten Dienstag des Monats im Hinblick auf Sicherheit und Qualität aktualisiert.

Binäre .NET-Distributionen von Microsoft werden auf von Microsoft verwalteten Servern in Azure entwickelt und getestet und entsprechen den Best Practices von Microsoft in Bezug auf Entwicklung und Sicherheit.

[Red Hat unterstützt .NET](https://developers.redhat.com/topics/dotnet/) unter Red Hat Enterprise Linux (RHEL). Red Hat und Microsoft arbeiten eng zusammen, um sicherzustellen, dass .NET Core ebenso auf RHEL funktioniert.

[Tizen unterstützt .NET](https://developer.tizen.org/development/training/.net-application) auf Tizen-Plattformen.

Weitere Informationen finden Sie unter [Releases und Unterstützung für .NET Core und .NET 5](releases-and-support.md).

## <a name="tools-and-productivity"></a>Tools und Produktivität

.NET bietet Ihnen eine Auswahl von Sprachen, integrierten Entwicklungsumgebungen (IDEs) und anderen Tools.

### <a name="programming-languages"></a>Programmiersprachen

.NET unterstützt drei Programmiersprachen:

* [C#](../csharp/index.yml)

  C# (Aussprache „C Sharp“) ist eine moderne, objektorientierte und typsichere Programmiersprache. C# hat seine Wurzeln in der C-Sprachenfamilie und ist Programmierern, die mit C, C++, Java und JavaScript arbeiten, sofort vertraut.

* [F#](../fsharp/index.yml)

  Die Sprache F# unterstützt funktionale, objektorientierte und imperative Programmiermodelle.

* [Visual Basic](../visual-basic/index.yml)

  Von allen .NET-Sprachen gleicht die Syntax von Visual Basic der menschlichen Sprache am meisten, was das Lernen vereinfacht. Im Gegensatz zu den Programmiersprachen C# und F#, für die Microsoft aktiv neue Features entwickelt, ist die Visual Basic-Sprache stabil. Visual Basic wird zwar nicht für Web-Apps, aber für Web-APIs unterstützt.

Im Folgenden finden Sie einige Funktionen, die die .NET-Sprachen unterstützen:

* [Typsicherheit](../standard/base-types/common-type-system.md)
* Typrückschluss: [C#](../csharp/programming-guide/types/index.md#specifying-types-in-variable-declarations), [F#](../fsharp/language-reference/type-inference.md), [Visual Basic](../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
* [Generische Typen](../standard/generics.md)
* [Delegaten](../standard/delegates-lambdas.md)
* [Lambdaausdrücke](../standard/delegates-lambdas.md)
* [Ereignisse](../standard/events/index.md)
* [Ausnahmen](../standard/exceptions/index.md)
* [Attribute](../standard/attributes/index.md)
* [Asynchroner Code](../standard/async.md)
* [Parallele Programmierung](../standard/parallel-programming/index.md)
* [Codeanalysetools](../fundamentals/code-analysis/overview.md)

### <a name="ides"></a>IDEs

Die integrierten Entwicklungsumgebungen für .NET umfassen Folgendes:

* [Visual Studio](https://visualstudio.microsoft.com/vs/)

  Die Ausführung ist nur unter Windows möglich. Durch die umfangreiche integrierte Funktionalität ist die Arbeit mit .NET möglich. Die Community-Edition ist für Studenten, Open-Source-Mitwirkende und Einzelpersonen kostenlos.

* [Visual Studio Code](https://code.visualstudio.com/)

  Die Ausführung unter Windows, macOS und Linux ist möglich. Kostenlos und Open Source. Es sind Erweiterungen für die Arbeit mit .NET-Sprachen verfügbar.

* [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/)

  Die Ausführung ist nur unter macOS möglich. Hiermit können .NET-Apps und Spiele für iOS, Android und das Web entwickelt werden.

* [GitHub Codespaces](https://github.com/features/codespaces)

  Dies ist eine Visual Studio Code-Onlineumgebung, die sich derzeit in der Betaversion befindet.

### <a name="sdk-and-runtimes"></a>SDK und Runtimes

Das [.NET SDK](sdk.md) besteht aus mehreren Bibliotheken und Tools zum Entwickeln und Ausführen von .NET-Anwendungen.

Wenn Sie [.NET herunterladen](https://dotnet.microsoft.com/download/dotnet-core/), können Sie das SDK oder eine *Runtime* wie die .NET- oder ASP.NET Core-Runtime auswählen. Installieren Sie die Runtime auf einem Computer, den Sie für die Ausführung von .NET-Apps vorbereiten möchten. Installieren Sie das SDK auf dem Computer, den Sie für das Entwickeln verwenden möchten. Wenn Sie das SDK herunterladen, erhalten Sie automatisch auch die Runtimes.

Beim Download des SDK werden die folgenden Komponenten heruntergeladen:

* [.NET-CLI:](tools/index.md) Sie können diese Befehlszeilentools für die lokale Entwicklung und Continuous-Integration-Skripts verwenden.
* `dotnet`-[Treiber](tools/index.md#driver) Dies ist ein CLI-Befehl, der frameworkabhängige Apps ausführt.
* [Roslyn](https://github.com/dotnet/roslyn)- und [F#](https://github.com/microsoft/visualfsharp)-Programmiersprachencompiler
* [MSBuild](/visualstudio/msbuild/msbuild)-Build-Engine
* [.NET-Runtime](#clr): Diese bietet ein Typsystem, eine Funktion zum Laden von Assemblys, einen Garbage Collector, native Interoperabilität und andere grundlegende Dienste.
* [Laufzeitbibliotheken](#runtime-libraries). Diese umfassen primitive Datentypen und grundlegende Hilfsprogramme.
* ASP.NET Core-Runtime: Diese bietet grundlegende Dienste für mit dem Internet verbundene Apps (z. B. Web-Apps, IoT-Apps und mobile Back-Ends).
* Desktopruntime: Hier sind grundlegende Dienste für Windows-Desktop-Apps einschließlich Windows Forms und WPF enthalten.

Weitere Informationen finden Sie in den folgenden Ressourcen:

* [.NET Core SDK – Übersicht](sdk.md)
* [Übersicht über die .NET Core-CLI](tools/index.md)
* [dotnet-Befehl](tools/dotnet.md)

### <a name="project-system-and-msbuild"></a>Projektsystem und MSBuild

Eine .NET-App wird mithilfe von [MSBuild](/visualstudio/msbuild/msbuild) aus Quellcode erstellt. Eine Projektdatei ( *.csproj* , *.fsproj* oder *.vbproj* ) gibt [Ziele](/visualstudio/msbuild/msbuild-targets) und zugeordnete [Aufgaben](/visualstudio/msbuild/msbuild-tasks) an, die für das Kompilieren, Packen und Veröffentlichen von Code zuständig sind. Es gibt SDK-Bezeichner, die auf Standardsammlungen von Zielen und Aufgaben verweisen. Die Verwendung dieser Bezeichner trägt dazu bei, dass Projektdateien klein und einfach zu verwenden sind. Dies ist beispielsweise eine Projektdatei für eine Konsolen-App:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

Dies ist ein Beispiel für eine Web-App:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

In diesen Beispielen gibt das `Sdk`-Attribut des Elements `Project` mehrere MSBuild-Ziele und -Aufgaben an, die das Projekt erstellen.  Das `TargetFramework`-Element gibt die .NET-Version an, von der die App abhängt. Sie können die Projektdatei bearbeiten, um zusätzliche Ziele und Aufgaben hinzuzufügen, die für das Projekt spezifisch sind.

Weitere Informationen finden Sie unter [.NET SDKs für Projekte](project-sdk/overview.md) und [Zielframeworks in Projekten im SDK-Format](../standard/frameworks.md).

### <a name="cicd"></a>CI/CD

MSBuild und die .NET-CLI können mit verschiedenen Continuous-Integration-Tools und -Umgebungen verwendet werden. Beispiele:

* [GitHub-Aktionen](https://github.com/features/actions)
* [Azure DevOps](/azure/devops/user-guide/what-is-azure-devops)
* [CAKE](https://cakebuild.net/)
* [FAKE](https://fake.build/)

Weitere Informationen finden Sie unter [Verwenden des .NET Core SDK und der zugehörigen Tools in Continuous Integration (CI)](tools/using-ci-with-cli.md).

### <a name="nuget"></a>NuGet

[NuGet](/nuget/what-is-nuget) ist ein Open-Source-Paket-Manager, der für .NET konzipiert ist. Ein NuGet-Paket ist eine *ZIP* -Datei mit der Erweiterung `.nupkg`, die kompilierten Code (DLLs), andere Dateien im Zusammenhang mit diesem Code und ein beschreibendes Manifest enthält, in dem Informationen wie die Versionsnummer des Pakets enthalten sind. Entwickler, die Code teilen möchten, erstellen und veröffentlichen Pakete auf [nuget.org](https://nuget.org) oder einem privaten Host. Entwickler, die freigegebenen Code verwenden möchten, fügen ein Paket zu ihrem Projekt hinzu und können dann die API abrufen, die vom Paket in ihrem Projektcode verfügbar gemacht wird.

Weitere Informationen finden Sie in der [NuGet-Dokumentation](/nuget/).

### <a name="net-interactive"></a>.NET interaktiv

.NET Interactive ist eine Gruppe von CLI-Tools und APIs, die Benutzern das Erstellen interaktiver Funktionen für das Web, Markdown und Notebooks ermöglicht.

Weitere Informationen finden Sie in den folgenden Ressourcen:

* [.NET-Tutorial im Browser](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1)
* [Verwenden von .NET-Notebooks mit Jupyter auf dem Computer](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md)
* [.NET Interactive-Dokumentation](https://github.com/dotnet/interactive/blob/main/docs/README.md)

## <a name="execution-models"></a>Ausführungsmodelle

.NET-Apps führen [verwalteten Code](../standard/managed-code.md) in einer Runtimeumgebung aus, die als Common Language Runtime (CLR) bezeichnet wird.

### <a name="clr"></a>CLR

Die [.NET-CLR](../standard/clr.md) ist eine plattformübergreifende Runtime, die die Unterstützung für Windows, macOS und Linux umfasst. Die CLR behandelt die Speicherbelegung und -verwaltung. Bei der CLR handelt es sich auch um einen virtuellen Computer, der nicht nur Apps ausführt, sondern auch mithilfe eines Just-In-Time-Compilers (JIT) Code generiert und kompiliert.

Weitere Informationen finden Sie unter [Übersicht: Common Language Runtime (CLR)](../standard/clr.md).

### <a name="jit-compiler-and-il"></a>JIT-Compiler und IL

.NET-Sprachen auf höherer Ebene, z.B. C#, werden zu einem hardwareunabhängigen Anweisungssatz kompiliert, der als Zwischensprache (Intermediate Language, IL) bezeichnet wird. Wenn eine App ausgeführt wird, übersetzt der JIT-Compiler Zwischensprache (IL) in einen Computercode, die der Prozessor versteht. Die JIT-Kompilierung erfolgt auf dem gleichen Computer, auf dem auch der Code ausgeführt wird.

Da die JIT-Kompilierung während der Ausführung der Anwendung stattfindet, ist die Kompilierzeit Teil der Laufzeit. Daher müssen JIT-Compiler eine Balance zwischen der Zeit, die in die Optimierung des Codes investiert werden kann, und den Ersparnissen finden, die der resultierende Code erzeugt. Ein JIT-Compiler kennt jedoch die tatsächliche Hardware und befreit die Entwickler davon, verschiedene Implementierungen für verschiedene Plattformen bereitstellen zu müssen.

Der .NET-JIT-Compiler kann eine *mehrstufige Kompilierung* durchführen, was bedeutet, dass einzelne Methoden zur Laufzeit erneut kompiliert werden können. Dieses Feature ermöglicht eine schnelle Kompilierung, während immer noch eine stark optimierte Version des Codes für häufig verwendete Methoden erstellt werden kann.

Weitere Informationen finden Sie unter [Verwalteter Ausführungsprozess](../standard/managed-execution-process.md) und [Mehrstufige Kompilierung](whats-new/dotnet-core-3-0.md#tiered-compilation).

### <a name="aot-compiler"></a>AOT-Compiler

Der JIT-Compiler ist die Standardeinstellung für die meisten .NET-Workloads, aber .NET bietet zwei Formen der Ahead-of-Time-Kompilierung (AOT):

* Einige Szenarios erfordern eine vollständige AOT-Kompilierung. Ein Beispiel hierfür ist [iOS](/xamarin/ios/).
* In anderen Szenarios wird für einen Großteil des App-Codes eine AOT-Kompilierung, teilweise aber auch eine JIT-Kompilierung durchgeführt. Einige Codemuster eignen sich nicht für die AOT-Kompilierung (z. B. Generics). Ein Beispiel für diese Form der AOT-Kompilierung ist die [ReadyToRun](whats-new/dotnet-core-3-0.md#readytorun-images)-Veröffentlichungsoption. Diese Form bietet nur die Vorteile und keine Nachteile der AOT-Kompilierung.

### <a name="automatic-memory-management"></a>Automatische Speicherverwaltung

Der *Garbage Collector* (GC) verwaltet die Belegung und Freigabe von Arbeitsspeicher für Anwendungen. Jedes Mal, wenn Ihr Code ein neues Objekt erstellt, belegt die CLR Speicher für das Objekt aus dem [verwalteten Heap](../standard/garbage-collection/fundamentals.md#the-managed-heap). Solange ein Adressbereich im verwalteten Heap verfügbar ist, reserviert die Laufzeit Arbeitsspeicher für neue Objekte. Wenn nicht genügend freier Arbeitsspeicher übrig bleibt, sucht der GC nach Objekten im verwalteten Heap, die nicht mehr von der Anwendung verwendet werden. Anschließend wird dieser Arbeitsspeicher freigegeben.

Der GC ist nur einer der CLR-Dienste, die bei der Sicherstellung der *Speichersicherheit* helfen. Ein Programm ist speichersicher, wenn es nur auf belegten Speicherplatz zugreift. Beispielsweise stellt die Runtime sicher, dass eine App nicht auf belegten Arbeitsspeicher außerhalb des zulässigen Bereichs eines Arrays zugreift.

Weitere Informationen finden Sie unter [Automatic Memory Management](../standard/automatic-memory-management.md) und [Grundlagen der Garbage Collection](../standard/garbage-collection/fundamentals.md).

### <a name="working-with-unmanaged-resources"></a>Arbeiten mit nicht verwalteten Ressourcen

Manchmal muss Code auf *nicht verwaltete Ressourcen* verweisen. Nicht verwaltete Ressourcen sind Ressourcen, die nicht automatisch von der .NET-Runtime verwaltet werden. Ein Dateihandle ist z.B. eine nicht verwaltete Ressource. Ein <xref:System.IO.FileStream>-Objekt ist ein verwaltetes Objekt, aber es verweist auf ein Dateihandle, das nicht verwaltet ist. Wenn Sie mit <xref:System.IO.FileStream> fertig sind, müssen Sie das Dateihandle explizit freigeben.

In .NET implementieren Objekte, die auf nicht verwaltete Ressourcen verweisen, die <xref:System.IDisposable>-Schnittstelle. Wenn Sie mit dem Objekt fertig sind, können Sie die <xref:System.IDisposable.Dispose>-Methode des Objekts aufrufen, die für die Freigabe nicht verwalteter Ressourcen zuständig ist. Die .NET-Sprachen bieten eine bequeme `using`-Anweisung ([C#](../csharp/language-reference/keywords/using.md), [F#](../fsharp/language-reference/resource-management-the-use-keyword.md), [VB](../visual-basic/language-reference/statements/using-statement.md)), die sicherstellt, dass die `Dispose`-Methode aufgerufen wird.

Weitere Informationen finden Sie unter [Bereinigen von nicht verwalteten Ressourcen](../standard/garbage-collection/unmanaged.md).

## <a name="deployment-models"></a>Bereitstellungsmodelle

.NET-Apps können in zwei verschiedenen Modi veröffentlicht werden:

* Bei der Veröffentlichung als *eigenständige* App wird eine ausführbare Datei erstellt, die die [.NET-Runtime](#sdk-and-runtimes) und [-Bibliotheken](#runtime-libraries) sowie die Anwendung und zugehörige Abhängigkeiten enthält. Benutzer der Anwendung können diese auf einem Computer ausführen, auf dem die .NET-Runtime nicht installiert ist. Eigenständige Apps sind plattformspezifisch und können optional mithilfe einer Form der [AOT-Kompilierung](#aot-compiler) veröffentlicht werden.

* Bei der Veröffentlichung als *frameworkabhängige* App werden eine ausführbare Datei und Binärdateien ( *DLL* -Dateien) erstellt, die nur die Anwendung selbst und ihre Abhängigkeiten enthalten. Benutzer der Anwendung müssen die [.NET-Runtime](#sdk-and-runtimes) separat installieren. Die ausführbare Datei ist plattformspezifisch, die *DLL-Dateien* der frameworkabhängigen Anwendungen gelten aber als plattformübergreifend verwendbar.

  Sie können parallel mehrere Versionen der Runtime installieren, um frameworkabhängige Apps auszuführen, die auf verschiedene Runtimeversionen abzielen. Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../standard/frameworks.md).

Ausführbare Dateien werden für bestimmte Zielplattformen erstellt, die Sie mit einem [Runtimebezeichner (RID)](rid-catalog.md) angeben.

Weitere Informationen finden Sie unter [Übersicht über die .NET Core-Anwendungsveröffentlichung](deploying/index.md) und [Einführung zu .NET und Docker](docker/introduction.md).

## <a name="runtime-libraries"></a>Runtimebibliotheken

.NET verfügt über viele verschiedene Standardklassenbibliotheken. Die wichtigsten davon werden als Basisklassenbibliothek (BCL) bezeichnet. Zusammen werden sie als Runtimebibliotheken oder Frameworkbibliotheken bezeichnet. Diese Bibliotheken bieten Implementierungen für viele allgemeine und workloadspezifische Typen und Hilfsprogrammfunktionen.

Im Folgenden finden Sie einige Beispiele für Typen, die in den Runtimebibliotheken definiert sind:

* Primitive Typen wie <xref:System.Boolean?displayProperty=nameWithType> und <xref:System.Int32?displayProperty=nameWithType>.
* Sammlungen, z.B. <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> und <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
* Datentypen, z. B. <xref:System.Data.DataSet?displayProperty=nameWithType> und <xref:System.Data.DataTable?displayProperty=nameWithType>
* Netzwerkhilfsprogrammtypen, z. B. <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
* [Datei- und Stream-E/A](../standard/io/index.md)-Hilfsprogrammtypen, z. B. <xref:System.IO.FileStream?displayProperty=nameWithType> und <xref:System.IO.TextWriter?displayProperty=nameWithType>
* [Serialisierungshilfsprogrammtypen](../standard/serialization/index.md), z. B. <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> und <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
* Hochleistungstypen, z. B. <xref:System.Span%601?displayProperty=nameWithType>, <xref:System.Numerics.Vector?displayProperty=nameWithType> und [Pipelines](../standard/io/pipelines.md).

Weitere Information finden Sie unter [Frameworkbibliotheken](../standard/framework-libraries.md) und [Quellcode für die Bibliotheken](https://github.com/dotnet/runtime/tree/master/src/libraries).

## <a name="microsoftextensions-libraries"></a>Microsoft.Extensions-Bibliotheken

Die Bibliotheken für einige häufig verwendete Anwendungsfunktionen sind nicht in den Runtimebibliotheken enthalten, werden jedoch in NuGet-Paketen wie den folgenden bereitgestellt:

| NuGet-Paket | Dokumentation |
|---------|---------|
| [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) | [Verwaltung der Anwendungslebensdauer (generischer Host)](extensions/generic-host.md) |
| [Microsoft.Extensions.DependencyInjection](https://www.nuget.org/packages/Microsoft.Extensions.DependencyInjection) | [Abhängigkeitsinjektion](extensions/dependency-injection.md)
| [Microsoft.Extensions.Configuration](https://www.nuget.org/packages/Microsoft.Extensions.Configuration) | [Configuration](extensions/configuration.md) |
| [Microsoft.Extensions.Logging](https://www.nuget.org/packages/Microsoft.Extensions.Logging) | [Logging](extensions/logging.md) |
| [Microsoft.Extensions.Options](https://www.nuget.org/packages/Microsoft.Extensions.Options) | [Optionenmuster](extensions/options.md) |

Weitere Informationen finden Sie im [GitHub-Repository „dotnet/extensions“](https://github.com/dotnet/extensions)

## <a name="data-access"></a>Datenzugriff

.NET bietet einen objektrelationalen Mapper (ORM) und eine Möglichkeit zum Schreiben von SQL-Abfragen in Code.

### <a name="entity-framework-core"></a>Entity Framework Core

Entity Framework Core (EF Core) ist eine [Open-Source-](https://github.com/aspnet/EntityFrameworkCore) und plattformübergreifende Datenzugriffstechnologie, die als ORM fungieren kann. Mit EF Core können Sie mit einer Datenbank arbeiten, indem Sie auf .NET-Objekte im Code verweisen. Dadurch wird die Menge des Datenzugriffscodes reduziert, den Sie andernfalls schreiben und testen müssen. EF Core unterstützt viele Datenbank-Engines.

Weitere Informationen finden Sie unter [Entity Framework Core](/ef/core/) und [Datenbankanbieter](/ef/core/providers/).

### <a name="linq"></a>LINQ

Language Integrated Query (LINQ) ermöglicht das Schreiben von deklarativem Code zum Arbeiten mit Daten. Die Daten können in vielfältiger Form vorliegen (als In-Memory-Objekte, in einer SQL-Datenbank oder in einem XML-Dokument), aber der LINQ-Code weicht in der Regel nicht für die verschiedenen Datenquellen ab.

Weitere Informationen finden Sie unter [Übersicht über LINQ](../standard/linq/index.md).

## <a name="net-terminology"></a>.NET-Terminologie

Es kann hilfreich sein, zu wissen, wie sich die Nutzung einiger Begriffe im Laufe der Zeit geändert hat, um die .NET-Dokumentation zu verstehen.

### <a name="net-core-and-net-5"></a>.NET Core und .NET 5

Microsoft veröffentlichte im Jahr 2002 mit [.NET Framework](../framework/get-started/overview.md) eine Entwicklungsplattform zum Erstellen von Windows-Apps. Heute steht Version 4.8 von .NET Framework zur Verfügung, die noch immer von [Microsoft unterstützt wird](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework).

Microsoft begann 2014, einen plattformübergreifenden Open-Source-Nachfolger für .NET Framework zu schreiben. Diese neue Implementierung von .NET hieß .NET Core, bis Version 3.1 erreicht wurde. Die nächste Version nach .NET Core 3.1 ist .NET 5.0, die sich derzeit in der Vorschau befindet. Die Versionsnummer „4“ wurde übersprungen, um Verwechslungen zwischen dieser Implementierung von .NET und .NET Framework 4.8 zu vermeiden. Die Bezeichnung „Core“ wurde weggelassen, um deutlich zu machen, dass dies nun die Hauptimplementierung von .NET ist.

In diesem Artikel geht es um .NET 5, aber ein Großteil der Dokumentation für .NET 5 enthält immer noch Verweise auf .NET Core oder .NET Framework. Außerdem wird die Bezeichnung „Core“ weiterhin in den Namen [ASP.NET Core](/aspnet/core/) und [Entity Framework Core](/ef/core/) verwendet.

Die Dokumentation bezieht sich auch auf .NET Standard. [.NET Standard](../standard/net-standard.md) ist eine API-Spezifikation, mit der Sie Klassenbibliotheken für mehrere Implementierungen von .NET entwickeln können.

Weitere Informationen finden Sie unter [.NET-Architekturkomponenten](../standard/components.md).

### <a name="overloaded-terms"></a>Überladene Begriffe

Einige der Begriffe für .NET können verwirrend sein, da dasselbe Wort in verschiedenen Kontexten auf unterschiedliche Weise verwendet wird. Dies sind einige der wichtigsten Instanzen:

* **Laufzeit**

  |Kontext  |Bedeutung von „Runtime“ |
  |---------|---------|
  | [Common Language Runtime (CLR)](#clr)| Die Ausführungsumgebung eines verwalteten Programms. Das Betriebssystem ist Teil der Runtimeumgebung, gehört jedoch nicht zur .NET-Runtime. |
  | [.NET-Runtime auf der .NET-Downloadseite](https://dotnet.microsoft.com/download/dotnet-core) | Dies sind die [CLR](#clr) und [Runtimebibliotheken](#runtime-libraries), die zusammen Unterstützung für das Ausführen von [frameworkabhängigen](#deployment-models) Apps bieten. Die Seite bietet auch Runtimeoptionen für ASP.NET Core-Server-Apps und Windows-Desktop-Apps. |
  | [Runtimebezeichner (RID)](rid-catalog.md) | Dies ist die Betriebssystemplattform und CPU-Architektur, auf der eine .NET-App ausgeführt wird. Zum Beispiel: Windows x64 und Linux x64 |

* **Framework**

  |Kontext  | Bedeutung von „Framework“ |
  |---------|---------------------|
  | .NET Framework | Dies ist die ursprüngliche Implementierung von .NET für Windows. „Framework“ wird großgeschrieben. |
  | Zielframework | Die Sammlung von APIs, auf der eine .NET-App oder -Bibliothek basiert. Beispiele: .NET Core 3.1 und .NET Standard 2.0 |
  | Zielframeworkmoniker (Target Framework Moniker, TFM)  | Ein Zielframeworkmoniker (TFM) ist ein standardisiertes Tokenformat zum Angeben des Zielframeworks einer .NET-App oder -Bibliothek. Beispiel: `net462` für .NET Framework 4.6.2 |
  | Frameworkabhängige App | Dies ist eine App, die nur auf einem Computer ausgeführt werden kann, auf dem Sie die Runtime von der [.NET-Downloadseite](https://dotnet.microsoft.com/download/dotnet-core) installiert haben. „Framework“ ist in dieser Verwendung dasselbe wie „Runtime“, die Sie von der .NET-Downloadseite herunterladen. |

* **SDK**

  |Kontext  | Bedeutung von „SDK“ |
  |---------|---------------|
  | [SDK auf der .NET-Downloadseite](#sdk-and-runtimes)  | Dies ist eine Sammlung von Tools und Bibliotheken, die Sie herunterladen und installieren, um .NET-Apps zu entwickeln und auszuführen. Dabei sind die CLI, MSBuild, die .NET-Runtime und andere Komponenten enthalten.|
  | [Projekt im SDK-Format](#project-system-and-msbuild) | Dies sind mehrere MSBuild-Ziele und -Aufgaben, die angeben, wie ein Projekt für einen bestimmten App-Typ erstellt wird. Das SDK wird in diesem Sinne mithilfe des `Sdk`-Attibuts des `Project`-Elements in einer Projektdatei angegeben. |

* **platform**

  |Kontext  | Bedeutung von „Plattform“ |
  |---------|--------------------|
  | Plattformübergreifend | „Plattform“ steht in diesem Fall für ein Betriebssystem und die Hardware, auf dem bzw. der die Ausführung erfolgt (z. B. Windows, macOS, Linux, iOS und Android). |
  | .NET-Plattform | Die Verwendung variiert. Der Verweis kann auf eine Implementierung von .NET (z. B. .NET Framework oder .NET 5) oder ein übergeordnetes Konzept von .NET einschließlich aller Implementierungen erfolgen. |

Weitere Informationen zur .NET-Terminologie finden Sie im [.NET-Glossar](../standard/glossary.md).

## <a name="advanced-scenarios"></a>Erweiterte Szenarien

In den folgenden Abschnitten werden einige Funktionen von .NET erläutert, die in erweiterten Szenarios nützlich sind.

### <a name="native-interop"></a>Native Interoperabilität

Jedes Betriebssystem umfasst eine Anwendungsprogrammierschnittstelle (Application Programming Interface, API), die Systemdienste bereitstellt. In .NET gibt es verschiedene Möglichkeiten, diese APIs aufzurufen.

Die wichtigste Methode für die Interoperabilität mit nativen APIs ist ein „Plattformaufruf“ (kurz: P/Invoke). P/Invoke wird auf Linux- und Windows-Plattformen unterstützt. Eine nur für Windows verfügbare Methode für die Interoperabilität wird als „COM-Interop“ bezeichnet, die im Zusammenhang mit [COM-Komponenten](/cpp/atl/introduction-to-com) in verwaltetem Code funktioniert. Die Methode basiert auf der P/Invoke-Infrastruktur, funktioniert jedoch etwas anders.

Weitere Informationen finden Sie unter [Native Interoperabilität](../standard/native-interop/index.md).

### <a name="unsafe-code"></a>Unsicherer Code

Je nach Sprachunterstützung können Sie mit der CLR auf nativen Speicher zugreifen und Zeigerarithmetik über `unsafe`-Code ausführen. Diese Vorgänge werden für bestimmte Algorithmen sowie für die Systeminteroperabilität benötigt. Unsicherer Code ist zwar leistungsstark, aber von seiner Verwendung wird abgeraten, sofern er nicht für die Interoperabilität mit System-APIs oder zur Implementierung des effizientesten Algorithmus erforderlich ist. Unsicherer Code wird in verschiedenen Umgebungen möglicherweise unterschiedlich ausgeführt und bietet weder die Vorteile des Garbage Collectors noch Typsicherheit. Es wird empfohlen, die Verwendung von unsicherem Code so weit wie möglich einzugrenzen und den Code sehr gründlich zu testen.

Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger (C#-Programmierhandbuch)](../csharp/programming-guide/unsafe-code-pointers/index.md).

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Auswählen eines .NET-Tutorials](tutorials/index.md)

> [!div class="nextstepaction"]
> [Testen von .NET im Browser](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)

> [!div class="nextstepaction"]
> [Überblick über C#](../csharp/tour-of-csharp/index.md)

> [!div class="nextstepaction"]
> [Überblick über F#](../fsharp/tour.md)
