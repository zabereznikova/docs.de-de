---
title: 'Tutorial: Erstellen einer .NET Core-Lösung unter macOS mit Visual Studio Code'
description: Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe mithilfe von Visual Studio Code.
ms.date: 12/19/2019
ms.openlocfilehash: 4dc44a0aa155dca3c106a7da68cf100ef644b58b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715303"
---
# <a name="tutorial-create-a-net-core-solution-in-macos-using-visual-studio-code"></a>Tutorial: Erstellen einer .NET Core-Lösung unter macOS mit Visual Studio Code

Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe für macOS. Erfahren Sie, wie Projekte und Unittests erstellt, die Debuggingtools verwendet und Bibliotheken von Drittanbietern über [NuGet](https://www.nuget.org/) eingebunden werden.

> [!NOTE]
> In diesem Artikel wird [Visual Studio Code](https://code.visualstudio.com) unter macOS verwendet.

## <a name="prerequisites"></a>Voraussetzungen

Installieren Sie das [.NET Core SDK](https://dotnet.microsoft.com/download). Das .NET Core SDK umfasst die neueste Version von .NET Core-Framework und -Runtime.

Installieren Sie [Visual Studio Code](https://code.visualstudio.com). Im Rahmen dieses Artikels installieren Sie auch Visual Studio Code-Erweiterungen, die den .NET Core-Entwicklungsprozess verbessern.

Installieren Sie die C#-Erweiterung für Visual Studio Code, indem Sie Visual Studio Code öffnen und <kbd>Fn</kbd>+<kbd>F1</kbd> drücken, um die Visual Studio Code-Palette zu öffnen. Geben Sie **ext install** ein, um die Liste mit Erweiterungen anzuzeigen. Wählen Sie die C#-Erweiterung aus. Starten Sie Visual Studio Code neu, um die Erweiterung zu aktivieren. Weitere Informationen finden Sie unter [Dokumentation zur C#-Erweiterung von Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="get-started"></a>Erste Schritte

In diesem Tutorial erstellen Sie drei Projekte: ein Bibliotheksprojekt, Tests für dieses Bibliotheksprojekt sowie eine Konsolenanwendung, die die Bibliothek nutzt. Sie können die Quelle für diesen Artikel im Repository „dotnet/samples“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/core/getting-started/golden). Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Starten Sie Visual Studio Code. Drücken Sie <kbd>STRG</kbd>+<kbd>\`</kbd> (das Zeichen für das invertierte Hochkomma oder das Graviszeichen), oder wählen Sie **Anzeigen > Terminal** aus dem Menü aus, um ein eingebettetes Terminal in Visual Studio Code zu öffnen. Sie können noch immer eine externe Shell mit dem Explorer-Befehl **In Eingabeaufforderung öffnen** (**In Terminal öffnen** unter Mac oder Linux) öffnen, wenn Sie lieber außerhalb von Visual Studio Code arbeiten möchten.

Beginnen Sie, indem Sie eine Projektmappendatei erstellen, die als Container für mindestens ein .NET Core-Projekt dient. Führen Sie im Terminal den Befehl [`dotnet new`](../tools/dotnet-new.md) aus, um eine neue Projektmappe *golden.sln* in einem neuen Ordner namens *golden* zu erstellen:

```dotnetcli
dotnet new sln -o golden
```

Navigieren Sie zum neuen Ordner *golden*, und führen Sie den folgenden Befehl aus, um ein Bibliotheksprojekt zu erstellen, das zwei Dateien im Ordner *library* erstellt: *library.csproj* und *Class1.cs*:

```dotnetcli
dotnet new classlib -o library
```

Führen Sie den [`dotnet sln`](../tools/dotnet-sln.md)-Befehl aus, um das neu erstellte *library.csproj*-Projekt zur Projektmappe hinzuzufügen:

```dotnetcli
dotnet sln add library/library.csproj
```

Die *library.csproj*-Datei enthält die folgenden Informationen:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Unsere Bibliotheksmethode serialisieren und deserialisieren Objekte im JSON-Format. Um die JSON-Serialisierung und Deserialisierung zu unterstützen, fügen Sie einen Verweis zum `Newtonsoft.Json`-NuGet-Paket hinzu. Der `dotnet add`-Befehl fügt neue Elemente zu einem Projekt hinzu. Um einen Verweis auf ein NuGet-Paket hinzuzufügen, führen Sie den [`dotnet add package`](../tools/dotnet-add-package.md)-Befehl aus, und geben den Namen des Pakets an.

```dotnetcli
dotnet add library package Newtonsoft.Json
```

Dadurch werden `Newtonsoft.Json` und dessen Abhängigkeiten zum Klassenbibliotheksprojekt hinzugefügt. Alternativ können Sie die *library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

Führen Sie [`dotnet restore`](../tools/dotnet-restore.md) aus ([siehe Hinweis](#dotnet-restore-note)), wodurch Abhängigkeiten wiederhergestellt werden und ein *obj*-Ordner mit drei Dateien innerhalb von *library* erstellt wird, einschließlich einer *project.assets.json*-Datei:

```dotnetcli
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

Die `Thing`-Klasse enthält eine öffentliche Methode, `Get`, die die Summe zweier Zahlen durch Konvertierung der Summe in eine Zeichenfolge zurückgibt, die anschließend in eine ganze Zahl serialisiert wird. Hierbei werden verschiedene moderne C#-Features wie etwa [`using static`-Anweisungen](../../csharp/language-reference/keywords/using-static.md), [Ausdruckskörpermember](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) und [Zeichenfolgeninterpolation](../../csharp/language-reference/tokens/interpolated.md) verwendet.

Erstellen Sie die Bibliothek mithilfe des [`dotnet build`](../tools/dotnet-build.md)-Befehls. Dadurch wird eine integrierte *library.dll*-Datei unter *golden/library/bin/Debug/netstandard1.4* erstellt.

```dotnetcli
dotnet build
```

## <a name="create-the-test-project"></a>Erstellen des Testprojekts

Erstellen Sie eine Testprojekt für die Bibliothek. Erstellen Sie aus dem *golden*-Ordner ein neues Testprojekt:

```dotnetcli
dotnet new xunit -o test-library
```

Fügen sie das Testprojekt zur Projektmappe hinzu:

```dotnetcli
dotnet sln add test-library/test-library.csproj
```

Fügen Sie der von Ihnen im letzten Abschnitt erstellten Bibliothek einen Projektverweis hinzu, damit der Compiler das Bibliotheksprojekt finden und verwenden kann. Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
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

```dotnetcli
dotnet restore 
dotnet test test-library/test-library.csproj
```

Diese Befehle finden rekursiv alle Projekte, deren Abhängigkeiten wiederhergestellt werden sollen, erstellen sie und aktivieren den xUnit-Textlauf, um die Tests auszuführen. Der einzelne Text schlägt wie erwartet fehl.

Bearbeiten Sie die Datei *UnitTest1.cs*, und ändern Sie die Assertion von `Assert.NotEqual` zu `Assert.Equal`. Führen Sie den folgenden Befehl aus dem *golden*-Ordner aus, um den Test erneut auszuführen, der diesmal erfolgreich ausgeführt wird.

```dotnetcli
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a>Schreiben der Konsolen-App

Die Konsolen-App, die Sie mithilfe der folgenden Schritte erstellen, ist vom Bibliotheksprojekt abhängig, das Sie zuvor erstellt haben, und ruft seine Bibliotheksmethode auf, wenn es ausgeführt wird. Mithilfe dieses Entwicklungsmusters sehen Sie, wie Sie wiederverwendbare Bibliotheken für mehrere Projekte erstellen können.

Erstellen Sie eine neue Konsolenanwendung aus dem *golden*-Ordner:

```dotnetcli
dotnet new console -o app
```

Fügen Sie das Konsolen-App-Projekt zur Projektmappe hinzu:

```dotnetcli
dotnet sln add app/app.csproj
```

Erstellen Sie die Abhängigkeit von der Bibliothek, indem Sie den `dotnet add reference`-Befehl ausführen:

```dotnetcli
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

```dotnetcli
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a>Debuggen der Anwendung

Legen Sie bei der Anweisung `WriteLine` in der `Main`-Methode einen Haltepunkt fest. Sie erreichen dies, indem Sie entweder die <kbd>Fn</kbd>+<kbd>F9</kbd>-Taste drücken, wenn sich der Cursor in der `WriteLine`-Zeile befindet, oder indem Sie auf den linken Rand der Zeile klicken, in der Sie den Breakpoint festlegen möchten. Es erscheint ein Roter Kreis im Rand neben der Codezeile. Wenn der Haltepunkt erreicht ist, wird die Ausführung des Codes angehalten, *bevor* die Haltepunktzeile ausgeführt wird.

Öffnen Sie die Registerkarte „Debugger“, indem Sie das Debugger-Symbol in der Visual Studio Code-Symbolleiste auswählen, **Anzeigen > Debuggen** aus der Menüleiste auswählen oder die Tastenkombination <kbd>Befehl</kbd>+<kbd>UMSCHALT</kbd>+<kbd>D</kbd> verwenden:

![Visual Studio Code-Debugger](./media/using-on-macos/visual-studio-code-debugger.png)

Klicken Sie auf die Schaltfläche „Wiedergabe“, um die Anwendung unter dem Debugger zu starten. Sie haben in diesem Projekt sowohl ein Testprojekt als auch eine Anwendung erstellt. Der Debugger fragt, welches Projekt gestartet werden soll. Wählen Sie das Projekt „App“ aus. Die App startet mit der Ausführung und läuft bis zum Haltepunkt, wo sie anhält. Führen Sie die `Get`-Methode schrittweise aus, und stellen Sie sicher, dass Sie die richtigen Argumente eingefügt haben. Bestätigen Sie, dass die Antwort 42 ist.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
