---
title: Erste Schritte mit .NET Core unter Verwendung der CLI
description: Dies ist ein Tutorial zu den ersten Schritte mit .NET Core unter Windows, Linux oder macOS unter Verwendung der .NET Core-CLI.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: af1b374cd14d5070194c035024ce2328c9016646
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503546"
---
# <a name="get-started-with-net-core-using-the-net-core-cli"></a>Erste Schritte mit .NET Core unter Verwendung der .NET Core-CLI

In diesem Artikel wird erläutert, wie Sie die .NET Core-CLI verwenden, um .NET Core-Apps zu entwickeln, die unter Windows, Linux und macOS funktionieren.

Wenn Sie mit der .NET Core-CLI nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über die .NET Core-CLI](../tools/index.md).

## <a name="prerequisites"></a>Voraussetzungen

- [.NET Core SDK 3.1](https://dotnet.microsoft.com/download) oder neuere Version
- Ein Text-Editor oder Code-Editor Ihrer Wahl.

## <a name="hello-console-app"></a>Hallo Konsolenanwendung!

Sie können den Beispielcode im Repository „dotnet/samples“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild). Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*. Navigieren Sie zum erstellten Ordner, und geben Sie Folgendes ein.

```dotnetcli
dotnet new console
dotnet run
```

Hier eine kurze Beschreibung der Schritte:

01. `dotnet new console`

    Mit [dotnet new](../tools/dotnet-new.md) wird eine aktuelle Projektdatei *Hello.csproj* mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden. Zudem wird *Program.cs* erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.
    
    *Hello.csproj*:
    
    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]
    
    Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.
    
    - Das Element `<OutputType>` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.
    - Das Element `<TargetFramework>` gibt an, welche .NET-Implementierung verwendet werden soll. In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für diese in einem einzigen Vorgang vornehmen. In diesem Tutorial beschränken wir uns auf Builds für .NET Core 3.1.
    
    *Program.cs*:
    
    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]
    
    Das Programm startet mithilfe von `using System`, was bedeutet, dass alles im Namespace `System` in den Geltungsbereich für diese Datei gebracht wird. Der `System`-Namespace enthält die `Console`-Klasse.
    
    Wir definieren dann einen Namespace namens `Hello`. Sie können diesen Namen nach Wunsch ändern. Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen namens `args` verwendet. Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das Programm ausgeführt wird. Allerdings wird dieses Array nicht verwendet, und das Programm gibt lediglich den Text „Hello World!“ auf der Konsole aus. Später werden wir Änderungen am Code vornehmen, die dieses Argument verwenden.
    
    `dotnet new` ruft [dotnet restore](../tools/dotnet-restore.md) implizit auf. `dotnet restore` führt einen Aufruf in [NuGet](https://www.nuget.org/) (dem Paket-Manager von .NET) aus, um die Struktur der Abhängigkeiten wiederherzustellen. NuGet analysiert die *Hello.csproj*-Datei, lädt die in der Datei definierten Abhängigkeiten herunter (oder ruft diese aus einem Cache auf Ihrem Computer ab) und schreibt die *obj/project.assets.json*-Datei, die zum Kompilieren und Ausführen des Beispiels erforderlich ist.

02. `dotnet run`

    [dotnet run](../tools/dotnet-run.md) ruft [dotnet build](../tools/dotnet-build.md) auf, um sicherzustellen, dass die Buildziele erstellt wurden, und ruft anschließend `dotnet <assembly.dll>` auf, um die Zielanwendung auszuführen.
    
    ```dotnetcli
    dotnet run
    ```

    Sie erhalten die folgende Ausgabe.

    ```console
    Hello World!
    ```
    
    Sie können alternativ `dotnet build` ausführen, um den Code zu kompilieren, ohne die Konsolenanwendungen des Builds auszuführen. Dies führt zu einer als DLL-Datei kompilierten Anwendung, die auf dem Namen des Projekts basiert. In diesem Fall wird die erstellte Datei mit *Hello.dll*  benannt. Diese App kann mit `dotnet bin\Debug\netcoreapp3.1\Hello.dll` unter Windows ausgeführt werden (verwenden Sie für Nicht-Windows-Systeme `/`).
    
    ```dotnetcli
    dotnet bin\Debug\netcoreapp3.1\Hello.dll
    ```

    Sie erhalten die folgende Ausgabe.

    ```console
    Hello World!
    ```
    
    Beim Kompilieren der App wurde neben `Hello.dll` eine betriebssystemspezifische ausführbare Datei erstellt. Unter Windows lautet ihr Name `Hello.exe`, unter Linux oder macOS `hello`. Im obigen Beispiel wird die Datei mit `Hello.exe` oder `Hello` benannt. Sie können diese ausführbare Datei direkt ausführen.

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a>Ändern des Programms

Ändern wir das Programm ein bisschen. Fibonacci-Zahlen sind interessant, also fügen wir sie zusätzlich zur Verwendung des Arguments für die Begrüßung der Person hinzu, die die Anwendung ausführt.

01. Ersetzen Sie den Inhalt der *Program.cs*-Datei durch den folgenden Code:

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. Führen Sie [dotnet build](../tools/dotnet-build.md) aus, um diese Änderungen zu kompilieren.

03. Führen Sie das Programm aus, und übergeben Sie einen Parameter an die App. Wenn Sie den `dotnet`-Befehl verwenden, um eine App auszuführen, fügen Sie `--` am Ende hinzu. Alles rechts von `--` wird als Parameter an die App übergeben. Im folgenden Beispiel wird der Wert `John` an die App übergeben.

    ```dotnetcli
    dotnet run -- John
    ```

    Sie erhalten die folgende Ausgabe.

    ```console
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

Und das ist schon alles! Sie können *Program.cs* beliebig ändern.

## <a name="working-with-multiple-files"></a>Arbeiten mit mehreren Dateien

Einzelne Dateien eignen sich gut für einfache einmalige Programme, aber wenn Sie eine komplexere App erstellen, verfügen Sie wahrscheinlich über mehrere Codedateien in Ihrem Projekt. Wir bauen dazu auf dem vorherigen Fibonacci-Beispiel auf, indem wir Fibonacci-Werte zwischenspeichern und einige rekursive Features hinzufügen.

01. Fügen Sie eine neue Datei im *Hello*-Verzeichnis mit dem Namen *FibonacciGenerator.cs* durch den folgenden Code hinzu:

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. Ändern Sie die `Main`-Methode in Ihrer *Program.cs*-Datei, um die neue Klasse zu instanziieren und rufen Sie die Methode wie im folgenden Beispiel auf:

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. Führen Sie [dotnet build](../tools/dotnet-build.md) aus, um diese Änderungen zu kompilieren.

04. Führen Sie Ihre App aus, indem Sie [dotnet run](../tools/dotnet-run.md) ausführen.

    ```dotnetcli
    dotnet run
    ```

    Sie erhalten die folgende Ausgabe.

    ```console
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

Sobald Sie bereit sind, Ihre App zu verteilen, führen Sie den Befehl [dotnet publish](../tools/dotnet-publish.md) aus, um den Ordner _publish_ unter _bin\\debug\\netcoreapp3.1\\publish\\_ zu erzeugen (verwenden Sie für Nicht-Windows-Systeme `/`). Sie können den Inhalt des Ordners _publish_ auf andere Plattformen verteilen, sofern auf diesen bereits die .NET-Laufzeit installiert ist.

```dotnetcli
dotnet publish
```

Sie erhalten eine Ausgabe ähnlich der folgenden.

```console
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

Die obige Ausgabe kann sich je nach Ihrem aktuellen Ordner und Betriebssystem unterscheiden, aber die Ausgabe sollte ähnlich sein.

Sie können Ihre veröffentlichte App mit dem Befehl [dotnet](../tools/dotnet.md) ausführen:

```dotnetcli
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll
```

Sie erhalten die folgende Ausgabe.

```console
Hello World!
```

Wie am Anfang dieses Artikels erwähnt, wurde beim Kompilieren der App neben `Hello.dll` eine betriebssystemspezifische ausführbare Datei erstellt. Unter Windows lautet ihr Name `Hello.exe`, unter Linux oder macOS `hello`. Im obigen Beispiel wird die Datei mit `Hello.exe` oder `Hello` benannt. Sie können diese veröffentlichte ausführbare Datei direkt ausführen.

```console
.\bin\Debug\netcoreapp3.1\publish\Hello.exe

Hello World!
```

## <a name="conclusion"></a>Schlussbemerkung

Und das ist schon alles! Nun können Sie beginnen, die grundlegenden Konzepte zur Erstellung Ihrer eigene Programme zu nutzen.

## <a name="see-also"></a>Siehe auch

- [Organisieren und Testen von Projekten mit der .NET Core-CLI](testing-with-cli.md)
- [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](../deploying/deploy-with-cli.md)
- [.NET Core-Anwendungsbereitstellung](../deploying/index.md)
