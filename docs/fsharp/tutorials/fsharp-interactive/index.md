---
title: Referenz zu F# Interactive (dotnet)
description: Hier erfahren Sie, wie F# Interactive (dotnet fsi) zum interaktiven Ausführen von F#-Code in der Konsole oder zum Ausführen von F#-Skripts verwendet wird.
ms.date: 10/31/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: 89570a54ecebe625a1612e4b97b01c3693e4707c
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400865"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="bc622-103">Interaktive Programmierung mit F\#</span><span class="sxs-lookup"><span data-stu-id="bc622-103">Interactive programming with F\#</span></span>

<span data-ttu-id="bc622-104">F# Interactive (dotnet fsi) dient zum interaktiven Ausführen von F#-Code in der Konsole oder zum Ausführen von F#-Skripts.</span><span class="sxs-lookup"><span data-stu-id="bc622-104">F# Interactive (dotnet fsi) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="bc622-105">Dies bedeutet, dass F# Interactive eine REPL (Read, Evaluate, Print Loop = Lesen-Auswerten-Drucken-Schleife) für F# ausführt.</span><span class="sxs-lookup"><span data-stu-id="bc622-105">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="bc622-106">Führen Sie `dotnet fsi` aus, um F# Interactive in der Konsole auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bc622-106">To run F# Interactive from the console, run `dotnet fsi`.</span></span> <span data-ttu-id="bc622-107">Sie finden `dotnet fsi` in einem beliebigen .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="bc622-107">You will find `dotnet fsi` in any .NET SDK.</span></span>

<span data-ttu-id="bc622-108">Informationen zu verfügbaren Befehlszeilenoptionen finden Sie unter [F# Interactive-Optionen](../../language-reference/fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="bc622-108">For information about available command-line options, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

## <a name="executing-code-directly-in-f-interactive"></a><span data-ttu-id="bc622-109">Direktes Ausführen von Code in F# Interactive</span><span class="sxs-lookup"><span data-stu-id="bc622-109">Executing code directly in F# Interactive</span></span>

<span data-ttu-id="bc622-110">Da F# Interactive eine REPL (read-eval-print-Loop) ist, können Sie Code interaktiv in dieser Loop ausführen.</span><span class="sxs-lookup"><span data-stu-id="bc622-110">Because F# Interactive is a REPL (read-eval-print loop), you can execute code interactively in it.</span></span> <span data-ttu-id="bc622-111">Nachfolgend finden Sie ein Beispiel für eine interaktive Sitzung, nachdem `dotnet fsi` über die Befehlszeile ausgeführt wurde:</span><span class="sxs-lookup"><span data-stu-id="bc622-111">Here is an example of an interactive session after executing `dotnet fsi` from the command line:</span></span>

```console
Microsoft (R) F# Interactive version 11.0.0.0 for F# 5.0
Copyright (c) Microsoft Corporation. All Rights Reserved.

For help type #help;;

> let square x = x *  x;;
val square : x:int -> int

> square 12;;
val it : int = 144

> printfn "Hello, FSI!"
- ;;
Hello, FSI!
val it : unit = ()
```

<span data-ttu-id="bc622-112">Beachten Sie zwei wichtige Aspekte:</span><span class="sxs-lookup"><span data-stu-id="bc622-112">You'll notice two main things:</span></span>

1. <span data-ttu-id="bc622-113">Der gesamte Code muss zur Auswertung mit einem doppelten Semikolon (`;;`) beendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc622-113">All code must be terminated with a double semicolon (`;;`) to be evaluated</span></span>
2. <span data-ttu-id="bc622-114">Der Code wird ausgewertet und in einem `it`-Wert gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bc622-114">Code is evaluated and stored in an `it` value.</span></span> <span data-ttu-id="bc622-115">Sie können interaktiv auf `it` verweisen.</span><span class="sxs-lookup"><span data-stu-id="bc622-115">You can reference `it` interactively.</span></span>

<span data-ttu-id="bc622-116">F# Interactive unterstützt zudem mehrzeilige Eingaben.</span><span class="sxs-lookup"><span data-stu-id="bc622-116">F# Interactive also supports multi-line input.</span></span> <span data-ttu-id="bc622-117">Sie müssen Ihre Eingaben lediglich mit einem doppelten Semikolon (`;;`) beenden.</span><span class="sxs-lookup"><span data-stu-id="bc622-117">You just need to terminate your submission with a double semicolon (`;;`).</span></span> <span data-ttu-id="bc622-118">Sehen Sie sich den folgenden Ausschnitt an, der in F# Interactive eingefügt und ausgewertet wurde:</span><span class="sxs-lookup"><span data-stu-id="bc622-118">Consider the following snippet that has been pasted into and evaluated by F# Interactive:</span></span>

```console
> let getOddSquares xs =
-     xs
-     |> List.filter (fun x -> x % 2 <> 0)
-     |> List.map (fun x -> x * x)
-
- printfn "%A" (getOddSquares [1..10]);;
[1; 9; 25; 49; 81]
val getOddSquares : xs:int list -> int list
val it : unit = ()

>
```

<span data-ttu-id="bc622-119">Die Formatierung des Codes wird beibehalten, und die Eingabe wird durch ein doppeltes Semikolon (`;;`) beendet.</span><span class="sxs-lookup"><span data-stu-id="bc622-119">The code's formatting is preserved, and there is a double semicolon (`;;`) terminating the input.</span></span> <span data-ttu-id="bc622-120">Anschließend wurde der Code von F# Interactive ausgewertet, und die Ergebnisse wurden ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="bc622-120">F# Interactive then evaluated the code and printed the results!</span></span>

## <a name="scripting-with-f"></a><span data-ttu-id="bc622-121">Skripterstellung mit F\#</span><span class="sxs-lookup"><span data-stu-id="bc622-121">Scripting with F\#</span></span>

<span data-ttu-id="bc622-122">Die interaktive Auswertung von Code in F# Interactive ist eine hervorragende Lernmethode. Sie werden jedoch rasch feststellen, dass diese Vorgehensweise weniger produktiv ist als das Schreiben von Code in einem normalen Editor.</span><span class="sxs-lookup"><span data-stu-id="bc622-122">Evaluating code interactively in F# Interactive can be a great learning tool, but you'll quickly find that it's not as productive as writing code in a normal editor.</span></span> <span data-ttu-id="bc622-123">Um die reguläre Codebearbeitung zu unterstützen, können Sie F#-Skripts schreiben.</span><span class="sxs-lookup"><span data-stu-id="bc622-123">To support normal code editing, you can write F# scripts.</span></span>

<span data-ttu-id="bc622-124">Für Skripts wird die Dateierweiterung **.fsx** verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc622-124">Scripts use the file extension **.fsx**.</span></span> <span data-ttu-id="bc622-125">Statt Quellcode zu kompilieren und später die kompilierte Assembly auszuführen, können Sie einfach **dotnet fsi** ausführen und den Dateinamen des Skripts mit dem F#-Quellcode angeben. F# Interactive liest dann den Code und führt ihn in Echtzeit aus.</span><span class="sxs-lookup"><span data-stu-id="bc622-125">Instead of compiling source code and then later running the compiled assembly, you can just run **dotnet fsi** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span> <span data-ttu-id="bc622-126">Sehen wir uns z. B. das folgende Skript `Script.fsx` an:</span><span class="sxs-lookup"><span data-stu-id="bc622-126">For example, consider the following script called `Script.fsx`:</span></span>

```fsharp
let getOddSquares xs =
    xs
    |> List.filter (fun x -> x % 2 <> 0)
    |> List.map (fun x -> x * x)

getOddSquares [1..10]
```

<span data-ttu-id="bc622-127">Wenn diese Datei auf Ihrem Computer erstellt wird, können Sie sie mit `dotnet fsi` ausführen. Die Ausgabe wird unmittelbar in Ihrem Terminalfenster angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bc622-127">When this file is created in your machine, you can run it with `dotnet fsi` and see the output directly in your terminal window:</span></span>

```console
dotnet fsi Script.fsx
[1; 9; 25; 49; 81]
```

<span data-ttu-id="bc622-128">Das Erstellen von F#-Skripts wird nativ in [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md) und [Visual Studio für Mac](../../get-started/get-started-with-visual-studio-for-mac.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bc622-128">F# scripting is natively supported in [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md), and [Visual Studio for Mac](../../get-started/get-started-with-visual-studio-for-mac.md).</span></span>

## <a name="referencing-packages-in-f-interactive"></a><span data-ttu-id="bc622-129">Verweisen auf Pakete in F# Interactive</span><span class="sxs-lookup"><span data-stu-id="bc622-129">Referencing packages in F# Interactive</span></span>

> [!NOTE]
> <span data-ttu-id="bc622-130">Die Paketverwaltung ist ein F# 5-Feature, das derzeit bei Verwendung des aktuellen .NET 5-SDK verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bc622-130">Package management is an F# 5 feature and is currently available using the latest .NET 5 SDK.</span></span>

<span data-ttu-id="bc622-131">F# Interactive unterstützt Verweise auf NuGet-Pakete mit der `#r "nuget:"`-Syntax und einer optionalen Version:</span><span class="sxs-lookup"><span data-stu-id="bc622-131">F# Interactive supports referencing NuGet packages with the `#r "nuget:"` syntax and an optional version:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json"
open Newtonsoft.Json

let data = {| Name = "Don Syme"; Occupation = "F# Creator" |}
JsonConvert.SerializeObject(data)
```

<span data-ttu-id="bc622-132">Wenn keine Version angegeben wird, wird das höchste verfügbare Paket verwendet, bei dem es sich nicht um eine Vorschauversion handelt.</span><span class="sxs-lookup"><span data-stu-id="bc622-132">If a version is not specified, the highest available non-preview package is taken.</span></span> <span data-ttu-id="bc622-133">Um auf eine bestimmte Version zu verweisen, fügen Sie die Version mit Komma ein.</span><span class="sxs-lookup"><span data-stu-id="bc622-133">To reference a specific version, introduce the version via a comma.</span></span> <span data-ttu-id="bc622-134">Dies kann nützlich sein, um auf eine Vorschauversion eines Pakets zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="bc622-134">This can be handy when referencing a preview version of a package.</span></span> <span data-ttu-id="bc622-135">Sehen Sie sich z. B. das folgende Skript an, bei dem eine Vorschauversion von [DiffSharp](https://diffsharp.github.io/) verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="bc622-135">For example, consider this script using a preview version of [DiffSharp](https://diffsharp.github.io/):</span></span>

```fsharp
#r "nuget: DiffSharp-lite,1.0.0-preview-328097867"
open DiffSharp

// A 1D tensor
let t1 = dsharp.tensor [ 0.0 .. 0.2 .. 1.0 ]

// A 2x2 tensor
let t2 = dsharp.tensor [ [ 0; 1 ]; [ 2; 2 ] ]

// Define a scalar-to-scalar function
let f (x: Tensor) = sin (sqrt x)

printfn "%A" (f (dsharp.tensor 1.2))
```

<span data-ttu-id="bc622-136">Sie können beliebig viele Paketverweise in einem Skript angeben.</span><span class="sxs-lookup"><span data-stu-id="bc622-136">You can specify as many package references as you like in a script.</span></span>

## <a name="referencing-assemblies-on-disk-with-f-interactive"></a><span data-ttu-id="bc622-137">Verweisen auf Assemblys auf einem Datenträger mit F# Interactive</span><span class="sxs-lookup"><span data-stu-id="bc622-137">Referencing assemblies on disk with F# interactive</span></span>

<span data-ttu-id="bc622-138">Wenn Sie über eine Assembly auf einem Datenträger verfügen und in einem Skript auf diese Assembly verweisen möchten, können Sie sie mit der `#r`-Syntax angeben.</span><span class="sxs-lookup"><span data-stu-id="bc622-138">Alternatively, if you have an assembly on disk and wish to reference that in a script, you can use the `#r` syntax to specify an assembly.</span></span> <span data-ttu-id="bc622-139">Gehen wir von folgendem Code in einem Projekt aus, der in `MyAssembly.dll` kompiliert wird:</span><span class="sxs-lookup"><span data-stu-id="bc622-139">Consider the following code in a project compiled into `MyAssembly.dll`:</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

<span data-ttu-id="bc622-140">Nach der Kompilierung können Sie in einer Datei `Script.fsx` wie folgt darauf verweisen:</span><span class="sxs-lookup"><span data-stu-id="bc622-140">One compiled, you can reference it in a file called `Script.fsx` like so:</span></span>

```fsharp
#r "path/to/MyAssembly.dll"

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="bc622-141">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bc622-141">The output is as follows:</span></span>

```console
dotnet fsi Script.fsx
90
```

<span data-ttu-id="bc622-142">Sie können beliebig viele Assemblyverweise in einem Skript angeben.</span><span class="sxs-lookup"><span data-stu-id="bc622-142">You can specify as many assembly references as you like in a script.</span></span>

## <a name="loading-other-scripts"></a><span data-ttu-id="bc622-143">Laden anderer Skripts</span><span class="sxs-lookup"><span data-stu-id="bc622-143">Loading other scripts</span></span>

<span data-ttu-id="bc622-144">Bei der Skripterstellung ist es häufig nützlich, unterschiedliche Skripts für unterschiedliche Aufgaben zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc622-144">When scripting, it can often be helpful to use different scripts for different tasks.</span></span> <span data-ttu-id="bc622-145">In einigen Fällen bietet es sich an, Code aus einem Skript in einem anderen Skript wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="bc622-145">Sometimes you may want to reuse code from on script in another.</span></span> <span data-ttu-id="bc622-146">Anstatt die Skriptinhalte zu kopieren und in Ihrer Datei einzufügen, können Sie sie ganz einfach mit `#load` laden und auswerten.</span><span class="sxs-lookup"><span data-stu-id="bc622-146">Rather than copy-pasting its contents into your file, you can simple load and evaluate it with `#load`.</span></span>

<span data-ttu-id="bc622-147">Angenommen, Sie verfügen über die Datei `Script1.fsx`:</span><span class="sxs-lookup"><span data-stu-id="bc622-147">Consider the following `Script1.fsx`:</span></span>

```fsharp
let square x = x * x
```

<span data-ttu-id="bc622-148">Außerdem über die verbrauchende Datei `Script2.fsx`:</span><span class="sxs-lookup"><span data-stu-id="bc622-148">And the consuming file, `Script2.fsx`:</span></span>

```fsharp
#load "Script1.fsx"
open Script1

printfn "%d" (square 12)
```

<span data-ttu-id="bc622-149">Beachten Sie, dass die Deklaration `open Script1` erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="bc622-149">Note that the `open Script1` declaration is required.</span></span> <span data-ttu-id="bc622-150">Der Grund dafür ist, dass Konstrukte in einem F#-Skript in einem Modul der obersten Ebene kompiliert werden, das dem Namen der Skriptdatei entspricht, in dem es sich befindet.</span><span class="sxs-lookup"><span data-stu-id="bc622-150">This is because constructs in an F# script are compiled into a top-level module that is the name of the script file it is in.</span></span>

<span data-ttu-id="bc622-151">Sie können `Script2.fsx` wie folgt auswerten:</span><span class="sxs-lookup"><span data-stu-id="bc622-151">You can evaluate `Script2.fsx` like so:</span></span>

```console
dotnet fsi Script2.fsx
144
```

<span data-ttu-id="bc622-152">Sie können beliebig viele `#load`-Anweisungen in einem Skript angeben.</span><span class="sxs-lookup"><span data-stu-id="bc622-152">You can specify as many `#load` directives as you like in a script.</span></span>

## <a name="using-the-fsi-object-in-f-code"></a><span data-ttu-id="bc622-153">Verwenden des `fsi`-Objekts in F#-Code</span><span class="sxs-lookup"><span data-stu-id="bc622-153">Using the `fsi` object in F# code</span></span>

<span data-ttu-id="bc622-154">F#-Skripts können auf ein benutzerdefiniertes `fsi`-Objekt zugreifen, das die F# Interactive-Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="bc622-154">F# scripts have access to a custom `fsi` object that represents the F# Interactive session.</span></span> <span data-ttu-id="bc622-155">Mit diesem Objekt können Aspekte wie die Ausgabeformatierung angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="bc622-155">It allows you to customize things like output formatting.</span></span> <span data-ttu-id="bc622-156">Darüber hinaus können Sie auf diese Weise auf Befehlszeilenargumente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bc622-156">It is also how you can access command-line arguments.</span></span>

<span data-ttu-id="bc622-157">Im folgenden Beispiel wird gezeigt, wie Befehlszeilenargumente abgerufen und verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="bc622-157">The following example shows how to get and use command-line arguments:</span></span>

```fsharp
let args = fsi.CommandLineArgs

for arg in args do
    printfn "%s" arg
```

<span data-ttu-id="bc622-158">Bei der Auswertung werden alle Argumente ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="bc622-158">When evaluated, it prints all arguments.</span></span> <span data-ttu-id="bc622-159">Das erste Argument ist immer der Name des Skripts, das ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="bc622-159">The first argument is always the name of the script that is evaluated:</span></span>

```dotnet
dotnet fsi Script1.fsx hello world from fsi
Script1.fsx
hello
world
from
fsi
```

<span data-ttu-id="bc622-160">Sie können auch mit `System.Environment.GetCommandLineArgs()` auf diese Argumente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bc622-160">You can also use `System.Environment.GetCommandLineArgs()` to access the same arguments.</span></span>

## <a name="f-interactive-directive-reference"></a><span data-ttu-id="bc622-161">Referenz zu F# Interactive-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="bc622-161">F# Interactive directive reference</span></span>

<span data-ttu-id="bc622-162">Die zuvor erwähnten Anweisungen `#r` und `#load` sind nur in F# Interactive verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc622-162">The `#r` and `#load` directives seen previously are only available in F# Interactive.</span></span> <span data-ttu-id="bc622-163">Eine Reihe weiterer Anweisungen sind ebenfalls nur in F# Interactive verfügbar:</span><span class="sxs-lookup"><span data-stu-id="bc622-163">There are several directives only available in F# Interactive:</span></span>

|<span data-ttu-id="bc622-164">Anweisung</span><span class="sxs-lookup"><span data-stu-id="bc622-164">Directive</span></span>|<span data-ttu-id="bc622-165">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc622-165">Description</span></span>|
|---------|-----------|
|`#r "nuget:..."`|<span data-ttu-id="bc622-166">Verweist auf ein Paket aus NuGet.</span><span class="sxs-lookup"><span data-stu-id="bc622-166">References a package from NuGet</span></span>|
|`#r "assembly-name.dll"`|<span data-ttu-id="bc622-167">Verweist auf eine Assembly auf einem Datenträger</span><span class="sxs-lookup"><span data-stu-id="bc622-167">References an assembly on disk</span></span>|
|`#load "file-name.fsx"`|<span data-ttu-id="bc622-168">Liest eine Quelldatei, kompiliert sie und führt sie aus.</span><span class="sxs-lookup"><span data-stu-id="bc622-168">Reads a source file, compiles it, and runs it.</span></span>|
|`#help`|<span data-ttu-id="bc622-169">Zeigt Informationen über verfügbare Anweisungen an.</span><span class="sxs-lookup"><span data-stu-id="bc622-169">Displays information about available directives.</span></span>|
|`#I`|<span data-ttu-id="bc622-170">Gibt einen Assemblysuchpfad an (in Anführungszeichen).</span><span class="sxs-lookup"><span data-stu-id="bc622-170">Specifies an assembly search path in quotation marks.</span></span>|
|`#quit`|<span data-ttu-id="bc622-171">Beendet eine F# Interactive-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="bc622-171">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="bc622-172">`#time "on"` oder `#time "off"`</span><span class="sxs-lookup"><span data-stu-id="bc622-172">`#time "on"` or `#time "off"`</span></span>|<span data-ttu-id="bc622-173">Einzeln angegeben aktiviert bzw. deaktiviert `#time` die Anzeige von Leistungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="bc622-173">By itself, `#time` toggles whether to display performance information.</span></span> <span data-ttu-id="bc622-174">Wenn `"on"` festgelegt ist, überwacht F# Interactive die reale Zeit, die CPU-Zeit sowie Garbage Collection-Informationen für jeden Codeabschnitt, der interpretiert und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc622-174">When it is `"on"`, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="bc622-175">Wenn Sie Dateien oder Pfade in F# Interactive angeben, wird ein Zeichenfolgenliteral erwartet.</span><span class="sxs-lookup"><span data-stu-id="bc622-175">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="bc622-176">Daher müssen Dateien und Pfade in Anführungszeichen stehen. Es gelten die üblichen Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="bc622-176">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="bc622-177">Sie können das Zeichen `@` verwenden, damit F# Interactive eine Zeichenfolge mit einem Pfad als ausführliche Zeichenfolge interpretiert.</span><span class="sxs-lookup"><span data-stu-id="bc622-177">You can use the `@` character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="bc622-178">F# Interactive ignoriert in diesem Fall alle Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="bc622-178">This causes F# Interactive to ignore any escape characters.</span></span>

## <a name="interactive-and-compiled-preprocessor-directives"></a><span data-ttu-id="bc622-179">Interaktive und kompilierte Präprozessordirektiven</span><span class="sxs-lookup"><span data-stu-id="bc622-179">Interactive and compiled preprocessor directives</span></span>

<span data-ttu-id="bc622-180">Wenn Sie Code in F# Interactive kompilieren (unabhängig davon, ob die Ausführung interaktiv oder über ein Skript erfolgt), ist das Symbol **INTERACTIVE** definiert.</span><span class="sxs-lookup"><span data-stu-id="bc622-180">When you compile code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="bc622-181">Beim Kompilieren von Code im Compiler ist das Symbol **COMPILED** definiert.</span><span class="sxs-lookup"><span data-stu-id="bc622-181">When you compile code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="bc622-182">Wenn Code im Kompilierungsmodus und im interaktiven Modus unterschiedlich sein muss, können Sie mithilfe von Präprozessordirektiven für die bedingte Kompilierung bestimmen, welche Variante verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc622-182">Thus, if code needs to be different in compiled and interactive modes, you can use these preprocessor directives for conditional compilation to determine which to use.</span></span> <span data-ttu-id="bc622-183">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bc622-183">For example:</span></span>

```fsharp
#if INTERACTIVE
// Some code that executes only in FSI
// ...
#endif
```

## <a name="using-f-interactive-in-visual-studio"></a><span data-ttu-id="bc622-184">Verwenden von F# Interactive in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bc622-184">Using F# Interactive in Visual Studio</span></span>

<span data-ttu-id="bc622-185">Zum Ausführen von F# Interactive über Visual Studio können Sie auf die entsprechende Symbolleistenschaltfläche **F# Interactive** klicken oder die Tastenkombination **Strg+Alt+F** verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc622-185">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive** , or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="bc622-186">Dadurch wird das Interactive-Fenster geöffnet, ein Toolfenster, in dem eine F# Interactive-Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc622-186">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="bc622-187">Sie können auch Code auswählen, den Sie im interaktiven Fenster ausführen möchten, und die Tastenkombination **ALT+EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="bc622-187">You can also select some code that you want to run in the interactive window and hit the key combination **Alt+Enter**.</span></span> <span data-ttu-id="bc622-188">F# Interactive wird in einem Toolfenster mit der Bezeichnung **F# Interactive** gestartet.</span><span class="sxs-lookup"><span data-stu-id="bc622-188">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="bc622-189">Wenn Sie diese Tastenkombination verwenden, überprüfen Sie, ob das Editorfenster den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="bc622-189">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="bc622-190">Unabhängig davon, ob Sie die Konsole oder Visual Studio verwenden, wird eine Eingabeaufforderung angezeigt, und der Interpreter erwartet Ihre Eingabe.</span><span class="sxs-lookup"><span data-stu-id="bc622-190">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="bc622-191">Sie können Code auf die gleiche Weise wie in einer Codedatei eingeben.</span><span class="sxs-lookup"><span data-stu-id="bc622-191">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="bc622-192">Geben Sie zum Kompilieren und Ausführen des Codes zwei Semikolons ( **;;** ) ein, um eine oder mehrere Zeilen der Eingabe zu beenden.</span><span class="sxs-lookup"><span data-stu-id="bc622-192">To compile and execute the code, enter two semicolons ( **;;** ) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="bc622-193">F# Interactive beginnt mit der Kompilierung des Codes, und wenn der Code erfolgreich kompiliert wurde, führt F# Interactive den Code aus und gibt die Signatur der kompilierten Typen und Werte aus.</span><span class="sxs-lookup"><span data-stu-id="bc622-193">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="bc622-194">Wenn Fehler auftreten, gibt der Interpreter die Fehlermeldungen aus.</span><span class="sxs-lookup"><span data-stu-id="bc622-194">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="bc622-195">In der gleichen Sitzung eingegebener Code kann auf alle zuvor eingegebenen Konstrukte zugreifen. Daher können Sie Programme erstellen.</span><span class="sxs-lookup"><span data-stu-id="bc622-195">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="bc622-196">Ein umfangreicher Puffer im Toolfenster ermöglicht es Ihnen, den Code bei Bedarf in eine Datei zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="bc622-196">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="bc622-197">In Visual Studio wird F# Interactive unabhängig vom Projekt ausgeführt. Daher können Sie im Projekt definierte Konstrukte nur dann in F# Interactive verwenden, wenn Sie den Code für die Funktion in das Interactive-Fenster kopieren.</span><span class="sxs-lookup"><span data-stu-id="bc622-197">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="bc622-198">Sie können die Befehlszeilenargumente (Optionen) von F# Interactive steuern, indem Sie die Einstellungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="bc622-198">You can control the F# Interactive command-line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="bc622-199">Wählen Sie im Menü **Extras** den Eintrag **Optionen** aus, und erweitern Sie anschließend **F#-Tools**.</span><span class="sxs-lookup"><span data-stu-id="bc622-199">On the **Tools** menu, select **Options...** , and then expand **F# Tools**.</span></span> <span data-ttu-id="bc622-200">Die beiden Einstellungen, die Sie ändern können, sind die F# Interactive-Optionen und die Einstellung **64-Bit-F# Interactive** , die nur relevant ist, wenn Sie F# Interactive auf einem 64-Bit-Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="bc622-200">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="bc622-201">Mit dieser Einstellung legen Sie fest, ob Sie die dedizierte 64-Bit-Version von **fsi.exe** oder aber **fsianycpu.exe** ausführen möchten, die anhand der Computerarchitektur ermittelt, ob sie als 32-Bit- oder 64-Bit-Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc622-201">This setting determines whether you want to run the dedicated 64-bit version of **fsi.exe** or **fsianycpu.exe** , which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bc622-202">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="bc622-202">Related articles</span></span>

|<span data-ttu-id="bc622-203">Titel</span><span class="sxs-lookup"><span data-stu-id="bc622-203">Title</span></span>|<span data-ttu-id="bc622-204">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc622-204">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="bc622-205">F# Interactive-Optionen</span><span class="sxs-lookup"><span data-stu-id="bc622-205">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="bc622-206">Beschreibt die Befehlszeilensyntax und Optionen für F# Interactive (fsi.exe)</span><span class="sxs-lookup"><span data-stu-id="bc622-206">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
