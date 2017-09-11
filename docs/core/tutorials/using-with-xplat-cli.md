---
title: Erste Schritte mit .NET Core unter Verwendung von CLI
description: Erste Schritte mit .NET Core unter Windows, Linux oder Mac OS unter Verwendung der .NET Core-Befehlszeilenschnittstelle (CLI).
keywords: .NET Core, CLI
author: cartermp
ms.author: mairaw
ms.date: 03/08/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 41632e63-d5c6-4427-a09e-51dc1116d45f
ms.translationtype: HT
ms.sourcegitcommit: 9b63485ca10fe9f6d63c7134128bbfceaede6302
ms.openlocfilehash: b853f74ea2daa60bd68502f07f243c814c8c1947
ms.contentlocale: de-de
ms.lasthandoff: 08/24/2017

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="7b8ac-104">Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="7b8ac-104">Getting started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="7b8ac-105">In diesem Thema erfahren Sie, wie Sie plattformübergreifende Anwendungen mit .NET Core CLI-Tools auf Ihrem Computer erstellen können.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-105">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="7b8ac-106">Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="7b8ac-106">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7b8ac-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="7b8ac-107">Prerequisites</span></span>

- <span data-ttu-id="7b8ac-108">[.NET Core SDK 1.0](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="7b8ac-108">[.NET Core SDK 1.0](https://www.microsoft.com/net/download/core).</span></span>
- <span data-ttu-id="7b8ac-109">Ein Text-Editor oder Code-Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-109">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="7b8ac-110">Hallo Konsolenanwendung!</span><span class="sxs-lookup"><span data-stu-id="7b8ac-110">Hello, Console App!</span></span>

<span data-ttu-id="7b8ac-111">Sie können den Beispielcode im Repository „dotnet/docs“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild).</span><span class="sxs-lookup"><span data-stu-id="7b8ac-111">You can [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild) from the dotnet/docs GitHub repository.</span></span> <span data-ttu-id="7b8ac-112">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="7b8ac-112">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="7b8ac-113">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-113">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="7b8ac-114">Navigieren Sie zum erstellten Ordner, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7b8ac-114">Navigate to the folder you created and type the following:</span></span>

```
$ dotnet new console
$ dotnet restore
$ dotnet run
```

<span data-ttu-id="7b8ac-115">Hier eine kurze Beschreibung der Schritte:</span><span class="sxs-lookup"><span data-stu-id="7b8ac-115">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="7b8ac-116">Mit [`dotnet new`](../tools/dotnet-new.md) wird eine aktuelle Projektdatei `Hello.csproj` mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-116">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="7b8ac-117">Zudem wird `Program.cs` erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-117">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="7b8ac-118">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="7b8ac-118">`Hello.csproj`:</span></span>

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]   

   <span data-ttu-id="7b8ac-119">Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-119">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="7b8ac-120">Das Tag `OutputType` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-120">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="7b8ac-121">Das Tag `TargetFramework` gibt an, welche .NET-Implementierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-121">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="7b8ac-122">In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für diese in einem einzigen Vorgang vornehmen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-122">In an advance scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="7b8ac-123">In diesem Tutorial beschränken wir uns auf Builds für .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-123">In this tutorial, we'll stick to building only for .NET Core 1.0.</span></span>

   <span data-ttu-id="7b8ac-124">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="7b8ac-124">`Program.cs`:</span></span>

   <span data-ttu-id="7b8ac-125">[!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]</span><span class="sxs-lookup"><span data-stu-id="7b8ac-125">[!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]</span></span>   

   <span data-ttu-id="7b8ac-126">Das Programm startet mithilfe von `using System`, was bedeutet, dass alles im Namespace `System` in den Geltungsbereich für diese Datei gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-126">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="7b8ac-127">Der Namespace `System` enthält grundlegende Konstrukte, wie z.B. `string`, oder numerische Typen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-127">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="7b8ac-128">Wir definieren dann einen Namespace namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-128">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="7b8ac-129">Sie können diesen Namen nach Wunsch ändern.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-129">You can change this to anything you want.</span></span> <span data-ttu-id="7b8ac-130">Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-130">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="7b8ac-131">Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-131">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="7b8ac-132">Dieses Array wird allerdings nicht verwendet. Die Anwendung gibt lediglich „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="7b8ac-132">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="7b8ac-133">auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-133">to the console.</span></span> <span data-ttu-id="7b8ac-134">Später werden wir Änderungen am Code vornehmen, die dieses Argument verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-134">Later, we'll make changes to the code that will make use of this argument.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="7b8ac-135">[`dotnet restore`](../tools/dotnet-restore.md) führt einen Aufruf in [NuGet](https://www.nuget.org/) (dem Paket-Manager von .NET) aus, um die Struktur der Abhängigkeiten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-135">[`dotnet restore`](../tools/dotnet-restore.md) calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="7b8ac-136">NuGet analysiert die *Hello.csproj*-Datei, lädt die in der Datei angegebenen Abhängigkeiten herunter (oder ruft diese aus einem Cache auf Ihrem Computer ab) und schreibt die *obj/project.assets.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-136">NuGet analyzes the *Hello.csproj* file, downloads the dependencies stated in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file.</span></span>  <span data-ttu-id="7b8ac-137">Die *project.assets.json*-Datei ist zum Kompilieren und Ausführen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-137">The *project.assets.json* file is necessary to be able to compile and run.</span></span>
   
   <span data-ttu-id="7b8ac-138">Bei der *project.assets.json*-Datei handelt es sich um eine persistente und umfassende Gruppe des Diagramms von NuGet-Abhängigkeiten und anderen Informationen, die eine Anwendung beschreiben.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-138">The *project.assets.json* file is a persisted and complete set of the graph of NuGet dependencies and other information describing an app.</span></span>  <span data-ttu-id="7b8ac-139">Diese Datei wird von anderen Tools wie [`dotnet build`](../tools/dotnet-build.md) und [`dotnet run`](../tools/dotnet-run.md) gelesen, die dadurch in die Lage versetzt werden, den Quellcode mit einer vorschriftsmäßigen Menge von NuGet-Abhängigkeiten und Bindungsauflösungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-139">This file is read by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), enabling them to process the source code with a correct set of NuGet dependencies and binding resolutions.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="7b8ac-140">[`dotnet run`](../tools/dotnet-run.md) ruft [`dotnet build`](../tools/dotnet-build.md) auf, um sicherzustellen, dass die Buildziele erstellt wurden, und ruft anschließend `dotnet <assembly.dll>` auf, um die Zielanwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-140">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>
   
    ```
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="7b8ac-141">Sie können alternativ [`dotnet build`](../tools/dotnet-build.md) ausführen, um den Code zu kompilieren, ohne die Konsolenanwendungen des Builds auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-141">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="7b8ac-142">Dies führt zu einer kompilierten Anwendung, wie einer DLL-Datei, die mit `dotnet bin\Debug\netcoreapp1.0\Hello.dll` unter Windows ausgeführt werden kann (verwenden Sie `/` für nicht-Windowssysteme).</span><span class="sxs-lookup"><span data-stu-id="7b8ac-142">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp1.0\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="7b8ac-143">Sie können auch Argumente für die Anwendung angeben, wie Sie später im Thema sehen werden.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-143">You may also specify arguments to the application as you'll see later on the topic.</span></span>

    ```
    $ dotnet bin\Debug\netcoreapp1.0\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="7b8ac-144">In einem komplexen Szenario ist es möglich, die Anwendung als eigenständigen Satz plattformspezifischer Dateien zu erstellen, die auf einen Computer bereitgestellt und ausgeführt werden können, auf dem nicht notwendigerweise .NET Core installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-144">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="7b8ac-145">Details finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="7b8ac-145">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="7b8ac-146">Erweitern des Programms</span><span class="sxs-lookup"><span data-stu-id="7b8ac-146">Augmenting the program</span></span>

<span data-ttu-id="7b8ac-147">Ändern wir das Programm ein bisschen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-147">Let's change the program a bit.</span></span> <span data-ttu-id="7b8ac-148">Fibonacci-Zahlen sind interessant, also fügen wir sie zusätzlich zur Verwendung des Arguments für die Begrüßung der Person hinzu, die die Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-148">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="7b8ac-149">Ersetzen Sie den Inhalt der *Program.cs*-Datei durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7b8ac-149">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   <span data-ttu-id="7b8ac-150">[!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]</span><span class="sxs-lookup"><span data-stu-id="7b8ac-150">[!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]</span></span>   

2. <span data-ttu-id="7b8ac-151">Führen Sie [`dotnet build`](../tools/dotnet-build.md) aus, um die Änderungen zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-151">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="7b8ac-152">Führen Sie das Programm aus, das einen Parameter für die App übergibt:</span><span class="sxs-lookup"><span data-stu-id="7b8ac-152">Run the program passing a parameter to the app:</span></span>

   ```
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

<span data-ttu-id="7b8ac-153">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="7b8ac-153">And that's it!</span></span>  <span data-ttu-id="7b8ac-154">Sie können `Program.cs` beliebig erweitern.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-154">You can augment `Program.cs` any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="7b8ac-155">Arbeiten mit mehreren Dateien</span><span class="sxs-lookup"><span data-stu-id="7b8ac-155">Working with multiple files</span></span>

<span data-ttu-id="7b8ac-156">Einzelne Dateien sind für einfache einmalige Programme in Ordnung, aber wenn Sie eine komplexere Anwendung erstellen, verfügen Sie wahrscheinlich über mehrere Quelldateien in Ihrem Projekt. Bauen wir auf den vorherigen Fibonacci-Werten auf und fügen wir rekursive Features hinzu.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-156">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span> 

1. <span data-ttu-id="7b8ac-157">Fügen Sie eine neue Datei im *Hello*-Verzeichnis mit dem Namen *FibonacciGenerator.cs* durch den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="7b8ac-157">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   <span data-ttu-id="7b8ac-158">[!code-csharp[Fibonacci-Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]</span><span class="sxs-lookup"><span data-stu-id="7b8ac-158">[!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]</span></span>   

2. <span data-ttu-id="7b8ac-159">Ändern Sie die `Main`-Methode in Ihrer *Program.cs*-Datei, um die neue Klasse zu instanziieren und rufen Sie die Methode wie im folgenden Beispiel auf:</span><span class="sxs-lookup"><span data-stu-id="7b8ac-159">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   <span data-ttu-id="7b8ac-160">[!code-csharp[Neues Programm.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]</span><span class="sxs-lookup"><span data-stu-id="7b8ac-160">[!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]</span></span>

3. <span data-ttu-id="7b8ac-161">Führen Sie [`dotnet build`](../tools/dotnet-build.md) aus, um diese Änderungen zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-161">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="7b8ac-162">Führen Sie Ihre App durch, indem Sie [`dotnet run`](../tools/dotnet-run.md) ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-162">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="7b8ac-163">Nachfolgend sehen Sie die Programmausgabe:</span><span class="sxs-lookup"><span data-stu-id="7b8ac-163">The following shows the program output:</span></span>

   ```
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

<span data-ttu-id="7b8ac-164">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="7b8ac-164">And that's it!</span></span> <span data-ttu-id="7b8ac-165">Nun können Sie beginnen, die grundlegenden Konzepte zur Erstellung Ihrer eigene Programme zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-165">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

<span data-ttu-id="7b8ac-166">Beachten Sie, dass die Befehle und die Schritte in diesem Lernprogramm zum Ausführen der Anwendung nur während der Entwicklungszeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-166">Note that the commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="7b8ac-167">Nachdem Sie Ihre Anwendung bereitstellen möchten, sollten Sie einen Blick auf die verschiedenen [Bereitstellungsstrategien](../deploying/index.md) für .NET Core-Anwendungen und den [`dotnet publish`](../tools/dotnet-publish.md)-Befehl werfen.</span><span class="sxs-lookup"><span data-stu-id="7b8ac-167">Once you're ready to deploy your app, you'll want to take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b8ac-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b8ac-168">See also</span></span>

[<span data-ttu-id="7b8ac-169">Organisieren und Testen von Projekten mit .NET Core CLI-Tools</span><span class="sxs-lookup"><span data-stu-id="7b8ac-169">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)

