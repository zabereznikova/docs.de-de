---
title: Konsolenanwendung
description: In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: 08dab8e7b210ab5159645563cd381d50145d764b
ms.sourcegitcommit: be7862cac09066bc505586cbf071d0e2c8fb1508
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2017
---
# <a name="console-application"></a><span data-ttu-id="df6f1-104">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="df6f1-104">Console Application</span></span>

## <a name="introduction"></a><span data-ttu-id="df6f1-105">Einführung</span><span class="sxs-lookup"><span data-stu-id="df6f1-105">Introduction</span></span>
<span data-ttu-id="df6f1-106">In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="df6f1-107">Es werden die folgenden Themen abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="df6f1-107">You’ll learn:</span></span>
*   <span data-ttu-id="df6f1-108">Grundlagen der .NET Core-Befehlszeilenschnittstelle (CLI)</span><span class="sxs-lookup"><span data-stu-id="df6f1-108">The basics of the .NET Core Command Line Interface (CLI)</span></span>
*   <span data-ttu-id="df6f1-109">Die Struktur einer C#-Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="df6f1-109">The structure of a C# Console Application</span></span>
*   <span data-ttu-id="df6f1-110">Konsolen-E/A</span><span class="sxs-lookup"><span data-stu-id="df6f1-110">Console I/O</span></span>
*   <span data-ttu-id="df6f1-111">Grundlagen der Datei-E/A-APIs in .NET Core</span><span class="sxs-lookup"><span data-stu-id="df6f1-111">The basics of File I/O APIs in .NET Core</span></span>
*   <span data-ttu-id="df6f1-112">Grundlagen des taskbasierten asynchronen Programmiermodells in .NET Core</span><span class="sxs-lookup"><span data-stu-id="df6f1-112">The basics of the Task Asynchronous Programming Model in .NET Core</span></span>

<span data-ttu-id="df6f1-113">Sie erstellen eine Anwendung, die eine Textdatei einliest und die Inhalte dieser Textdatei an die Konsole ausgibt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-113">You’ll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="df6f1-114">Das Tempo der Ausgabe in der Konsole wird so festgelegt, dass ein lautes Mitlesen möglich ist.</span><span class="sxs-lookup"><span data-stu-id="df6f1-114">The output to the console will be paced to match reading it aloud.</span></span> <span data-ttu-id="df6f1-115">Sie können die Ausgabe beschleunigen oder verlangsamen, indem Sie die Tasten < oder > drücken.</span><span class="sxs-lookup"><span data-stu-id="df6f1-115">You can speed up or slow down the pace by pressing the ‘<’ or ‘>’ keys.</span></span>

<span data-ttu-id="df6f1-116">In diesem Tutorial werden viele Features abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="df6f1-117">Gehen wir sie einzeln an.</span><span class="sxs-lookup"><span data-stu-id="df6f1-117">Let’s build them one by one.</span></span> 
## <a name="prerequisites"></a><span data-ttu-id="df6f1-118">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="df6f1-118">Prerequisites</span></span>
<span data-ttu-id="df6f1-119">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="df6f1-119">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="df6f1-120">Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="df6f1-120">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="df6f1-121">Sie können diese Anwendung unter Windows, Linux, macOS oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-121">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="df6f1-122">Sie müssen Ihren bevorzugten Code-Editor installieren.</span><span class="sxs-lookup"><span data-stu-id="df6f1-122">You’ll need to install your favorite code editor.</span></span> 
## <a name="create-the-application"></a><span data-ttu-id="df6f1-123">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="df6f1-123">Create the Application</span></span>
<span data-ttu-id="df6f1-124">Im ersten Schritt wird eine neue Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-124">The first step is to create a new application.</span></span> <span data-ttu-id="df6f1-125">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="df6f1-125">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="df6f1-126">Legen Sie das Verzeichnis als aktuelles Verzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="df6f1-126">Make that the current directory.</span></span> <span data-ttu-id="df6f1-127">Geben Sie an der Eingabeaufforderung den Befehl `dotnet new console` ein.</span><span class="sxs-lookup"><span data-stu-id="df6f1-127">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="df6f1-128">Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-128">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="df6f1-129">Bevor Sie damit beginnen, Änderungen durchzuführen, gehen wir die Schritte zur Ausführung der einfachen Hello World-Anwendung durch.</span><span class="sxs-lookup"><span data-stu-id="df6f1-129">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="df6f1-130">Geben Sie nach dem Erstellen der Anwendung `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)) an der Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="df6f1-130">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="df6f1-131">Mit diesem Befehl wird der Prozess zur NuGet-Paketwiederherstellung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-131">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="df6f1-132">NuGet ist ein .NET-Paket-Manager.</span><span class="sxs-lookup"><span data-stu-id="df6f1-132">NuGet is a .NET package manager.</span></span> <span data-ttu-id="df6f1-133">Mit diesem Befehl werden alle fehlenden abhängigen Komponenten für Ihr Projekt heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-133">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="df6f1-134">Da es sich um ein neues Projekt handelt, ist keine der abhängigen Komponenten vorhanden, deshalb wird zunächst das .NET Core-Framework heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-134">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="df6f1-135">Nach diesem ersten Schritt, Sie müssen nur auszuführende `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)) Wenn Sie neue abhängigen Pakete hinzufügen oder aktualisieren Sie die Versionen eine Ihrer Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="df6f1-135">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span> <span data-ttu-id="df6f1-136">Bei diesem Vorgang wird auch die Projektsperrdatei (project.lock.json) in Ihrem Projektverzeichnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-136">This process also creates the project lock file (project.lock.json) in your project directory.</span></span> <span data-ttu-id="df6f1-137">Diese Datei bietet Unterstützung beim Verwalten der Projektabhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="df6f1-137">This file helps to manage the project dependencies.</span></span> <span data-ttu-id="df6f1-138">Sie enthält den lokalen Speicherort für alle Projektabhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="df6f1-138">It contains the local location of all the project dependencies.</span></span> <span data-ttu-id="df6f1-139">Sie müssen nicht die Datei im Datenquellen-Steuerelements abgelegt. Es wird generiert, wenn Sie ausführen `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)).</span><span class="sxs-lookup"><span data-stu-id="df6f1-139">You do not need to put the file in source control; it will be generated when you run `dotnet restore` ([see note](#dotnet-restore-note)).</span></span> 

<span data-ttu-id="df6f1-140">Nach dem Wiederherstellen der Pakete führen Sie `dotnet build` aus.</span><span class="sxs-lookup"><span data-stu-id="df6f1-140">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="df6f1-141">Hiermit wird das Buildmodul ausgeführt und die ausführbare Datei für Ihre Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-141">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="df6f1-142">Abschließend führen Sie `dotnet run` aus, um Ihre Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="df6f1-142">Finally, you execute `dotnet run` to run your application.</span></span>  

<span data-ttu-id="df6f1-143">Der gesamte Code für die einfache Hello World-Anwendung ist in „Program.cs“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="df6f1-143">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="df6f1-144">Öffnen Sie diese Datei mit Ihrem bevorzugten Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="df6f1-144">Open that file with your favorite text editor.</span></span> <span data-ttu-id="df6f1-145">Wir werden jetzt die ersten Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-145">We’re about to make our first changes.</span></span>
<span data-ttu-id="df6f1-146">Am Anfang der Datei sehen Sie eine using-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="df6f1-146">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="df6f1-147">Diese Anweisung informiert den Compiler, dass alle Typen aus dem `System`-Namespace im Gültigkeitsbereich liegen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-147">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="df6f1-148">Wie andere objektorientierte Sprachen, die Sie vielleicht schon verwendet haben, verwendet C# Namespaces, um Typen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="df6f1-148">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="df6f1-149">Dieses Hello World-Programm funktioniert genauso.</span><span class="sxs-lookup"><span data-stu-id="df6f1-149">This hello world program is no different.</span></span> <span data-ttu-id="df6f1-150">Sie können sehen, dass das Programm im `ConsoleApplication`-Namespace enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="df6f1-150">You can see that the program is enclosed in the `ConsoleApplication` namespace.</span></span> <span data-ttu-id="df6f1-151">Dies ist kein besonders aussagekräftiger Name, ändern Sie ihn deshalb in `TeleprompterConsole`:</span><span class="sxs-lookup"><span data-stu-id="df6f1-151">That’s not a very descriptive name, so change it to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="df6f1-152">Lesen und Ausgeben der Datei</span><span class="sxs-lookup"><span data-stu-id="df6f1-152">Reading and Echoing the File</span></span>
<span data-ttu-id="df6f1-153">Das erste hinzuzufügende Feature ist die Möglichkeit zum Lesen einer Textdatei und zum Anzeigen des gesamten Texts in der Konsole.</span><span class="sxs-lookup"><span data-stu-id="df6f1-153">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="df6f1-154">Fügen wir zunächst eine Textdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="df6f1-154">First, let’s add a text file.</span></span> <span data-ttu-id="df6f1-155">Kopieren Sie die Datei [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) aus dem GitHub-Repository für dieses [Beispiel](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter) in Ihr Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="df6f1-155">Copy the [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="df6f1-156">Diese Datei dient als Skript für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="df6f1-156">This will serve as the script for your application.</span></span> <span data-ttu-id="df6f1-157">Wenn Sie Informationen dazu erhalten möchten, wie Sie die Beispiel-App für dieses Thema herunterladen, finden Sie Anweisungen im Thema [Beispiele und Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="df6f1-157">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="df6f1-158">Fügen Sie als Nächstes die folgenden Methoden in Ihre Program-Klasse ein (rechts neben der `Main`-Methode):</span><span class="sxs-lookup"><span data-stu-id="df6f1-158">Next, add the following method in your Program class (right below the `Main` method):</span></span>

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

<span data-ttu-id="df6f1-159">Diese Methode verwendet Typen aus zwei neuen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="df6f1-159">This method uses types from two new namespaces.</span></span> <span data-ttu-id="df6f1-160">Für die Kompilierung müssen Sie oben in der Datei die folgenden zwei Zeilen einfügen:</span><span class="sxs-lookup"><span data-stu-id="df6f1-160">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="df6f1-161">Die `IEnumerable<T>`-Schnittstelle ist im `System.Collections.Generic`-Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="df6f1-161">The `IEnumerable<T>` interface is defined in the `System.Collections.Generic` namespace.</span></span> <span data-ttu-id="df6f1-162">Die <xref:System.IO.File>-Klasse ist im `System.IO`-Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="df6f1-162">The <xref:System.IO.File> class is defined in the `System.IO` namespace.</span></span>

<span data-ttu-id="df6f1-163">Diese Methode ist ein besonderer Typ von C#-Methode, der als *Enumeratormethode* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="df6f1-163">This method is a special type of C# method called an *Enumerator method*.</span></span> <span data-ttu-id="df6f1-164">Enumeratormethoden geben Sequenzen zurück, die verzögert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="df6f1-164">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="df6f1-165">Dies bedeutet, dass jedes Element in der Sequenz dann generiert wird, wenn es vom Code angefordert wird, der die Sequenz verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="df6f1-165">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="df6f1-166">Enumeratormethoden sind Methoden, die mindestens eine `yield return`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="df6f1-166">Enumerator methods are methods that contain one or more `yield return` statements.</span></span> <span data-ttu-id="df6f1-167">Das von der `ReadFrom`-Methode zurückgegebene Objekt enthält den Code zum Generieren aller Elemente in der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="df6f1-167">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="df6f1-168">In diesem Beispiel umfasst dies das Einlesen der nächsten Textzeile aus der Quelldatei und die Rückgabe dieser Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="df6f1-168">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="df6f1-169">Jedes Mal, wenn der aufrufende Code die nächste Zeile aus der Sequenz anfordert, liest der Code die nächste Zeile aus der Textdatei und gibt sie zurück.</span><span class="sxs-lookup"><span data-stu-id="df6f1-169">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="df6f1-170">Wenn die Datei vollständig gelesen wurde, gibt die Sequenz an, dass keine weiteren Elemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="df6f1-170">When the file has been completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="df6f1-171">Es gibt zwei weitere C#-Syntaxelemente, die möglicherweise neu für Sie sind.</span><span class="sxs-lookup"><span data-stu-id="df6f1-171">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="df6f1-172">Die `using`-Anweisung in dieser Methode verwaltet die Ressourcenbereinigung.</span><span class="sxs-lookup"><span data-stu-id="df6f1-172">The `using` statement in this method manages resource cleanup.</span></span> <span data-ttu-id="df6f1-173">Die Variable, die in der `using`-Anweisung initialisiert wird – in diesem Beispiel `reader` –, muss die `IDisposable`-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="df6f1-173">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the `IDisposable` interface.</span></span> <span data-ttu-id="df6f1-174">Die <xref:System.IDisposable>-Schnittstelle definiert eine einzige Methode, `Dispose`, die aufgerufen werden muss, wenn die Ressource freigegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="df6f1-174">The <xref:System.IDisposable> interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="df6f1-175">Der Compiler generiert diesen Aufruf, wenn die Ausführung die schließende geschweifte Klammer der `using`-Anweisung erreicht.</span><span class="sxs-lookup"><span data-stu-id="df6f1-175">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="df6f1-176">Der vom Compiler generierte Code stellt sicher, dass die Ressource selbst dann freigegeben wird, wenn der Code im durch die using-Anweisung definierten Block eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="df6f1-176">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="df6f1-177">Die `reader`-Variable wird mit dem `var`-Schlüsselwort definiert.</span><span class="sxs-lookup"><span data-stu-id="df6f1-177">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="df6f1-178">`var` definiert eine *implizit typisierte lokale Variable*.</span><span class="sxs-lookup"><span data-stu-id="df6f1-178">`var` defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="df6f1-179">Dies bedeutet, dass der Typ der Variablen durch den Kompilierzeittyp des Objekts bestimmt wird, das der Variablen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="df6f1-179">That means the type of the variable is determined by the compile time type of the object assigned to the variable.</span></span> <span data-ttu-id="df6f1-180">Hier können, die den Rückgabewert ist der <xref:System.IO.File.OpenText(System.String)> Methode, die eine <xref:System.IO.StreamReader> Objekt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-180">Here, that is the return value from the <xref:System.IO.File.OpenText(System.String)> method, which is a <xref:System.IO.StreamReader> object.</span></span>
 
<span data-ttu-id="df6f1-181">Füllen wir jetzt den Code in der `Main`-Methode, um die Datei zu lesen:</span><span class="sxs-lookup"><span data-stu-id="df6f1-181">Now, let’s fill in the code to read the file in the `Main` method:</span></span> 

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line); 
}
```

<span data-ttu-id="df6f1-182">Führen Sie das Programm aus (Sie verwenden hierzu `dotnet run`, und jede Zeile wird einzeln an der Konsole ausgegeben).</span><span class="sxs-lookup"><span data-stu-id="df6f1-182">Run the program (using `dotnet run` and you can see every line printed out to the console).</span></span>  

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="df6f1-183">Hinzufügen von Verzögerungen und Formatieren der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="df6f1-183">Adding Delays and Formatting output</span></span>
<span data-ttu-id="df6f1-184">Der Text wird momentan zu schnell ausgegeben, um ihn laut mitzulesen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-184">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="df6f1-185">Jetzt müssen Sie Verzögerungen in der Ausgabe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-185">Now you need to add the delays in the output.</span></span> <span data-ttu-id="df6f1-186">Zu Beginn erstellen Sie einen Teil des grundlegenden Codes, der eine asynchrone Verarbeitung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="df6f1-186">As you start, you’ll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="df6f1-187">Auf diese ersten Schritte folgen jedoch einige Antimuster.</span><span class="sxs-lookup"><span data-stu-id="df6f1-187">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="df6f1-188">Die Antimuster werden in Kommentaren erläutert, die Sie im Code hinzufügen, und der Code wird in späteren Schritten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="df6f1-188">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="df6f1-189">Dieser Abschnitt umfasst zwei Schritte.</span><span class="sxs-lookup"><span data-stu-id="df6f1-189">There are two steps to this section.</span></span> <span data-ttu-id="df6f1-190">Zunächst aktualisieren Sie die Iteratormethode, um anstelle von ganzen Zeilen einzelne Wörter zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="df6f1-190">First, you’ll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="df6f1-191">Dies wird durch diese Änderungen erreicht.</span><span class="sxs-lookup"><span data-stu-id="df6f1-191">That’s done with these modifications.</span></span> <span data-ttu-id="df6f1-192">Ersetzen Sie die `yield return line;`-Anweisung durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="df6f1-192">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="df6f1-193">Als Nächstes ändern Sie die Art und Weise, in der die Dateizeilen verarbeitet werden und fügen nach jedem geschriebenen Wort eine Verzögerung hinzu.</span><span class="sxs-lookup"><span data-stu-id="df6f1-193">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="df6f1-194">Ersetzen Sie die `Console.WriteLine(line)`-Anweisung in der `Main`-Methode durch den folgenden Block:</span><span class="sxs-lookup"><span data-stu-id="df6f1-194">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

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

<span data-ttu-id="df6f1-195">Die `Task`-Klasse ist im `System.Threading.Tasks`-Namespace enthalten, deshalb müssen Sie diese `using`-Anweisung am Anfang der Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="df6f1-195">The `Task` class is in the `System.Threading.Tasks` namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="df6f1-196">Führen Sie das Beispiel aus, und überprüfen Sie die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="df6f1-196">Run the sample, and check the output.</span></span> <span data-ttu-id="df6f1-197">Jetzt folgt nach der Ausgabe jedes Worts eine Pause von 200 ms.</span><span class="sxs-lookup"><span data-stu-id="df6f1-197">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="df6f1-198">Die angezeigte Ausgabe ist jedoch fehlerhaft, weil der Quelltext mehrere Zeilen umfasst, die mehr als 80 Zeichen ohne Zeilenumbruch aufweisen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-198">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="df6f1-199">Der Text ist möglicherweise schwer zu lesen, wenn er ohne Umbrüche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="df6f1-199">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="df6f1-200">Dieses Problem kann einfach gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="df6f1-200">That’s easy to fix.</span></span> <span data-ttu-id="df6f1-201">Sie verfolgen einfach die Länge jeder Zeile nach und generieren immer dann eine neue Zeile, wenn die Zeilenlänge einen bestimmten Schwellenwert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="df6f1-201">You’ll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="df6f1-202">Deklarieren Sie nach der Deklaration von `words` eine lokale Variable, die die Zeilenlänge enthält:</span><span class="sxs-lookup"><span data-stu-id="df6f1-202">Declare a local variable after the declaration of `words` that holds the line length:</span></span>

```csharp
var lineLength = 0;
```
 
<span data-ttu-id="df6f1-203">Fügen Sie dann nach der `yield return word + " ";`-Anweisung (vor der schließenden geschweiften Klammer) den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="df6f1-203">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```
 
<span data-ttu-id="df6f1-204">Führen Sie das Beispiel aus. Jetzt sollten Sie in der Lage sein, den Text im festgelegten Tempo laut mitzulesen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-204">Run the sample, and you’ll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="df6f1-205">Asynchrone Tasks</span><span class="sxs-lookup"><span data-stu-id="df6f1-205">Async Tasks</span></span>
<span data-ttu-id="df6f1-206">Zuletzt fügen Sie den Code hinzu, mit dem in einem Task die Ausgabe asynchron geschrieben wird, während in einem weiteren Task Eingaben vom Benutzer gelesen werden, um ggf. die Geschwindigkeit der Textanzeige zu erhöhen oder zu verringern.</span><span class="sxs-lookup"><span data-stu-id="df6f1-206">In this final step, you’ll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display.</span></span> <span data-ttu-id="df6f1-207">Hierzu sind einige Schritte erforderlich, damit Sie am Ende über alle benötigten Aktualisierungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-207">This has a few steps in it and by the end, you’ll have all the updates that you need.</span></span>
<span data-ttu-id="df6f1-208">Im ersten Schritt erstellen Sie eine asynchrone <xref:System.Threading.Tasks.Task>-Rückgabemethode, die den Code repräsentiert, den Sie bisher zum Lesen und Anzeigen der Datei erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="df6f1-208">The first step is to create an asynchronous <xref:System.Threading.Tasks.Task> returning method that represents the code you’ve created so far to read and display the file.</span></span>

<span data-ttu-id="df6f1-209">Fügen Sie diese Methode zu Ihrer `Program`-Klasse hinzu (diese stammt aus dem Körper Ihrer `Main`-Methode):</span><span class="sxs-lookup"><span data-stu-id="df6f1-209">Add this method to your `Program` class (it’s taken from the body of your `Main` method):</span></span>

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(200);
        }
    }
}
```

<span data-ttu-id="df6f1-210">Sie werden zwei Änderungen bemerken.</span><span class="sxs-lookup"><span data-stu-id="df6f1-210">You’ll notice two changes.</span></span> <span data-ttu-id="df6f1-211">Zunächst wird im Methodenkörper anstelle eines Aufrufs von <xref:System.Threading.Tasks.Task.Wait> zum synchronen Warten auf eine Taskbeendigung in dieser Version das Schlüsselwort `await` verwendet.</span><span class="sxs-lookup"><span data-stu-id="df6f1-211">First, in the body of the method, instead of calling <xref:System.Threading.Tasks.Task.Wait> to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="df6f1-212">Hierzu müssen Sie der Methodensignatur den `async`-Modifizierer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-212">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="df6f1-213">Diese Methode gibt einen `Task` zurück.</span><span class="sxs-lookup"><span data-stu-id="df6f1-213">This method returns a `Task`.</span></span> <span data-ttu-id="df6f1-214">Beachten Sie, dass es keine return-Anweisungen gibt, die ein `Task`-Objekt zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="df6f1-214">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="df6f1-215">Stattdessen wird dieses `Task`-Objekt durch Code erstellt, den der Compiler beim Verwenden des `await`-Operators generiert.</span><span class="sxs-lookup"><span data-stu-id="df6f1-215">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="df6f1-216">Sie können sich dies so vorstellen, dass die Methode eine Rückgabe durchführt, wenn sie ein `await`-Schlüsselwort erreicht.</span><span class="sxs-lookup"><span data-stu-id="df6f1-216">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="df6f1-217">Der zurückgegebene `Task` gibt an, dass der Vorgang noch nicht abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="df6f1-217">The returned `Task` indicates that the work has not completed.</span></span>
<span data-ttu-id="df6f1-218">Die Methode wird fortgesetzt, wenn der erwartete Task abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="df6f1-218">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="df6f1-219">Nach Abschluss der Ausführung weist der zurückgegebene `Task` darauf hin, dass er abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="df6f1-219">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="df6f1-220">Der aufrufende Code kann den zurückgegebenen `Task` überwachen, um zu ermitteln, wann dieser abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="df6f1-220">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="df6f1-221">Sie können diese neue Methode in Ihrer `Main`-Methode aufrufen:</span><span class="sxs-lookup"><span data-stu-id="df6f1-221">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="df6f1-222">Hier führt der Code in `Main` einen asynchronen Wartevorgang aus.</span><span class="sxs-lookup"><span data-stu-id="df6f1-222">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="df6f1-223">Sie sollten nach Möglichkeit anstelle eines synchronen Wartevorgangs immer den `await`-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="df6f1-223">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="df6f1-224">In der `Main`-Methode einer Konsolenanwendung kann der `await`-Operator jedoch nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df6f1-224">But, in a console application’s `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="df6f1-225">Dies würde dazu führen, dass die Anwendung beendet wird, bevor alle Tasks abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="df6f1-225">That would result in the application exiting before all tasks have completed.</span></span>

<span data-ttu-id="df6f1-226">Als Nächstes müssen Sie die zweite asynchrone Methode schreiben, um Inhalte aus der Konsole zu lesen und auf die Tasteneingaben < und > zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-226">Next, you need to write the second asynchronous method to read from the Console and watch for the ‘<’ and ‘>’ keys.</span></span> <span data-ttu-id="df6f1-227">Hier ist die Methode, die Sie für diesen Task hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="df6f1-227">Here’s the method you add for that task:</span></span>

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
        } while (true);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="df6f1-228">Hiermit wird ein Lambda-Ausdruck zur Darstellung eines <xref:System.Action>-Delegaten erstellt. Mit diesem wird ein Schlüssel aus der Konsole gelesen und eine lokale Variable geändert, die die Verzögerung beim Drücken der Tasten < oder > durch den Benutzer repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="df6f1-228">This creates a lambda expression to represent an <xref:System.Action> delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the ‘<’ or ‘>’ keys.</span></span> <span data-ttu-id="df6f1-229">Diese Methode verwendet <xref:System.Console.ReadKey> zum Blockieren und wartet darauf, dass der Benutzer eine Taste drückt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-229">This method uses <xref:System.Console.ReadKey> to block and wait for the user to press a key.</span></span>

<span data-ttu-id="df6f1-230">Um dieses Feature abzuschließen, müssen Sie eine neue `async Task`-Rückgabemethode erstellen, die beide Tasks (`GetInput` und `ShowTeleprompter`) startet und außerdem die von diesen Tasks gemeinsam verwendeten Daten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="df6f1-230">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>
 
<span data-ttu-id="df6f1-231">Es muss eine neue Klasse erstellt werden, mit der die von diesen zwei Tasks gemeinsam verwendeten Daten verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="df6f1-231">It’s time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="df6f1-232">Diese Klasse enthält zwei öffentliche Eigenschaften: die Verzögerung und ein Flag, mit dem angegeben wird, dass die Datei vollständig gelesen wurde:</span><span class="sxs-lookup"><span data-stu-id="df6f1-232">This class contains two public properties: the delay, and a flag to indicate that the file has been completely read:</span></span>

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        private object lockHandle = new object();
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            lock (lockHandle)
            {
                DelayInMilliseconds = newDelay;
            }
        }
    }
}
```

<span data-ttu-id="df6f1-233">Platzieren Sie diese Klasse in einer neuen Datei, und fügen Sie diese Klasse in den `TeleprompterConsole`-Namespace ein (wie oben gezeigt).</span><span class="sxs-lookup"><span data-stu-id="df6f1-233">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="df6f1-234">Sie benötigen außerdem eine `using static`-Anweisung, damit Sie ohne die Namen der übergeordneten Klasse oder des Namespace auf die `Min`- und `Max`-Methode verweisen können.</span><span class="sxs-lookup"><span data-stu-id="df6f1-234">You’ll also need to add a `using static` statement so that you can reference the `Min` and `Max` method without the enclosing class or namespace names.</span></span> <span data-ttu-id="df6f1-235">Eine `using static`-Anweisung importiert die Methoden einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="df6f1-235">A `using static` statement imports the methods from one class.</span></span> <span data-ttu-id="df6f1-236">Dies steht in Kontrast zu den bisher verwendeten `using`-Anweisungen, die alle Klassen aus einem Namespace importiert haben.</span><span class="sxs-lookup"><span data-stu-id="df6f1-236">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="df6f1-237">Ein weiteres neues Sprachfeature ist die `lock`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="df6f1-237">The other language feature that’s new is the `lock` statement.</span></span> <span data-ttu-id="df6f1-238">Mit dieser Anweisung wird sichergestellt, dass zu jedem Zeitpunkt nur ein einziger Thread in diesem Codeabschnitt vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="df6f1-238">This statement ensures that only a single thread can be in that code at any given time.</span></span> <span data-ttu-id="df6f1-239">Wenn sich ein Thread im gesperrten Abschnitt befindet, müssen andere Threads warten, bis der erste Thread diesen Abschnitt verlässt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-239">If one thread is in the locked section, other threads must wait for the first thread to exit that section.</span></span> <span data-ttu-id="df6f1-240">Die `lock`-Anweisung verwendet ein Objekt, das den gesperrten Abschnitt schützt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-240">The `lock` statement uses an object that guards the lock section.</span></span> <span data-ttu-id="df6f1-241">Diese Klasse verwendet ein Standardidiom, um ein privates Objekt in der Klasse zu sperren.</span><span class="sxs-lookup"><span data-stu-id="df6f1-241">This class follows a standard idiom to lock a private object in the class.</span></span>

<span data-ttu-id="df6f1-242">Im nächsten Schritt müssen Sie die `ShowTeleprompter`- und `GetInput`-Methoden zur Verwendung des neuen `config`-Objekts aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="df6f1-242">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="df6f1-243">Schreiben Sie einen finalen `Task`, der die `async`-Methode zurückgibt, um beide Tasks zu starten und den Vorgang zu beenden, sobald der erste Task beendet wird:</span><span class="sxs-lookup"><span data-stu-id="df6f1-243">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="df6f1-244">Eine neue Methode hier besteht die <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="df6f1-244">The one new method here is the <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> call.</span></span> <span data-ttu-id="df6f1-245">Hiermit wird ein `Task` erstellt, der abgeschlossen wird, sobald einer der Tasks in dieser Argumentliste beendet ist.</span><span class="sxs-lookup"><span data-stu-id="df6f1-245">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="df6f1-246">Im nächsten Schritt müssen Sie die `ShowTeleprompter`- und `GetInput`-Methoden zur Verwendung des neuen `config`-Objekts aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="df6f1-246">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
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
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="df6f1-247">Diese neue Version von `ShowTeleprompter` ruft eine neue Methode in der `TeleprompterConfig`-Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="df6f1-247">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="df6f1-248">Jetzt müssen Sie `Main` aktualisieren, um anstelle von `ShowTeleprompter` `RunTeleprompter` aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="df6f1-248">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

<span data-ttu-id="df6f1-249">Zum Abschluss müssen Sie die `SetDone`-Methode hinzufügen und die `Done`-Eigenschaft in die `TelePrompterConfig`-Klasse einfügen:</span><span class="sxs-lookup"><span data-stu-id="df6f1-249">To finish, you'll need to add the `SetDone` method, and the `Done` property to the `TelePrompterConfig` class:</span></span>

```csharp
public bool Done => done;

private bool done;

public void SetDone()
{
    done = true;    
}
```

## <a name="conclusion"></a><span data-ttu-id="df6f1-250">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="df6f1-250">Conclusion</span></span>
<span data-ttu-id="df6f1-251">In diesem Tutorial wurden verschiedene Features von C# und den .NET Core-Bibliotheken vorgestellt, die bei der Arbeit in Konsolenanwendungen benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="df6f1-251">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span>
<span data-ttu-id="df6f1-252">Sie können auf diesem Wissen aufbauen, um C# und die hier beschriebenen Klassen weiter zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="df6f1-252">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="df6f1-253">Sie haben die Grundlagen der Datei- und Konsolen-E/A kennengelernt, und es wurden die blockierende und die nicht blockierende Verwendung des taskbasierten asynchronen Programmiermodells vorgestellt. Außerdem haben Sie einen Überblick über die Sprache C# und die Struktur von C#-Programmen erhalten, und Sie haben die .NET Core-Befehlszeilenschnittstelle (CLI) und andere Tools kennengelernt.</span><span class="sxs-lookup"><span data-stu-id="df6f1-253">You’ve seen the basics of File and Console I/O, blocking and non-blocking use of the Task based Asynchronous programming model, a tour of the C# language and how C# programs are organized and the .NET Core Command Line Interface and tools.</span></span>
 
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]