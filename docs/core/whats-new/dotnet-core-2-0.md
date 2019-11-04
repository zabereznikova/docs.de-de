---
title: Neuigkeiten in .NET Core 2.0
description: Informationen zu den neuen Funktionen in .NET Core.
ms.date: 08/13/2017
ms.openlocfilehash: fcac4255e7370f31ea6c26771fdd7d341bafe38b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100844"
---
# <a name="whats-new-in-net-core-20"></a>Neuigkeiten in .NET Core 2.0

.NET Core 2.0 enthält Verbesserungen und neue Funktionen in folgenden Bereichen:

- [Tools](#tooling)
- [Sprachenunterstützung](#language-support)
- [Plattformverbesserungen](#platform-improvements)
- [API-Änderungen](#api-changes-and-library-support)
- [Integration von Visual Studio](#visual-studio-integration)
- [Dokumentationsverbesserungen](#documentation-improvements)

## <a name="tooling"></a>Tools

### <a name="dotnet-restore-runs-implicitly"></a>„dotnet restore“ wird implizit ausgeführt.

In früheren Versionen von .NET Core mussten Sie den [dotnet restore](../tools/dotnet-restore.md)-Befehl sowohl ausführen, um Abhängigkeiten sofort nach der Erstellung eines neuen Projekts mit dem [dotnet new](../tools/dotnet-new.md)-Befehl herunterzuladen, als auch immer dann, wenn Sie dem Projekt eine neue Abhängigkeit hinzugefügt hatten.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Sie können den automatischen Aufruf von `dotnet restore` auch deaktivieren, indem Sie die Befehlszeilenoption `--no-restore` den Befehlen `new`, `run`, `build`, `publish`, `pack` und `test` übergeben.

### <a name="retargeting-to-net-core-20"></a>Neuzuweisung zu .NET Core 2.0

Wenn .NET Core 2.0 SDK installiert ist, können Projekte, die .NET Core 1.x zugewiesen sind, .NET Core 2.0 neu zugewiesen werden.

Bearbeiten Sie Ihre Projektdatei für die Neuzuweisung zu .NET Core 2.0 durch Ändern des Werts des `<TargetFramework>`-Elements (oder `<TargetFrameworks>`-Elements, wenn Ihre Projektdatei mehrere Zuweisungen enthält) von 1.x in 2.0:

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

Auf die gleiche Weise können Sie auch .NET Standard-Bibliotheken zu .NET Standard 2.0 neu zuweisen:

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

Weitere Informationen zum Migrieren Ihres Projekts zu .NET Core 2.0 finden Sie unter [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index) (Migrieren von ASP.NET Core 1.x zu ASP.NET Core 2.0).

## <a name="language-support"></a>Sprachenunterstützung

Außer C# und F# unterstützt .NET Core 2.0 auch Visual Basic.

### <a name="visual-basic"></a>Visual Basic

Mit Version 2.0 unterstützt .NET Core jetzt Visual Basic 2017. Sie können Visual Basic zum Erstellen folgender Projekttypen verwenden:

- .NET Core-Konsolen-Apps
- .NET Core-Klassenbibliotheken
- .NET Standard-Klassenbibliotheken
- .NET Core-Komponententestprojekte
- .NET Core-xUnit-Testprojekte

Führen Sie z.B. zum Erstellen einer „Hello World“-Anwendung in Visual Basic die folgenden Schritte in der Befehlszeile aus:

1. Öffnen Sie ein Konsolenfenster, erstellen Sie ein Verzeichnis für Ihr Projekt, und machen Sie es zu Ihrem aktuellen Verzeichnis.

1. Geben Sie den Befehl `dotnet new console -lang vb` ein.

   Der Befehl erstellt eine Projektdatei mit einer `.vbproj`-Erweiterung zusammen mit einer Visual Basic-Quellcodedatei mit dem Namen *Program.vb*. Diese Datei enthält den Quellcode, um die Zeichenfolge „Hello World!“ im Konsolenfenster anzuzeigen.

1. Geben Sie den Befehl `dotnet run` ein. Die [.NET Core-CLI](../tools/index.md) kompiliert die Anwendung automatisch und führt sie aus, um die Meldung „Hallo Welt!“ anzuzeigen. im Konsolenfenster anzuzeigen.

### <a name="support-for-c-71"></a>Unterstützung für C# 7.1

.NET Core 2.0 unterstützt C# 7.1 und wird so durch eine Reihe neuer Funktionen einschließlich der folgenden ergänzt:

- Die `Main`-Methode, der Einstiegspunkt der Anwendung, kann mit dem [async](../../csharp/language-reference/keywords/async.md)-Schlüsselwort gekennzeichnet werden.
- Abgeleitete Tupelnamen.
- Standardausdrücke.

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a>Plattformverbesserungen

.NET Core 2.0 umfasst eine Reihe von Funktionen, die das Installieren von .NET Core und die Verwendung auf unterstützten Betriebssystemen erleichtern.

### <a name="net-core-for-linux-is-a-single-implementation"></a>.NET Core für Linux ist eine einzelne Implementierung.

.NET Core 2.0 bietet eine einzelne Linux-Implementierung, die für mehrere Linux-Distributionen verwendet werden kann. .NET Core 1.x setzte das Herunterladen einer distributionsspezifischen Linux-Implementierung voraus.

Sie können auch Apps entwickeln, die für das Betriebssystem Linux im Allgemeinen vorgesehen sind. .NET Core 1.x setzte voraus, dass Sie für jede Linux-Distribution separat entwickeln.

### <a name="support-for-the-apple-cryptographic-libraries"></a>Unterstützung der kryptografischen Apple-Bibliotheken

.NET Core 1.x auf macOS setzte die kryptografische Bibliothek des OpenSSL-Toolkits voraus. .NET Core 2.0 verwendet die kryptografischen Apple-Bibliotheken und benötigt OpenSSL nicht, sodass Sie auf dessen Installation zukünftig verzichten können.

## <a name="api-changes-and-library-support"></a>API-Änderungen und Bibliotheksunterstützung

### <a name="support-for-net-standard-20"></a>Unterstützung für .NET Standard 2.0

.NET Standard definiert einen Satz von APIs mit Versionsangabe, die in .NET Implementierungen verfügbar sein müssen, die dieser Version des Standards entsprechen. .NET Standard ist auf Bibliotheksentwickler ausgerichtet. Er soll die Funktionalität garantieren, die einer Bibliothek zur Verfügung steht, die für eine Version von .NET Standard in jeder .NET-Implementierung vorgesehen ist. .NET Core 1.x unterstützt die .NET Standard-Version 1.6; .NET Core 2.0 unterstützt die neueste Version, .NET Standard 2.0. Weitere Informationen finden Sie unter [.NET Standard](../../standard/net-standard.md).

.NET Standard 2.0 umfasst über 20.000 APIs mehr, als in .NET Standard 1.6 verfügbar waren. Diese Oberflächenerweiterung resultiert zu einem großen Teil aus dem Einbeziehen in .NET Framework und Xamarin üblicher APIs in .NET Standard.

.NET Standard 2.0-Klassenbibliotheken können auch auf .NET Framework-Klassenbibliotheken verweisen, vorausgesetzt, dass sie APIs aufrufen, die in .NET Standard 2.0 vorhanden sind. Es ist keine Neukompilierung der .NET Framework-Bibliotheken erforderlich.

Eine Liste der APIs, die .NET Standard seit der letzten Version, .NET Standard 1.6, hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md) (.NET Standard 2.0 im Vergleich zu 1.6).

### <a name="expanded-surface-area"></a>Erweiterte Oberfläche

Die Gesamtanzahl der in .NET Core 2.0 verfügbaren APIs hat sich im Vergleich zu .NET Core 1.1 mehr als verdoppelt.

Und mit dem [Windows Compatibility Pack](../porting/windows-compat-pack.md) ist die Portierung aus .NET Framework ebenfalls viel einfacher geworden.

### <a name="support-for-net-framework-libraries"></a>Unterstützung für .NET Framework-Bibliotheken

.NET Core-Code kann auf vorhandene .NET Framework-Bibliotheken einschließlich der vorhandenen NuGet-Pakete verweisen. Beachten Sie, dass die Bibliotheken APIs verwenden müssen, die im .NET Standard enthalten sind.

## <a name="visual-studio-integration"></a>Visual Studio-Integration

Visual Studio 2017 Version 15.3 und in einigen Fällen Visual Studio für Mac bieten eine Reihe erheblicher Verbesserungen für .NET Core-Entwickler.

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a>Neuzuweisung von .NET Core-Apps und .NET Standard-Bibliotheken

Wenn das .NET Core 2.0 SDK installiert ist, können Sie Projekte von .NET Core 1.x zu .NET Core 2.0 und .NET Standard 1.x-Bibliotheken zu .NET-Standard 2.0 neu zuweisen.

Um Ihr Projekt in Visual Studio neu zuzuweisen, öffnen Sie die Registerkarte **Anwendung** des Eigenschaftendialogfelds des Projekts und ändern den Wert **Zielframework** in **.NET Core 2.0** oder **.NET Standard 2.0**. Sie können es auch ändern, indem Sie mit der rechten Maustaste auf das Projekt klicken und die Option **\*.csproj-Datei bearbeiten** auswählen. Weitere Informationen finden Sie weiter oben in diesem Thema im Abschnitt [Tools](#tooling).

### <a name="live-unit-testing-support-for-net-core"></a>Live Unit Testing-Unterstützung für .NET Core

Wenn Sie Ihren Code ändern, führt Live Unit Testing automatisch alle betroffenen Komponententests im Hintergrund aus und zeigt die Ergebnisse und die Codeabdeckung in der Visual Studio-Umgebung live an. .NET Core 2.0 unterstützt jetzt Live Unit Testing. Bisher war Live Unit Testing nur für .NET Framework-Anwendungen verfügbar.

Weitere Informationen finden Sie unter [Live Unit Testing mit Visual Studio 2017](/visualstudio/test/live-unit-testing) und [Live Unit Testing – häufig gestellte Fragen](/visualstudio/test/live-unit-testing-faq).

### <a name="better-support-for-multiple-target-frameworks"></a>Bessere Unterstützung für mehrere Zielframeworks

Wenn Sie ein Projekt für mehrere Zielframeworks erstellen, können Sie nun die Zielplattform im Hauptebenenmenü auswählen. In der folgenden Abbildung ist ein Projekt namens „SCD1“ für 64-Bit-macOS X 10.11 (`osx.10.11-x64`) und 64-Bit-Windows 10/Windows Server 2016 (`win10-x64`) bestimmt. Sie können das Zielframework vor der Projektschaltfläche auswählen, in diesem Fall zum Ausführen eines Debugbuilds.

![Screenshot mit der Zielframeworkauswahl beim Erstellen eines Projekts](./media/dotnet-core-2-0/target-framework-selection.png)

### <a name="side-by-side-support-for-net-core-sdks"></a>Parallele Unterstützung für .NET Core-SDKs

Sie können das .NET Core-SDK jetzt unabhängig von Visual Studio installieren. So können mit einer einzelnen Version von Visual Studio Projekte für verschiedene .NET Core-Versionen erstellt werden. Bisher waren Visual Studio und das .NET Core-SDK eng miteinander verbunden; eine bestimmte SDK-Version gehörte zu einer bestimmten Version von Visual Studio.

## <a name="documentation-improvements"></a>Dokumentationsverbesserungen

### <a name="net-application-architecture"></a>.NET-Anwendungsarchitektur

[.NET-Anwendungsarchitektur](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) ermöglicht Ihnen Zugriff auf eine Sammlung von E-Books, die Hilfestellung, bewährte Methoden und Beispielanwendungen zur Verwendung von .NET beim Erstellen folgender Software bieten:

- [Microservices und Docker-Container](../../architecture/microservices/index.md)
- [Webanwendungen mit ASP.NET](../../architecture/modern-web-apps-azure/index.md)
- [Mobile applications with Xamarin (Mobile Anwendungen mit Xamarin)](/xamarin/xamarin-forms/enterprise-application-patterns/index)
- [Anwendungen, die mit Azure in der Cloud bereitgestellt werden](/azure/architecture/reference-architectures/index)

## <a name="see-also"></a>Siehe auch

- [What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0) (Neuigkeiten in ASP.NET Core 2.0)
