---
title: Erste Schritte mit .NET Core unter Mac OS
description: "Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe mithilfe von Visual Studio Code."
keywords: .NET, .NET Core, Mac, macOS, Visual Studio Code
author: bleroy
ms.author: mairaw
ms.date: 03/23/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
ms.workload: dotnetcore
ms.openlocfilehash: 5a8f1fca7623763d43b977d0cc44396de249c62e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="getting-started-with-net-core-on-macos"></a>Erste Schritte mit .NET Core unter Mac OS

Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe für macOS. Erfahren Sie, wie Projekte und Unittests erstellt, die Debuggingtools verwendet und Bibliotheken von Drittanbietern über [NuGet](https://www.nuget.org/) eingebunden werden.

> [!NOTE]
> In diesem Artikel wird [Visual Studio Code](http://code.visualstudio.com) unter macOS verwendet.

## <a name="prerequisites"></a>Erforderliche Komponenten

Installieren Sie das [.NET Core SDK](https://www.microsoft.com/net/core). Das .NET Core SDK umfasst die neueste Version von .NET Core-Framework und -Runtime.

Installieren Sie [Visual Studio Code](http://code.visualstudio.com). Im Rahmen dieses Artikels installieren Sie auch Visual Studio Code-Erweiterungen, die den .NET Core-Entwicklungsprozess verbessern.

Installieren Sie die C#-Erweiterung für Visual Studio Code, indem Sie Visual Studio Code öffnen und <kbd>F1</kbd> drücken, um die Visual Studio Code-Palette zu öffnen. Geben Sie **ext install** ein, um die Liste mit Erweiterungen anzuzeigen. Wählen Sie die C#-Erweiterung aus. Starten Sie Visual Studio Code neu, um die Erweiterung zu aktivieren. Weitere Informationen finden Sie unter [Dokumentation zur C#-Erweiterung von Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="getting-started"></a>Erste Schritte

In diesem Tutorial erstellen Sie drei Projekte: ein Bibliotheksprojekt, Tests für dieses Bibliotheksprojekt sowie eine Konsolenanwendung, die die Bibliothek nutzt. Sie können die Quelle für dieses Thema im Repository „dotnet/docs“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden). Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Starten Sie Visual Studio Code. Drücken Sie <kbd>STRG</kbd>+<kbd>\`</kbd> (das Zeichen für das invertierte Hochkomma oder das Graviszeichen), oder wählen Sie **Anzeigen > Integriertes Terminal** aus dem Menü aus, um ein eingebettetes Terminal in Visual Studio Code zu öffnen. Sie können noch immer eine externe Shell mit dem Explorer-Befehl **In Eingabeaufforderung öffnen** (**In Terminal öffnen** unter Mac oder Linux) öffnen, wenn Sie lieber außerhalb von Visual Studio Code arbeiten möchten.

Beginnen Sie, indem Sie eine Projektmappendatei erstellen, die als Container für mindestens ein .NET Core-Projekt dient. Erstellen Sie im Terminal einen *golden*-Ordner, und öffnen Sie den Ordner. Dieser Ordner ist der Stamm der Projektmappe. Führen Sie den [`dotnet new`](../tools/dotnet-new.md)-Befehl aus, um eine neue Projektmappe, *golden.sln*, zu erstellen:

```console
dotnet new sln
```

Führen Sie aus dem *golden*-Ordner den folgenden Befehl aus, um ein Bibliotheksprojekt zu erstellen, das zwei Dateien im *library*-Ordner erstellt: *library.csproj* and *Class1.cs*.

```console
dotnet new classlib -o library
```

Führen Sie den [`dotnet sln`](../tools/dotnet-sln.md)-Befehl aus, um das neu erstellte *library.csproj*-Projekt zur Projektmappe hinzuzufügen:

```console
dotnet sln add library/library.csproj
```

Die *library.csproj*-Datei enthält die folgenden Informationen:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

Unsere Bibliotheksmethode serialisieren und deserialisieren Objekte im JSON-Format. Um die JSON-Serialisierung und Deserialisierung zu unterstützen, fügen Sie einen Verweis zum `Newtonsoft.Json`-NuGet-Paket hinzu. Der `dotnet add`-Befehl fügt neue Elemente zu einem Projekt hinzu. Um einen Verweis auf ein NuGet-Paket hinzuzufügen, führen Sie den [`dotnet add package`](../tools/dotnet-add-package.md)-Befehl aus, und geben den Namen des Pakets an.

```console
dotnet add library package Newtonsoft.Json
```

Dadurch werden `Newtonsoft.Json` und dessen Abhängigkeiten zum Klassenbibliotheksprojekt hinzugefügt. Alternativ können Sie die *library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="10.0.1" />
</ItemGroup>
```

Führen Sie [`dotnet restore`](../tools/dotnet-restore.md) aus ([siehe Hinweis](#dotnet-restore-note)), wodurch Abhängigkeiten wiederhergestellt werden und ein *obj*-Ordner mit drei Dateien innerhalb von *library* erstellt wird, einschließlich einer *project.assets.json*-Datei:

```console
dotnet restore
```

Benennen Sie im Ordner *library* die Datei *Class1.cs* in *Thing.cs* um. Ersetzen Sie den Code durch Folgendes:

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

Die `Thing`-Klasse enthält eine öffentliche Methode, `Get`, die die Summe zweier Zahlen durch Konvertierung der Summe in eine Zeichenfolge zurückgibt, die anschließend in eine ganze Zahl serialisiert wird. Hierbei werden verschiedene moderne C#-Features verwendet, wie etwa [`using static`-Direktiven](../../csharp/language-reference/keywords/using-static.md), [Ausdruckskörpermitglieder](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) und [interpolierte Zeichenfolgen](../../csharp/language-reference/keywords/interpolated-strings.md).

Erstellen Sie die Bibliothek mithilfe des [`dotnet build`](../tools/dotnet-build.md)-Befehls. Dadurch wird eine integrierte *library.dll*-Datei unter *golden/library/bin/Debug/netstandard1.4* erstellt.

```console
dotnet build
```

## <a name="create-the-test-project"></a>Erstellen des Testprojekts

Erstellen Sie eine Testprojekt für die Bibliothek. Erstellen Sie aus dem *golden*-Ordner ein neues Testprojekt:

```console
dotnet new xunit -o test-library
```

Fügen sie das Testprojekt zur Projektmappe hinzu:

```console
dotnet sln add test-library/test-library.csproj
```

Fügen Sie der von Ihnen im letzten Abschnitt erstellten Bibliothek einen Projektverweis hinzu, damit der Compiler das Bibliotheksprojekt finden und verwenden kann. Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):

```console
dotnet add test-library/test-library.csproj reference library/library.csproj
```

Alternativ können Sie die *test-library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

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
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

Beachten Sie, dass der Wert 42 nicht 19+23 (oder 42) entspricht, wenn Sie zum ersten Mal den Komponententest (`Assert.NotEqual`) erstellen, was fehlschlagen wird. Ein wichtiger Schritt beim Erstellen von Komponententests ist die Erstellung des Tests, der zuerst einmal fehlschlägt, um seine Logik zu bestätigen.

Führen Sie im *golden*-Ordner die folgenden Befehle aus:

```console
dotnet restore 
dotnet test test-library/test-library.csproj
```

Diese Befehle finden rekursiv alle Projekte, deren Abhängigkeiten wiederhergestellt werden sollen, erstellen sie und aktivieren den xUnit-Textlauf, um die Tests auszuführen. Der einzelne Text schlägt wie erwartet fehl.

Bearbeiten Sie die Datei *UnitTest1.cs*, und ändern Sie die Assertion von `Assert.NotEqual` zu `Assert.Equal`. Führen Sie den folgenden Befehl aus dem *golden*-Ordner aus, um den Test erneut auszuführen, der diesmal erfolgreich ausgeführt wird.

```console
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a>Schreiben der Konsolen-App

Die Konsolen-App, die Sie mithilfe der folgenden Schritte erstellen, ist vom Bibliotheksprojekt abhängig, das Sie zuvor erstellt haben, und ruft seine Bibliotheksmethode auf, wenn es ausgeführt wird. Mithilfe dieses Entwicklungsmusters sehen Sie, wie Sie wiederverwendbare Bibliotheken für mehrere Projekte erstellen können.

Erstellen Sie eine neue Konsolenanwendung aus dem *golden*-Ordner:

```console
dotnet new console -o app
```

Fügen Sie das Konsolen-App-Projekt zur Projektmappe hinzu:

```console
dotnet sln add app/app.csproj
```

Erstellen Sie die Abhängigkeit von der Bibliothek, indem Sie den `dotnet add reference`-Befehl ausführen:

```console
dotnet add app/app.csproj reference library/library.csproj
```

Führen Sie `dotnet restore` aus ([siehe Hinweis](#dotnet-restore-note)), um die Abhängigkeiten der drei Projekte in der Projektmappe wiederherzustellen. Öffnen Sie *Program.cs*, und ersetzen Sie den Inhalt der `Main`-Methode durch diese Zeile:

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

Fügen Sie ganz oben in der *Program.cs*-Datei zwei `using`-Direktiven hinzu:

```csharp
using static System.Console;
using Library;
```

Führen Sie den folgenden `dotnet run`-Befehl aus, um die ausführbare Datei auszuführen, wobei die `-p`-Option für `dotnet run` das Projekt für die Hauptanwendung angibt. Die App erzeugt die Zeichenfolge „Die Antwort ist 42“.

```console
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a>Debuggen der Anwendung

Legen Sie bei der Anweisung `WriteLine` in der `Main`-Methode einen Haltepunkt fest. Dies erreichen Sie, indem Sie entweder die <kbd>F9</kbd>-Taste drücken, wenn sich der Cursor auf der `WriteLine`-Zeile befindet, oder indem Sie auf den linken Rand der Zeile klicken, wo Sie den Haltepunkt festlegen möchten. Es erscheint ein Roter Kreis im Rand neben der Codezeile. Wenn der Haltepunkt erreicht ist, wird die Ausführung des Codes angehalten, *bevor* die Haltepunktzeile ausgeführt wird.

Öffnen Sie die Registerkarte „Debugger“, indem Sie das Debugger-Symbol in der Visual Studio Code-Symbolleiste auswählen, **Anzeigen > Debuggen** aus der Menüleiste auswählen oder den Tastaturkurzbefehl <kbd>STRG</kbd>+<kbd>UMSCHALT</kbd>+<kbd>D</kbd> verwenden:

![Visual Studio Code-Debugger](./media/using-on-macos/vscodedebugger.png)

Klicken Sie auf die Schaltfläche „Wiedergabe“, um die Anwendung unter dem Debugger zu starten. Die App startet mit der Ausführung und läuft bis zum Haltepunkt, wo sie anhält. Führen Sie die `Get`-Methode schrittweise aus, und stellen Sie sicher, dass Sie die richtigen Argumente eingefügt haben. Bestätigen Sie, dass die Antwort 42 ist.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]