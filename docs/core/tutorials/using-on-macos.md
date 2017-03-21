---
title: Erste Schritte mit .NET Core unter Mac OS
description: Erste Schritte mit .NET Core unter Mac OS mit Visual Studio Code
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 02/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: c4d1b7690ca87f2a1a9ced4d82e47aee2f7ecc9f
ms.lasthandoff: 03/07/2017

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-code"></a>Erste Schritte mit .NET Core unter Mac OS mit Visual Studio Code

Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe mit [Visual Studio Code](http://code.visualstudio.com).
Erfahren Sie, wie Projekte und Unittests erstellt, die Debuggingtools verwendet und Bibliotheken von Drittanbietern über [NuGet](http://nuget.org) eingebunden werden.

In diesem Artikel wird Visual Studio Code unter Mac OS verwendet. Wo Unterschiede zur Windows-Plattform vorhanden sind, wird darauf hingewiesen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Bevor Sie beginnen, müssen Sie das [.NET Core SDK](https://www.microsoft.com/net/core) installieren. Das .NET Core SDK umfasst die neueste Version von .NET Core-Framework und -Runtime.

Darüber hinaus müssen Sie auch [Visual Studio Code](http://code.visualstudio.com) installieren.
Im Rahmen dieses Artikels installieren Sie auch Erweiterungen, die den .NET Core-Entwicklungsprozess verbessern.

## <a name="getting-started"></a>Erste Schritte

Die Quelle für dieses Tutorial ist auf [GitHub](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden) verfügbar.

Starten Sie Visual Studio Code. Drücken Sie die Tastenkombination STRG+ „\`“ (das invertierte Hochkomma), um ein eingebettetes Terminal in VS Code zu öffnen. (Wenn Sie möchten, können Sie auch ein separates Terminalfenster verwenden.)

Nach dem Öffnen des Terminals erstellen Sie drei Projekte: ein Bibliotheksprojekt, Tests für dieses Bibliotheksprojekt sowie eine Konsolenanwendung, die die Bibliothek nutzt. 

Erstellen Sie zunächst diese Ordner. Erstellen Sie im Terminal ein „goldenes“ Verzeichnis. Öffnen Sie in VS Code das *goldene* Verzeichnis. Dieses Verzeichnis ist der Stamm der Projektmappe. Führen Sie den [`dotnet new`](../tools/dotnet-new.md)-Befehl aus, um eine neue Projektmappe zu erstellen:

```
dotnet new sln
```

Dieser Befehl erstellt eine *golden.sln*-Datei für die gesamte Projektmappe.

Die nächste Aufgabe ist die Erstellung der Bibliothek. Wechseln Sie im Terminalfenster (im eingebetteten Terminal in VS Code oder in einem anderen Terminal) zu *golden/*, und geben Sie den Befehl ein:

```
dotnet new classlib -o library
```

Dadurch wird ein Bibliotheksprojekt mit zwei Dateien erstellt: *library.csproj* und *Class1.cs* im Verzeichnis *Bibliothek*. Sie möchten dieses Bibliotheksprojekt in Ihre Projektmappe einbauen. Führen Sie den [`dotnet sln`](../tools/dotnet-sln.md)-Befehl aus, um das neu erstellte *library.csproj*-Projekt zur Projektmappe hinzuzufügen:

```
dotnet sln add library/library.csproj
```

Betrachten Sie das Projekt, das Sie erstellt haben. Die *library.csproj*-Datei enthält die folgenden Informationen:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

Diese Bibliotheksprojekt nutzt die JSON-Darstellung von Objekten. Daher sollten Sie einen Verweis auf das NuGet-Paket `Newtonsoft.Json` hinzufügen. Der `dotnet add`-Befehl fügt neue Elemente zu einem Projekt hinzu. Um einen Verweis auf ein NuGet-Paket hinzuzufügen, führen Sie den `package`-Befehl aus, und geben den Namen des Pakets an. 

```
dotnet add library package Newtonsoft.Json
```

Dadurch werden `Newtonsoft.Json` und dessen Abhängigkeiten zum Klassenbibliotheksprojekt hinzugefügt. Alternativ können Sie die *library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1</Version>
  </PackageReference>
</ItemGroup>
```

Nachdem Sie diese Abhängigkeiten hinzugefügt haben, müssen Sie diese Pakete im Arbeitsbereich installieren. Führen Sie den Befehl `dotnet restore` aus, um alle Abhängigkeiten zu aktualisieren, und speichern Sie die *obj/project.assets.json*-Datei im Projektverzeichnis. Diese Datei enthält die vollständige Abhängigkeitsstruktur aller Abhängigkeiten in Ihrem Projekt. Sie müssen diese Datei nicht lesen. Sie wird von Tools im .NET Core SDK verwendet.

Aktualisieren Sie als Nächstes den C#-Code. Erstellen Sie eine `Thing`-Klasse, die eine öffentliche Methode enthält. Diese Methode gibt die Summe zweier Zahlen zurück. Hierzu werden diese Zahlen jedoch in eine JSON-Zeichenfolge konvertiert und anschließend deserialisiert. Benennen Sie die Datei *Class1.cs* in *Thing.cs*. Ersetzen Sie den vorhandenen Code (für die mittels Vorlage generierte Class1) durch folgenden Code:

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

Hierbei werden verschiedene moderne C#-Features verwendet, wie etwa statische Using-Direktiven, Ausdruckskörpermitglieder und interpolierte Zeichenfolgen. Informationen hierzu finden Sie im Abschnitt [Einführung in C#](../../csharp/index.md).

Nachdem Sie den Code aktualisiert haben, können Sie die Bibliothek mithilfe von `dotnet build` erstellen.

Sie verfügen nun über eine integrierte *library.dll*-Datei unter *golden/library/bin/Debug/netstandard1.4*.

### <a name="writing-the-test-project"></a>Schreiben des Testprojekts

Erstellen Sie ein Testprojekt für die von Ihnen erstellte Bibliothek. Navigieren Sie zum *goldenen* Verzeichnis. Führen Sie `dotnet new xunit -o test-library` aus, um ein neues Testprojekt zu erstellen. Sie sollten dieses Projekt der Projektmappe hinzufügen und `dotnet sln add test-library/test-library.csproj` ausführen.

Für die in den obigen Schritten erstellte Bibliothek müssen Sie einen Abhängigkeitsknoten hinzufügen. Der `dotnet add reference`-Befehl führt folgendes aus:

```
dotnet add test-library/test-library.csproj reference library/library.csproj
```

Alternativ können Sie die *test-library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

Der Knoten `library` gibt an, dass diese Abhängigkeit in ein Projekt im aktuellen Arbeitsbereich aufgelöst werden soll. Ohne diese explizite Angabe ist es möglich, dass das Testprojekt für ein NuGet-Paket mit demselben Namen erstellt wird.

Nachdem Sie die Abhängigkeiten ordnungsgemäß konfiguriert haben, erstellen Sie nun die Tests für Ihre Bibliothek. Öffnen Sie *UnitTest1.cs*, und ersetzen Sie den Inhalt durch den folgenden Code:

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.Equal(42, new Thing().Get(19, 23));
        }
    }
}
```

Führen Sie nun `dotnet restore` und `dotnet build` aus. Diese Befehle werden alle Projekte rekursiv suchen, um Abhängigkeiten wiederherzustellen und sie zu erstellen.
Abschließend führen Sie `dotnet test test-library/test-library.csproj` zum Ausführen der Tests durch.
Der Test Runner der xUnit-Konsole führt den einen Test aus und meldet, dass er erfolgreich verlaufen ist. 

### <a name="writing-the-console-app"></a>Schreiben der Konsolenanwendung

Führen Sie `dotnet new console -o app` in Ihrem Terminal aus, um eine neue Konsolenanwendung zu erstellen. Dieses Projekt ist auch Teil der Projektmappe. Führen Sie also `dotnet sln add app/app.csproj` aus, um das Projekt der Projektmappe hinzuzufügen.

Die Konsolenanwendung hängt von der erstellten Bibliothek ab, die Sie in den vorherigen Schritten erstellt und getestet haben. Führen Sie `dotnet add reference` erneut aus, um dies anzugeben:

```
dotnet add app/app.csproj reference library/library.csproj
```

Führen Sie `dotnet restore` aus, um alle Abhängigkeiten wiederherzustellen. Öffnen Sie *program.cs*, und ersetzen Sie den Inhalt der `Main`-Methode durch diese Zeile:

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

Am Anfang der Datei müssen Sie einige `using`-Anweisungen hinzufügen:

```csharp
using static System.Console;
using Library;
```

Führen Sie anschließend `dotnet build` aus. Damit werden die Assemblys erstellt, und Sie können `dotnet run -p app/app.csproj` eingeben, um die ausführbare Datei auszuführen.
Das `-p`-Argument auf `dotnet run` gibt das Projekt für die Hauptanwendung an.

### <a name="debugging-your-application"></a>Debuggen der Anwendung

Sie können Ihren Code in VS Code mithilfe der C#-Erweiterung debuggen.
Installieren Sie diese Erweiterung, indem Sie `F1` drücken, um die VS Code-Palette zu öffnen. Geben Sie `ext install` ein, um die Liste mit Erweiterungen anzuzeigen. Wählen Sie die C#-Erweiterung aus. (Weitere Details finden Sie auf der Seite mit der [Dokumentation zur C#-Erweiterung von Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).)

Nachdem Sie die Erweiterung installiert haben, werden Sie von VS Code aufgefordert, die Anwendung neu zu starten, um die neue Erweiterung zu laden. Nach der Installation der Erweiterung können Sie die Registerkarte „Debugger“ aufrufen (siehe Abbildung).

![VS Code-Debugger](./media/using-on-macos/vscodedebugger.png)

Legen Sie bei der Anweisung `WriteLine` in `Main` einen Haltepunkt fest. Drücken Sie hierzu die Taste `F9`, oder klicken Sie an den linken Rand der Zeile, in der Sie den Haltepunkt festlegen möchten. Öffnen Sie den Debugger, indem Sie auf das Debugger-Symbol links im VS Code-Bildschirm klicken (siehe Abbildung). Klicken Sie anschließend auf die Schaltfläche „Wiedergabe“, um die Anwendung unter dem Debugger zu starten.

Sie sollten beim Haltepunkt ankommen. Führen Sie die `Get`-Methode schrittweise aus, und stellen Sie sicher, dass Sie die richtigen Argumente eingefügt haben. Stellen Sie sicher, dass die Antwort tatsächlich 42 lautet.

