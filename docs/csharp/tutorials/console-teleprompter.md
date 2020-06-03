---
title: Konsolenanwendung
description: In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.
ms.date: 03/06/2017
ms.technology: csharp-fundamentals
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: 06affa01b67edeea09088834cf131adb55650bbb
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794662"
---
# <a name="console-app"></a><span data-ttu-id="e9bca-103">Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="e9bca-103">Console app</span></span>

<span data-ttu-id="e9bca-104">In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-104">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="e9bca-105">Es werden die folgenden Themen abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="e9bca-105">You'll learn:</span></span>

- <span data-ttu-id="e9bca-106">Die Grundlagen zur .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="e9bca-106">The basics of the .NET Core CLI</span></span>
- <span data-ttu-id="e9bca-107">Die Struktur einer C#-Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="e9bca-107">The structure of a C# Console Application</span></span>
- <span data-ttu-id="e9bca-108">Konsolen-E/A</span><span class="sxs-lookup"><span data-stu-id="e9bca-108">Console I/O</span></span>
- <span data-ttu-id="e9bca-109">Grundlagen der Datei-E/A-APIs in .NET</span><span class="sxs-lookup"><span data-stu-id="e9bca-109">The basics of File I/O APIs in .NET</span></span>
- <span data-ttu-id="e9bca-110">Grundlagen des taskbasierten asynchronen Programmiermodells in .NET</span><span class="sxs-lookup"><span data-stu-id="e9bca-110">The basics of the Task-based Asynchronous Programming in .NET</span></span>

<span data-ttu-id="e9bca-111">Sie erstellen eine Anwendung, die eine Textdatei liest und die Inhalte dieser Textdatei an die Konsole ausgibt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-111">You'll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="e9bca-112">Das Tempo der Ausgabe in der Konsole ist so festgelegt, dass ein lautes Mitlesen möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e9bca-112">The output to the console is paced to match reading it aloud.</span></span> <span data-ttu-id="e9bca-113">Sie können die Ausgabe beschleunigen oder verlangsamen, indem Sie die Tasten „<“ (kleiner als) oder „>“ (größer als) drücken.</span><span class="sxs-lookup"><span data-stu-id="e9bca-113">You can speed up or slow down the pace by pressing the '<' (less than) or '>' (greater than) keys.</span></span>

<span data-ttu-id="e9bca-114">In diesem Tutorial werden viele Features abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-114">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="e9bca-115">Gehen wir sie einzeln an.</span><span class="sxs-lookup"><span data-stu-id="e9bca-115">Let's build them one by one.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9bca-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e9bca-116">Prerequisites</span></span>

- <span data-ttu-id="e9bca-117">Richten Sie Ihren Computer für die Ausführung von .NET Core ein.</span><span class="sxs-lookup"><span data-stu-id="e9bca-117">Set up your machine to run .NET Core.</span></span> <span data-ttu-id="e9bca-118">Die Installationsanweisungen finden Sie auf der Seite [.NET Core-Downloads](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="e9bca-118">You can find the installation instructions on the [.NET Core downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="e9bca-119">Sie können diese Anwendung unter Windows, Linux, macOS oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-119">You can run this application on Windows, Linux, macOS, or in a Docker container.</span></span>

- <span data-ttu-id="e9bca-120">Installieren Sie Ihren bevorzugten Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="e9bca-120">Install your favorite code editor.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="e9bca-121">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="e9bca-121">Create the app</span></span>

<span data-ttu-id="e9bca-122">Im ersten Schritt wird eine neue Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-122">The first step is to create a new application.</span></span> <span data-ttu-id="e9bca-123">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e9bca-123">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="e9bca-124">Legen Sie das Verzeichnis als aktuelles Verzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="e9bca-124">Make that the current directory.</span></span> <span data-ttu-id="e9bca-125">Geben Sie an der Eingabeaufforderung den Befehl `dotnet new console` ein.</span><span class="sxs-lookup"><span data-stu-id="e9bca-125">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="e9bca-126">Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-126">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="e9bca-127">Bevor Sie damit beginnen, Änderungen durchzuführen, gehen wir die Schritte zur Ausführung der einfachen Hello World-Anwendung durch.</span><span class="sxs-lookup"><span data-stu-id="e9bca-127">Before you start making modifications, let's go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="e9bca-128">Geben Sie nach dem Erstellen der Anwendung den Befehl `dotnet restore` an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="e9bca-128">After creating the application, type `dotnet restore` at the command prompt.</span></span> <span data-ttu-id="e9bca-129">Mit diesem Befehl wird der Prozess zur NuGet-Paketwiederherstellung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-129">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="e9bca-130">NuGet ist ein .NET-Paket-Manager.</span><span class="sxs-lookup"><span data-stu-id="e9bca-130">NuGet is a .NET package manager.</span></span> <span data-ttu-id="e9bca-131">Mit diesem Befehl werden alle fehlenden abhängigen Komponenten für Ihr Projekt heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-131">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="e9bca-132">Da es sich um ein neues Projekt handelt, ist keine der abhängigen Komponenten vorhanden, deshalb wird zunächst das .NET Core-Framework heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-132">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="e9bca-133">Nach diesem ersten Schritt müssen Sie `dotnet restore` nur ausführen, wenn Sie neue abhängige Pakete hinzufügen oder die Versionen abhängiger Komponenten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e9bca-133">After this initial step, you will only need to run `dotnet restore` when you add new dependent packages, or update the versions of any of your dependencies.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="e9bca-134">Nach dem Wiederherstellen der Pakete führen Sie `dotnet build` aus.</span><span class="sxs-lookup"><span data-stu-id="e9bca-134">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="e9bca-135">Hiermit wird die Build-Engine ausgeführt und die ausführbare Datei für Ihre Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-135">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="e9bca-136">Abschließend führen Sie `dotnet run` aus, um Ihre Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="e9bca-136">Finally, you execute `dotnet run` to run your application.</span></span>

<span data-ttu-id="e9bca-137">Der gesamte Code für die einfache Hello World-Anwendung ist in „Program.cs“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9bca-137">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="e9bca-138">Öffnen Sie diese Datei mit Ihrem bevorzugten Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="e9bca-138">Open that file with your favorite text editor.</span></span> <span data-ttu-id="e9bca-139">Wir werden jetzt die ersten Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-139">We're about to make our first changes.</span></span> <span data-ttu-id="e9bca-140">Am Anfang der Datei sehen Sie eine using-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="e9bca-140">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="e9bca-141">Diese Anweisung informiert den Compiler, dass alle Typen aus dem `System`-Namespace im Gültigkeitsbereich liegen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-141">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="e9bca-142">Wie andere objektorientierte Sprachen, die Sie vielleicht schon verwendet haben, verwendet C# Namespaces, um Typen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="e9bca-142">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="e9bca-143">Dieses Hello World-Programm funktioniert genauso.</span><span class="sxs-lookup"><span data-stu-id="e9bca-143">This Hello World program is no different.</span></span> <span data-ttu-id="e9bca-144">Sie können sehen, dass das Programm in den Namespace eingeschlossen ist, wobei der Name auf dem des aktuellen Verzeichnisses basiert.</span><span class="sxs-lookup"><span data-stu-id="e9bca-144">You can see that the program is enclosed in the namespace with the name based on the name of the current directory.</span></span> <span data-ttu-id="e9bca-145">Für dieses Tutorial ändern wir den Namen des Namespace in `TeleprompterConsole`:</span><span class="sxs-lookup"><span data-stu-id="e9bca-145">For this tutorial, let's change the name of the namespace to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="e9bca-146">Lesen und Ausgeben der Datei</span><span class="sxs-lookup"><span data-stu-id="e9bca-146">Reading and Echoing the File</span></span>

<span data-ttu-id="e9bca-147">Das erste hinzuzufügende Feature ist die Möglichkeit zum Lesen einer Textdatei und zum Anzeigen des gesamten Texts in der Konsole.</span><span class="sxs-lookup"><span data-stu-id="e9bca-147">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="e9bca-148">Fügen wir zunächst eine Textdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="e9bca-148">First, let's add a text file.</span></span> <span data-ttu-id="e9bca-149">Kopieren Sie die Datei [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) aus dem GitHub-Repository für dieses [Beispiel](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) in Ihr Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e9bca-149">Copy the [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="e9bca-150">Diese Datei dient als Skript für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e9bca-150">This will serve as the script for your application.</span></span> <span data-ttu-id="e9bca-151">Wenn Sie Informationen dazu erhalten möchten, wie Sie die Beispiel-App für dieses Thema herunterladen, finden Sie Anweisungen im Thema [Beispiele und Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="e9bca-151">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="e9bca-152">Fügen Sie als Nächstes die folgende Methode in Ihre `Program`-Klasse ein (rechts neben der `Main`-Methode):</span><span class="sxs-lookup"><span data-stu-id="e9bca-152">Next, add the following method in your `Program` class (right below the `Main` method):</span></span>

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

<span data-ttu-id="e9bca-153">Diese Methode verwendet Typen aus zwei neuen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="e9bca-153">This method uses types from two new namespaces.</span></span> <span data-ttu-id="e9bca-154">Für die Kompilierung müssen Sie oben in der Datei die folgenden zwei Zeilen einfügen:</span><span class="sxs-lookup"><span data-stu-id="e9bca-154">For this to compile you'll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="e9bca-155">Die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle ist im <xref:System.Collections.Generic>-Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="e9bca-155">The <xref:System.Collections.Generic.IEnumerable%601> interface is defined in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="e9bca-156">Die <xref:System.IO.File>-Klasse ist im <xref:System.IO>-Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="e9bca-156">The <xref:System.IO.File> class is defined in the <xref:System.IO> namespace.</span></span>

<span data-ttu-id="e9bca-157">Diese Methode ist ein besonderer Typ von C#-Methode, der als *Iteratormethode* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="e9bca-157">This method is a special type of C# method called an *Iterator method*.</span></span> <span data-ttu-id="e9bca-158">Enumeratormethoden geben Sequenzen zurück, die verzögert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="e9bca-158">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="e9bca-159">Dies bedeutet, dass jedes Element in der Sequenz dann generiert wird, wenn es vom Code angefordert wird, der die Sequenz verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e9bca-159">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="e9bca-160">Enumeratormethoden sind Methoden, die mindestens eine [`yield return`](../language-reference/keywords/yield.md)-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9bca-160">Enumerator methods are methods that contain one or more [`yield return`](../language-reference/keywords/yield.md) statements.</span></span> <span data-ttu-id="e9bca-161">Das von der `ReadFrom`-Methode zurückgegebene Objekt enthält den Code zum Generieren aller Elemente in der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="e9bca-161">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="e9bca-162">In diesem Beispiel umfasst dies das Einlesen der nächsten Textzeile aus der Quelldatei und die Rückgabe dieser Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e9bca-162">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="e9bca-163">Jedes Mal, wenn der aufrufende Code die nächste Zeile aus der Sequenz anfordert, liest der Code die nächste Zeile aus der Textdatei und gibt sie zurück.</span><span class="sxs-lookup"><span data-stu-id="e9bca-163">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="e9bca-164">Wenn die Datei vollständig gelesen wurde, gibt die Sequenz an, dass keine weiteren Elemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e9bca-164">When the file is completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="e9bca-165">Es gibt zwei weitere C#-Syntaxelemente, die möglicherweise neu für Sie sind.</span><span class="sxs-lookup"><span data-stu-id="e9bca-165">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="e9bca-166">Die [`using`](../language-reference/keywords/using-statement.md)-Anweisung in dieser Methode verwaltet die Ressourcenbereinigung.</span><span class="sxs-lookup"><span data-stu-id="e9bca-166">The [`using`](../language-reference/keywords/using-statement.md) statement in this method manages resource cleanup.</span></span> <span data-ttu-id="e9bca-167">Die Variable, die in der `using`-Anweisung initialisiert wird – in diesem Beispiel `reader` –, muss die <xref:System.IDisposable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="e9bca-167">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="e9bca-168">Diese Schnittstelle definiert eine einzige Methode, `Dispose`, die aufgerufen werden muss, wenn die Ressource freigegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9bca-168">That interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="e9bca-169">Der Compiler generiert diesen Aufruf, wenn die Ausführung die schließende geschweifte Klammer der `using`-Anweisung erreicht.</span><span class="sxs-lookup"><span data-stu-id="e9bca-169">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="e9bca-170">Der vom Compiler generierte Code stellt sicher, dass die Ressource selbst dann freigegeben wird, wenn der Code im durch die using-Anweisung definierten Block eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="e9bca-170">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="e9bca-171">Die `reader`-Variable wird mit dem `var`-Schlüsselwort definiert.</span><span class="sxs-lookup"><span data-stu-id="e9bca-171">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="e9bca-172">[`var`](../language-reference/keywords/var.md) definiert eine *implizit typisierte lokale Variable*.</span><span class="sxs-lookup"><span data-stu-id="e9bca-172">[`var`](../language-reference/keywords/var.md) defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="e9bca-173">Dies bedeutet, dass der Typ der Variablen durch den Kompilierzeittyp des Objekts bestimmt wird, das der Variablen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e9bca-173">That means the type of the variable is determined by the compile-time type of the object assigned to the variable.</span></span> <span data-ttu-id="e9bca-174">Hier ist dies der Rückgabewert der <xref:System.IO.File.OpenText(System.String)>-Methode, bei dem es sich um ein <xref:System.IO.StreamReader>-Objekt handelt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-174">Here, that is the return value from the <xref:System.IO.File.OpenText(System.String)> method, which is a <xref:System.IO.StreamReader> object.</span></span>

<span data-ttu-id="e9bca-175">Geben Sie jetzt den Code ein, um die Datei in der `Main`-Methode zu lesen:</span><span class="sxs-lookup"><span data-stu-id="e9bca-175">Now, let's fill in the code to read the file in the `Main` method:</span></span>

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line);
}
```

<span data-ttu-id="e9bca-176">Führen Sie das Programm (unter Verwendung von `dotnet run`) aus. Jede Zeile wird einzeln an der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="e9bca-176">Run the program (using `dotnet run`) and you can see every line printed out to the console.</span></span>

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="e9bca-177">Hinzufügen von Verzögerungen und Formatieren der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="e9bca-177">Adding Delays and Formatting output</span></span>

<span data-ttu-id="e9bca-178">Der Text wird momentan zu schnell ausgegeben, um ihn laut mitzulesen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-178">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="e9bca-179">Jetzt müssen Sie Verzögerungen in der Ausgabe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-179">Now you need to add the delays in the output.</span></span> <span data-ttu-id="e9bca-180">Zu Beginn erstellen Sie einen Teil des grundlegenden Codes, der asynchrone Verarbeitung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e9bca-180">As you start, you'll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="e9bca-181">Auf diese ersten Schritte folgen jedoch einige Antimuster.</span><span class="sxs-lookup"><span data-stu-id="e9bca-181">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="e9bca-182">Die Antimuster werden in Kommentaren erläutert, die Sie im Code hinzufügen, und der Code wird in späteren Schritten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e9bca-182">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="e9bca-183">Dieser Abschnitt umfasst zwei Schritte.</span><span class="sxs-lookup"><span data-stu-id="e9bca-183">There are two steps to this section.</span></span> <span data-ttu-id="e9bca-184">Zunächst aktualisieren Sie die Iteratormethode, um anstelle von ganzen Zeilen einzelne Wörter zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e9bca-184">First, you'll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="e9bca-185">Dies wird durch diese Änderungen erreicht.</span><span class="sxs-lookup"><span data-stu-id="e9bca-185">That's done with these modifications.</span></span> <span data-ttu-id="e9bca-186">Ersetzen Sie die `yield return line;`-Anweisung durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e9bca-186">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="e9bca-187">Als Nächstes ändern Sie die Art und Weise, in der die Dateizeilen verarbeitet werden und fügen nach jedem geschriebenen Wort eine Verzögerung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e9bca-187">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="e9bca-188">Ersetzen Sie die `Console.WriteLine(line)`-Anweisung in der `Main`-Methode durch den folgenden Block:</span><span class="sxs-lookup"><span data-stu-id="e9bca-188">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

<span data-ttu-id="e9bca-189">Die <xref:System.Threading.Tasks.Task>-Klasse ist im <xref:System.Threading.Tasks>-Namespace enthalten, deshalb müssen Sie diese `using`-Anweisung am Anfang der Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e9bca-189">The <xref:System.Threading.Tasks.Task> class is in the <xref:System.Threading.Tasks> namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="e9bca-190">Führen Sie das Beispiel aus, und überprüfen Sie die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e9bca-190">Run the sample, and check the output.</span></span> <span data-ttu-id="e9bca-191">Jetzt folgt nach der Ausgabe jedes Worts eine Pause von 200 ms.</span><span class="sxs-lookup"><span data-stu-id="e9bca-191">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="e9bca-192">Die angezeigte Ausgabe ist jedoch fehlerhaft, weil der Quelltext mehrere Zeilen umfasst, die mehr als 80 Zeichen ohne Zeilenumbruch aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-192">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="e9bca-193">Der Text ist möglicherweise schwer zu lesen, wenn er ohne Umbrüche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e9bca-193">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="e9bca-194">Dieses Problem kann einfach gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e9bca-194">That's easy to fix.</span></span> <span data-ttu-id="e9bca-195">Sie verfolgen einfach die Länge jeder Zeile nach und generieren immer dann eine neue Zeile, wenn die Zeilenlänge einen bestimmten Schwellenwert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="e9bca-195">You'll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="e9bca-196">Deklarieren Sie nach der Deklaration von `words` in der `ReadFrom`-Methode eine lokale Variable, die die Zeilenlänge enthält:</span><span class="sxs-lookup"><span data-stu-id="e9bca-196">Declare a local variable after the declaration of `words` in the `ReadFrom` method that holds the line length:</span></span>

```csharp
var lineLength = 0;
```

<span data-ttu-id="e9bca-197">Fügen Sie dann nach der `yield return word + " ";`-Anweisung (vor der schließenden geschweiften Klammer) den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="e9bca-197">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```

<span data-ttu-id="e9bca-198">Führen Sie das Beispiel aus. Jetzt sollten Sie in der Lage sein, den Text im festgelegten Tempo laut mitzulesen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-198">Run the sample, and you'll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="e9bca-199">Asynchrone Tasks</span><span class="sxs-lookup"><span data-stu-id="e9bca-199">Async Tasks</span></span>

<span data-ttu-id="e9bca-200">In diesem letzten Schritt fügen Sie den Code hinzu, mit dem in einem Task die Ausgabe asynchron geschrieben wird, während in einem weiteren Task Eingaben vom Benutzer gelesen werden, um ggf. die Geschwindigkeit der Textanzeige zu erhöhen oder zu verringern oder die Textanzeige ganz zu beenden.</span><span class="sxs-lookup"><span data-stu-id="e9bca-200">In this final step, you'll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display, or stop the text display altogether.</span></span> <span data-ttu-id="e9bca-201">Hierzu sind einige Schritte erforderlich, damit Sie am Ende über alle benötigten Aktualisierungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-201">This has a few steps in it and by the end, you'll have all the updates that you need.</span></span> <span data-ttu-id="e9bca-202">Im ersten Schritt erstellen Sie eine asynchrone <xref:System.Threading.Tasks.Task>-Rückgabemethode, die den Code darstellt, den Sie bisher zum Lesen und Anzeigen der Datei erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e9bca-202">The first step is to create an asynchronous <xref:System.Threading.Tasks.Task> returning method that represents the code you've created so far to read and display the file.</span></span>

<span data-ttu-id="e9bca-203">Fügen Sie diese Methode Ihrer `Program`-Klasse hinzu (diese stammt aus dem Textkörper Ihrer `Main`-Methode):</span><span class="sxs-lookup"><span data-stu-id="e9bca-203">Add this method to your `Program` class (it's taken from the body of your `Main` method):</span></span>

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(200);
        }
    }
}
```

<span data-ttu-id="e9bca-204">Sie werden zwei Änderungen bemerken.</span><span class="sxs-lookup"><span data-stu-id="e9bca-204">You'll notice two changes.</span></span> <span data-ttu-id="e9bca-205">Zunächst wird im Methodenkörper anstelle eines Aufrufs von <xref:System.Threading.Tasks.Task.Wait> zum synchronen Warten auf eine Taskbeendigung in dieser Version das Schlüsselwort `await` verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9bca-205">First, in the body of the method, instead of calling <xref:System.Threading.Tasks.Task.Wait> to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="e9bca-206">Hierzu müssen Sie der Methodensignatur den `async`-Modifizierer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-206">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="e9bca-207">Diese Methode gibt einen `Task` zurück.</span><span class="sxs-lookup"><span data-stu-id="e9bca-207">This method returns a `Task`.</span></span> <span data-ttu-id="e9bca-208">Beachten Sie, dass es keine return-Anweisungen gibt, die ein `Task`-Objekt zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e9bca-208">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="e9bca-209">Stattdessen wird dieses `Task`-Objekt durch Code erstellt, den der Compiler beim Verwenden des `await`-Operators generiert.</span><span class="sxs-lookup"><span data-stu-id="e9bca-209">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="e9bca-210">Sie können sich dies so vorstellen, dass die Methode eine Rückgabe durchführt, wenn sie ein `await`-Schlüsselwort erreicht.</span><span class="sxs-lookup"><span data-stu-id="e9bca-210">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="e9bca-211">Der zurückgegebene `Task` gibt an, dass der Vorgang noch nicht abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e9bca-211">The returned `Task` indicates that the work has not completed.</span></span> <span data-ttu-id="e9bca-212">Die Methode wird fortgesetzt, wenn der erwartete Task abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e9bca-212">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="e9bca-213">Nach Abschluss der Ausführung weist der zurückgegebene `Task` darauf hin, dass er abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e9bca-213">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="e9bca-214">Der aufrufende Code kann den zurückgegebenen `Task` überwachen, um zu ermitteln, wann dieser abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e9bca-214">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="e9bca-215">Sie können diese neue Methode in Ihrer `Main`-Methode aufrufen:</span><span class="sxs-lookup"><span data-stu-id="e9bca-215">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="e9bca-216">Hier führt der Code in `Main` einen asynchronen Wartevorgang aus.</span><span class="sxs-lookup"><span data-stu-id="e9bca-216">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="e9bca-217">Sie sollten nach Möglichkeit anstelle eines synchronen Wartevorgangs immer den `await`-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="e9bca-217">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="e9bca-218">In der `Main`-Methode einer Konsolenanwendung kann der `await`-Operator jedoch nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9bca-218">But, in a console application's `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="e9bca-219">Dies würde dazu führen, dass die Anwendung beendet wird, bevor alle Tasks abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="e9bca-219">That would result in the application exiting before all tasks have completed.</span></span>

> [!NOTE]
> <span data-ttu-id="e9bca-220">Wenn Sie C# 7.1 oder höher verwenden, können Sie Konsolenanwendungen mit der [`async` `Main`-Methode](../whats-new/csharp-7-1.md#async-main) erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-220">If you use C# 7.1 or later, you can create console applications with [`async` `Main` method](../whats-new/csharp-7-1.md#async-main).</span></span>

<span data-ttu-id="e9bca-221">Als Nächstes müssen Sie die zweite asynchrone Methode schreiben, um Inhalte aus der Konsole zu lesen und auf die Tasteneingaben „<“ (kleiner als) und „>“ (größer als) sowie „X“ und „x“ zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="e9bca-221">Next, you need to write the second asynchronous method to read from the Console and watch for the '<' (less than), '>' (greater than) and 'X' or 'x' keys.</span></span> <span data-ttu-id="e9bca-222">Dies ist die Methode, die Sie für diesen Task hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e9bca-222">Here's the method you add for that task:</span></span>

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
            {
                break;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="e9bca-223">Hiermit wird ein Lambdaausdruck zur Darstellung eines <xref:System.Action>-Delegaten erstellt. Mit diesem wird ein Schlüssel aus der Konsole gelesen und eine lokale Variable geändert, die die Verzögerung beim Drücken der Tasten „<“ (kleiner als) oder „>“ (größer als) durch den Benutzer darstellt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-223">This creates a lambda expression to represent an <xref:System.Action> delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the '<' (less than) or '>' (greater than) keys.</span></span> <span data-ttu-id="e9bca-224">Die Delegatmethode wird beendet, wenn der Benutzer die Tasten „X“ oder „x“ drückt, sodass der Benutzer die Textanzeige jederzeit beenden kann.</span><span class="sxs-lookup"><span data-stu-id="e9bca-224">The delegate method finishes when user presses the 'X' or 'x'  keys, which allow the user to stop the text display at any time.</span></span> <span data-ttu-id="e9bca-225">Diese Methode verwendet <xref:System.Console.ReadKey> zum Blockieren und wartet darauf, dass der Benutzer eine Taste drückt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-225">This method uses <xref:System.Console.ReadKey> to block and wait for the user to press a key.</span></span>

<span data-ttu-id="e9bca-226">Um dieses Feature abzuschließen, müssen Sie eine neue `async Task`-Rückgabemethode erstellen, die beide Tasks (`GetInput` und `ShowTeleprompter`) startet und außerdem die von diesen Tasks gemeinsam verwendeten Daten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e9bca-226">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>

<span data-ttu-id="e9bca-227">Es muss eine neue Klasse erstellt werden, mit der die von diesen zwei Tasks gemeinsam verwendeten Daten verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="e9bca-227">It's time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="e9bca-228">Diese Klasse enthält zwei öffentliche Eigenschaften: die Verzögerung und ein Flag `Done`, mit dem angegeben wird, dass die Datei vollständig gelesen wurde:</span><span class="sxs-lookup"><span data-stu-id="e9bca-228">This class contains two public properties: the delay, and a flag `Done` to indicate that the file has been completely read:</span></span>

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            DelayInMilliseconds = newDelay;
        }

        public bool Done { get; private set; }

        public void SetDone()
        {
            Done = true;
        }
    }
}
```

<span data-ttu-id="e9bca-229">Platzieren Sie diese Klasse in einer neuen Datei, und fügen Sie diese Klasse in den `TeleprompterConsole`-Namespace ein (wie oben gezeigt).</span><span class="sxs-lookup"><span data-stu-id="e9bca-229">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="e9bca-230">Sie benötigen außerdem eine `using static`-Anweisung, damit Sie ohne die Namen der übergeordneten Klasse oder des Namespace auf die `Min`- und `Max`-Methode verweisen können.</span><span class="sxs-lookup"><span data-stu-id="e9bca-230">You'll also need to add a `using static` statement so that you can reference the `Min` and `Max` methods without the enclosing class or namespace names.</span></span> <span data-ttu-id="e9bca-231">Eine [`using static`](../language-reference/keywords/using-static.md)-Anweisung importiert die Methoden einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="e9bca-231">A [`using static`](../language-reference/keywords/using-static.md) statement imports the methods from one class.</span></span> <span data-ttu-id="e9bca-232">Dies steht in Kontrast zu den bisher verwendeten `using`-Anweisungen, die alle Klassen aus einem Namespace importiert haben.</span><span class="sxs-lookup"><span data-stu-id="e9bca-232">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="e9bca-233">Im nächsten Schritt müssen Sie die `ShowTeleprompter`- und `GetInput`-Methoden zur Verwendung des neuen `config`-Objekts aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e9bca-233">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="e9bca-234">Schreiben Sie einen finalen `Task`, der die `async`-Methode zurückgibt, um beide Tasks zu starten und den Vorgang zu beenden, sobald der erste Task beendet wird:</span><span class="sxs-lookup"><span data-stu-id="e9bca-234">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="e9bca-235">Die neue Methode hier ist der <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])>-Aufruf.</span><span class="sxs-lookup"><span data-stu-id="e9bca-235">The one new method here is the <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> call.</span></span> <span data-ttu-id="e9bca-236">Hiermit wird ein `Task` erstellt, der abgeschlossen wird, sobald einer der Tasks in dieser Argumentliste beendet ist.</span><span class="sxs-lookup"><span data-stu-id="e9bca-236">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="e9bca-237">Im nächsten Schritt müssen Sie die `ShowTeleprompter`- und `GetInput`-Methoden zur Verwendung des neuen `config`-Objekts aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="e9bca-237">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
                config.SetDone();
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="e9bca-238">Diese neue Version von `ShowTeleprompter` ruft eine neue Methode in der `TeleprompterConfig`-Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="e9bca-238">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="e9bca-239">Jetzt müssen Sie `Main` aktualisieren, um anstelle von `ShowTeleprompter``RunTeleprompter` aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="e9bca-239">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

## <a name="conclusion"></a><span data-ttu-id="e9bca-240">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="e9bca-240">Conclusion</span></span>

<span data-ttu-id="e9bca-241">In diesem Tutorial wurden verschiedene Features von C# und den .NET Core-Bibliotheken vorgestellt, die bei der Arbeit in Konsolenanwendungen benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="e9bca-241">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span> <span data-ttu-id="e9bca-242">Sie können auf diesem Wissen aufbauen, um C# und die hier beschriebenen Klassen weiter zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="e9bca-242">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="e9bca-243">Sie haben die Grundlagen der Datei- und Konsolen-E/A kennengelernt, und es wurden die blockierende und die nicht blockierende Verwendung der taskbasierten asynchronen Programmierung vorgestellt. Außerdem haben Sie einen Überblick über die Sprache C# und die Struktur von C#-Programmen erhalten, und Sie haben die .NET Core-CLI kennengelernt.</span><span class="sxs-lookup"><span data-stu-id="e9bca-243">You've seen the basics of File and Console I/O, blocking and non-blocking use of the Task-based asynchronous programming, a tour of the C# language and how C# programs are organized, and the .NET Core CLI.</span></span>

<span data-ttu-id="e9bca-244">Weitere Informationen zur Datei-E/A finden Sie im Thema [Datei- und Stream-E/A](../../standard/io/index.md).</span><span class="sxs-lookup"><span data-stu-id="e9bca-244">For more information about File I/O, see the [File and Stream I/O](../../standard/io/index.md) topic.</span></span> <span data-ttu-id="e9bca-245">Weitere Informationen zu dem in diesem Tutorial verwendeten asynchronen Programmiermodell finden sie in den Themen [Aufgabenbasierte asynchrone Programmierung](../../standard/parallel-programming/task-based-asynchronous-programming.md) und [Asynchrone Programmierung](../async.md).</span><span class="sxs-lookup"><span data-stu-id="e9bca-245">For more information about asynchronous programming model used in this tutorial, see the [Task-based Asynchronous Programming](../../standard/parallel-programming/task-based-asynchronous-programming.md) topic and the [Asynchronous programming](../async.md) topic.</span></span>
