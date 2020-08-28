---
title: Referenz zu F# Interactive (dotnet)
description: Hier erfahren Sie, wie F# Interactive (dotnet fsi) zum interaktiven Ausführen von F#-Code in der Konsole oder zum Ausführen von F#-Skripts verwendet wird.
ms.date: 08/20/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: 760b096c8a3ee0d495b893ab66fa6f9007cdbbf9
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867619"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="b311b-103">Interaktive Programmierung mit F\#</span><span class="sxs-lookup"><span data-stu-id="b311b-103">Interactive programming with F\#</span></span>

<span data-ttu-id="b311b-104">F# Interactive (dotnet fsi) dient zum interaktiven Ausführen von F#-Code in der Konsole oder zum Ausführen von F#-Skripts.</span><span class="sxs-lookup"><span data-stu-id="b311b-104">F# Interactive (dotnet fsi) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="b311b-105">Dies bedeutet, dass F# Interactive eine REPL (Read, Evaluate, Print Loop = Lesen-Auswerten-Drucken-Schleife) für F# ausführt.</span><span class="sxs-lookup"><span data-stu-id="b311b-105">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="b311b-106">Führen Sie `dotnet fsi` aus, um F# Interactive in der Konsole auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b311b-106">To run F# Interactive from the console, run `dotnet fsi`.</span></span> <span data-ttu-id="b311b-107">Sie finden `dotnet fsi` in einem beliebigen .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="b311b-107">You will find `dotnet fsi` in any .NET SDK.</span></span>

<span data-ttu-id="b311b-108">Informationen zu verfügbaren Befehlszeilenoptionen finden Sie unter [F# Interactive-Optionen](../../language-reference/fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="b311b-108">For information about command line options available, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

<span data-ttu-id="b311b-109">Zum Ausführen von F# Interactive über Visual Studio können Sie auf die entsprechende Symbolleistenschaltfläche **F# Interactive** klicken oder die Tastenkombination **Strg+Alt+F** verwenden.</span><span class="sxs-lookup"><span data-stu-id="b311b-109">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive**, or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="b311b-110">Dadurch wird das Interactive-Fenster geöffnet, ein Toolfenster, in dem eine F# Interactive-Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b311b-110">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="b311b-111">Sie können auch Code auswählen, den Sie im interaktiven Fenster ausführen möchten, und die Tastenkombination **ALT+EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="b311b-111">You can also select some code that you want to run in the interactive window and hit the key combination **Alt+Enter**.</span></span> <span data-ttu-id="b311b-112">F# Interactive wird in einem Toolfenster mit der Bezeichnung **F# Interactive** gestartet.</span><span class="sxs-lookup"><span data-stu-id="b311b-112">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="b311b-113">Wenn Sie diese Tastenkombination verwenden, überprüfen Sie, ob das Editorfenster den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="b311b-113">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="b311b-114">Unabhängig davon, ob Sie die Konsole oder Visual Studio verwenden, wird eine Eingabeaufforderung angezeigt, und der Interpreter erwartet Ihre Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b311b-114">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="b311b-115">Sie können Code auf die gleiche Weise wie in einer Codedatei eingeben.</span><span class="sxs-lookup"><span data-stu-id="b311b-115">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="b311b-116">Geben Sie zum Kompilieren und Ausführen des Codes zwei Semikolons (**;;**) ein, um eine oder mehrere Zeilen der Eingabe zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b311b-116">To compile and execute the code, enter two semicolons (**;;**) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="b311b-117">F# Interactive beginnt mit der Kompilierung des Codes, und wenn der Code erfolgreich kompiliert wurde, führt F# Interactive den Code aus und gibt die Signatur der kompilierten Typen und Werte aus.</span><span class="sxs-lookup"><span data-stu-id="b311b-117">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="b311b-118">Wenn Fehler auftreten, gibt der Interpreter die Fehlermeldungen aus.</span><span class="sxs-lookup"><span data-stu-id="b311b-118">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="b311b-119">In der gleichen Sitzung eingegebener Code kann auf alle zuvor eingegebenen Konstrukte zugreifen. Daher können Sie Programme erstellen.</span><span class="sxs-lookup"><span data-stu-id="b311b-119">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="b311b-120">Ein umfangreicher Puffer im Toolfenster ermöglicht es Ihnen, den Code bei Bedarf in eine Datei zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="b311b-120">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="b311b-121">In Visual Studio wird F# Interactive unabhängig vom Projekt ausgeführt. Daher können Sie im Projekt definierte Konstrukte nur dann in F# Interactive verwenden, wenn Sie den Code für die Funktion in das Interactive-Fenster kopieren.</span><span class="sxs-lookup"><span data-stu-id="b311b-121">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="b311b-122">Wenn Sie ein Projekt geöffnet haben, das auf einige Bibliotheken verweist, können Sie auf diese über den **Projektmappen-Explorer** in F# Interactive verweisen.</span><span class="sxs-lookup"><span data-stu-id="b311b-122">If you have a project open that references some libraries, you can reference these in F# Interactive through **Solution Explorer**.</span></span> <span data-ttu-id="b311b-123">Um auf eine Bibliothek in F# Interactive zu verweisen, erweitern Sie den Knoten **Verweise**, öffnen Sie das Kontextmenü für die Bibliothek, und wählen Sie **An F# Interactive senden** aus.</span><span class="sxs-lookup"><span data-stu-id="b311b-123">To reference a library in F# Interactive, expand the **References** node, open the shortcut menu for the library, and choose **Send to F# Interactive**.</span></span>

<span data-ttu-id="b311b-124">Sie können die Befehlszeilenargumente (Optionen) von F# Interactive steuern, indem Sie die Einstellungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="b311b-124">You can control the F# Interactive command line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="b311b-125">Wählen Sie im Menü **Extras** den Eintrag **Optionen** aus, und erweitern Sie anschließend **F#-Tools**.</span><span class="sxs-lookup"><span data-stu-id="b311b-125">On the **Tools** menu, select **Options...**, and then expand **F# Tools**.</span></span> <span data-ttu-id="b311b-126">Die beiden Einstellungen, die Sie ändern können, sind die F# Interactive-Optionen und die Einstellung **64-Bit-F# Interactive**, die nur relevant ist, wenn Sie F# Interactive auf einem 64-Bit-Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="b311b-126">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="b311b-127">Mit dieser Einstellung legen Sie fest, ob Sie die dedizierte 64-Bit-Version von fsi.exe oder aber fsianycpu.exe ausführen möchten, die anhand der Computerarchitektur ermittelt, ob sie als 32-Bit- oder 64-Bit-Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b311b-127">This setting determines whether you want to run the dedicated 64-bit version of fsi.exe or fsianycpu.exe, which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>

## <a name="scripting-with-f"></a><span data-ttu-id="b311b-128">Skripterstellung mit F\#</span><span class="sxs-lookup"><span data-stu-id="b311b-128">Scripting with F\#</span></span>

<span data-ttu-id="b311b-129">Für Skripts wird die Dateierweiterung **.fsx** oder **.fsscript** verwendet.</span><span class="sxs-lookup"><span data-stu-id="b311b-129">Scripts use the file extension **.fsx** or **.fsscript**.</span></span> <span data-ttu-id="b311b-130">Statt Quellcode zu kompilieren und später die kompilierte Assembly auszuführen, können Sie einfach **dotnet fsi** ausführen und den Dateinamen des Skripts mit dem F#-Quellcode angeben. F# Interactive liest dann den Code und führt ihn in Echtzeit aus.</span><span class="sxs-lookup"><span data-stu-id="b311b-130">Instead of compiling source code and then later running the compiled assembly, you can just run **dotnet fsi** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span>

## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a><span data-ttu-id="b311b-131">Unterschiede zwischen interaktiven Umgebungen, kompilierten Umgebungen und Skripterstellungsumgebungen</span><span class="sxs-lookup"><span data-stu-id="b311b-131">Differences between the interactive, scripting, and compiled environments</span></span>

<span data-ttu-id="b311b-132">Wenn Sie Code in F# Interactive kompilieren, unabhängig davon, ob die Ausführung interaktiv oder über ein Skript erfolgt, ist das Symbol **INTERACTIVE** definiert.</span><span class="sxs-lookup"><span data-stu-id="b311b-132">When you are compiling code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="b311b-133">Beim Kompilieren von Code im Compiler ist das Symbol **COMPILED** definiert.</span><span class="sxs-lookup"><span data-stu-id="b311b-133">When you are compiling code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="b311b-134">Wenn Code im Kompilierungsmodus und interaktiven Modus unterschiedlich sein muss, können Sie mithilfe von Präprozessoranweisungen für die bedingte Kompilierung bestimmen, welcher Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b311b-134">Thus, if code needs to be different in compiled and interactive modes, you can use preprocessor directives for conditional compilation to determine which to use.</span></span>

<span data-ttu-id="b311b-135">Beim Ausführen von Skripts in F# Interactive sind einige Direktiven verfügbar, die beim Ausführen des Compilers nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b311b-135">Some directives are available when you are executing scripts in F# Interactive that are not available when you are executing the compiler.</span></span> <span data-ttu-id="b311b-136">In der folgenden Tabelle sind die Direktiven zusammengefasst, die verfügbar sind, wenn Sie F# Interactive verwenden.</span><span class="sxs-lookup"><span data-stu-id="b311b-136">The following table summarizes directives that are available when you are using F# Interactive.</span></span>

|<span data-ttu-id="b311b-137">Anweisung</span><span class="sxs-lookup"><span data-stu-id="b311b-137">Directive</span></span>|<span data-ttu-id="b311b-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b311b-138">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="b311b-139">**#help**</span><span class="sxs-lookup"><span data-stu-id="b311b-139">**#help**</span></span>|<span data-ttu-id="b311b-140">Zeigt Informationen über verfügbare Anweisungen an.</span><span class="sxs-lookup"><span data-stu-id="b311b-140">Displays information about available directives.</span></span>|
|<span data-ttu-id="b311b-141">**#I**</span><span class="sxs-lookup"><span data-stu-id="b311b-141">**#I**</span></span>|<span data-ttu-id="b311b-142">Gibt einen Assemblysuchpfad an (in Anführungszeichen).</span><span class="sxs-lookup"><span data-stu-id="b311b-142">Specifies an assembly search path in quotation marks.</span></span>|
|<span data-ttu-id="b311b-143">**#load**</span><span class="sxs-lookup"><span data-stu-id="b311b-143">**#load**</span></span>|<span data-ttu-id="b311b-144">Liest eine Quelldatei, kompiliert sie und führt sie aus.</span><span class="sxs-lookup"><span data-stu-id="b311b-144">Reads a source file, compiles it, and runs it.</span></span>|
|<span data-ttu-id="b311b-145">**#quit**</span><span class="sxs-lookup"><span data-stu-id="b311b-145">**#quit**</span></span>|<span data-ttu-id="b311b-146">Beendet eine F# Interactive-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b311b-146">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="b311b-147">**#r**</span><span class="sxs-lookup"><span data-stu-id="b311b-147">**#r**</span></span>|<span data-ttu-id="b311b-148">Verweist auf eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="b311b-148">References an assembly.</span></span>|
|<span data-ttu-id="b311b-149">**#time ["on"&#124;"off"]**</span><span class="sxs-lookup"><span data-stu-id="b311b-149">**#time ["on"&#124;"off"]**</span></span>|<span data-ttu-id="b311b-150">Einzeln angegeben aktiviert bzw. deaktiviert **#time** die Anzeige von Leistungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="b311b-150">By itself, **#time** toggles whether to display performance information.</span></span> <span data-ttu-id="b311b-151">Wenn die Option aktiviert ist, überwacht F# Interactive die reale Zeit, die CPU-Zeit sowie Garbage Collection-Informationen für jeden Codeabschnitt, der interpretiert und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b311b-151">When it is enabled, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="b311b-152">Wenn Sie Dateien oder Pfade in F# Interactive angeben, wird ein Zeichenfolgenliteral erwartet.</span><span class="sxs-lookup"><span data-stu-id="b311b-152">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="b311b-153">Daher müssen Dateien und Pfade in Anführungszeichen stehen. Es gelten die üblichen Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="b311b-153">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="b311b-154">Zusätzlich können Sie das Zeichen @ verwenden. F# Interactive wird damit angewiesen, eine Zeichenfolge mit einem Pfad als wörtliche Zeichenfolge zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="b311b-154">Also, you can use the @ character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="b311b-155">F# Interactive ignoriert in diesem Fall alle Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="b311b-155">This causes F# Interactive to ignore any escape characters.</span></span>

<span data-ttu-id="b311b-156">Der Kompilierungsmodus und der interaktive Modus unterscheiden sich u. a. durch die Art des Zugriffs auf Befehlszeilenargumente.</span><span class="sxs-lookup"><span data-stu-id="b311b-156">One of the differences between compiled and interactive mode is the way you access command line arguments.</span></span> <span data-ttu-id="b311b-157">Verwenden Sie im Kompilierungsmodus **System.Environment.GetCommandLineArgs**.</span><span class="sxs-lookup"><span data-stu-id="b311b-157">In compiled mode, use **System.Environment.GetCommandLineArgs**.</span></span> <span data-ttu-id="b311b-158">Verwenden Sie in Skripts **fsi.CommandLineArgs**.</span><span class="sxs-lookup"><span data-stu-id="b311b-158">In scripts, use **fsi.CommandLineArgs**.</span></span>

<span data-ttu-id="b311b-159">Im folgenden Code wird das Erstellen einer Funktion veranschaulicht, die die Befehlszeilenargumente in einem Skript liest, und es wird außerdem gezeigt, wie aus einem Skript auf eine andere Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b311b-159">The following code illustrates how to create a function that reads the command line arguments in a script and also demonstrates how to reference another assembly from a script.</span></span> <span data-ttu-id="b311b-160">Die erste Codedatei **MyAssembly.fs** ist der Code für die Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b311b-160">The first code file, **MyAssembly.fs**, is the code for the assembly being referenced.</span></span> <span data-ttu-id="b311b-161">Kompilieren Sie diese Datei mit der Befehlszeile: **fsc -a MyAssembly.fs** und führen Sie dann die zweite Datei mit der Befehlszeile: **fsi --exec file1.fsx** testen</span><span class="sxs-lookup"><span data-stu-id="b311b-161">Compile this file with the command line: **fsc -a MyAssembly.fs** and then execute the second file as a script with the command line: **fsi --exec file1.fsx** test</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="b311b-162">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b311b-162">The output is as follows:</span></span>

```console
Command line arguments:
file1.fsx
test
90
```

## <a name="package-management-in-f-interactive"></a><span data-ttu-id="b311b-163">Paketverwaltung in F# Interactive</span><span class="sxs-lookup"><span data-stu-id="b311b-163">Package Management in F# Interactive</span></span>

[!NOTE] <span data-ttu-id="b311b-164">Die Paketverwaltung ist als Previewfunktion in Versionen von `dotnet fsi`, die in `3.1.300` und höheren Versionen des .NET SDK enthalten sind, sowie in allen `5.*`-Versionen des .NET SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b311b-164">Package management is available as a preview feature in versions of `dotnet fsi` shipped in the `3.1.300` and greater versions of the .NET SDK, as well as all `5.*` versions of the .NET SDK.</span></span> <span data-ttu-id="b311b-165">Führen Sie `dotnet fsi` mit dem Argument `--langversion:preview` aus, um es in dieser Vorschauversion zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b311b-165">To enable it in this preview release, run `dotnet fsi` with the `--langversion:preview` argument.</span></span>

<span data-ttu-id="b311b-166">Die `#r`-Syntax für das Verweisen auf eine DLL in F# Interactive kann auch verwendet werden, um auf ein NuGet-Paket über die folgende Syntax zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="b311b-166">The `#r` syntax for referencing a DLL in F# Interactive can also be used to reference a nuget package via the following syntax:</span></span>

```fsharp
#r "nuget: <package name>
```

<span data-ttu-id="b311b-167">Um beispielsweise auf das Paket `FSharp.Data` zu verweisen, verwenden Sie den folgenden `#r`-Verweis:</span><span class="sxs-lookup"><span data-stu-id="b311b-167">For example, to reference the `FSharp.Data` package, use the following `#r` reference:</span></span>

```fsharp
#r "nuget: FSharp.Data"
```

<span data-ttu-id="b311b-168">Nach Ausführung dieser Zeile wird die neueste Version des Pakets `FSharp.Data` in Ihren NuGet-Cache heruntergeladen, auf die in der aktuellen F# Interactive-Sitzung verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b311b-168">After executing this line, the latest version of the `FSharp.Data` package will be downloaded to your nuget cache and referenced in the current F# Interactive session.</span></span>

<span data-ttu-id="b311b-169">Zusätzlich zum Paketnamen kann über eine Kurzsyntax auf bestimmte Versionen eines Pakets verwiesen werden:</span><span class="sxs-lookup"><span data-stu-id="b311b-169">In addition to the package name, specific versions of a package can be referenced via a short syntax:</span></span>

```fsharp
#r "nuget: FSharp.Data, 3.3.2"
```

<span data-ttu-id="b311b-170">oder auf explizitere Weise:</span><span class="sxs-lookup"><span data-stu-id="b311b-170">or in a more explicit fashion:</span></span>

```fsharp
#r "nuget: FSharp.Data, Version=3.3.2"
```

## <a name="related-articles"></a><span data-ttu-id="b311b-171">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="b311b-171">Related articles</span></span>

|<span data-ttu-id="b311b-172">Titel</span><span class="sxs-lookup"><span data-stu-id="b311b-172">Title</span></span>|<span data-ttu-id="b311b-173">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b311b-173">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="b311b-174">F# Interactive-Optionen</span><span class="sxs-lookup"><span data-stu-id="b311b-174">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="b311b-175">Beschreibt die Befehlszeilensyntax und Optionen für F# Interactive (fsi.exe)</span><span class="sxs-lookup"><span data-stu-id="b311b-175">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
|[<span data-ttu-id="b311b-176">Referenz zur F# Interactive-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="b311b-176">F# Interactive Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-interactive-library-reference)|<span data-ttu-id="b311b-177">Beschreibt die beim Ausführen von Code in F# Interactive verfügbare Bibliotheksfunktion.</span><span class="sxs-lookup"><span data-stu-id="b311b-177">Describes library functionality available when executing code in F# interactive.</span></span>|
