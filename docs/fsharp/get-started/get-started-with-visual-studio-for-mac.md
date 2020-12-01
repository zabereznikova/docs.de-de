---
title: 'Beginnen Sie mit F # in Visual Studio für Mac'
description: 'Erfahren Sie, wie Sie F # mit Visual Studio für Mac verwenden.'
ms.date: 07/03/2018
ms.openlocfilehash: d2ad24ad18bb31419b39508f2cf555c82fbe2e0b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437991"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="28580-103">Beginnen Sie mit F # in Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="28580-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="28580-104">F # und die Visual F# Tools werden in der Visual Studio für Mac IDE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="28580-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="28580-105">Stellen Sie sicher, dass [Visual Studio für Mac installiert](install-fsharp.md#install-f-with-visual-studio-for-mac)ist.</span><span class="sxs-lookup"><span data-stu-id="28580-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="28580-106">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="28580-106">Creating a console application</span></span>

<span data-ttu-id="28580-107">Eines der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="28580-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="28580-108">Dazu gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="28580-108">Here's how to do it.</span></span>  <span data-ttu-id="28580-109">Nachdem Visual Studio für Mac geöffnet ist:</span><span class="sxs-lookup"><span data-stu-id="28580-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="28580-110">Zeigen Sie im Menü Datei auf **neue** Projekt **Mappe** .</span><span class="sxs-lookup"><span data-stu-id="28580-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="28580-111">Im Dialogfeld Neues Projekt gibt es zwei verschiedene Vorlagen für die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="28580-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="28580-112">Es gibt einen unter anderen-> .net, der die .NET Framework als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="28580-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="28580-113">Die andere Vorlage befindet sich unter .net Core->-APP, die auf .net Core abzielt.</span><span class="sxs-lookup"><span data-stu-id="28580-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="28580-114">Beide Vorlagen sollten für den Zweck dieses Artikels funktionieren.</span><span class="sxs-lookup"><span data-stu-id="28580-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="28580-115">Ändern Sie bei Bedarf unter Konsolen-app c# in F #.</span><span class="sxs-lookup"><span data-stu-id="28580-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="28580-116">Wählen Sie die Schaltfläche **weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="28580-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="28580-117">Benennen Sie Ihr Projekt, und wählen Sie die gewünschten Optionen für die APP aus.</span><span class="sxs-lookup"><span data-stu-id="28580-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="28580-118">Beachten Sie, dass der Vorschaufenster auf der Seite des Bildschirms angezeigt wird, auf der die Verzeichnisstruktur angezeigt wird, die basierend auf den ausgewählten Optionen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="28580-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="28580-119">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="28580-119">Click **Create**.</span></span>  <span data-ttu-id="28580-120">Ein F #-Projekt sollte nun in der Projektmappen-Explorer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="28580-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="28580-121">Schreiben von Code</span><span class="sxs-lookup"><span data-stu-id="28580-121">Writing your code</span></span>

<span data-ttu-id="28580-122">Beginnen wir, indem wir zuerst Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="28580-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="28580-123">Stellen Sie sicher, dass die `Program.fs` Datei geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="28580-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="28580-124">Im vorherigen Codebeispiel wurde eine Funktion `square` definiert, die eine Eingabe mit dem Namen annimmt `x` und Sie selbst multipliziert.</span><span class="sxs-lookup"><span data-stu-id="28580-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="28580-125">Da F # den [Typrückschluss](../language-reference/type-inference.md)verwendet, muss der Typ von `x` nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="28580-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="28580-126">Der F #-Compiler kennt die Typen, bei denen die Multiplikation gültig ist, und weist basierend auf der Aufruf von einen Typ zu `x` `square` .</span><span class="sxs-lookup"><span data-stu-id="28580-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="28580-127">Wenn Sie den Mauszeiger darüber bewegen `square` , sollte Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="28580-127">If you hover over `square`, you should see the following:</span></span>

```console
val square: x:int -> int
```

<span data-ttu-id="28580-128">Dies wird als Typsignatur der Funktion bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="28580-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="28580-129">Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen x annimmt und eine ganze Zahl erzeugt."</span><span class="sxs-lookup"><span data-stu-id="28580-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="28580-130">Beachten Sie, dass der Compiler `square` den `int` Typ für den Moment erteilt hat. Dies liegt daran, dass die Multiplikation nicht für *alle* Typen generisch ist, sondern für einen geschlossenen Satz von Typen generisch ist.</span><span class="sxs-lookup"><span data-stu-id="28580-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="28580-131">Der F #-Compiler `int` hat zu diesem Zeitpunkt gewählt, aber er passt die Typsignatur an, wenn Sie `square` mit einem anderen Eingabetyp, z. b. einer, aufzurufen `float` .</span><span class="sxs-lookup"><span data-stu-id="28580-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="28580-132">Eine weitere Funktion, `main` , ist definiert und wird mit dem- `EntryPoint` Attribut versehen, um dem F #-Compiler mitzuteilen, dass die Programmausführung gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="28580-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="28580-133">Es folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code zurückgegeben wird (in der Regel `0` ).</span><span class="sxs-lookup"><span data-stu-id="28580-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="28580-134">In dieser Funktion wird die `square` Funktion mit einem Argument von aufgerufen `12` .</span><span class="sxs-lookup"><span data-stu-id="28580-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="28580-135">Der F #-Compiler weist dann den Typ von zu (d. h. `square` `int -> int` eine Funktion, die einen annimmt `int` und einen erzeugt `int` ).</span><span class="sxs-lookup"><span data-stu-id="28580-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="28580-136">Der-Befehl `printfn` ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet, ähnlich wie Programmiersprachen im C-Stil, Parameter, die den in der Format Zeichenfolge angegebenen entsprechen, und dann das Ergebnis und eine neue Zeile ausgibt.</span><span class="sxs-lookup"><span data-stu-id="28580-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="28580-137">Ausführen Ihres Codes</span><span class="sxs-lookup"><span data-stu-id="28580-137">Running your code</span></span>

<span data-ttu-id="28580-138">Sie können den Code ausführen und Ergebnisse anzeigen, indem Sie im Menü der obersten Ebene auf **Ausführen** klicken und dann **ohne Debugging starten**.</span><span class="sxs-lookup"><span data-stu-id="28580-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="28580-139">Dadurch wird das Programm ohne Debuggen ausgeführt, und die Ergebnisse können angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="28580-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="28580-140">Nun sollte Folgendes im Konsolenfenster gedruckt angezeigt werden, das Visual Studio für Mac Popup angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="28580-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="28580-141">Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="28580-141">Congratulations!</span></span>  <span data-ttu-id="28580-142">Sie haben ihr erstes f #-Projekt in Visual Studio für Mac erstellt, eine f #-Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion gedruckt hat, und das Projekt ausführen, um einige Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="28580-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="28580-143">Verwenden von F# Interactive</span><span class="sxs-lookup"><span data-stu-id="28580-143">Using F# Interactive</span></span>

<span data-ttu-id="28580-144">Eine der besten Funktionen der Visual F# Tools in Visual Studio für Mac ist das F# Interactive Fenster.</span><span class="sxs-lookup"><span data-stu-id="28580-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="28580-145">Es ermöglicht Ihnen das Senden von Code an einen Prozess, in dem Sie diesen Code aufzurufen und das Ergebnis interaktiv sehen können.</span><span class="sxs-lookup"><span data-stu-id="28580-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="28580-146">Um mit der Verwendung zu beginnen, markieren Sie die `square` im Code definierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="28580-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="28580-147">Klicken Sie anschließend im Menü der obersten Ebene auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="28580-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="28580-148">Wählen Sie dann **Auswahl an F# Interactive senden** aus.</span><span class="sxs-lookup"><span data-stu-id="28580-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="28580-149">Dadurch wird der Code im Fenster F# Interactive ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="28580-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="28580-150">Alternativ dazu können Sie auch mit der rechten Maustaste auf die Auswahl klicken und **Auswahl senden an F# Interactive** auswählen.</span><span class="sxs-lookup"><span data-stu-id="28580-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="28580-151">Es sollte angezeigt werden, dass das Fenster F# Interactive mit folgendem Code angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="28580-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```console
>

val square : x:int -> int

>
```

<span data-ttu-id="28580-152">Dies zeigt die gleiche Funktions Signatur für die `square` Funktion, die Sie zuvor gesehen haben, als Sie mit dem Mauszeiger auf die Funktion gezeigt haben.</span><span class="sxs-lookup"><span data-stu-id="28580-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="28580-153">Da `square` jetzt im F# Interactive Prozess definiert ist, können Sie ihn mit unterschiedlichen Werten aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="28580-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="28580-154">Dadurch wird die Funktion ausgeführt, das Ergebnis an einen neuen Namen gebunden `it` und der Typ und der Wert von angezeigt `it` .</span><span class="sxs-lookup"><span data-stu-id="28580-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="28580-155">Beachten Sie, dass Sie jede Zeile mit beenden müssen `;;` .</span><span class="sxs-lookup"><span data-stu-id="28580-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="28580-156">Auf diese Weise F# Interactive weiß, wann der Funktions Aufrufvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="28580-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="28580-157">Sie können auch neue Funktionen in F# Interactive definieren:</span><span class="sxs-lookup"><span data-stu-id="28580-157">You can also define new functions in F# Interactive:</span></span>

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="28580-158">Im obigen Beispiel wird eine neue Funktion definiert, `isOdd` die eine annimmt `int` und überprüft, ob Sie ungerade ist.</span><span class="sxs-lookup"><span data-stu-id="28580-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="28580-159">Diese Funktion kann aufgerufen werden, um zu sehen, was Sie mit unterschiedlichen Eingaben zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="28580-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="28580-160">Sie können Funktionen innerhalb von Funktionsaufrufen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="28580-160">You can call functions within function calls:</span></span>

```console
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="28580-161">Sie können auch den [Pipe-Forward-Operator](../language-reference/symbol-and-operator-reference/index.md) verwenden, um den Wert in die beiden Funktionen zu überführen:</span><span class="sxs-lookup"><span data-stu-id="28580-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="28580-162">Der Pipe-Forward-Operator und mehr werden in späteren Tutorials behandelt.</span><span class="sxs-lookup"><span data-stu-id="28580-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="28580-163">Dies ist nur ein Überblick darüber, was Sie mit F# Interactive tun können.</span><span class="sxs-lookup"><span data-stu-id="28580-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="28580-164">Weitere Informationen finden Sie unter [interaktive Programmierung mit F #](../tools/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="28580-164">To learn more, check out [Interactive Programming with F#](../tools/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="28580-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="28580-165">Next steps</span></span>

<span data-ttu-id="28580-166">Wenn Sie dies noch nicht getan haben, sehen Sie sich die Einführung [von f # an](../tour.md), in der einige der wichtigsten Features der Programmiersprache f # behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="28580-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="28580-167">Sie erhalten einen Überblick über einige der Funktionen von F # und bieten zahlreiche Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="28580-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="28580-168">Es gibt auch einige hervorragend externe Ressourcen, die Sie verwenden können, die im [Leitfaden zu F #](../index.yml)vorgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="28580-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.yml).</span></span>

## <a name="see-also"></a><span data-ttu-id="28580-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28580-169">See also</span></span>

- [<span data-ttu-id="28580-170">Leitfaden für F#</span><span class="sxs-lookup"><span data-stu-id="28580-170">F# guide</span></span>](../index.yml)
- [<span data-ttu-id="28580-171">Einführung in F#</span><span class="sxs-lookup"><span data-stu-id="28580-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="28580-172">F#-Programmiersprachenreferenz</span><span class="sxs-lookup"><span data-stu-id="28580-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="28580-173">Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="28580-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="28580-174">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="28580-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
