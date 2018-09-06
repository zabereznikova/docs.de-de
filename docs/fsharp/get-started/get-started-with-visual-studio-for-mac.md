---
title: Erste Schritte mit f# in Visual Studio für Mac
description: Erfahren Sie, wie f# in Visual Studio für Mac verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: 6aceec299c29e04aecd7999cd1dda6a56dd2779a
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042323"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="7f145-103">Erste Schritte mit f# in Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="7f145-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="7f145-104">F# und Visual F#-Tools werden in der Visual Studio für Mac-IDE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f145-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="7f145-105">Stellen Sie sicher, dass man [Visual Studio für Mac installiert](install-fsharp.md#install-f-with-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="7f145-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="7f145-106">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="7f145-106">Creating a console application</span></span>

<span data-ttu-id="7f145-107">Eine der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="7f145-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="7f145-108">Und so gehen Sie dabei vor.</span><span class="sxs-lookup"><span data-stu-id="7f145-108">Here's how to do it.</span></span>  <span data-ttu-id="7f145-109">Sobald Visual Studio für Mac geöffnet ist:</span><span class="sxs-lookup"><span data-stu-id="7f145-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="7f145-110">Auf der **Datei** Startmenü **neue Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="7f145-110">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="7f145-111">Klicken Sie im Dialogfeld "Neues Projekt" gibt es unterschiedliche 2-Vorlagen für die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="7f145-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="7f145-112">Es gibt einen anderen -> .NET und .NET Framework ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="7f145-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="7f145-113">Die andere Vorlage befindet sich unter .NET Core >, das auf .NET Core-App.</span><span class="sxs-lookup"><span data-stu-id="7f145-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="7f145-114">Entweder Vorlage sollte im Rahmen dieses Artikels funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7f145-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="7f145-115">Unter Konsolen-app c#, f# bei Bedarf ändern.</span><span class="sxs-lookup"><span data-stu-id="7f145-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="7f145-116">Wählen Sie die **Weiter** Schaltfläche, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="7f145-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="7f145-117">Geben Sie Ihrem Projekt einen Namen ein, und wählen Sie die Optionen, die Sie für die app verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7f145-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="7f145-118">Beachten Sie, dass im Vorschaufenster auf der Seite des Bildschirms, der die Verzeichnisstruktur angezeigt wird, die erstellt werden, basierend auf den ausgewählten Optionen.</span><span class="sxs-lookup"><span data-stu-id="7f145-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="7f145-119">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7f145-119">Click **Create**.</span></span>  <span data-ttu-id="7f145-120">Eine f#-Projekt im Projektmappen-Explorer sollte nun angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7f145-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="7f145-121">Das Schreiben von code</span><span class="sxs-lookup"><span data-stu-id="7f145-121">Writing your code</span></span>

<span data-ttu-id="7f145-122">Erste Schritte zunächst, Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="7f145-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="7f145-123">Stellen Sie sicher, dass die `Program.fs` Datei geöffnet ist, und Ersetzen Sie deren Inhalt durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7f145-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="7f145-124">Im vorherigen Beispiel, eine Funktion `square` wurde der Eingabe mit dem Namen akzeptiert definiert `x` und von sich selbst multipliziert.</span><span class="sxs-lookup"><span data-stu-id="7f145-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="7f145-125">Da f# verwendet [Typrückschluss](../language-reference/type-inference.md), den Typ des `x` muss nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f145-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="7f145-126">F#-Compiler erkennt die Typen, in denen Multiplikation gültig ist, und weist einen Typ `x` basieren, wie `square` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7f145-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="7f145-127">Wenn Sie darauf zeigen `square`, sollte Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7f145-127">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="7f145-128">Dies ist als die Signatur der Funktion Typ bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="7f145-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="7f145-129">Sie können wie folgt gelesen werden: "Quadrat ist eine Funktion, die eine ganze Zahl, die mit dem Namen akzeptiert x und erzeugt eine ganze Zahl".</span><span class="sxs-lookup"><span data-stu-id="7f145-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="7f145-130">Beachten Sie, die der Compiler hat `square` der `int` Typ vorerst - Dies liegt daran Multiplikation nicht für generische *alle* Typen, aber stattdessen über einen vollständigen Satz von Typen ist generisch.</span><span class="sxs-lookup"><span data-stu-id="7f145-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="7f145-131">Der F#-Compiler übernommen `int` an diesem Punkt, aber es passt die Datentyp-Signatur Aufrufen `square` mit einem anderen Eingabetyp, z. B. eine `float`.</span><span class="sxs-lookup"><span data-stu-id="7f145-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="7f145-132">Eine andere Funktion, `main`, definiert ist, wird die ergänzt, mit der `EntryPoint` Attribut, um dem F#-Compiler diese Ausführung des Programms sollte dort beginnen.</span><span class="sxs-lookup"><span data-stu-id="7f145-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="7f145-133">Dabei wird die gleiche Konvention wie andere [Programmiersprachen C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in dem Befehlszeilenargumente an diese Funktion übergeben werden können und ein ganzzahligen Code wird zurückgegeben (in der Regel `0`).</span><span class="sxs-lookup"><span data-stu-id="7f145-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="7f145-134">Es ist in dieser Funktion, die wir Aufrufen der `square` Funktion mit dem Argument `12`.</span><span class="sxs-lookup"><span data-stu-id="7f145-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="7f145-135">F#-Compiler weist dann den Typ des `square` sein `int -> int` (, also eine Funktion, die nimmt eine `int` und erzeugt eine `int`).</span><span class="sxs-lookup"><span data-stu-id="7f145-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="7f145-136">Der Aufruf von `printfn` ist eine formatierte drucken Funktion, die eine Formatzeichenfolge, die Programmiersprachen C-Stil, Parameter ähnelt, verwendet die in der Formatzeichenfolge angegeben entsprechen, und gibt dann das Ergebnis und eine neue Zeile.</span><span class="sxs-lookup"><span data-stu-id="7f145-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="7f145-137">Ausführen des Codes</span><span class="sxs-lookup"><span data-stu-id="7f145-137">Running your code</span></span>

<span data-ttu-id="7f145-138">Sie können den Code auszuführen und Ergebnisse anzeigen, indem Sie auf **ausführen** Menü der obersten Ebene und dann **Starten ohne Debugging**.</span><span class="sxs-lookup"><span data-stu-id="7f145-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="7f145-139">Dies führt die Anwendung ohne Debuggen und ermöglicht es Ihnen, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f145-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="7f145-140">Sie sollten jetzt sehen, dass die folgenden im Konsolenfenster anzuzeigen, die Visual Studio für Mac eingeblendet wird, wird ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="7f145-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="7f145-141">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="7f145-141">Congratulations!</span></span>  <span data-ttu-id="7f145-142">Sie haben Ihr erste F#-Projekt in Visual Studio für Mac erstellten, geschrieben, dass eine F#-Funktion die Ergebnisse des Aufrufs dieser Funktion ausgegeben und führen Sie das Projekt aus, um einige Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f145-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="7f145-143">Verwenden von f# Interactive</span><span class="sxs-lookup"><span data-stu-id="7f145-143">Using F# Interactive</span></span>

<span data-ttu-id="7f145-144">Eine der besten Features von der Visual F#-Tools in Visual Studio für Mac ist die f# Interactive-Fenster.</span><span class="sxs-lookup"><span data-stu-id="7f145-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="7f145-145">Sie können Code über an einen Prozess zu senden, können Sie rufen diesen Code und zeigen Sie das Ergebnis interaktiv.</span><span class="sxs-lookup"><span data-stu-id="7f145-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="7f145-146">Um mit der Nutzung beginnen, markieren Sie die `square` Funktion, die in Ihrem Code definiert.</span><span class="sxs-lookup"><span data-stu-id="7f145-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="7f145-147">Klicken Sie anschließend auf **bearbeiten** Menü der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="7f145-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="7f145-148">Wählen Sie als Nächstes **Auswahl an f# Interactive senden**.</span><span class="sxs-lookup"><span data-stu-id="7f145-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="7f145-149">Dadurch wird den Code in die f# Interactive-Fenster ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f145-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="7f145-150">Alternativ können Sie klicken Sie mit der rechten Maustaste auf die Auswahl und wählen Sie **Auswahl an f# Interactive senden**.</span><span class="sxs-lookup"><span data-stu-id="7f145-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="7f145-151">F# Interactive-Fenster mit den folgenden darin angezeigt werden sollte:</span><span class="sxs-lookup"><span data-stu-id="7f145-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="7f145-152">Dies zeigt die gleiche Funktionssignatur für die `square` -Funktion, die Sie zuvor gesehen haben, wenn Sie über die Funktion gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f145-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="7f145-153">Da `square` ist nun im f# Interactive-Prozess definiert wird, können Sie ihn mit anderen Werten aufrufen:</span><span class="sxs-lookup"><span data-stu-id="7f145-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="7f145-154">Dies führt die Funktion, bindet das Ergebnis an einen neuen Namen `it`, und zeigt den Typ und Wert des `it`.</span><span class="sxs-lookup"><span data-stu-id="7f145-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="7f145-155">Beachten Sie, dass Sie jede Zeile mit dem Beenden müssen `;;`.</span><span class="sxs-lookup"><span data-stu-id="7f145-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="7f145-156">Dies ist wie f# Interactive weiß, wenn der Funktionsaufruf abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7f145-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="7f145-157">Sie können auch neue Funktionen in f# Interactive definieren:</span><span class="sxs-lookup"><span data-stu-id="7f145-157">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="7f145-158">Die oben genannten definiert eine neue Funktion, `isOdd`, nimmt ein `int` und prüft, ob es ungerade ist!</span><span class="sxs-lookup"><span data-stu-id="7f145-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="7f145-159">Sie können Aufrufen dieser Funktion können Sie sehen, was es mit unterschiedlichen Eingaben zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7f145-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="7f145-160">Sie können Funktionen innerhalb von Funktionsaufrufen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="7f145-160">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="7f145-161">Sie können auch die [Pipe-Forward-Operator](../language-reference/symbol-and-operator-reference/index.md) auf den Wert an die beiden Funktionen zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="7f145-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="7f145-162">Der Pipe-Forward-Operator und vieles mehr, werden in späteren Tutorials behandelt.</span><span class="sxs-lookup"><span data-stu-id="7f145-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="7f145-163">Dies ist nur ein kurzer Einblick in die Verwendungsmöglichkeiten mit f# Interactive.</span><span class="sxs-lookup"><span data-stu-id="7f145-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="7f145-164">Weitere Informationen finden Sie [Interaktive Programmierung mit f#](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="7f145-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7f145-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7f145-165">Next steps</span></span>

<span data-ttu-id="7f145-166">Wenn Sie nicht bereits getan haben, sehen Sie sich die [Einführung in f#](../tour.md), die behandelt einige der wichtigsten Funktionen der Sprache f#.</span><span class="sxs-lookup"><span data-stu-id="7f145-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="7f145-167">Es wird bieten Ihnen einen Überblick über einige der Funktionen von f# und bieten reichlich Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="7f145-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="7f145-168">Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können, im gerätekatalog dargestellt die [Leitfaden für f#](../index.md).</span><span class="sxs-lookup"><span data-stu-id="7f145-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7f145-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f145-169">See also</span></span>

- [<span data-ttu-id="7f145-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="7f145-170">Visual F#</span></span>](../index.md)  
- [<span data-ttu-id="7f145-171">Einführung in F#</span><span class="sxs-lookup"><span data-stu-id="7f145-171">Tour of F#</span></span>](../tour.md)  
- [<span data-ttu-id="7f145-172">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="7f145-172">F# language reference</span></span>](../language-reference/index.md)  
- [<span data-ttu-id="7f145-173">Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="7f145-173">Type inference</span></span>](../language-reference/type-inference.md)  
- [<span data-ttu-id="7f145-174">Symbol und dem Operator-Referenz</span><span class="sxs-lookup"><span data-stu-id="7f145-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
