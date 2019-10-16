---
title: Erste Schritte mit F# in Visual Studio für Mac
description: Erfahren Sie, wie F# in Visual Studio für Mac verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: d3604178f93cf17d21f25b09084be7e7977378b5
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082974"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="aaf5b-103">Erste Schritte mit F# in Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="aaf5b-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="aaf5b-104">F# und die visuellen F#-Tools werden in der IDE für Visual Studio für Mac unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="aaf5b-105">Um zu beginnen, stellen Sie sicher, dass [Visual Studio für Mac installiert](install-fsharp.md#install-f-with-visual-studio-for-mac) ist.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="aaf5b-106">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="aaf5b-106">Creating a console application</span></span>

<span data-ttu-id="aaf5b-107">Eines der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="aaf5b-108">Und so gehen Sie dabei vor.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-108">Here's how to do it.</span></span>  <span data-ttu-id="aaf5b-109">Nachdem Visual Studio für Mac geöffnet ist:</span><span class="sxs-lookup"><span data-stu-id="aaf5b-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="aaf5b-110">Zeigen Sie im Menü Datei auf **neue**Projekt **Mappe** .</span><span class="sxs-lookup"><span data-stu-id="aaf5b-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="aaf5b-111">Im Dialogfeld Neues Projekt gibt es zwei verschiedene Vorlagen für die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="aaf5b-112">Es gibt einen unter anderen-> .net, der die .NET Framework als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="aaf5b-113">Die andere Vorlage befindet sich unter .net core->-app, die auf .net Core abzielt.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="aaf5b-114">Beide Vorlagen sollten für den Zweck dieses Artikels funktionieren.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="aaf5b-115">Bei der Konsolen-App ändern Sie bei Bedarf C# zu F#.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="aaf5b-116">Wählen Sie die Schaltfläche **Weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="aaf5b-117">Benennen Sie Ihr Projekt, und wählen Sie die gewünschten Optionen für die App aus.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="aaf5b-118">Beachten Sie, dass ein Vorschaufenster auf der Seite des Fensters angezeigt wird, auf der die Verzeichnisstruktur dargestellt wird, die basierend auf den ausgewählten Optionen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="aaf5b-119">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-119">Click **Create**.</span></span>  <span data-ttu-id="aaf5b-120">Ein F#-Projekt sollte nun im Projektmappen-Explorer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="aaf5b-121">Schreiben von Code</span><span class="sxs-lookup"><span data-stu-id="aaf5b-121">Writing your code</span></span>

<span data-ttu-id="aaf5b-122">Beginnen wir, indem wir zuerst Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="aaf5b-123">Stellen Sie sicher, dass die Datei `Program.fs` geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="aaf5b-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="aaf5b-124">Im vorherigen Codebeispiel wurde eine Funktion `square` definiert, die eine Eingabe mit dem Namen `x` annimmt und diese mit sich selbst multipliziert.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="aaf5b-125">Da F# [Typrückschluss](../language-reference/type-inference.md) verwendet, muss der Typ von `x` nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="aaf5b-126">Der F#-Compiler versteht die Typen, bei denen eine Multiplikation gültig ist, und weist `x` basierend auf dem `square`-Aufruf einen Typen zu.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="aaf5b-127">Wenn Sie mit den Mauszeiger auf `square` zeigen, sollte Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="aaf5b-127">If you hover over `square`, you should see the following:</span></span>

```console
val square: x:int -> int
```

<span data-ttu-id="aaf5b-128">Dies wird als Typsignatur der Funktion bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="aaf5b-129">Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen" x "annimmt und eine ganze Zahl erstellt.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="aaf5b-130">Beachten Sie, dass der `square` Compiler `int` den Typ für den Moment erteilt hat. Dies liegt daran, dass die Multiplikation nicht für *alle* Typen generisch ist, sondern für einen geschlossenen Satz von Typen generisch ist.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="aaf5b-131">Der F# Compiler hat `int` an dieser Stelle gewählt, aber er passt die Typsignatur an, wenn `square` Sie mit einem `float`anderen Eingabetyp, z. b., aufruft.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="aaf5b-132">Eine weitere Funktion `main` ist definiert und wurde mit dem `EntryPoint`-Attribut versehen, um dem F#-Compiler mitzuteilen, dass die Programmausführung hier gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="aaf5b-133">Der Ausdruck folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code (in der Regel `0`) zurück gegeben wird.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="aaf5b-134">In dieser Funktion wird die `square` Funktion mit einem Argument von `12`aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="aaf5b-135">Der F# Compiler weist dann den Typ von `square` zu `int -> int` , d. h. eine Funktion, die einen `int` annimmt und einen `int`erzeugt.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="aaf5b-136">Der-Befehl ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet, ähnlich wie Programmiersprachen im C-Stil, Parameter, die den in der Format Zeichenfolge angegebenen entsprechen, und dann das Ergebnis und eine neue Zeile ausgibt. `printfn`</span><span class="sxs-lookup"><span data-stu-id="aaf5b-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="aaf5b-137">Ausführen des Codes</span><span class="sxs-lookup"><span data-stu-id="aaf5b-137">Running your code</span></span>

<span data-ttu-id="aaf5b-138">Sie können den Code ausführen und sich die Ergebnisse anzeigen lassen, indem Sie im Menü der obersten Ebene auf **Ausführen** klicken und dann **Ohne Debugging starten**.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="aaf5b-139">Dadurch wird das Programm ohne Debuggen ausgeführt, und die Ergebnisse können angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="aaf5b-140">Nun sollte Folgendes im Konsolenfenster dargestellt werden, das im Visual Studio für Mac-Popup angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="aaf5b-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="aaf5b-141">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="aaf5b-141">Congratulations!</span></span>  <span data-ttu-id="aaf5b-142">Sie haben Ihr erstes F#-Projekt in Visual Studio erstellt, eine F#-Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion ausgegeben hat, und das Projekt ausgeführt, um einige Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="aaf5b-143">Verwenden von F# Interactive</span><span class="sxs-lookup"><span data-stu-id="aaf5b-143">Using F# Interactive</span></span>

<span data-ttu-id="aaf5b-144">Eines der besten Features von Visual F#-Tools in Visual Studio für Mac ist das F# Interactive-Fenster.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="aaf5b-145">Es ermöglicht Ihnen das Senden von Code an einen Prozess, der diesen Code ausführt, sodass Sie das Ergebnis interaktiv sehen können.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="aaf5b-146">Um mit der Verwendung zu beginnen, markieren Sie die im Code definierte Funktion `square`.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="aaf5b-147">Klicken Sie anschließend im Menü der obersten Ebene auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="aaf5b-148">Wählen Sie als Nächstes **Auswahl an F# Interactive senden**.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="aaf5b-149">Dadurch wird der Code im F# Interactive-Fenster ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="aaf5b-150">Alternativ können Sie mit der rechten Maustaste auf die Auswahl klicken und **Auswahl an F# Interactive senden** wählen.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="aaf5b-151">Es sollte das interaktive Fenster mit folgendem F#-Code angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="aaf5b-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```console
>

val square : x:int -> int

>
```

<span data-ttu-id="aaf5b-152">Dies zeigt die gleiche Funktionssignatur für die `square`-Funktion, die Sie zuvor gesehen haben, als Sie mit dem Mauszeiger auf die Funktion gezeigt haben.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="aaf5b-153">Da `square` nun im F# Interactive-Prozess definiert wird, können Sie sie mit anderen Werten aufrufen:</span><span class="sxs-lookup"><span data-stu-id="aaf5b-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="aaf5b-154">Dadurch wird die Funktion ausgeführt, das Ergebnis an einen neuen Namen `it`gebunden und der Typ und der Wert von `it`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="aaf5b-155">Beachten Sie, dass Sie jede Zeile mit `;;`beenden müssen.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="aaf5b-156">Dies ist wie F# Interactive weiß, wenn der Funktionsaufruf abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="aaf5b-157">Sie können auch neue Funktionen in F# Interactive definieren:</span><span class="sxs-lookup"><span data-stu-id="aaf5b-157">You can also define new functions in F# Interactive:</span></span>

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="aaf5b-158">Im obigen Beispiel wird eine neue Funktion `isOdd` definiert, die eine `int`-Funktion annimmt und überprüft, ob diese ungerade ist.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="aaf5b-159">Diese Funktion kann mit unterschiedlichen Eingaben aufgerufen werden, um zu sehen, was sie zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="aaf5b-160">Sie können Funktionen innerhalb von Funktionsaufrufen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="aaf5b-160">You can call functions within function calls:</span></span>

```console
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="aaf5b-161">Sie können auch den [Pipe-Forward-Operator](../language-reference/symbol-and-operator-reference/index.md) verwenden, um den Wert in die beiden Funktionen zu überführen:</span><span class="sxs-lookup"><span data-stu-id="aaf5b-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="aaf5b-162">Der Pipe-Forward-Operator und mehr werden in späteren Tutorials behandelt.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="aaf5b-163">Dies ist nur ein kurzer Einblick in die Verwendungsmöglichkeiten von F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="aaf5b-164">Weitere Informationen finden Sie unter [Interaktive Programmierung mit F#](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="aaf5b-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="aaf5b-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="aaf5b-165">Next steps</span></span>

<span data-ttu-id="aaf5b-166">Wenn Sie nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md), die behandelt einige der wichtigsten Funktionen der Sprache F#.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="aaf5b-167">Es wird bieten Ihnen einen Überblick über einige der Funktionen von F# und bieten reichlich Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="aaf5b-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="aaf5b-168">Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können, im gerätekatalog dargestellt die [Leitfaden für F#](../index.md).</span><span class="sxs-lookup"><span data-stu-id="aaf5b-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aaf5b-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaf5b-169">See also</span></span>

- [<span data-ttu-id="aaf5b-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="aaf5b-170">Visual F#</span></span>](../index.md)
- [<span data-ttu-id="aaf5b-171">Einführung in F#</span><span class="sxs-lookup"><span data-stu-id="aaf5b-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="aaf5b-172">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="aaf5b-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="aaf5b-173">Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="aaf5b-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="aaf5b-174">Symbol-und Operator Verweis</span><span class="sxs-lookup"><span data-stu-id="aaf5b-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
