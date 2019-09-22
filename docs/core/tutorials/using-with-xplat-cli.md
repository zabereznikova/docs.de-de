---
title: Erste Schritte mit .NET Core unter Verwendung der CLI
description: Erste Schritte mit .NET Core unter Windows, Linux oder Mac OS unter Verwendung der .NET Core-Befehlszeilenschnittstelle (CLI).
author: thraka
ms.author: adegeo
ms.date: 08/07/2019
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: b5ef70967c8404dc5ce5b816bb9a1c3b1d7e4230
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117350"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="535bb-103">Erste Schritte mit .NET Core unter Windows/Linux/macOS unter Verwendung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="535bb-103">Get started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="535bb-104">In diesem Thema erfahren Sie, wie Sie plattformübergreifende Anwendungen mit .NET Core CLI-Tools auf Ihrem Computer erstellen können.</span><span class="sxs-lookup"><span data-stu-id="535bb-104">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="535bb-105">Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="535bb-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="535bb-106">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="535bb-106">Prerequisites</span></span>

- <span data-ttu-id="535bb-107">[.NET Core SDK 2.1](https://dotnet.microsoft.com/download) oder neuere Version</span><span class="sxs-lookup"><span data-stu-id="535bb-107">[.NET Core SDK 2.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="535bb-108">Ein Text-Editor oder Code-Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="535bb-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="535bb-109">Hallo Konsolenanwendung!</span><span class="sxs-lookup"><span data-stu-id="535bb-109">Hello, Console App!</span></span>

<span data-ttu-id="535bb-110">Sie können den Beispielcode im Repository „dotnet/samples“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild).</span><span class="sxs-lookup"><span data-stu-id="535bb-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="535bb-111">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="535bb-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="535bb-112">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*.</span><span class="sxs-lookup"><span data-stu-id="535bb-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="535bb-113">Navigieren Sie zum erstellten Ordner, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="535bb-113">Navigate to the folder you created and type the following:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="535bb-114">Hier eine kurze Beschreibung der Schritte:</span><span class="sxs-lookup"><span data-stu-id="535bb-114">Let's do a quick walkthrough:</span></span>

1. `dotnet new console`

   <span data-ttu-id="535bb-115">Mit [`dotnet new`](../tools/dotnet-new.md) wird eine aktuelle Projektdatei `Hello.csproj` mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="535bb-115">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="535bb-116">Zudem wird `Program.cs` erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="535bb-116">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="535bb-117">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="535bb-117">`Hello.csproj`:</span></span>

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   <span data-ttu-id="535bb-118">Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="535bb-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   - <span data-ttu-id="535bb-119">Das Tag `OutputType` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.</span><span class="sxs-lookup"><span data-stu-id="535bb-119">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   - <span data-ttu-id="535bb-120">Das Tag `TargetFramework` gibt an, welche .NET-Implementierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="535bb-120">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="535bb-121">In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für diese in einem einzigen Vorgang vornehmen.</span><span class="sxs-lookup"><span data-stu-id="535bb-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="535bb-122">In diesem Tutorial beschränken wir uns auf Builds für .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="535bb-122">In this tutorial, we'll stick to building only for .NET Core 2.1.</span></span>

   <span data-ttu-id="535bb-123">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="535bb-123">`Program.cs`:</span></span>

   [!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]

   <span data-ttu-id="535bb-124">Das Programm startet mithilfe von `using System`, was bedeutet, dass alles im Namespace `System` in den Geltungsbereich für diese Datei gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="535bb-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="535bb-125">Der Namespace `System` enthält grundlegende Konstrukte, wie z.B. `string`, oder numerische Typen.</span><span class="sxs-lookup"><span data-stu-id="535bb-125">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="535bb-126">Wir definieren dann einen Namespace namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="535bb-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="535bb-127">Sie können diesen Namen nach Wunsch ändern.</span><span class="sxs-lookup"><span data-stu-id="535bb-127">You can change this to anything you want.</span></span> <span data-ttu-id="535bb-128">Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="535bb-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="535bb-129">Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="535bb-129">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="535bb-130">Dieses Array wird allerdings nicht verwendet. Die Anwendung gibt lediglich „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="535bb-130">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="535bb-131">auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="535bb-131">to the console.</span></span> <span data-ttu-id="535bb-132">Später werden wir Änderungen am Code vornehmen, die dieses Argument verwenden.</span><span class="sxs-lookup"><span data-stu-id="535bb-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   <span data-ttu-id="535bb-133">`dotnet new` ruft [`dotnet restore`](../tools/dotnet-restore.md) implizit auf.</span><span class="sxs-lookup"><span data-stu-id="535bb-133">`dotnet new` calls [`dotnet restore`](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="535bb-134">`dotnet restore` führt einen Aufruf in [NuGet](https://www.nuget.org/) (dem Paket-Manager von .NET) aus, um die Struktur der Abhängigkeiten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="535bb-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="535bb-135">NuGet analysiert die *Hello.csproj*-Datei, lädt die in der Datei definierten Abhängigkeiten herunter (oder ruft diese aus einem Cache auf Ihrem Computer ab) und schreibt die *obj/project.assets.json*-Datei, die zum Kompilieren und Ausführen des Beispiels erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="535bb-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="535bb-136">Wenn Sie eine .NET Core 1.x-Version des SDKs verwenden, müssen Sie `dotnet restore` nach dem Aufrufen von `dotnet new` selbst aufrufen.</span><span class="sxs-lookup"><span data-stu-id="535bb-136">If you're using a .NET Core 1.x version of the SDK, you'll have to call `dotnet restore` yourself after calling `dotnet new`.</span></span>

2. `dotnet run`

   <span data-ttu-id="535bb-137">[`dotnet run`](../tools/dotnet-run.md) ruft [`dotnet build`](../tools/dotnet-build.md) auf, um sicherzustellen, dass die Buildziele erstellt wurden, und ruft anschließend `dotnet <assembly.dll>` auf, um die Zielanwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="535bb-137">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```console
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="535bb-138">Sie können alternativ [`dotnet build`](../tools/dotnet-build.md) ausführen, um den Code zu kompilieren, ohne die Konsolenanwendungen des Builds auszuführen.</span><span class="sxs-lookup"><span data-stu-id="535bb-138">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="535bb-139">Dies führt zu einer kompilierten Anwendung, wie einer DLL-Datei, die mit `dotnet bin\Debug\netcoreapp2.1\Hello.dll` unter Windows ausgeführt werden kann (verwenden Sie `/` für nicht-Windowssysteme).</span><span class="sxs-lookup"><span data-stu-id="535bb-139">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp2.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="535bb-140">Sie können auch Argumente für die Anwendung angeben, wie Sie später im Thema sehen werden.</span><span class="sxs-lookup"><span data-stu-id="535bb-140">You may also specify arguments to the application as you'll see later on the topic.</span></span>

    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="535bb-141">In einem komplexen Szenario ist es möglich, die Anwendung als eigenständigen Satz plattformspezifischer Dateien zu erstellen, die auf einen Computer bereitgestellt und ausgeführt werden können, auf dem nicht notwendigerweise .NET Core installiert ist.</span><span class="sxs-lookup"><span data-stu-id="535bb-141">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="535bb-142">Details finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="535bb-142">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="535bb-143">Erweitern des Programms</span><span class="sxs-lookup"><span data-stu-id="535bb-143">Augmenting the program</span></span>

<span data-ttu-id="535bb-144">Ändern wir das Programm ein bisschen.</span><span class="sxs-lookup"><span data-stu-id="535bb-144">Let's change the program a bit.</span></span> <span data-ttu-id="535bb-145">Fibonacci-Zahlen sind interessant, also fügen wir sie zusätzlich zur Verwendung des Arguments für die Begrüßung der Person hinzu, die die Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="535bb-145">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="535bb-146">Ersetzen Sie den Inhalt der *Program.cs*-Datei durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="535bb-146">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. <span data-ttu-id="535bb-147">Führen Sie [`dotnet build`](../tools/dotnet-build.md) aus, um diese Änderungen zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="535bb-147">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="535bb-148">Führen Sie das Programm aus, das einen Parameter für die App übergibt:</span><span class="sxs-lookup"><span data-stu-id="535bb-148">Run the program passing a parameter to the app:</span></span>

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

<span data-ttu-id="535bb-149">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="535bb-149">And that's it!</span></span>  <span data-ttu-id="535bb-150">Sie können `Program.cs` beliebig erweitern.</span><span class="sxs-lookup"><span data-stu-id="535bb-150">You can augment `Program.cs` any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="535bb-151">Arbeiten mit mehreren Dateien</span><span class="sxs-lookup"><span data-stu-id="535bb-151">Working with multiple files</span></span>

<span data-ttu-id="535bb-152">Einzelne Dateien eignen sich gut für einfache einmalige Programme, aber wenn Sie eine komplexere App erstellen, verfügen Sie wahrscheinlich über mehrere Quelldateien in Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="535bb-152">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project.</span></span>
<span data-ttu-id="535bb-153">Wir bauen dazu auf dem vorherigen Fibonacci-Beispiel auf, indem wir Fibonacci-Werte zwischenspeichern und einige rekursive Features hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="535bb-153">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

1. <span data-ttu-id="535bb-154">Fügen Sie eine neue Datei im *Hello*-Verzeichnis mit dem Namen *FibonacciGenerator.cs* durch den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="535bb-154">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   [!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. <span data-ttu-id="535bb-155">Ändern Sie die `Main`-Methode in Ihrer *Program.cs*-Datei, um die neue Klasse zu instanziieren und rufen Sie die Methode wie im folgenden Beispiel auf:</span><span class="sxs-lookup"><span data-stu-id="535bb-155">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   [!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. <span data-ttu-id="535bb-156">Führen Sie [`dotnet build`](../tools/dotnet-build.md) aus, um diese Änderungen zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="535bb-156">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="535bb-157">Führen Sie Ihre App durch, indem Sie [`dotnet run`](../tools/dotnet-run.md) ausführen.</span><span class="sxs-lookup"><span data-stu-id="535bb-157">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="535bb-158">Nachfolgend sehen Sie die Programmausgabe:</span><span class="sxs-lookup"><span data-stu-id="535bb-158">The following shows the program output:</span></span>

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

## <a name="publish-your-app"></a><span data-ttu-id="535bb-159">Veröffentlichen der App</span><span class="sxs-lookup"><span data-stu-id="535bb-159">Publish your app</span></span>

<span data-ttu-id="535bb-160">Sobald Sie bereit sind, Ihre App zu verteilen, führen Sie den Befehl [`dotnet publish`](../tools/dotnet-publish.md) aus, um den Ordner _publish_ unter _bin\\debug\\netcoreapp2.1\\publish\\_ zu erzeugen (verwenden Sie für Nicht-Windows-Systeme `/`).</span><span class="sxs-lookup"><span data-stu-id="535bb-160">Once you're ready to distribute your app, use the [`dotnet publish`](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp2.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="535bb-161">Sie können den Inhalt des Ordners _publish_ auf andere Plattformen verteilen, sofern auf diesen bereits die .NET-Laufzeit installiert ist.</span><span class="sxs-lookup"><span data-stu-id="535bb-161">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

<span data-ttu-id="535bb-162">Sie können Ihre veröffentlichte App mit dem Befehl [dotnet](../tools/dotnet.md) ausführen:</span><span class="sxs-lookup"><span data-stu-id="535bb-162">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```console
$ dotnet bin\Debug\netcoreapp2.1\publish\Hello.dll
Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="535bb-163">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="535bb-163">Conclusion</span></span>

<span data-ttu-id="535bb-164">Das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="535bb-164">And that's it!</span></span> <span data-ttu-id="535bb-165">Nun können Sie beginnen, die grundlegenden Konzepte zur Erstellung Ihrer eigene Programme zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="535bb-165">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="535bb-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="535bb-166">See also</span></span>

- [<span data-ttu-id="535bb-167">Organisieren und Testen von Projekten mit .NET Core CLI-Tools</span><span class="sxs-lookup"><span data-stu-id="535bb-167">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)
- [<span data-ttu-id="535bb-168">Veröffentlichen von .NET Core-Apps mit der CLI</span><span class="sxs-lookup"><span data-stu-id="535bb-168">Publish .NET Core apps with the CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="535bb-169">Weitere Informationen zur App-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="535bb-169">Learn more about app deployment</span></span>](../deploying/index.md)
