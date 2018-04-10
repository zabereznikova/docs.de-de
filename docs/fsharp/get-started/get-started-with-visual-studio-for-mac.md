---
title: Erste Schritte mit f# in Visual Studio für Mac
description: Informationen Sie zum f# mit Visual Studio für Mac verwenden
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f56d67a7ecb9c68703638cbe05d8531891c132cd
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2018
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="cc1e6-103">Erste Schritte mit f# in Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="cc1e6-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="cc1e6-104">F# und Visual f#-Tools werden in der Visual Studio für Mac-IDE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span>  <span data-ttu-id="cc1e6-105">Um zu beginnen, sollten Sie [Visual Studio für Mac herunterladen](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), sofern Sie noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-105">To begin, you should [download Visual Studio for Mac](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), if you haven't already.</span></span>  <span data-ttu-id="cc1e6-106">In diesem Artikel verwendet die Visual Studio Community 2017 für Mac, jedoch können Sie f# mit der Version Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-106">This article uses the Visual Studio Community 2017 for Mac, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="cc1e6-107">Installieren [F#]</span><span class="sxs-lookup"><span data-stu-id="cc1e6-107">Installing F#</span></span> #

<span data-ttu-id="cc1e6-108">Nach dem Herunterladen von Visual Studio für Mac, werden sie aufgefordert, wählen, was Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-108">After downloading Visual Studio for Mac, it will prompt you to choose what you want to install.</span></span>  <span data-ttu-id="cc1e6-109">Im Rahmen dieses Artikels wird die Standardeinstellungen verlassen.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-109">For the purposes of this article we will be leaving the defaults.</span></span>  <span data-ttu-id="cc1e6-110">Im Gegensatz zu Visual Studio für Windows müssen Sie nicht ausdrücklich F#-Unterstützung installieren.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-110">In contrast to Visual Studio for Windows, you do not need to specifically install F# support.</span></span>  <span data-ttu-id="cc1e6-111">Drücken Sie auf "Installieren", um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-111">Press "Install" to proceed.</span></span>

<span data-ttu-id="cc1e6-112">Nachdem die Installation abgeschlossen ist, wählen Sie "Visual Studio starten" aus.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-112">After the install completes, choose "Start Visual Studio".</span></span>  <span data-ttu-id="cc1e6-113">Sie können es auch über Finder auf MacOS starten.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-113">You can also launch it through Finder on macOS.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="cc1e6-114">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="cc1e6-114">Creating a console application</span></span>

<span data-ttu-id="cc1e6-115">Eines der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-115">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="cc1e6-116">Und so gehen Sie dabei vor.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-116">Here's how to do it.</span></span>  <span data-ttu-id="cc1e6-117">Sobald Visual Studio für Mac geöffnet wird:</span><span class="sxs-lookup"><span data-stu-id="cc1e6-117">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="cc1e6-118">Auf der **Datei** Sie im Menü **neue Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-118">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="cc1e6-119">Klicken Sie im Dialogfeld "Neues Projekt" stehen für die Konsolenanwendung 2 unterschiedliche Vorlagen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-119">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="cc1e6-120">Ist ein anderen -> .NET, das auf .NET Framework abzielt.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-120">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="cc1e6-121">Die andere Vorlage ist unter .NET Core -> App verwendet, die .NET Core als Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-121">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="cc1e6-122">Entweder Vorlage sollte für die in diesem Artikel funktionieren.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-122">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="cc1e6-123">Unter Konsolen-app C#-, f# bei Bedarf ändern.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-123">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="cc1e6-124">Wählen Sie die **Weiter** Schaltfläche weitergehen!</span><span class="sxs-lookup"><span data-stu-id="cc1e6-124">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="cc1e6-125">Benennen Sie dem Projekt, und wählen Sie die Optionen für die app aus.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-125">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="cc1e6-126">Beachten Sie, dass das Vorschaufenster auf der Seite des Bildschirms, der die Verzeichnisstruktur anzeigt, die erstellt werden soll, basierend auf der ausgewählten Optionen.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-126">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="cc1e6-127">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-127">Click **Create**.</span></span>  <span data-ttu-id="cc1e6-128">Jetzt sollte eine f#-Projekt im Projektmappen-Explorer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-128">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="cc1e6-129">Das Schreiben des Codes</span><span class="sxs-lookup"><span data-stu-id="cc1e6-129">Writing your code</span></span>

<span data-ttu-id="cc1e6-130">Fangen wir zuerst, Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-130">Let's get started by writing some code first.</span></span>  <span data-ttu-id="cc1e6-131">Stellen Sie sicher, dass die `Program.fs` Datei geöffnet ist, und Ersetzen Sie den Inhalt durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc1e6-131">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="cc1e6-132">Im vorherigen Codebeispiel ist eine Funktion `square` hat definiert wurde, der mit dem Namen Eingabe akzeptiert `x` und multipliziert es eigenständig.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-132">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="cc1e6-133">Da die f# verwendet [Typrückschluss](../language-reference/type-inference.md), den Typ des `x` muss nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-133">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="cc1e6-134">F#-Compiler erkennt die Typen, in denen Multiplikation gültig ist, und weist einen Typ an `x` basierend auf wie `square` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-134">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="cc1e6-135">Wenn Sie zeigen `square`, sollte Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cc1e6-135">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="cc1e6-136">Dies ist das sogenannte Typsignatur für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-136">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="cc1e6-137">Sie können wie folgt gelesen werden: "Quadrat ist eine Funktion, die eine ganze Zahl, die mit dem Namen akzeptiert x und erzeugt eine ganze Zahl".</span><span class="sxs-lookup"><span data-stu-id="cc1e6-137">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="cc1e6-138">Beachten Sie, den der Compiler gegeben haben `square` der `int` Typ fürs - Dies ist da Multiplikation nicht generisch über ist *alle* Typen, aber stattdessen über einen vollständigen Satz von Typen ist generisch.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-138">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="cc1e6-139">Der f#-Compiler, die entnommen `int` an diesem Punkt, aber es wird anpassen die Typsignatur beim Aufrufen `square` durch ein anderes Eingabetyp, z. B. eine `float`.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-139">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="cc1e6-140">Eine andere Funktion `main`, definiert ist, ist die Angabe der `EntryPoint` Attribut anzuweisen, die f#-Compiler, Ausführung des Programms sollte dort starten.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-140">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="cc1e6-141">Es folgt die gleiche Konvention wie andere [Programmiersprachen C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), wobei Befehlszeilenargumente an diese Funktion übergeben werden können und ein ganzzahligen Code zurückgegeben wird (in der Regel `0`).</span><span class="sxs-lookup"><span data-stu-id="cc1e6-141">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="cc1e6-142">Es ist in dieser Funktion, die wir Aufrufen der `square` Funktion mit dem Argument `12`.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-142">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="cc1e6-143">F#-Compiler weist den Typ des `square` werden `int -> int` (d. h. eine Funktion, die akzeptiert ein `int` und erzeugt eine `int`).</span><span class="sxs-lookup"><span data-stu-id="cc1e6-143">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="cc1e6-144">Der Aufruf von `printfn` ist eine formatierte Druckfunktion befindlichen eine Formatzeichenfolge, ähnlich wie bei Programmiersprachen C-Format verwenden, Parameter, der den angegebenen, in der Formatzeichenfolge entspricht, und gibt dann das Ergebnis und eine neue Zeile.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-144">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="cc1e6-145">Ausführen des Codes</span><span class="sxs-lookup"><span data-stu-id="cc1e6-145">Running your code</span></span>

<span data-ttu-id="cc1e6-146">Sie können den Code ausführen und Ergebnisse anzeigen, indem Sie auf **ausführen** aus dem Menü der obersten Ebene und dann **Starten ohne Debugging**.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-146">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="cc1e6-147">Dies wird das Programm ohne Debuggen auszuführen und ermöglicht Ihnen, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-147">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="cc1e6-148">Jetzt sollte gedruckt an das Konsolenfenster, das Visual Studio für Mac per POP, um ausgelesen Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cc1e6-148">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="cc1e6-149">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="cc1e6-149">Congratulations!</span></span>  <span data-ttu-id="cc1e6-150">Erste f#-Projekts in Visual Studio für Mac erstellt haben, geschrieben, dass eine F#-Funktion die Ergebnisse der Aufrufe dieser Funktion gedruckt und führen Sie das Projekt, um einige Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-150">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="cc1e6-151">Verwenden von f# Interactive</span><span class="sxs-lookup"><span data-stu-id="cc1e6-151">Using F# Interactive</span></span>

<span data-ttu-id="cc1e6-152">Eine der besten Funktionen oder die Visual F#-Datenbanktools in Visual Studio für Mac ist das f# Interactive-Fenster.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-152">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="cc1e6-153">Sie können Sie Code über an einen Prozess zu senden, Sie diesen Code aufrufen können und das Ergebnis interaktiv angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-153">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="cc1e6-154">Um zu beginnen, verwenden es, markieren Sie die `square` Funktion, die in Ihrem Code definiert.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-154">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="cc1e6-155">Klicken Sie anschließend auf **bearbeiten** aus dem Menü der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-155">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="cc1e6-156">Wählen Sie als Nächstes **Auswahl an f# Interactive senden**.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-156">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="cc1e6-157">Dies führt den Code in der f# Interactive-Fenster.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-157">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="cc1e6-158">Alternativ können Sie mit der rechten Maustaste auf die Auswahl und wählen Sie **Auswahl an f# Interactive senden**.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-158">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="cc1e6-159">Daraufhin sollte das f# Interactive-Fenster mit den folgenden darin angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="cc1e6-159">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="cc1e6-160">Dies zeigt die gleiche Funktionssignatur für die `square` -Funktion, die Sie zuvor gesehen haben, wenn Sie über die Funktion gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-160">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="cc1e6-161">Da `square` ist nun in der f# Interactive-Prozess definiert, können Sie es mit unterschiedlichen Werten aufrufen:</span><span class="sxs-lookup"><span data-stu-id="cc1e6-161">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="cc1e6-162">Dies führt die Funktion, bindet das Ergebnis in einen neuen Namen `it`, und zeigt den Typ und Wert des `it`.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-162">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="cc1e6-163">Beachten Sie, dass Sie jede Zeile mit beenden müssen `;;`.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-163">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="cc1e6-164">Dies ist wie f# Interactive weiß, wenn der Funktionsaufruf abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-164">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="cc1e6-165">Sie können auch neue Funktionen in f# Interactive definieren:</span><span class="sxs-lookup"><span data-stu-id="cc1e6-165">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="cc1e6-166">Die oben genannten definiert eine neue Funktion `isOdd`, nimmt ein `int` und prüft, ob es ungerade ist!</span><span class="sxs-lookup"><span data-stu-id="cc1e6-166">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="cc1e6-167">Sie können diese Funktion, um festzustellen, was es mit unterschiedlichen Eingaben zurückgibt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-167">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="cc1e6-168">Sie können Funktionen in Funktionsaufrufen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="cc1e6-168">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="cc1e6-169">Sie können auch die [Pipe-Forward-Operator](../language-reference/symbol-and-operator-reference/index.md) pipeline den Wert in die zwei Funktionen für:</span><span class="sxs-lookup"><span data-stu-id="cc1e6-169">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="cc1e6-170">Der Pipe-Forward-Operator und vieles mehr, werden in späteren Lernprogrammen behandelt.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-170">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="cc1e6-171">Dies ist nur einen Einblick in die Verwendungsmöglichkeiten mit f# Interactive.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-171">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="cc1e6-172">Weitere Auschecken [Interaktive Programmierung mit F#-](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="cc1e6-172">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cc1e6-173">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cc1e6-173">Next steps</span></span>

<span data-ttu-id="cc1e6-174">Wenn Sie nicht bereits getan haben, sehen Sie sich die [Tour von F#-](../tour.md), die behandelt einige der wichtigsten Funktionen der Programmiersprache f#.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-174">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="cc1e6-175">Er bieten Ihnen einen Überblick über die Funktionen von f#, und gibt ausreichend Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="cc1e6-175">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="cc1e6-176">Es gibt auch einige sehr hilfreiche externe Ressourcen, die Sie verwenden können, präsentiert, in der [F#-Handbuch](../index.md).</span><span class="sxs-lookup"><span data-stu-id="cc1e6-176">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cc1e6-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc1e6-177">See also</span></span>
 [<span data-ttu-id="cc1e6-178">Visual F#</span><span class="sxs-lookup"><span data-stu-id="cc1e6-178">Visual F#</span></span>](../index.md)  
 [<span data-ttu-id="cc1e6-179">Einführung in F#</span><span class="sxs-lookup"><span data-stu-id="cc1e6-179">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="cc1e6-180">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="cc1e6-180">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="cc1e6-181">Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="cc1e6-181">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="cc1e6-182">Symbol und dem Operator-Referenz</span><span class="sxs-lookup"><span data-stu-id="cc1e6-182">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
