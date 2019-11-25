---
title: Erste Schritte mit .NET Core unter Verwendung der CLI
description: Erste Schritte mit .NET Core unter Windows, Linux oder Mac OS unter Verwendung der .NET Core-Befehlszeilenschnittstelle (CLI).
author: thraka
ms.author: adegeo
ms.date: 08/07/2019
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: cf8c3ae070f4c77789dc55ba4d7888c7b15c8653
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736989"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Erste Schritte mit .NET Core unter Windows/Linux/macOS unter Verwendung der Befehlszeile

In diesem Thema erfahren Sie, wie Sie plattformübergreifende Anwendungen mit .NET Core CLI-Tools auf Ihrem Computer erstellen können.

Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/index.md).

## <a name="prerequisites"></a>Erforderliche Komponenten

- [.NET Core SDK 2.1](https://dotnet.microsoft.com/download) oder neuere Version
- Ein Text-Editor oder Code-Editor Ihrer Wahl.

## <a name="hello-console-app"></a>Hallo Konsolenanwendung!

Sie können den Beispielcode im Repository „dotnet/samples“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild). Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*. Navigieren Sie zum erstellten Ordner, und geben Sie Folgendes ein:

```dotnetcli
dotnet new console
dotnet run
```

Hier eine kurze Beschreibung der Schritte:

1. `dotnet new console`

   Mit [`dotnet new`](../tools/dotnet-new.md) wird eine aktuelle Projektdatei *Hello.csproj* mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden. Zudem wird *Program.cs* erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.

   *Hello.csproj*:

   [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.

   - Das Tag `OutputType` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.
   - Das Tag `TargetFramework` gibt an, welche .NET-Implementierung verwendet werden soll. In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für diese in einem einzigen Vorgang vornehmen. In diesem Tutorial beschränken wir uns auf Builds für .NET Core 2.1.

   *Program.cs*:

   [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]

   Das Programm startet mithilfe von `using System`, was bedeutet, dass alles im Namespace `System` in den Geltungsbereich für diese Datei gebracht wird. Der `System`-Namespace enthält die `Console`-Klasse.

   Wir definieren dann einen Namespace namens `Hello`. Sie können diesen Namen nach Wunsch ändern. Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen als Argument verwendet. Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird. Dieses Array wird allerdings nicht verwendet. Die Anwendung gibt lediglich „Hello World!“ auf der Konsole aus. Später werden wir Änderungen am Code vornehmen, die dieses Argument verwenden.

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   `dotnet new` ruft [`dotnet restore`](../tools/dotnet-restore.md) implizit auf. `dotnet restore` führt einen Aufruf in [NuGet](https://www.nuget.org/) (dem Paket-Manager von .NET) aus, um die Struktur der Abhängigkeiten wiederherzustellen. NuGet analysiert die *Hello.csproj*-Datei, lädt die in der Datei definierten Abhängigkeiten herunter (oder ruft diese aus einem Cache auf Ihrem Computer ab) und schreibt die *obj/project.assets.json*-Datei, die zum Kompilieren und Ausführen des Beispiels erforderlich ist.

   > [!IMPORTANT]
   > Wenn Sie eine .NET Core 1.x-Version des SDKs verwenden, müssen Sie `dotnet restore` nach dem Aufrufen von `dotnet new` selbst aufrufen.

2. `dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) ruft [`dotnet build`](../tools/dotnet-build.md) auf, um sicherzustellen, dass die Buildziele erstellt wurden, und ruft anschließend `dotnet <assembly.dll>` auf, um die Zielanwendung auszuführen.

    ```console
    $ dotnet run
    Hello World!
    ```

    Sie können alternativ [`dotnet build`](../tools/dotnet-build.md) ausführen, um den Code zu kompilieren, ohne die Konsolenanwendungen des Builds auszuführen. Dies führt zu einer kompilierten Anwendung, wie einer DLL-Datei, die mit `dotnet bin\Debug\netcoreapp2.1\Hello.dll` unter Windows ausgeführt werden kann (verwenden Sie `/` für nicht-Windowssysteme). Sie können auch Argumente für die Anwendung angeben, wie Sie später im Thema sehen werden.

    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    In einem komplexen Szenario ist es möglich, die Anwendung als eigenständigen Satz plattformspezifischer Dateien zu erstellen, die auf einen Computer bereitgestellt und ausgeführt werden können, auf dem nicht notwendigerweise .NET Core installiert ist. Details finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).

### <a name="augmenting-the-program"></a>Erweitern des Programms

Ändern wir das Programm ein bisschen. Fibonacci-Zahlen sind interessant, also fügen wir sie zusätzlich zur Verwendung des Arguments für die Begrüßung der Person hinzu, die die Anwendung ausführt.

1. Ersetzen Sie den Inhalt der *Program.cs*-Datei durch den folgenden Code:

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. Führen Sie [`dotnet build`](../tools/dotnet-build.md) aus, um diese Änderungen zu kompilieren.

3. Führen Sie das Programm aus, das einen Parameter für die App übergibt:

   ```console
   $ dotnet run -- John
   Hello John!
   Fibonacci Numbers 1-15:
   1: 0
   2: 1
   3: 1
   4: 2
   5: 3
   6: 5
   7: 8
   8: 13
   9: 21
   10: 34
   11: 55
   12: 89
   13: 144
   14: 233
   15: 377
   ```

Und das ist schon alles!  Sie können *Program.cs* beliebig erweitern.

## <a name="working-with-multiple-files"></a>Arbeiten mit mehreren Dateien

Einzelne Dateien eignen sich gut für einfache einmalige Programme, aber wenn Sie eine komplexere App erstellen, verfügen Sie wahrscheinlich über mehrere Quelldateien in Ihrem Projekt.
Wir bauen dazu auf dem vorherigen Fibonacci-Beispiel auf, indem wir Fibonacci-Werte zwischenspeichern und einige rekursive Features hinzufügen.

1. Fügen Sie eine neue Datei im *Hello*-Verzeichnis mit dem Namen *FibonacciGenerator.cs* durch den folgenden Code hinzu:

   [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. Ändern Sie die `Main`-Methode in Ihrer *Program.cs*-Datei, um die neue Klasse zu instanziieren und rufen Sie die Methode wie im folgenden Beispiel auf:

   [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. Führen Sie [`dotnet build`](../tools/dotnet-build.md) aus, um diese Änderungen zu kompilieren.

4. Führen Sie Ihre App durch, indem Sie [`dotnet run`](../tools/dotnet-run.md) ausführen. Nachfolgend sehen Sie die Programmausgabe:

   ```console
   $ dotnet run
   0
   1
   1
   2
   3
   5
   8
   13
   21
   34
   55
   89
   144
   233
   377
   ```

## <a name="publish-your-app"></a>Veröffentlichen der App

Sobald Sie bereit sind, Ihre App zu verteilen, führen Sie den Befehl [`dotnet publish`](../tools/dotnet-publish.md) aus, um den Ordner _publish_ unter _bin\\debug\\netcoreapp2.1\\publish\\_ zu erzeugen (verwenden Sie für Nicht-Windows-Systeme `/`). Sie können den Inhalt des Ordners _publish_ auf andere Plattformen verteilen, sofern auf diesen bereits die .NET-Laufzeit installiert ist.

Sie können Ihre veröffentlichte App mit dem Befehl [dotnet](../tools/dotnet.md) ausführen:

```console
$ dotnet bin\Debug\netcoreapp2.1\publish\Hello.dll
Hello World!
```

## <a name="conclusion"></a>Schlussbemerkung

Und das ist schon alles! Nun können Sie beginnen, die grundlegenden Konzepte zur Erstellung Ihrer eigene Programme zu nutzen.

## <a name="see-also"></a>Siehe auch

- [Organisieren und Testen von Projekten mit .NET Core CLI-Tools](testing-with-cli.md)
- [Veröffentlichen von .NET Core-Apps mit der CLI](../deploying/deploy-with-cli.md)
- [Weitere Informationen zur App-Bereitstellung](../deploying/index.md)
