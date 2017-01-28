---
title: Erste Schritte mit .NET Core unter Mac OS
description: Erste Schritte mit .NET Core unter Mac OS mit Visual Studio Code
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
translationtype: Human Translation
ms.sourcegitcommit: 7ac95fa4b2aac81b2e8d33cedf2faf36a0bbf210
ms.openlocfilehash: 33d87c3236e5f592cd59eab77df1059ac089b88c

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-code"></a>Erste Schritte mit .NET Core unter Mac OS mit Visual Studio Code

von [Bertrand Le Roy](https://github.com/bleroy),  [Phillip Carter](https://github.com/cartermp), [Bill Wagner](https://github.com/billwagner)

Beiträge von [Toni Solarin-Sodara](https://github.com/tsolarin)

Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe mit [Visual Studio Code](http://code.visualstudio.com).
Erfahren Sie, wie Projekte und Unittests erstellt, die Debuggingtools verwendet und Bibliotheken von Drittanbietern über [NuGet](http://nuget.org) eingebunden werden.

In diesem Artikel wird Visual Studio Code unter Mac OS verwendet. Wo Unterschiede zur Windows-Plattform vorhanden sind, wird darauf hingewiesen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Bevor Sie beginnen, müssen Sie das derzeit in der Vorschauversion vorliegende [.NET Core SDK](https://www.microsoft.com/net/core) installieren. Das .NET Core SDK umfasst die neueste Version von .NET Core-Framework und -Runtime.

Darüber hinaus müssen Sie auch [Visual Studio Code](http://code.visualstudio.com) installieren.
Im Rahmen dieses Artikels installieren Sie auch Erweiterungen, die den .NET Core-Entwicklungsprozess verbessern.

Alle entsprechenden Links finden Sie auf der [.NET-Homepage](http://dot.net).

## <a name="getting-started"></a>Erste Schritte

Die Quelle für dieses Tutorial ist auf [GitHub](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden) verfügbar.

Starten Sie Visual Studio Code. Drücken Sie die Tastenkombination STRG+ „\`“ (das invertierte Hochkomma), um ein eingebettetes Terminal in VS Code zu öffnen. (Wenn Sie möchten, können Sie auch ein separates Terminalfenster verwenden.)

Nach dem Öffnen des Terminals erstellen Sie drei Projekte: ein Bibliotheksprojekt, Tests für dieses Bibliotheksprojekt sowie eine Konsolenanwendung, die die Bibliothek nutzt. Verwenden Sie für diese drei Projekte eine Standardordnerstruktur. Das bedeutet, dass die .NET Core SDK-Tools die Beziehung zwischen Ihren Produktionscodeprojekten und Ihren Testcodeprojekten erkennen. Dadurch wird der Entwicklungsprozess produktiver.

Erstellen Sie zunächst diese Ordner. Erstellen Sie im Terminal ein „goldenes“ Verzeichnis. Erstellen Sie unter diesem Verzeichnis die Verzeichnisse `src` und `test`. Erstellen Sie unter `src` die Verzeichnisse `app` und `library`. Erstellen Sie in `test` das Verzeichnis `test-library`. Verwenden Sie hierzu das Terminal in VS Code, oder klicken Sie in VS Code auf den übergeordneten Order und anschließend auf das Symbol „Neuer Ordner“.

Öffnen Sie in VS Code das „goldene“ Verzeichnis. Dieses Verzeichnis ist der Stamm der Projektmappe.

Als Nächstes erstellen Sie die Datei `global.json` im Stammverzeichnis für Ihre Projektmappe.
Die Datei `global.json` enthält Folgendes:

```json
{
    "projects": [
        "src",
        "test"
    ]
}
```

Ihre Verzeichnisstruktur sollte nun wie folgt aussehen:


```
/golden
|__global.json
|__/src
   |__/app
   |__/library
|__/test
   |__/test-library
```

### <a name="writing-the-library"></a>Schreiben der Bibliothek

Die nächste Aufgabe ist die Erstellung der Bibliothek. Wechseln Sie im Terminalfenster (im eingebetteten Terminal in VS Code oder in einem anderen Terminal) zum Verzeichnis `golden/src/library`, und geben Sie den Befehl `dotnet new -t lib` ein.
Dadurch wird ein Bibliotheksprojekt mit zwei Dateien erstellt: `project.json` und `Library.cs`.

`project.json` enthält folgende Informationen:

```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable"
  },
  "dependencies": {},
  "frameworks": {
    "netstandard1.6": {
      "dependencies": {
        "NETStandard.Library": "1.6.0"
      }
    }
  }
}
```


Diese Bibliotheksprojekt nutzt die JSON-Darstellung von Objekten. Daher sollten Sie einen Verweis auf das NuGet-Paket `Newtonsoft.Json` hinzufügen. Fügen Sie in `project.json` die neueste Vorabversion des Pakets als Abhängigkeit hinzu:

```json
"dependencies": {
    "Newtonsoft.Json": "9.0.1-beta1"
},
```

Nachdem Sie diese Abhängigkeiten hinzugefügt haben, müssen Sie diese Pakete im Arbeitsbereich installieren. Führen Sie den Befehl `dotnet restore` aus, um alle Abhängigkeiten zu aktualisieren, und speichern Sie die Datei `project.lock.json` im Projektverzeichnis. Diese Datei enthält die vollständige Abhängigkeitsstruktur aller Abhängigkeiten in Ihrem Projekt. Sie müssen diese Datei nicht lesen. Sie wird von Tools im .NET Core SDK verwendet.

Aktualisieren Sie als Nächstes den C#-Code. Erstellen Sie eine `Thing`-Klasse, die eine öffentliche Methode enthält. Diese Methode gibt die Summe zweier Zahlen zurück. Hierzu werden diese Zahlen jedoch in eine JSON-Zeichenfolge konvertiert und anschließend deserialisiert. Benennen Sie die Datei `Library.cs` in `Thing.cs` um. Ersetzen Sie den vorhandenen Code (für die mittels Vorlage generierte Class1) durch folgenden Code:

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

Nun haben Sie die Datei `library.dll` im Verzeichnis `golden/src/library/bin/Debug/netstandard1.6` erstellt.

### <a name="writing-the-test-project"></a>Schreiben des Testprojekts

Erstellen Sie ein Testprojekt für die von Ihnen erstellte Bibliothek. Wechseln Sie in das Verzeichnis `test/test-library`. Führen Sie `dotnet new -t xunittest` aus, um ein neues Testprojekt zu erstellen. 

Für die in den obigen Schritten erstellte Bibliothek müssen Sie einen Abhängigkeitsknoten hinzufügen. Öffnen Sie `project.json`, und aktualisieren Sie den Abschnitt „dependencies“ wie folgt (auch den Knoten `library`, der hier der letzte Knoten ist):

```json
"dependencies": {
  "System.Runtime.Serialization.Primitives": "4.1.1",
  "xunit": "2.1.0",
  "dotnet-test-xunit": "1.0.0-rc2-192208-24",
  "library": {
    "target": "project"
  }
}
```

Der Knoten `library` gibt an, dass diese Abhängigkeit in ein Projekt im aktuellen Arbeitsbereich aufgelöst werden soll. Ohne diese explizite Angabe ist es möglich, dass das Testprojekt für ein NuGet-Paket mit demselben Namen erstellt wird.

Nachdem Sie die Abhängigkeiten ordnungsgemäß konfiguriert haben, erstellen Sie nun die Tests für Ihre Bibliothek. Öffnen Sie `Tests.cs`, und ersetzen Sie den Inhalt durch den folgenden Code:

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

Führen Sie nun `dotnet restore`, `dotnet build` und `dotnet test` aus.
Der Test Runner der xUnit-Konsole führt den einen Test aus und meldet, dass er erfolgreich verlaufen ist. 

### <a name="writing-the-console-app"></a>Schreiben der Konsolenanwendung

Wechseln Sie in Ihrem Terminal in das Verzeichnis `golden/src/app`. Führen Sie `dotnet new` aus, um eine neue Konsolenanwendung zu erstellen.

Die Konsolenanwendung hängt von der erstellten Bibliothek ab, die Sie in den vorherigen Schritten erstellt und getestet haben. Dies müssen Sie angeben, indem Sie `project.json` bearbeiten und diese Abhängigkeit hinzufügen.  Fügen Sie im Knoten `dependencies` den Knoten `library` wie folgt hinzu:

```json
"dependencies": {
  "library": {
    "target": "project"
  }
}
```

Der Knoten `project` ist hier wichtig, da er sich in der Testbibliothek befunden hat. Er gibt an, dass dies kein NuGet-Paket, sondern ein Projekt in der aktuellen Projektmappe ist.

Führen Sie `dotnet restore` aus, um alle Abhängigkeiten wiederherzustellen. Öffnen Sie `program.cs`, und ersetzen Sie den Inhalt der `Main`-Methode durch diese Zeile:

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

Am Anfang der Datei müssen Sie einige `using`-Anweisungen hinzufügen:

```csharp
using static System.Console;
using Library;
```

Führen Sie anschließend `dotnet build` aus. Damit werden die Assemblys erstellt, und Sie können `dotnet run` eingeben, um die ausführbare Datei auszuführen.

### <a name="debugging-your-application"></a>Debuggen der Anwendung

Sie können Ihren Code in VS Code mithilfe der C#-Erweiterung debuggen.
Installieren Sie diese Erweiterung, indem Sie `F1` drücken, um die VS Code-Palette zu öffnen. Geben Sie `ext install` ein, um die Liste mit Erweiterungen anzuzeigen. Wählen Sie die C#-Erweiterung aus. (Weitere Details finden Sie auf der Seite mit der [Dokumentation zur C#-Erweiterung von Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).)

Nachdem Sie die Erweiterung installiert haben, werden Sie von VS Code aufgefordert, die Anwendung neu zu starten, um die neue Erweiterung zu laden. Nach der Installation der Erweiterung können Sie die Registerkarte „Debugger“ aufrufen (siehe Abbildung).

![VS Code-Debugger](./media/using-on-macos/vscodedebugger.png)


Wenn Sie den Debugger starten, werden Sie von VS Code angewiesen, den Debugger zu konfigurieren. Dabei wird das Verzeichnis `.vscode` mit zwei Dateien erstellt: `tasks.json` und `launch.json`. Diese beiden Dateien steuern die Debugger-Konfiguration. Bei den meisten Projekten ist dieses Verzeichnis nicht in der Quellcodeverwaltung enthalten.
Es ist in dem Beispiel enthalten, das mit dieser exemplarischen Vorgehensweise verbunden ist, sodass Sie erkennen können, welche Änderungen Sie vornehmen müssen.

Ihre Projektmappe enthält mehrere Projekte. Daher sollten Sie diese Dateien anpassen, damit die richtigen Befehle ausgeführt werden. Öffnen Sie zunächst `tasks.json`. Die standardmäßige Buildaufgabe führt `dotnet build` im Quellverzeichnis des Arbeitsbereichs aus. Sie möchten sie jedoch im Verzeichnis `src/app` ausführen. Daher müssen Sie den Knoten `options` hinzufügen, um das aktuelle Arbeitsverzeichnis wie folgt festzulegen:

```json
"options": {
    "cwd": "${workspaceRoot}/src/app"
}
```

Als Nächstes müssen `launch.json` öffnen und den Programmpfad aktualisieren. Unter „configurations“ ist ein Knoten angegeben, der das Programm beschreibt. Folgendes wird angezeigt:

```json
"program": "${workspaceRoot}/bin/Debug/<target-framework>/<project-name.dll>",
```

Ändern Sie dies wie folgt:

```json
"program": "${workspaceRoot}/src/app/bin/Debug/netcoreapp1.0/app.dll",
```

Wenn Sie mit Windows arbeiten, müssen Sie die Datei `project.json` der Anwendung (im Verzeichnis `src/app`) aktualisieren, damit portierbare PDB-Dateien erstellt werden. (Unter Mac OSX und Linux werden diese Dateien automatisch erstellt.)
Fügen Sie in `buildOptions` den Knoten `debugType` hinzu. Sie müssen den Knoten `debugType` in `project.json` für die beiden Ordner `src/app` und `src/library` hinzufügen.

```json
  "buildOptions": {
    "debugType": "portable"
  },
```

Legen Sie bei der Anweisung `WriteLine` in `Main` einen Haltepunkt fest. Drücken Sie hierzu die Taste `F9`, oder klicken Sie an den linken Rand der Zeile, in der Sie den Haltepunkt festlegen möchten. Öffnen Sie den Debugger, indem Sie auf das Debugger-Symbol links im VS Code-Bildschirm klicken (siehe Abbildung). Klicken Sie anschließend auf die Schaltfläche „Wiedergabe“, um die Anwendung unter dem Debugger zu starten.

Sie sollten beim Haltepunkt ankommen. Führen Sie die `Get`-Methode schrittweise aus, und stellen Sie sicher, dass Sie die richtigen Argumente eingefügt haben. Stellen Sie sicher, dass die Antwort tatsächlich 42 lautet.



<!--HONumber=Jan17_HO3-->


