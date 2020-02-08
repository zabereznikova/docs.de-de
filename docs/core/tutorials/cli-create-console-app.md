---
title: Erste Schritte mit .NET Core unter Verwendung der CLI
description: Dies ist ein Tutorial zu den ersten Schritte mit .NET Core unter Windows, Linux oder macOS unter Verwendung der .NET Core-CLI.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: 6e1c7881aa415ea54307d80214001a2f0fe5b4a6
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920464"
---
# <a name="get-started-with-net-core-using-the-net-core-cli"></a><span data-ttu-id="a76c8-103">Erste Schritte mit .NET Core unter Verwendung der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="a76c8-103">Get started with .NET Core using the .NET Core CLI</span></span>

<span data-ttu-id="a76c8-104">In diesem Artikel wird erläutert, wie Sie die .NET Core-CLI verwenden, um .NET Core-Apps zu entwickeln, die unter Windows, Linux und macOS funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a76c8-104">This article will show you how to start developing .NET Core apps that work on Windows, Linux, and macOS using the .NET Core CLI.</span></span>

<span data-ttu-id="a76c8-105">Wenn Sie mit der .NET Core-CLI nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über die .NET Core-CLI](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="a76c8-105">If you're unfamiliar with the .NET Core CLI, see the [.NET Core CLI overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a76c8-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a76c8-106">Prerequisites</span></span>

- <span data-ttu-id="a76c8-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) oder neuere Version</span><span class="sxs-lookup"><span data-stu-id="a76c8-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="a76c8-108">Ein Text-Editor oder Code-Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="a76c8-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="a76c8-109">Hallo Konsolenanwendung!</span><span class="sxs-lookup"><span data-stu-id="a76c8-109">Hello, Console App!</span></span>

<span data-ttu-id="a76c8-110">Sie können den Beispielcode im Repository „dotnet/samples“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild).</span><span class="sxs-lookup"><span data-stu-id="a76c8-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="a76c8-111">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="a76c8-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="a76c8-112">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*.</span><span class="sxs-lookup"><span data-stu-id="a76c8-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="a76c8-113">Navigieren Sie zum erstellten Ordner, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a76c8-113">Navigate to the folder you created and type the following:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="a76c8-114">Hier eine kurze Beschreibung der Schritte:</span><span class="sxs-lookup"><span data-stu-id="a76c8-114">Let's do a quick walkthrough:</span></span>

01. `dotnet new console`

    <span data-ttu-id="a76c8-115">Mit [dotnet new](../tools/dotnet-new.md) wird eine aktuelle Projektdatei *Hello.csproj* mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a76c8-115">[dotnet new](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="a76c8-116">Zudem wird *Program.cs* erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="a76c8-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>
    
    <span data-ttu-id="a76c8-117">*Hello.csproj*:</span><span class="sxs-lookup"><span data-stu-id="a76c8-117">*Hello.csproj*:</span></span>
    
    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]
    
    <span data-ttu-id="a76c8-118">Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a76c8-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>
    
    - <span data-ttu-id="a76c8-119">Das Element `<OutputType>` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-119">The `<OutputType>` element specifies that we're building an executable, in other words a console application.</span></span>
    - <span data-ttu-id="a76c8-120">Das Element `<TargetFramework>` gibt an, welche .NET-Implementierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a76c8-120">The `<TargetFramework>` element specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="a76c8-121">In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für diese in einem einzigen Vorgang vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="a76c8-122">In diesem Tutorial beschränken wir uns auf Builds für .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="a76c8-122">In this tutorial, we'll stick to building only for .NET Core 3.1.</span></span>
    
    <span data-ttu-id="a76c8-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="a76c8-123">*Program.cs*:</span></span>
    
    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]
    
    <span data-ttu-id="a76c8-124">Das Programm startet mithilfe von `using System`, was bedeutet, dass alles im Namespace `System` in den Geltungsbereich für diese Datei gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="a76c8-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="a76c8-125">Der `System`-Namespace enthält die `Console`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="a76c8-125">The `System` namespace includes the `Console` class.</span></span>
    
    <span data-ttu-id="a76c8-126">Wir definieren dann einen Namespace namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="a76c8-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="a76c8-127">Sie können diesen Namen nach Wunsch ändern.</span><span class="sxs-lookup"><span data-stu-id="a76c8-127">You can change this to anything you want.</span></span> <span data-ttu-id="a76c8-128">Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen namens `args` verwendet.</span><span class="sxs-lookup"><span data-stu-id="a76c8-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings named `args`.</span></span> <span data-ttu-id="a76c8-129">Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a76c8-129">This array contains the list of arguments passed in when the program is run.</span></span> <span data-ttu-id="a76c8-130">Allerdings wird dieses Array nicht verwendet, und das Programm gibt lediglich den Text „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="a76c8-130">As it is, this array is not used and the program simply writes the text "Hello World!"</span></span> <span data-ttu-id="a76c8-131">auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="a76c8-131">to the console.</span></span> <span data-ttu-id="a76c8-132">Später werden wir Änderungen am Code vornehmen, die dieses Argument verwenden.</span><span class="sxs-lookup"><span data-stu-id="a76c8-132">Later, we'll make changes to the code that will make use of this argument.</span></span>
    
    <span data-ttu-id="a76c8-133">`dotnet new` ruft [dotnet restore](../tools/dotnet-restore.md) implizit auf.</span><span class="sxs-lookup"><span data-stu-id="a76c8-133">`dotnet new` calls [dotnet restore](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="a76c8-134">`dotnet restore` führt einen Aufruf in [NuGet](https://www.nuget.org/) (dem Paket-Manager von .NET) aus, um die Struktur der Abhängigkeiten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="a76c8-135">NuGet analysiert die *Hello.csproj*-Datei, lädt die in der Datei definierten Abhängigkeiten herunter (oder ruft diese aus einem Cache auf Ihrem Computer ab) und schreibt die *obj/project.assets.json*-Datei, die zum Kompilieren und Ausführen des Beispiels erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a76c8-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

02. `dotnet run`

    <span data-ttu-id="a76c8-136">[dotnet run](../tools/dotnet-run.md) ruft [dotnet build](../tools/dotnet-build.md) auf, um sicherzustellen, dass die Buildziele erstellt wurden, und ruft anschließend `dotnet <assembly.dll>` auf, um die Zielanwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-136">[dotnet run](../tools/dotnet-run.md) calls [dotnet build](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>
    
    ```console
    dotnet run

    Hello World!
    ```
    
    <span data-ttu-id="a76c8-137">Sie können alternativ `dotnet build` ausführen, um den Code zu kompilieren, ohne die Konsolenanwendungen des Builds auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-137">Alternatively, you can also run `dotnet build` to compile the code without running the build console applications.</span></span> <span data-ttu-id="a76c8-138">Dies führt zu einer als DLL-Datei kompilierten Anwendung, die auf dem Namen des Projekts basiert.</span><span class="sxs-lookup"><span data-stu-id="a76c8-138">This results in a compiled application, as a DLL file, based on the name of the project.</span></span> <span data-ttu-id="a76c8-139">In diesem Fall wird die erstellte Datei mit *Hello.dll*  benannt.</span><span class="sxs-lookup"><span data-stu-id="a76c8-139">In this case, the file created is named *Hello.dll*.</span></span> <span data-ttu-id="a76c8-140">Diese App kann mit `dotnet bin\Debug\netcoreapp3.1\Hello.dll` unter Windows ausgeführt werden (verwenden Sie für Nicht-Windows-Systeme `/`).</span><span class="sxs-lookup"><span data-stu-id="a76c8-140">This app can be run with `dotnet bin\Debug\netcoreapp3.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span>
    
    ```console
    dotnet bin\Debug\netcoreapp3.1\Hello.dll

    Hello World!
    ```
    
    <span data-ttu-id="a76c8-141">Beim Kompilieren der App wurde neben `Hello.dll` eine betriebssystemspezifische ausführbare Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="a76c8-141">When the app is compiled, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="a76c8-142">Unter Windows lautet ihr Name `Hello.exe`, unter Linux oder macOS `hello`.</span><span class="sxs-lookup"><span data-stu-id="a76c8-142">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="a76c8-143">Im obigen Beispiel wird die Datei mit `Hello.exe` oder `Hello` benannt.</span><span class="sxs-lookup"><span data-stu-id="a76c8-143">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="a76c8-144">Sie können diese ausführbare Datei direkt ausführen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-144">You can run that executable directly.</span></span>

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a><span data-ttu-id="a76c8-145">Ändern des Programms</span><span class="sxs-lookup"><span data-stu-id="a76c8-145">Modify the program</span></span>

<span data-ttu-id="a76c8-146">Ändern wir das Programm ein bisschen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-146">Let's change the program a bit.</span></span> <span data-ttu-id="a76c8-147">Fibonacci-Zahlen sind interessant, also fügen wir sie zusätzlich zur Verwendung des Arguments für die Begrüßung der Person hinzu, die die Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="a76c8-147">Fibonacci numbers are fun, so let's add that and also to use the argument to greet the person running the app.</span></span>

01. <span data-ttu-id="a76c8-148">Ersetzen Sie den Inhalt der *Program.cs*-Datei durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="a76c8-148">Replace the contents of your *Program.cs*  file with the following code:</span></span>

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. <span data-ttu-id="a76c8-149">Führen Sie [dotnet build](../tools/dotnet-build.md) aus, um diese Änderungen zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a76c8-149">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

03. <span data-ttu-id="a76c8-150">Führen Sie das Programm aus, und übergeben Sie einen Parameter an die App.</span><span class="sxs-lookup"><span data-stu-id="a76c8-150">Run the program passing a parameter to the app.</span></span> <span data-ttu-id="a76c8-151">Wenn Sie den `dotnet`-Befehl verwenden, um eine App auszuführen, fügen Sie `--` am Ende hinzu.</span><span class="sxs-lookup"><span data-stu-id="a76c8-151">When you use the `dotnet` command to run an app, add `--` to the end.</span></span> <span data-ttu-id="a76c8-152">Alles rechts von `--` wird als Parameter an die App übergeben.</span><span class="sxs-lookup"><span data-stu-id="a76c8-152">Anything to the right of `--` will be passed as a parameter to the app.</span></span> <span data-ttu-id="a76c8-153">Im folgenden Beispiel wird der Wert `John` an die App übergeben.</span><span class="sxs-lookup"><span data-stu-id="a76c8-153">In the following example, the value `John` is passed to the app.</span></span>

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

<span data-ttu-id="a76c8-154">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="a76c8-154">And that's it!</span></span> <span data-ttu-id="a76c8-155">Sie können *Program.cs* beliebig ändern.</span><span class="sxs-lookup"><span data-stu-id="a76c8-155">You can modify *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="a76c8-156">Arbeiten mit mehreren Dateien</span><span class="sxs-lookup"><span data-stu-id="a76c8-156">Working with multiple files</span></span>

<span data-ttu-id="a76c8-157">Einzelne Dateien eignen sich gut für einfache einmalige Programme, aber wenn Sie eine komplexere App erstellen, verfügen Sie wahrscheinlich über mehrere Codedateien in Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="a76c8-157">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple code files on your project.</span></span> <span data-ttu-id="a76c8-158">Wir bauen dazu auf dem vorherigen Fibonacci-Beispiel auf, indem wir Fibonacci-Werte zwischenspeichern und einige rekursive Features hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-158">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

01. <span data-ttu-id="a76c8-159">Fügen Sie eine neue Datei im *Hello*-Verzeichnis mit dem Namen *FibonacciGenerator.cs* durch den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="a76c8-159">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. <span data-ttu-id="a76c8-160">Ändern Sie die `Main`-Methode in Ihrer *Program.cs*-Datei, um die neue Klasse zu instanziieren und rufen Sie die Methode wie im folgenden Beispiel auf:</span><span class="sxs-lookup"><span data-stu-id="a76c8-160">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. <span data-ttu-id="a76c8-161">Führen Sie [dotnet build](../tools/dotnet-build.md) aus, um diese Änderungen zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a76c8-161">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

04. <span data-ttu-id="a76c8-162">Führen Sie Ihre App aus, indem Sie [dotnet run](../tools/dotnet-run.md) ausführen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-162">Run your app by executing [dotnet run](../tools/dotnet-run.md).</span></span> <span data-ttu-id="a76c8-163">Nachfolgend sehen Sie die Programmausgabe:</span><span class="sxs-lookup"><span data-stu-id="a76c8-163">The following shows the program output:</span></span>

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

## <a name="publish-your-app"></a><span data-ttu-id="a76c8-164">Veröffentlichen der App</span><span class="sxs-lookup"><span data-stu-id="a76c8-164">Publish your app</span></span>

<span data-ttu-id="a76c8-165">Sobald Sie bereit sind, Ihre App zu verteilen, führen Sie den Befehl [dotnet publish](../tools/dotnet-publish.md) aus, um den Ordner _publish_ unter _bin\\debug\\netcoreapp3.1\\publish\\_ zu erzeugen (verwenden Sie für Nicht-Windows-Systeme `/`).</span><span class="sxs-lookup"><span data-stu-id="a76c8-165">Once you're ready to distribute your app, use the [dotnet publish](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp3.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="a76c8-166">Sie können den Inhalt des Ordners _publish_ auf andere Plattformen verteilen, sofern auf diesen bereits die .NET-Laufzeit installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a76c8-166">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

```console
dotnet publish
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

<span data-ttu-id="a76c8-167">Die obige Ausgabe kann sich je nach Ihrem aktuellen Ordner und Betriebssystem unterscheiden, aber die Ausgabe sollte ähnlich sein.</span><span class="sxs-lookup"><span data-stu-id="a76c8-167">The output above may differ based on your current folder and operating system, but the output should be similar.</span></span>

<span data-ttu-id="a76c8-168">Sie können Ihre veröffentlichte App mit dem Befehl [dotnet](../tools/dotnet.md) ausführen:</span><span class="sxs-lookup"><span data-stu-id="a76c8-168">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```console
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll

Hello World!
```

<span data-ttu-id="a76c8-169">Wie am Anfang dieses Artikels erwähnt, wurde beim Kompilieren der App neben `Hello.dll` eine betriebssystemspezifische ausführbare Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="a76c8-169">As mentioned at the start of this article, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="a76c8-170">Unter Windows lautet ihr Name `Hello.exe`, unter Linux oder macOS `hello`.</span><span class="sxs-lookup"><span data-stu-id="a76c8-170">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="a76c8-171">Im obigen Beispiel wird die Datei mit `Hello.exe` oder `Hello` benannt.</span><span class="sxs-lookup"><span data-stu-id="a76c8-171">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="a76c8-172">Sie können diese veröffentlichte ausführbare Datei direkt ausführen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-172">You can run this published executable directly.</span></span>

```console
.\bin\Debug\netcoreapp3.1\publish\Hello.exe

Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="a76c8-173">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="a76c8-173">Conclusion</span></span>

<span data-ttu-id="a76c8-174">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="a76c8-174">And that's it!</span></span> <span data-ttu-id="a76c8-175">Nun können Sie beginnen, die grundlegenden Konzepte zur Erstellung Ihrer eigene Programme zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="a76c8-175">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="a76c8-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a76c8-176">See also</span></span>

- [<span data-ttu-id="a76c8-177">Organisieren und Testen von Projekten mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="a76c8-177">Organizing and testing projects with the .NET Core CLI</span></span>](testing-with-cli.md)
- [<span data-ttu-id="a76c8-178">Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="a76c8-178">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="a76c8-179">.NET Core-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="a76c8-179">.NET Core application deployment</span></span>](../deploying/index.md)
