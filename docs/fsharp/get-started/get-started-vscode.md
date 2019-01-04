---
title: Erste Schritte mit F# in Visual Studio Code
description: Erfahren Sie, wie Sie F# mit Visual Studio Code und Ionide-Plug-Ins Suite verwenden.
ms.date: 12/23/2018
ms.openlocfilehash: 34802551bf4e34abb5aa0130643f32dbce68f1b2
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54029553"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="cd262-103">Erste Schritte mit F# in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cd262-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="cd262-104">Können Sie F# in schreiben [Visual Studio Code](https://code.visualstudio.com) mit der [Ionide-Plug-Ins](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) um plattformübergreifende, einfache (Integrated Development Environment, IDE) Erfahrung mit IntelliSense und basic-Code zu erhalten. Refactorings.</span><span class="sxs-lookup"><span data-stu-id="cd262-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="cd262-105">Besuchen Sie [Ionide.io](http://ionide.io) Weitere Informationen zu den-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="cd262-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="cd262-106">Um zu beginnen, stellen Sie sicher, dass man [F# und Ionide-Plug-in ordnungsgemäß installiert](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="cd262-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="cd262-107">Erstellen Ihres ersten Projekts mit Ionide</span><span class="sxs-lookup"><span data-stu-id="cd262-107">Creating your first project with Ionide</span></span>

<span data-ttu-id="cd262-108">Zum Erstellen eines neuen F# Projekt, öffnen Sie Visual Studio Code in einen neuen Ordner (Sie können sie einen beliebigen Namen).</span><span class="sxs-lookup"><span data-stu-id="cd262-108">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="cd262-109">Öffnen Sie als Nächstes die befehlspalette (**Ansicht > Befehlspalette**) und geben Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cd262-109">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="cd262-110">Dieser Vorgang beruht die [FÄLSCHEN](https://github.com/fsharp-editing/Forge) Projekt.</span><span class="sxs-lookup"><span data-stu-id="cd262-110">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="cd262-111">Wenn Sie Vorlagenoptionen für die nicht angezeigt wird, versuchen Sie es Aktualisieren von Vorlagen mithilfe des folgenden Befehls in der Befehlspalette: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="cd262-111">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="cd262-112">Wählen Sie "F#: Neues Projekt"durch Drücken von **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="cd262-112">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="cd262-113">Dadurch gelangen Sie mit dem nächsten Schritt, die für das Auswählen einer Projektvorlage.</span><span class="sxs-lookup"><span data-stu-id="cd262-113">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="cd262-114">Wählen Sie die `classlib` Vorlage und Trefferanzahl **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="cd262-114">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="cd262-115">Wählen Sie als Nächstes ein Verzeichnis zum Erstellen des Projekts in ein.</span><span class="sxs-lookup"><span data-stu-id="cd262-115">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="cd262-116">Wenn Sie sie leer lassen, wird das aktuelle Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd262-116">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="cd262-117">Zum Schluss benennen Sie Ihr Projekt im letzten Schritt an.</span><span class="sxs-lookup"><span data-stu-id="cd262-117">Finally, name your project in the final step.</span></span> <span data-ttu-id="cd262-118">F#verwendet [Pascal-Schreibweise](http://c2.com/cgi/wiki?PascalCase) für Projektnamen.</span><span class="sxs-lookup"><span data-stu-id="cd262-118">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="cd262-119">In diesem Artikel wird `ClassLibraryDemo` als Namen.</span><span class="sxs-lookup"><span data-stu-id="cd262-119">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="cd262-120">Wenn Sie den Namen eingegeben haben, für das Projekt erstellt werden sollen, drücken Sie **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="cd262-120">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="cd262-121">Wenn Sie den vorherigen Schritt ausgeführt haben, erhalten Sie Visual Studio Code-Arbeitsbereich auf der linken Seite mit den folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cd262-121">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="cd262-122">Die F# Projekt selbst, darunter die `ClassLibraryDemo` Ordner.</span><span class="sxs-lookup"><span data-stu-id="cd262-122">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="cd262-123">Zum Hinzufügen von Paketen über die richtige Verzeichnisstruktur [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="cd262-123">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="cd262-124">Eine plattformübergreifende Buildskript mit [ `FAKE` ](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="cd262-124">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="cd262-125">Die `paket.exe` ausführbare Datei, Abrufen von Paketen und Abhängigkeiten für Sie beheben kann.</span><span class="sxs-lookup"><span data-stu-id="cd262-125">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="cd262-126">Ein `.gitignore` Datei, wenn Sie dieses Projekt zur quellcodeverwaltung im Git-basierte hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="cd262-126">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="cd262-127">Schreiben von code</span><span class="sxs-lookup"><span data-stu-id="cd262-127">Writing some code</span></span>

<span data-ttu-id="cd262-128">Öffnen der *ClassLibraryDemo* Ordner.</span><span class="sxs-lookup"><span data-stu-id="cd262-128">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="cd262-129">Daraufhin sollte die folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="cd262-129">You should see the following files:</span></span>

1. <span data-ttu-id="cd262-130">`ClassLibraryDemo.fs`, eine F# Implementierungsdatei mit einer definierten Klasse.</span><span class="sxs-lookup"><span data-stu-id="cd262-130">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="cd262-131">`ClassLibraryDemo.fsproj`, eine F# Projektdatei verwendet, um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd262-131">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="cd262-132">`Script.fsx`, eine F# -Skriptdatei, die von der Quelldatei geladen.</span><span class="sxs-lookup"><span data-stu-id="cd262-132">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="cd262-133">`paket.references`, ein Paket-Abhängigkeits-Datei, die die Abhängigkeiten des Projekts angibt.</span><span class="sxs-lookup"><span data-stu-id="cd262-133">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="cd262-134">Open `Script.fsx`, und fügen Sie den folgenden Code am Ende des Zertifikats:</span><span class="sxs-lookup"><span data-stu-id="cd262-134">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="cd262-135">Diese Funktion konvertiert ein Wort in eine Form der [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="cd262-135">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="cd262-136">Der nächste Schritt ist mit F# Interactive (FSI) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="cd262-136">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="cd262-137">Markieren Sie die gesamte Funktion (es sollte 11 Zeilen lang sein).</span><span class="sxs-lookup"><span data-stu-id="cd262-137">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="cd262-138">Sobald er hervorgehoben wird, enthalten die **Alt** Schlüssel, und klicken Sie auf **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="cd262-138">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="cd262-139">Sehen Sie ein Fenster angezeigt werden, unten, und es sollte etwa wie folgt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cd262-139">You'll notice a window pop up below, and it should show something like this:</span></span>

![Beispiel für F# Interactive-Ausgabe mit Ionide](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="cd262-141">In diesem Fall drei Dinge:</span><span class="sxs-lookup"><span data-stu-id="cd262-141">This did three things:</span></span>

1. <span data-ttu-id="cd262-142">Es werden die FSI-Prozess wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="cd262-142">It started the FSI process.</span></span>
2. <span data-ttu-id="cd262-143">Sie haben den markierten Code über den Prozess FSI gesendet.</span><span class="sxs-lookup"><span data-stu-id="cd262-143">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="cd262-144">Der Prozess FSI ausgewertet den Code, dem Sie über gesendet.</span><span class="sxs-lookup"><span data-stu-id="cd262-144">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="cd262-145">Da war gesendeten über eine [Funktion](../language-reference/functions/index.md), Sie können nun Aufrufen dieser Funktion mit FSI!</span><span class="sxs-lookup"><span data-stu-id="cd262-145">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="cd262-146">Geben Sie im interactive-Fenster Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cd262-146">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="cd262-147">Daraufhin sollte das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="cd262-147">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="cd262-148">Jetzt testen wir ein Vokal als den ersten Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="cd262-148">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="cd262-149">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cd262-149">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="cd262-150">Daraufhin sollte das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="cd262-150">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="cd262-151">Die Funktion wird wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cd262-151">The function appears to be working as expected.</span></span> <span data-ttu-id="cd262-152">Herzlichen Glückwunsch, Sie soeben geschrieben haben Ihre erste F# Funktion in Visual Studio Code, und es mit FSI ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="cd262-152">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="cd262-153">Wie Sie möglicherweise bemerkt haben, werden die Zeilen in FSI mit beendet `;;`.</span><span class="sxs-lookup"><span data-stu-id="cd262-153">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="cd262-154">Dies ist da FSI mehrere Zeilen eingeben kann.</span><span class="sxs-lookup"><span data-stu-id="cd262-154">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="cd262-155">Die `;;` können Sie am Ende FSI wissen, wann der Code beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="cd262-155">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="cd262-156">Erläutern den code</span><span class="sxs-lookup"><span data-stu-id="cd262-156">Explaining the code</span></span>

<span data-ttu-id="cd262-157">Wenn Sie nicht sicher sind, zu der Code tatsächlich Wozu dient, wird eine detaillierte Anleitung.</span><span class="sxs-lookup"><span data-stu-id="cd262-157">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="cd262-158">Wie Sie sehen können, `toPigLatin` ist eine Funktion, die ein Wort als Eingabe und konvertiert es in ein Pig-Latin-Darstellung des Begriffs.</span><span class="sxs-lookup"><span data-stu-id="cd262-158">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="cd262-159">Die Regeln für diese sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="cd262-159">The rules for this are as follows:</span></span>

<span data-ttu-id="cd262-160">Wenn das erste Zeichen in einem Wort mit einem Vokal beginnt, fügen Sie am Ende des Worts "juhu" hinzu.</span><span class="sxs-lookup"><span data-stu-id="cd262-160">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="cd262-161">Wenn sie mit einem Vokal nicht startet, wird verschieben Sie dem ersten Zeichen am Ende des Worts zu, und fügen Sie "Weg" hinzu.</span><span class="sxs-lookup"><span data-stu-id="cd262-161">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="cd262-162">Sie haben möglicherweise im FSI Folgendes festgestellt:</span><span class="sxs-lookup"><span data-stu-id="cd262-162">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="cd262-163">Dies gibt an, dass `toPigLatin` ist eine Funktion, die in akzeptiert eine `string` als Eingabe (namens `word`), und wird ein anderes `string`.</span><span class="sxs-lookup"><span data-stu-id="cd262-163">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="cd262-164">Dies bezeichnet man als den [der Typsignatur der Funktion](https://fsharpforfunandprofit.com/posts/function-signatures/), ein wesentlicher Bestandteil von F#, die Schlüssel zum Verständnis der F#-Code ist.</span><span class="sxs-lookup"><span data-stu-id="cd262-164">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="cd262-165">Sie werden dies auch feststellen, wenn Sie darauf zeigen, dass die Funktion in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="cd262-165">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="cd262-166">In den Text der Funktion sehen Sie zwei Teile:</span><span class="sxs-lookup"><span data-stu-id="cd262-166">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="cd262-167">Eine innere Funktion namens `isVowel`, die bestimmt, ob ein angegebenes Zeichen (`c`) überprüfen, ob diese einer der über die angegebenen Muster entspricht, besteht ein Vokal [Musterabgleich](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="cd262-167">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="cd262-168">Ein [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) -Ausdruck, der prüft, ob das erste Zeichen ist ein Vokal Konstrukte, die einen Rückgabewert aus der Eingabezeichen abhängig, ob das erste Zeichen wurde ein Vokal oder nicht:</span><span class="sxs-lookup"><span data-stu-id="cd262-168">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="cd262-169">Die ablaufsteuerung `toPigLatin` ist daher:</span><span class="sxs-lookup"><span data-stu-id="cd262-169">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="cd262-170">Überprüfen Sie, ob das erste Zeichen des eingegebenen Worts ein Vokal ist.</span><span class="sxs-lookup"><span data-stu-id="cd262-170">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="cd262-171">Wenn es sich handelt, fügen Sie am Ende des Worts "juhu".</span><span class="sxs-lookup"><span data-stu-id="cd262-171">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="cd262-172">Andernfalls verschieben Sie dem ersten Zeichen am Ende des Worts zu, und fügen Sie "Weg" hinzu.</span><span class="sxs-lookup"><span data-stu-id="cd262-172">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="cd262-173">Eine letzte Sache dazu bitte beachten Sie: Es gibt keine explizite Anweisung von der Funktion, im Gegensatz zu es viele weitere Sprachen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cd262-173">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="cd262-174">Dies ist da F# ausdrucksbasiert ist, und der letzte Ausdruck in den Hauptteil einer Funktion der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="cd262-174">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="cd262-175">Da `if..then..else` ist selbst ein Ausdruck, der Text der der `then` Block oder im Text der der `else` Block wird je nach dem eingegebenen Wert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd262-175">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="cd262-176">Verschieben von Skriptcode in der Implementierungsdatei hinzu</span><span class="sxs-lookup"><span data-stu-id="cd262-176">Moving your script code into the implementation file</span></span>

<span data-ttu-id="cd262-177">Die vorherigen Abschnitten in diesem Artikel veranschaulicht die allgemeine ersten Schritt bei der Schreiben von F# Code: das Schreiben einer anfänglichen-Funktion und interaktiv mit FSI ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd262-177">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="cd262-178">Dies bezeichnet man als REPL-driven Development, in denen [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) steht für "Lesen-auswerten-ausgeben-Schleife".</span><span class="sxs-lookup"><span data-stu-id="cd262-178">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="cd262-179">Es ist eine hervorragende Möglichkeit, mit der Funktionalität zu experimentieren, bis Sie funktioniert haben.</span><span class="sxs-lookup"><span data-stu-id="cd262-179">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="cd262-180">Der nächste Schritt im REPL-driven Development, verschieben Sie den funktionierenden Code in ist eine F# Implementierungsdatei einschließen.</span><span class="sxs-lookup"><span data-stu-id="cd262-180">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="cd262-181">Sie können dann kompiliert werden, indem die F# Compiler in eine Assembly, die ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="cd262-181">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="cd262-182">Öffnen Sie zunächst `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="cd262-182">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="cd262-183">Sie werden feststellen, dass der Code bereits vorhanden vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cd262-183">You'll notice that some code is already in there.</span></span> <span data-ttu-id="cd262-184">Fahren Sie fort, und löschen Sie die Definition der Klasse, aber stellen Sie sicher, dass die [ `namespace` ](../language-reference/namespaces.md) Deklaration oben.</span><span class="sxs-lookup"><span data-stu-id="cd262-184">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="cd262-185">Als Nächstes erstellen Sie ein neues [ `module` ](../language-reference/modules.md) namens `PigLatin` , und kopieren Sie die `toPigLatin` als solche in diese Funktion:</span><span class="sxs-lookup"><span data-stu-id="cd262-185">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="cd262-186">Öffnen Sie als Nächstes die `Script.fsx` -Datei erneut, und löschen Sie das gesamte `toPigLatin` funktionieren, aber Achten Sie darauf, halten die folgenden zwei Zeilen in der Datei:</span><span class="sxs-lookup"><span data-stu-id="cd262-186">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```
<span data-ttu-id="cd262-187">Wählen Sie die beiden Textzeilen aus, und drücken Sie Alt + Eingabetaste, um diese Zeilen in FSI auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cd262-187">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="cd262-188">Diese lädt den Inhalt der Pig Latin-Bibliothek in den FSI-Prozess und `open` der `ClassLibraryDemo` Namespace, damit Sie Zugriff auf die Funktionalität haben.</span><span class="sxs-lookup"><span data-stu-id="cd262-188">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="cd262-189">Rufen Sie als Nächstes im Fenster FSI-Funktion mit dem `PigLatin` -Modul, das Sie zuvor definiert:</span><span class="sxs-lookup"><span data-stu-id="cd262-189">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="cd262-190">Erfolgreich!</span><span class="sxs-lookup"><span data-stu-id="cd262-190">Success!</span></span> <span data-ttu-id="cd262-191">Sie erhalten dieselben Ergebnisse wie bisher, aber jetzt aus geladen ein F# Implementierungsdatei einschließen.</span><span class="sxs-lookup"><span data-stu-id="cd262-191">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="cd262-192">Der wesentliche Unterschied besteht darin, die F# Quelldateien kompiliert werden, in Assemblys, die nicht nur in FSI überall ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="cd262-192">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="cd262-193">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd262-193">Summary</span></span>

<span data-ttu-id="cd262-194">In diesem Artikel haben Sie Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="cd262-194">In this article, you've learned:</span></span>

1. <span data-ttu-id="cd262-195">Wie Sie Visual Studio Code mit Ionide einrichten.</span><span class="sxs-lookup"><span data-stu-id="cd262-195">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="cd262-196">Vorgehensweise: Erstellen Ihrer ersten F# -Projekts mit Ionide.</span><span class="sxs-lookup"><span data-stu-id="cd262-196">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="cd262-197">Gewusst wie: Verwenden Sie F# Skripterstellung zum Schreiben Ihrer ersten F# im Ionide funktionieren, und führen Sie ihn anschließend in FSI.</span><span class="sxs-lookup"><span data-stu-id="cd262-197">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="cd262-198">Gewusst wie: Migrieren zu Skriptcode F# Datenquelle, und rufen Sie dann diesen Code von FSI.</span><span class="sxs-lookup"><span data-stu-id="cd262-198">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="cd262-199">Sie sind jetzt noch viel mehr schreiben ausgestattet F# code mit Visual Studio Code und Ionide.</span><span class="sxs-lookup"><span data-stu-id="cd262-199">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="cd262-200">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="cd262-200">Troubleshooting</span></span>

<span data-ttu-id="cd262-201">Hier sind einige Möglichkeiten, wie, die Sie bestimmte Probleme beheben können, denen auftreten können:</span><span class="sxs-lookup"><span data-stu-id="cd262-201">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="cd262-202">Um den Code Bearbeitungsfunktionen Ionide, erhalten Ihre F# müssen Dateien gespeichert werden, auf dem Datenträger und in einen Ordner, der in der Visual Studio Code-Arbeitsbereich geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="cd262-202">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="cd262-203">Wenn Sie Änderungen an Ihrem System oder Ionide erforderlichen Komponenten installiert, mit Visual Studio Code geöffnet haben, starten Sie Visual Studio Code neu.</span><span class="sxs-lookup"><span data-stu-id="cd262-203">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="cd262-204">Überprüfen Sie, dass Sie die F#-Compiler und F# interactive über die Befehlszeile ohne einen vollständig qualifizierten Pfad verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cd262-204">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="cd262-205">Sie können dazu eingeben `fsc` in einer Befehlszeile für den F#-Compiler und `fsi` oder `fsharpi` für die Visual F#-tools für Windows und Mono unter Mac/Linux, bzw.</span><span class="sxs-lookup"><span data-stu-id="cd262-205">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="cd262-206">Wenn Sie ungültige Zeichen in Ihrem Projektverzeichnisse verfügen, funktionieren möglicherweise nicht Ionide.</span><span class="sxs-lookup"><span data-stu-id="cd262-206">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="cd262-207">Benennen Sie Ihre Projektverzeichnisse, wenn dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="cd262-207">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="cd262-208">Wenn keines der Ionide-Befehle verwenden, überprüfen Sie Ihre [standardtastenzuordnungen von Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) um festzustellen, ob Sie sie versehentlich überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="cd262-208">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="cd262-209">Versuchen Sie es entfernen, wenn Ionide auf Ihrem Computer aufgeteilt wird und keines der genannten wurde das Problem behoben, die `ionide-fsharp` Verzeichnis auf Ihrem Computer und installieren Sie die Suite-Plug-In erneut.</span><span class="sxs-lookup"><span data-stu-id="cd262-209">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="cd262-210">Ionide ist ein open-Source-Projekt, erstellt und verwaltet, die von einem Mitglied der F# Community.</span><span class="sxs-lookup"><span data-stu-id="cd262-210">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="cd262-211">Sie Probleme melden und gerne am beitragen die [Ionide-VSCode: FSharp-GitHub-Repository](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="cd262-211">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="cd262-212">Wenn Sie ein Problem gemeldet haben, führen Sie [die Anweisungen zum Abrufen von Protokollen zu verwenden, wenn ein Problem meldet](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="cd262-212">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="cd262-213">Sie können auch weitere Hilfe bitten, aus der Ionide-Entwickler und F#-Community in den [Ionide Gitter Kanal](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="cd262-213">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cd262-214">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cd262-214">Next steps</span></span>

<span data-ttu-id="cd262-215">Weitere Informationen zu F# und die Funktionen der Sprache, sehen Sie sich [Einführung in F#](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="cd262-215">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
