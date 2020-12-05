---
title: Erste Schritte mit F# in Visual Studio Code
description: 'Erfahren Sie, wie Sie F # mit Visual Studio Code und der ionide-Plug-in-Suite verwenden.'
ms.date: 12/23/2018
ms.openlocfilehash: 11fb0d443fb7c2b3f270d45bfeaa91102ba28efd
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739801"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="6b2ce-103">Erste Schritte mit F# in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6b2ce-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="6b2ce-104">Sie können F # in [Visual Studio Code](https://code.visualstudio.com) mit dem [ionide-Plug](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) -in schreiben, um eine hervorragend plattformübergreifende, einfache integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) mit IntelliSense und coderegierungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and code refactorings.</span></span> <span data-ttu-id="6b2ce-105">Besuchen Sie [Ionide.IO](https://ionide.io) , um mehr über das Plug-in zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-105">Visit [Ionide.io](https://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="6b2ce-106">Stellen Sie zunächst sicher, dass [F # und das ionide-Plug-in ordnungsgemäß installiert](install-fsharp.md#install-f-with-visual-studio-code)sind.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="create-your-first-project-with-ionide"></a><span data-ttu-id="6b2ce-107">Erstellen Ihres ersten Projekts mit ionide</span><span class="sxs-lookup"><span data-stu-id="6b2ce-107">Create your first project with Ionide</span></span>

<span data-ttu-id="6b2ce-108">Um ein neues F #-Projekt zu erstellen, öffnen Sie eine Befehlszeile, und erstellen Sie ein neues Projekt mit dem .net Core-CLI:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-108">To create a new F# project, open a command line and create a new project with the .NET Core CLI:</span></span>

```dotnetcli
dotnet new console -lang "F#" -o FirstIonideProject
```

<span data-ttu-id="6b2ce-109">Ändern Sie nach Abschluss des Vorgangs das Verzeichnis in das Projekt, und öffnen Sie Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-109">Once it completes, change directory to the project and open Visual Studio Code:</span></span>

```console
cd FirstIonideProject
code .
```

<span data-ttu-id="6b2ce-110">Nachdem das Projekt Visual Studio Code geladen wurde, sollte der Bereich F # Projektmappen-Explorer auf der linken Seite des Fensters geöffnet angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-110">After the project loads on Visual Studio Code, you should see the F# Solution Explorer pane on the left-hand side of your window open.</span></span> <span data-ttu-id="6b2ce-111">Dies bedeutet, dass ionide das soeben erstellte Projekt erfolgreich geladen hat.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-111">This means Ionide has successfully loaded the project you just created.</span></span> <span data-ttu-id="6b2ce-112">Vor diesem Zeitpunkt können Sie Code im Editor schreiben, aber sobald dies geschieht, ist das Laden vollständig abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-112">You can write code in the editor before this point in time, but once this happens, everything has finished loading.</span></span>

## <a name="configure-f-interactive"></a><span data-ttu-id="6b2ce-113">Konfigurieren von F # Interactive</span><span class="sxs-lookup"><span data-stu-id="6b2ce-113">Configure F# interactive</span></span>

<span data-ttu-id="6b2ce-114">Stellen Sie zunächst sicher, dass die .net Core-Skripterstellung Ihre standardmäßige Skript Umgebung ist:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-114">First, ensure that .NET Core scripting is your default scripting environment:</span></span>

1. <span data-ttu-id="6b2ce-115">Öffnen Sie die Visual Studio Code Einstellungen (Einstellungen für die **Code**  >  **Einstellungen**  >  **Settings**).</span><span class="sxs-lookup"><span data-stu-id="6b2ce-115">Open the Visual Studio Code settings (**Code** > **Preferences** > **Settings**).</span></span>
1. <span data-ttu-id="6b2ce-116">Suchen Sie nach dem Begriff **F #-Skript**.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-116">Search for the term **F# Script**.</span></span>
1. <span data-ttu-id="6b2ce-117">Klicken Sie auf das Kontrollkästchen **FSharp: SDK-Skripts verwenden**.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-117">Click the checkbox that says **FSharp: use SDK scripts**.</span></span>

<span data-ttu-id="6b2ce-118">Dies ist zurzeit aufgrund von Legacy Verhaltensweisen in .NET Framework basierten Skripts notwendig, die nicht mit der .net Core-Skripterstellung funktionieren, und der ionide-Wert ist zurzeit für diese Abwärtskompatibilität geeignet.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-118">This is currently necessary due to some legacy behaviors in .NET Framework-based scripting that don't work with .NET Core scripting, and Ionide is currently striving for that backwards compatibility.</span></span> <span data-ttu-id="6b2ce-119">In Zukunft wird die .net Core-Skripterstellung zum Standard.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-119">In the future, .NET Core scripting will become the default.</span></span>

### <a name="write-your-first-script"></a><span data-ttu-id="6b2ce-120">Schreiben Ihres ersten Skripts</span><span class="sxs-lookup"><span data-stu-id="6b2ce-120">Write your first script</span></span>

<span data-ttu-id="6b2ce-121">Nachdem Sie Visual Studio Code für die Verwendung der .net Core-Skripterstellung konfiguriert haben, navigieren Sie in Visual Studio Code zur Explorer-Ansicht, und erstellen Sie eine neue Datei.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-121">Once you've configured Visual Studio Code to use .NET Core scripting, navigate to the Explorer view in Visual Studio Code and create a new file.</span></span> <span data-ttu-id="6b2ce-122">Nennen Sie Sie *myfirstscript. FSX*.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-122">Name it *MyFirstScript.fsx*.</span></span>

<span data-ttu-id="6b2ce-123">Fügen Sie nun den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-123">Now add the following code to it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="6b2ce-124">Diese Funktion konvertiert ein Wort in eine Form von [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="6b2ce-124">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="6b2ce-125">Der nächste Schritt besteht darin, ihn mit F# Interactive (FSI) zu evaluieren.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-125">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="6b2ce-126">Markieren Sie die gesamte Funktion (es sollte 11 Zeilen lang sein).</span><span class="sxs-lookup"><span data-stu-id="6b2ce-126">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="6b2ce-127">Halten Sie die **alt** -Taste gedrückt, und drücken Sie die **Eingabe** Taste.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-127">Once it's highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="6b2ce-128">Unten auf dem Bildschirm wird ein Terminalfenster angezeigt, das in etwa wie folgt aussehen sollte:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-128">You'll notice a terminal window pop up on the bottom of the screen, and it should look similar to this:</span></span>

![Beispiel für F# Interactive Ausgabe mit ionide](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="6b2ce-130">Dies hat drei Dinge getan:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-130">This did three things:</span></span>

1. <span data-ttu-id="6b2ce-131">Der FSI-Prozess wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-131">It started the FSI process.</span></span>
2. <span data-ttu-id="6b2ce-132">Der Code, den Sie über den FSI-Prozess hervorgehoben haben, wurde gesendet.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-132">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="6b2ce-133">Der FSI-Prozess hat den Code ausgewertet, den Sie gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-133">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="6b2ce-134">Da das, was Sie gesendet haben, eine [Funktion](../language-reference/functions/index.md)war, können Sie diese Funktion jetzt mit FSI abrufen!</span><span class="sxs-lookup"><span data-stu-id="6b2ce-134">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="6b2ce-135">Geben Sie im interaktiven Fenster Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-135">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="6b2ce-136">Das folgende Ergebnis wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-136">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="6b2ce-137">Nun versuchen wir, einen Vokal als ersten Buchstaben zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-137">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="6b2ce-138">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-138">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="6b2ce-139">Das folgende Ergebnis wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-139">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="6b2ce-140">Die Funktion scheint erwartungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-140">The function appears to be working as expected.</span></span> <span data-ttu-id="6b2ce-141">Herzlichen Glückwunsch, Sie haben ihre erste F #-Funktion in Visual Studio Code geschrieben und mit FSI ausgewertet!</span><span class="sxs-lookup"><span data-stu-id="6b2ce-141">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="6b2ce-142">Wie Sie vielleicht bemerkt haben, werden die Zeilen in FSI mit beendet `;;` .</span><span class="sxs-lookup"><span data-stu-id="6b2ce-142">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="6b2ce-143">Dies liegt daran, dass Sie mithilfe von FSI mehrere Zeilen eingeben können.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-143">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="6b2ce-144">Der `;;` am Ende ermöglicht FSI, wenn der Code abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-144">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="6b2ce-145">Erläutern des Codes</span><span class="sxs-lookup"><span data-stu-id="6b2ce-145">Explaining the code</span></span>

<span data-ttu-id="6b2ce-146">Wenn Sie nicht sicher sind, was der Code tatsächlich macht, finden Sie hier eine Schritt-für-Schritt-Anleitung.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-146">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="6b2ce-147">Wie Sie sehen können, `toPigLatin` ist eine Funktion, die ein Wort als Eingabe annimmt und Sie in eine Pig-Latin Darstellung dieses Worts konvertiert.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-147">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="6b2ce-148">Dies sind die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-148">The rules for this are as follows:</span></span>

<span data-ttu-id="6b2ce-149">Wenn das erste Zeichen in einem Wort mit einem vowel beginnt, fügen Sie am Ende des Worts "yay" hinzu.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-149">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="6b2ce-150">Wenn er nicht mit einem vowel beginnt, verschieben Sie das erste Zeichen an das Ende des Worts, und fügen Sie ihm "ay" hinzu.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-150">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="6b2ce-151">Möglicherweise haben Sie Folgendes in FSI bemerkt:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-151">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="6b2ce-152">Dies `toPigLatin` ist eine Funktion, die eine `string` als Eingabe annimmt (aufgerufen `word` ) und eine andere zurückgibt `string` .</span><span class="sxs-lookup"><span data-stu-id="6b2ce-152">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="6b2ce-153">Dies wird als die [Typsignatur](https://fsharpforfunandprofit.com/posts/function-signatures/)der-Funktion bezeichnet. Dies ist ein grundlegendes Element von f #, das zum Verständnis von f #-Code wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-153">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="6b2ce-154">Sie bemerken dies auch, wenn Sie in Visual Studio Code auf die Funktion zeigen.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-154">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="6b2ce-155">Im Hauptteil der Funktion werden zwei unterschiedliche Teile feststellen:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-155">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="6b2ce-156">Eine innere Funktion namens `isVowel` , die bestimmt, ob ein bestimmtes Zeichen ( `c` ) ein Vokal ist, indem überprüft wird, ob Sie mit einem der angegebenen Muster über den [Muster](../language-reference/pattern-matching.md)Abgleich übereinstimmt:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-156">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="6b2ce-157">Ein [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) Ausdruck, der überprüft, ob das erste Zeichen ein Vokal ist, und einen Rückgabewert aus den Eingabezeichen erstellt, basierend auf, wenn das erste Zeichen ein Vokal ist oder nicht:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-157">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="6b2ce-158">Der Ablauf von `toPigLatin` ist daher:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-158">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="6b2ce-159">Überprüfen Sie, ob das erste Zeichen des Eingabe Worts ein vowel ist.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-159">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="6b2ce-160">Wenn dies der Fall ist, fügen Sie "yay" an das Ende des Worts an.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-160">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="6b2ce-161">Verschieben Sie andernfalls das erste Zeichen an das Ende des Worts, und fügen Sie es hinzu.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-161">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="6b2ce-162">Folgendes ist zu beachten: in F # gibt es keine explizite Anweisung, die von der Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-162">There's one final thing to notice about this: in F#, there's no explicit instruction to return from the function.</span></span> <span data-ttu-id="6b2ce-163">Dies liegt daran, dass F # Ausdrucks basiert ist und der letzte Ausdruck, der im Text einer Funktion ausgewertet wurde, den Rückgabewert dieser Funktion bestimmt.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-163">This is because F# is expression-based, and the last expression evaluated in the body of a function determines the return value of that function.</span></span> <span data-ttu-id="6b2ce-164">Da `if..then..else` selbst ein Ausdruck ist, wird der `then` `else` von der Funktion zurückgegebene Wert durch Auswerten des Textblocks oder des Textblocks bestimmt `toPigLatin` .</span><span class="sxs-lookup"><span data-stu-id="6b2ce-164">Because `if..then..else` is itself an expression, evaluation of the body of the `then` block or the body of the `else` block determines the value returned by the `toPigLatin` function.</span></span>

## <a name="turn-the-console-app-into-a-pig-latin-generator"></a><span data-ttu-id="6b2ce-165">Umwandeln der Konsolen-app in einen Pig Latin-Generator</span><span class="sxs-lookup"><span data-stu-id="6b2ce-165">Turn the console app into a Pig Latin generator</span></span>

<span data-ttu-id="6b2ce-166">In den vorherigen Abschnitten dieses Artikels wurden die ersten Schritte zum Schreiben von F #-Code veranschaulicht: das Schreiben einer anfänglichen Funktion und das interaktive ausführen mit FSI.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-166">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="6b2ce-167">Dies wird als repl-gesteuerte Entwicklung bezeichnet, wobei [repl](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) für "Read-Evaluation-Print Loop" steht.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-167">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="6b2ce-168">Es ist eine gute Möglichkeit, mit der Funktionalität zu experimentieren, bis Sie etwas funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-168">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="6b2ce-169">Der nächste Schritt bei der repl-gesteuerten Entwicklung besteht darin, den funktionierenden Code in eine F #-Implementierungs Datei zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-169">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="6b2ce-170">Sie kann dann vom F #-Compiler in eine Assembly kompiliert werden, die ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-170">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="6b2ce-171">Öffnen Sie zunächst die Datei " *Program. FS* ", die Sie zuvor mit dem .net Core-CLI erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-171">To begin, open the *Program.fs* file that you created earlier with the .NET Core CLI.</span></span> <span data-ttu-id="6b2ce-172">Sie werden feststellen, dass der Code bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-172">You'll notice that some code is already in there.</span></span>

<span data-ttu-id="6b2ce-173">Erstellen Sie als nächstes eine neue mit [`module`](../language-reference/modules.md) dem Namen, `PigLatin` und kopieren `toPigLatin` Sie die zuvor erstellte Funktion in diese:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-173">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function you created earlier into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L3-L14)]

<span data-ttu-id="6b2ce-174">Dieses Modul sollte oberhalb der `main` Funktion und unterhalb der `open System` Deklaration liegen.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-174">This module should be above the `main` function and below the `open System` declaration.</span></span> <span data-ttu-id="6b2ce-175">Die Reihenfolge der Deklarationen ist in F # wichtig, daher müssen Sie die Funktion definieren, bevor Sie Sie in einer Datei abrufen.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-175">Order of declarations matters in F#, so you'll need to define the function before you call it in a file.</span></span>

<span data-ttu-id="6b2ce-176">Nennen Sie nun in der- `main` Funktion die Pig Latin Generator-Funktion für die Argumente:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-176">Now, in the `main` function, call your Pig Latin generator function on the arguments:</span></span>

```fsharp
[<EntryPoint>]
let main argv =
    for name in argv do
        let newName = PigLatin.toPigLatin name
        printfn %"{name} in Pig Latin is: {newName}"

    0
```

<span data-ttu-id="6b2ce-177">Nun können Sie Ihre Konsolen-App über die Befehlszeile ausführen:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-177">Now you can run your console app from the command line:</span></span>

```dotnetcli
dotnet run apple banana
```

<span data-ttu-id="6b2ce-178">Und Sie sehen, dass Sie das gleiche Ergebnis wie Ihre Skriptdatei ausgeben, aber dieses Mal als laufendes Programm!</span><span class="sxs-lookup"><span data-stu-id="6b2ce-178">And you'll see that it outputs the same result as your script file, but this time as a running program!</span></span>

## <a name="troubleshooting-ionide"></a><span data-ttu-id="6b2ce-179">Problembehandlung bei ionide</span><span class="sxs-lookup"><span data-stu-id="6b2ce-179">Troubleshooting Ionide</span></span>

<span data-ttu-id="6b2ce-180">Hier sind einige Möglichkeiten, wie Sie bestimmte Probleme beheben können, die möglicherweise auftreten können:</span><span class="sxs-lookup"><span data-stu-id="6b2ce-180">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="6b2ce-181">Um die Code Bearbeitungs Features von ionide zu erhalten, müssen die F #-Dateien auf dem Datenträger und in einem Ordner gespeichert werden, der im Arbeitsbereich Visual Studio Code geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-181">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
1. <span data-ttu-id="6b2ce-182">Wenn Sie Änderungen an Ihrem System vorgenommen oder die erforderlichen ionide-Komponenten mit Visual Studio Code Open installiert haben, starten Sie Visual Studio Code neu.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-182">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
1. <span data-ttu-id="6b2ce-183">Wenn Ihre Projekt Verzeichnisse ungültige Zeichen enthalten, funktioniert ionide möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-183">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="6b2ce-184">Benennen Sie die Projekt Verzeichnisse um, wenn dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-184">Rename your project directories if this is the case.</span></span>
1. <span data-ttu-id="6b2ce-185">Wenn keiner der ionide-Befehle funktioniert, überprüfen Sie Ihre [Visual Studio Code Key-Bindungen](https://code.visualstudio.com/docs/getstarted/keybindings#_advanced-customization) , um festzustellen, ob Sie Sie versehentlich überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-185">If none of the Ionide commands are working, check your [Visual Studio Code Key Bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_advanced-customization) to see if you're overriding them by accident.</span></span>
1. <span data-ttu-id="6b2ce-186">Wenn ionide auf dem Computer beschädigt ist und keines der oben genannten Probleme das Problem behoben hat, entfernen Sie das `ionide-fsharp` Verzeichnis auf Ihrem Computer, und installieren Sie die Plug-in-Suite erneut.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-186">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>
1. <span data-ttu-id="6b2ce-187">Wenn ein Projekt nicht geladen werden konnte (in F # Projektmappen-Explorer wird dies angezeigt), klicken Sie mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Details** anzeigen, um weitere Diagnoseinformationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-187">If a project failed to load (the F# Solution Explorer will show this), right-click on that project and click **See details** to get more diagnostic info.</span></span>

<span data-ttu-id="6b2ce-188">Ionide ist ein Open Source-Projekt, das von Mitgliedern der F #-Community erstellt und verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-188">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="6b2ce-189">Melden Sie sich mit Problemen an, und melden Sie sich gerne am " [ionide-vscode-FSharp"-GitHub-Repository](https://github.com/ionide/ionide-vscode-fsharp)an.</span><span class="sxs-lookup"><span data-stu-id="6b2ce-189">Please report issues and feel free to contribute at the [ionide-vscode-fsharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="6b2ce-190">Weitere Hilfe erhalten Sie von den ionide-Entwicklern und von der F #-Community im [ionide Gitter Channel](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="6b2ce-190">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6b2ce-191">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6b2ce-191">Next steps</span></span>

<span data-ttu-id="6b2ce-192">Weitere Informationen zu f # und den Funktionen der Sprache finden Sie unter Einführung in [f #](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="6b2ce-192">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
