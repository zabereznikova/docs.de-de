---
title: Erste Schritte mit F# in Visual Studio Code
description: Erfahren Sie, wie Sie F# mit Visual Studio Code und Ionide-Plug-Ins Suite verwenden.
ms.date: 12/23/2018
ms.openlocfilehash: baaa87207122cfe314972aee5dfaf8a41de2c394
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629976"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="690c7-103">Erste Schritte mit F# in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="690c7-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="690c7-104">Können Sie F# in schreiben [Visual Studio Code](https://code.visualstudio.com) mit der [Ionide-Plug-Ins](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) um plattformübergreifende, einfache (Integrated Development Environment, IDE) Erfahrung mit IntelliSense und basic-Code zu erhalten. Refactorings.</span><span class="sxs-lookup"><span data-stu-id="690c7-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="690c7-105">Besuchen Sie [Ionide.IO](http://ionide.io) , um mehr über das Plug-in zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="690c7-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="690c7-106">Um zu beginnen, stellen Sie sicher, dass man [F# und Ionide-Plug-in ordnungsgemäß installiert](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="690c7-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="690c7-107">Ionide generiert .NET Framework F# Projekte, nicht dotnet Core, die plattformübergreifende Kompatibilitätsprobleme aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="690c7-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="690c7-108">Wenn Sie **Linux** oder **OSX**ausführen, können Sie mit den [Befehlszeilen Tools](get-started-command-line.md)einfacher loslegen.</span><span class="sxs-lookup"><span data-stu-id="690c7-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command-line tools](get-started-command-line.md).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="690c7-109">Erstellen Ihres ersten Projekts mit ionide</span><span class="sxs-lookup"><span data-stu-id="690c7-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="690c7-110">Um ein neues F# Projekt zu erstellen, öffnen Sie Visual Studio Code in einem neuen Ordner (Sie können den Namen beliebig benennen).</span><span class="sxs-lookup"><span data-stu-id="690c7-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="690c7-111">Öffnen Sie als nächstes die Befehls Palette (zeigen Sie **> Befehls Palette**an), und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="690c7-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="690c7-112">Dies wird durch das Projekt " [Schmieden](https://github.com/fsharp-editing/Forge) " unterrichtet.</span><span class="sxs-lookup"><span data-stu-id="690c7-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="690c7-113">Wenn Sie keine Vorlagen Optionen sehen, versuchen Sie, Vorlagen zu aktualisieren, indem Sie den folgenden Befehl in `>F#: Refresh Project Templates`der Befehls Palette ausführen:.</span><span class="sxs-lookup"><span data-stu-id="690c7-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="690c7-114">Wählen SieF#": Neues Projekt "durch Drücken der **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="690c7-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="690c7-115">Dadurch gelangen Sie zum nächsten Schritt, in dem Sie eine Projektvorlage auswählen.</span><span class="sxs-lookup"><span data-stu-id="690c7-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="690c7-116">Wählen Sie `classlib` die Vorlage, und drücken **Sie die Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="690c7-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="690c7-117">Wählen Sie als nächstes ein Verzeichnis aus, in dem Sie das Projekt erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="690c7-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="690c7-118">Wenn Sie das Feld leer lassen, wird das aktuelle Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="690c7-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="690c7-119">Benennen Sie Ihr Projekt abschließend im letzten Schritt.</span><span class="sxs-lookup"><span data-stu-id="690c7-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="690c7-120">F#verwendet die [Pascal](http://c2.com/cgi/wiki?PascalCase) -Schreibweise für Projektnamen.</span><span class="sxs-lookup"><span data-stu-id="690c7-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="690c7-121">In diesem Artikel `ClassLibraryDemo` wird als Name verwendet.</span><span class="sxs-lookup"><span data-stu-id="690c7-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="690c7-122">Wenn Sie den gewünschten Namen für Ihr Projekt eingegeben haben, drücken Sie die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="690c7-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="690c7-123">Wenn Sie den vorherigen Schritt befolgt haben, sollte der Visual Studio Code Arbeitsbereich auf der linken Seite angezeigt werden, um Folgendes anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="690c7-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="690c7-124">Das F# Projekt selbst unterhalb des `ClassLibraryDemo` Ordners.</span><span class="sxs-lookup"><span data-stu-id="690c7-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="690c7-125">Die richtige Verzeichnisstruktur zum Hinzufügen von [`Paket`](https://fsprojects.github.io/Paket/)Paketen über.</span><span class="sxs-lookup"><span data-stu-id="690c7-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="690c7-126">Ein plattformübergreifendes Buildskript mit [`FAKE`](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="690c7-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="690c7-127">Die `paket.exe` ausführbare Datei, die Pakete abrufen und Abhängigkeiten für Sie auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="690c7-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="690c7-128">Eine `.gitignore` Datei, wenn Sie dieses Projekt der git-basierten Quell Code Verwaltung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="690c7-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="690c7-129">Schreiben von Code</span><span class="sxs-lookup"><span data-stu-id="690c7-129">Writing some code</span></span>

<span data-ttu-id="690c7-130">Öffnen Sie den Ordner *classlibrarydemo* .</span><span class="sxs-lookup"><span data-stu-id="690c7-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="690c7-131">Die folgenden Dateien sollten angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="690c7-131">You should see the following files:</span></span>

1. <span data-ttu-id="690c7-132">`ClassLibraryDemo.fs`, eine F# Implementierungs Datei, für die eine Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="690c7-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="690c7-133">`ClassLibraryDemo.fsproj`, eine F# Projektdatei, die zum Erstellen dieses Projekts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="690c7-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="690c7-134">`Script.fsx`, eine F# Skriptdatei, die die Quelldatei lädt.</span><span class="sxs-lookup"><span data-stu-id="690c7-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="690c7-135">`paket.references`, eine Paket Datei, die die Projekt Abhängigkeiten angibt.</span><span class="sxs-lookup"><span data-stu-id="690c7-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="690c7-136">Öffnen `Script.fsx`Sie, und fügen Sie den folgenden Code am Ende der Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="690c7-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="690c7-137">Diese Funktion konvertiert ein Wort in eine Form von [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="690c7-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="690c7-138">Der nächste Schritt ist mit F# Interactive (FSI) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="690c7-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="690c7-139">Markieren Sie die gesamte Funktion (es sollte 11 Zeilen lang sein).</span><span class="sxs-lookup"><span data-stu-id="690c7-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="690c7-140">Halten Sie die **alt** -Taste gedrückt, und drücken **Sie die Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="690c7-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="690c7-141">Sie sehen, dass ein Fenster unten angezeigt wird, und es sollte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="690c7-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![Beispiel für F# Interactive-Ausgabe mit Ionide](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="690c7-143">Dies hat drei Dinge getan:</span><span class="sxs-lookup"><span data-stu-id="690c7-143">This did three things:</span></span>

1. <span data-ttu-id="690c7-144">Der FSI-Prozess wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="690c7-144">It started the FSI process.</span></span>
2. <span data-ttu-id="690c7-145">Der Code, den Sie über den FSI-Prozess hervorgehoben haben, wurde gesendet.</span><span class="sxs-lookup"><span data-stu-id="690c7-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="690c7-146">Der FSI-Prozess hat den Code ausgewertet, den Sie gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="690c7-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="690c7-147">Da das, was Sie gesendet haben, eine [Funktion](../language-reference/functions/index.md)war, können Sie diese Funktion jetzt mit FSI abrufen!</span><span class="sxs-lookup"><span data-stu-id="690c7-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="690c7-148">Geben Sie im interaktiven Fenster Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="690c7-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="690c7-149">Das folgende Ergebnis sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="690c7-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="690c7-150">Nun versuchen wir, einen Vokal als ersten Buchstaben zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="690c7-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="690c7-151">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="690c7-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="690c7-152">Das folgende Ergebnis sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="690c7-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="690c7-153">Die Funktion scheint erwartungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="690c7-153">The function appears to be working as expected.</span></span> <span data-ttu-id="690c7-154">Herzlichen Glückwunsch, Sie haben Ihre F# erste Funktion in Visual Studio Code geschrieben und mit FSI ausgewertet!</span><span class="sxs-lookup"><span data-stu-id="690c7-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="690c7-155">Wie Sie vielleicht bemerkt haben, werden die Zeilen in FSI mit `;;`beendet.</span><span class="sxs-lookup"><span data-stu-id="690c7-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="690c7-156">Dies liegt daran, dass Sie mithilfe von FSI mehrere Zeilen eingeben können.</span><span class="sxs-lookup"><span data-stu-id="690c7-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="690c7-157">Der `;;` am Ende ermöglicht FSI, wenn der Code abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="690c7-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="690c7-158">Erläutern des Codes</span><span class="sxs-lookup"><span data-stu-id="690c7-158">Explaining the code</span></span>

<span data-ttu-id="690c7-159">Wenn Sie nicht sicher sind, was der Code tatsächlich macht, finden Sie hier eine Schritt-für-Schritt-Anleitung.</span><span class="sxs-lookup"><span data-stu-id="690c7-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="690c7-160">Wie Sie sehen können, `toPigLatin` ist eine Funktion, die ein Wort als Eingabe annimmt und in eine Pig-Latin-Darstellung dieses Worts konvertiert.</span><span class="sxs-lookup"><span data-stu-id="690c7-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="690c7-161">Dies sind die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="690c7-161">The rules for this are as follows:</span></span>

<span data-ttu-id="690c7-162">Wenn das erste Zeichen in einem Wort mit einem vowel beginnt, fügen Sie am Ende des Worts "yay" hinzu.</span><span class="sxs-lookup"><span data-stu-id="690c7-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="690c7-163">Wenn er nicht mit einem vowel beginnt, verschieben Sie das erste Zeichen an das Ende des Worts, und fügen Sie ihm "ay" hinzu.</span><span class="sxs-lookup"><span data-stu-id="690c7-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="690c7-164">Möglicherweise haben Sie Folgendes in FSI bemerkt:</span><span class="sxs-lookup"><span data-stu-id="690c7-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="690c7-165">Dies ist eine Funktion, die eine `string` als Eingabe annimmt (aufgerufen `word`) und eine andere `string`zurückgibt. `toPigLatin`</span><span class="sxs-lookup"><span data-stu-id="690c7-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="690c7-166">Dies bezeichnet man als den [der Typsignatur der Funktion](https://fsharpforfunandprofit.com/posts/function-signatures/), ein wesentlicher Bestandteil von F#, die Schlüssel zum Verständnis der F#-Code ist.</span><span class="sxs-lookup"><span data-stu-id="690c7-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="690c7-167">Sie bemerken dies auch, wenn Sie in Visual Studio Code auf die Funktion zeigen.</span><span class="sxs-lookup"><span data-stu-id="690c7-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="690c7-168">Im Hauptteil der Funktion werden zwei unterschiedliche Teile feststellen:</span><span class="sxs-lookup"><span data-stu-id="690c7-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="690c7-169">Eine innere Funktion namens `isVowel`, die bestimmt, ob ein bestimmtes Zeichen (`c`) ein Vokal ist, indem überprüft wird, ob Sie mit einem der angegebenen Muster über den [Muster](../language-reference/pattern-matching.md)Abgleich übereinstimmt:</span><span class="sxs-lookup"><span data-stu-id="690c7-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="690c7-170">Ein [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) Ausdruck, der überprüft, ob das erste Zeichen ein Vokal ist, und einen Rückgabewert aus den Eingabezeichen erstellt, basierend auf, wenn das erste Zeichen ein Vokal ist oder nicht:</span><span class="sxs-lookup"><span data-stu-id="690c7-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="690c7-171">Der Ablauf von `toPigLatin` ist daher:</span><span class="sxs-lookup"><span data-stu-id="690c7-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="690c7-172">Überprüfen Sie, ob das erste Zeichen des Eingabe Worts ein vowel ist.</span><span class="sxs-lookup"><span data-stu-id="690c7-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="690c7-173">Wenn dies der Fall ist, fügen Sie "yay" an das Ende des Worts an.</span><span class="sxs-lookup"><span data-stu-id="690c7-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="690c7-174">Verschieben Sie andernfalls das erste Zeichen an das Ende des Worts, und fügen Sie es hinzu.</span><span class="sxs-lookup"><span data-stu-id="690c7-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="690c7-175">Es gibt noch ein letztes, was zu beachten ist: Es gibt keine explizite Anweisung, von der Funktion zurückzugeben, anders als bei vielen anderen Sprachen.</span><span class="sxs-lookup"><span data-stu-id="690c7-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="690c7-176">Dies ist da F# ausdrucksbasiert ist, und der letzte Ausdruck in den Hauptteil einer Funktion der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="690c7-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="690c7-177">Da `if..then..else` selbst ein Ausdruck ist, wird der Text `then` des Blocks `else` oder der Textkörper des Blocks abhängig vom Eingabe Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="690c7-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="690c7-178">Verschieben des Skriptcodes in die Implementierungs Datei</span><span class="sxs-lookup"><span data-stu-id="690c7-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="690c7-179">In den vorherigen Abschnitten dieses Artikels wurden die ersten Schritte zum Schreiben F# von Code veranschaulicht: das Schreiben einer anfänglichen Funktion und die interaktive Ausführung mit FSI.</span><span class="sxs-lookup"><span data-stu-id="690c7-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="690c7-180">Dies wird als repl-gesteuerte Entwicklung bezeichnet, wobei [repl](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) für "Read-Evaluation-Print Loop" steht.</span><span class="sxs-lookup"><span data-stu-id="690c7-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="690c7-181">Es ist eine gute Möglichkeit, mit der Funktionalität zu experimentieren, bis Sie etwas funktionieren.</span><span class="sxs-lookup"><span data-stu-id="690c7-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="690c7-182">Der nächste Schritt bei der repl-gesteuerten Entwicklung besteht darin, den funktionierenden Code F# in eine Implementierungs Datei zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="690c7-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="690c7-183">Er kann dann vom F# Compiler in eine Assembly kompiliert werden, die ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="690c7-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="690c7-184">Öffnen `ClassLibraryDemo.fs`Sie zunächst.</span><span class="sxs-lookup"><span data-stu-id="690c7-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="690c7-185">Sie werden feststellen, dass der Code bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="690c7-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="690c7-186">Löschen Sie die Klassendefinition, und übernehmen Sie [`namespace`](../language-reference/namespaces.md) die Deklaration im oberen Bereich.</span><span class="sxs-lookup"><span data-stu-id="690c7-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="690c7-187">Erstellen Sie als nächstes eine [`module`](../language-reference/modules.md) neue `PigLatin` mit dem Namen `toPigLatin` , und kopieren Sie die Funktion in die folgende Funktion:</span><span class="sxs-lookup"><span data-stu-id="690c7-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="690c7-188">Öffnen Sie als nächstes `Script.fsx` die Datei erneut, und löschen Sie `toPigLatin` die gesamte Funktion. Stellen Sie jedoch sicher, dass die folgenden beiden Zeilen in der Datei beibehalten werden:</span><span class="sxs-lookup"><span data-stu-id="690c7-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="690c7-189">Wählen Sie beide Textzeilen aus, und drücken Sie Alt + Eingabe, um diese Zeilen in FSI auszuführen.</span><span class="sxs-lookup"><span data-stu-id="690c7-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="690c7-190">Diese werden den Inhalt der Pig Latin-Bibliothek in den FSI-Prozess und `open` den `ClassLibraryDemo` -Namespace laden, damit Sie auf die-Funktionalität zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="690c7-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="690c7-191">Anschließend wird im FSI-Fenster die Funktion mit dem `PigLatin` Modul aufgerufen, das Sie zuvor definiert haben:</span><span class="sxs-lookup"><span data-stu-id="690c7-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="690c7-192">Erfolgreich!</span><span class="sxs-lookup"><span data-stu-id="690c7-192">Success!</span></span> <span data-ttu-id="690c7-193">Sie erhalten dieselben Ergebnisse wie zuvor, werden aber nun aus einer F# Implementierungs Datei geladen.</span><span class="sxs-lookup"><span data-stu-id="690c7-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="690c7-194">Der Hauptunterschied besteht darin, F# dass Quelldateien in Assemblys kompiliert werden, die an einer beliebigen Stelle ausgeführt werden können, nicht nur in FSI.</span><span class="sxs-lookup"><span data-stu-id="690c7-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="690c7-195">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="690c7-195">Summary</span></span>

<span data-ttu-id="690c7-196">In diesem Artikel haben Sie Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="690c7-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="690c7-197">So richten Sie Visual Studio Code mit ionide ein</span><span class="sxs-lookup"><span data-stu-id="690c7-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="690c7-198">Erstellen Ihres ersten F# Projekts mit ionide</span><span class="sxs-lookup"><span data-stu-id="690c7-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="690c7-199">Verwenden F# der Skripterstellung zum Schreiben Ihrer ersten F# Funktion in ionide und deren Ausführung in FSI.</span><span class="sxs-lookup"><span data-stu-id="690c7-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="690c7-200">Migrieren Ihres Skriptcodes zu F# einer Quelle und anschließendes Abrufen des Codes von FSI.</span><span class="sxs-lookup"><span data-stu-id="690c7-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="690c7-201">Nun können Sie mit Visual Studio Code und ionide F# viel mehr Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="690c7-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="690c7-202">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="690c7-202">Troubleshooting</span></span>

<span data-ttu-id="690c7-203">Hier sind einige Möglichkeiten, wie Sie bestimmte Probleme beheben können, die möglicherweise auftreten können:</span><span class="sxs-lookup"><span data-stu-id="690c7-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="690c7-204">Um die Code Bearbeitungs Features von ionide zu erhalten, F# müssen die Dateien auf dem Datenträger und innerhalb eines Ordners, der im Arbeitsbereich Visual Studio Code geöffnet ist, gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="690c7-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="690c7-205">Wenn Sie Änderungen an Ihrem System vorgenommen oder die erforderlichen ionide-Komponenten mit Visual Studio Code Open installiert haben, starten Sie Visual Studio Code neu.</span><span class="sxs-lookup"><span data-stu-id="690c7-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="690c7-206">Überprüfen Sie, dass Sie die F#-Compiler und F# interactive über die Befehlszeile ohne einen vollständig qualifizierten Pfad verwenden können.</span><span class="sxs-lookup"><span data-stu-id="690c7-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="690c7-207">Sie können dazu eingeben `fsc` in einer Befehlszeile für den F#-Compiler und `fsi` oder `fsharpi` für die Visual F#-tools für Windows und Mono unter Mac/Linux, bzw.</span><span class="sxs-lookup"><span data-stu-id="690c7-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="690c7-208">Wenn Ihre Projekt Verzeichnisse ungültige Zeichen enthalten, funktioniert ionide möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="690c7-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="690c7-209">Benennen Sie die Projekt Verzeichnisse um, wenn dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="690c7-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="690c7-210">Wenn keiner der ionide-Befehle funktioniert, überprüfen Sie die [Visual Studio Code keybindungen](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) , um festzustellen, ob Sie Sie versehentlich überschreiben.</span><span class="sxs-lookup"><span data-stu-id="690c7-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="690c7-211">Wenn ionide auf dem Computer beschädigt ist und keines der oben genannten Probleme das Problem behoben hat, entfernen Sie `ionide-fsharp` das Verzeichnis auf Ihrem Computer, und installieren Sie die Plug-in-Suite erneut.</span><span class="sxs-lookup"><span data-stu-id="690c7-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="690c7-212">Ionide ist ein Open Source-Projekt, das F# von Mitgliedern der Community erstellt und verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="690c7-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="690c7-213">Melden Sie sich Probleme an, und nehmen Sie an [der "ionide-vscode" Teil: FSharp-GitHub](https://github.com/ionide/ionide-vscode-fsharp)-Repository.</span><span class="sxs-lookup"><span data-stu-id="690c7-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="690c7-214">Wenn Sie ein Problem melden müssen, befolgen Sie [die Anweisungen zum erhalten von Protokollen, die beim Melden eines Problems verwendet werden sollen](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="690c7-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="690c7-215">Sie können auch weitere Hilfe bitten, aus der Ionide-Entwickler und F#-Community in den [Ionide Gitter Kanal](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="690c7-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="690c7-216">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="690c7-216">Next steps</span></span>

<span data-ttu-id="690c7-217">Weitere Informationen zu F# und die Funktionen der Sprache, sehen Sie sich [Einführung in F#](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="690c7-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
