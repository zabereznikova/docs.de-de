---
title: Erste Schritte mit f# in Visual Studio
description: Informationen Sie zum Verwenden von f# in Visual Studio.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: 818bf50507a88e1d765da8d0505ed8da4790b71f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="be367-104">Erste Schritte mit f# in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="be367-104">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="be367-105">F# und Visual f#-Tools werden in der Visual Studio-IDE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be367-105">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>  <span data-ttu-id="be367-106">Um zu beginnen, sollten Sie [Herunterladen von Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), sofern Sie noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="be367-106">To begin, you should [download Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), if you haven't already.</span></span>  <span data-ttu-id="be367-107">In diesem Artikel verwendet 2017 Community-Edition von Visual Studio, aber Sie können f# mit der Version Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="be367-107">This article uses the Visual Studio 2017 Community Edition, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="be367-108">Installieren [F#]</span><span class="sxs-lookup"><span data-stu-id="be367-108">Installing F#</span></span> #

<span data-ttu-id="be367-109">Wenn beim Herunterladen von Visual Studio zum ersten Mal werden zunächst im Visual Studio-Installer installiert.</span><span class="sxs-lookup"><span data-stu-id="be367-109">If you're downloading Visual Studio for the first time, it will first install the Visual Studio installer.</span></span>  <span data-ttu-id="be367-110">Installieren Sie eine beliebige Version von Visual Studio 2017 vom Installationsprogramm ein.</span><span class="sxs-lookup"><span data-stu-id="be367-110">Install any version of Visual Studio 2017 from the installer.</span></span> <span data-ttu-id="be367-111">Wenn Sie bereits installiert haben, klicken Sie auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="be367-111">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="be367-112">Als Nächstes sehen Sie eine Liste von Arbeitslasten.</span><span class="sxs-lookup"><span data-stu-id="be367-112">You'll next see a list of Workloads.</span></span> <span data-ttu-id="be367-113">Sie können f# mithilfe einer der folgenden arbeitsauslastungen installieren:</span><span class="sxs-lookup"><span data-stu-id="be367-113">You can install F# through any of the following workloads:</span></span>

|<span data-ttu-id="be367-114">Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="be367-114">Workload</span></span>|<span data-ttu-id="be367-115">Aktion</span><span class="sxs-lookup"><span data-stu-id="be367-115">Action</span></span>|
|--------|------|
| <span data-ttu-id="be367-116">Plattformübergreifende .NET Core-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="be367-116">.NET Core cross-platform development</span></span> | <span data-ttu-id="be367-117">Keine Aktion - f# wird standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="be367-117">No action - F# is installed by default</span></span> |
| <span data-ttu-id="be367-118">ASP.NET und Webentwicklung</span><span class="sxs-lookup"><span data-stu-id="be367-118">ASP.NET and web development</span></span> | <span data-ttu-id="be367-119">Keine Aktion - f# wird standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="be367-119">No action - F# is installed by default</span></span> |
| <span data-ttu-id="be367-120">Azure-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="be367-120">Azure development</span></span> | <span data-ttu-id="be367-121">Keine Aktion - f# wird standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="be367-121">No action - F# is installed by default</span></span> |
| <span data-ttu-id="be367-122">Mobile Entwicklung mit .NET</span><span class="sxs-lookup"><span data-stu-id="be367-122">Mobile development with .NET</span></span> | <span data-ttu-id="be367-123">Keine Aktion - f# wird standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="be367-123">No action - F# is installed by default</span></span> |
| <span data-ttu-id="be367-124">Data Science und analytische Anwendungen</span><span class="sxs-lookup"><span data-stu-id="be367-124">Data science and analytical applications</span></span> | <span data-ttu-id="be367-125">Keine Aktion - f# wird standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="be367-125">No action - F# is installed by default</span></span> |
| <span data-ttu-id="be367-126">.NET-Desktopentwicklung</span><span class="sxs-lookup"><span data-stu-id="be367-126">.NET desktop development</span></span> | <span data-ttu-id="be367-127">Wählen Sie **desktop f#-sprachunterstützung** aus der rechten Seite</span><span class="sxs-lookup"><span data-stu-id="be367-127">Select **F# desktop language support** from the right-hand side</span></span> |
| <span data-ttu-id="be367-128">Datenspeicherung und -verarbeitung</span><span class="sxs-lookup"><span data-stu-id="be367-128">Data storage and processing</span></span> | <span data-ttu-id="be367-129">Wählen Sie **desktop f#-sprachunterstützung** aus der rechten Seite</span><span class="sxs-lookup"><span data-stu-id="be367-129">Select **F# desktop language support** from the right-hand side</span></span> |

<span data-ttu-id="be367-130">Klicken Sie anschließend auf **ändern** in der unteren rechten Ecke.</span><span class="sxs-lookup"><span data-stu-id="be367-130">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="be367-131">Dies installiert alles, was, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="be367-131">This will install everything you have selected.</span></span>  <span data-ttu-id="be367-132">Anschließend können Sie Visual Studio 2017 mit f#-sprachunterstützung öffnen, indem Sie auf **starten**.</span><span class="sxs-lookup"><span data-stu-id="be367-132">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="be367-133">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="be367-133">Creating a console application</span></span>

<span data-ttu-id="be367-134">Eines der grundlegendsten Projekte in Visual Studio ist die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="be367-134">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="be367-135">Und so gehen Sie dabei vor.</span><span class="sxs-lookup"><span data-stu-id="be367-135">Here's how to do it.</span></span>  <span data-ttu-id="be367-136">Nachdem Sie Visual Studio geöffnet ist:</span><span class="sxs-lookup"><span data-stu-id="be367-136">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="be367-137">Auf der **Datei** Sie im Menü **neu**, und wählen Sie dann **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="be367-137">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="be367-138">In das neue Projekt im Dialogfeld unter **Vorlagen**, sehen Sie **Visual f#**.</span><span class="sxs-lookup"><span data-stu-id="be367-138">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="be367-139">Wählen Sie diese Option, um die F#-Vorlagen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="be367-139">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="be367-140">Wählen Sie entweder **.NET Core-Konsolen-app** oder **Konsolen-app**.</span><span class="sxs-lookup"><span data-stu-id="be367-140">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="be367-141">Wählen Sie die **Okay** Schaltfläche, um die f#-Projekt zu erstellen!</span><span class="sxs-lookup"><span data-stu-id="be367-141">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="be367-142">Jetzt sollte eine f#-Projekt im Projektmappen-Explorer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="be367-142">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="be367-143">Das Schreiben des Codes</span><span class="sxs-lookup"><span data-stu-id="be367-143">Writing your code</span></span>

<span data-ttu-id="be367-144">Fangen wir zuerst, Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="be367-144">Let's get started by writing some code first.</span></span>  <span data-ttu-id="be367-145">Stellen Sie sicher, dass die `Program.fs` Datei geöffnet ist, und Ersetzen Sie den Inhalt durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="be367-145">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="be367-146">Im vorherigen Codebeispiel ist eine Funktion `square` hat definiert wurde, der mit dem Namen Eingabe akzeptiert `x` und multipliziert es eigenständig.</span><span class="sxs-lookup"><span data-stu-id="be367-146">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="be367-147">Da die f# verwendet [Typrückschluss](../language-reference/type-inference.md), den Typ des `x` muss nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be367-147">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="be367-148">F#-Compiler erkennt die Typen, in denen Multiplikation gültig ist, und weist einen Typ an `x` basierend auf wie `square` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="be367-148">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="be367-149">Wenn Sie zeigen `square`, sollte Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="be367-149">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="be367-150">Dies ist das sogenannte Typsignatur für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="be367-150">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="be367-151">Sie können wie folgt gelesen werden: "Quadrat ist eine Funktion, die eine ganze Zahl, die mit dem Namen akzeptiert x und erzeugt eine ganze Zahl".</span><span class="sxs-lookup"><span data-stu-id="be367-151">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="be367-152">Beachten Sie, den der Compiler gegeben haben `square` der `int` Typ fürs - Dies ist da Multiplikation nicht generisch über ist *alle* Typen, aber stattdessen über einen vollständigen Satz von Typen ist generisch.</span><span class="sxs-lookup"><span data-stu-id="be367-152">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="be367-153">Der f#-Compiler, die entnommen `int` an diesem Punkt, aber es wird anpassen die Typsignatur beim Aufrufen `square` durch ein anderes Eingabetyp, z. B. eine `float`.</span><span class="sxs-lookup"><span data-stu-id="be367-153">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="be367-154">Eine andere Funktion `main`, definiert ist, ist die Angabe der `EntryPoint` Attribut anzuweisen, die f#-Compiler, Ausführung des Programms sollte dort starten.</span><span class="sxs-lookup"><span data-stu-id="be367-154">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="be367-155">Es folgt die gleiche Konvention wie andere [Programmiersprachen C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), wobei Befehlszeilenargumente an diese Funktion übergeben werden können und ein ganzzahligen Code zurückgegeben wird (in der Regel `0`).</span><span class="sxs-lookup"><span data-stu-id="be367-155">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="be367-156">Es ist in dieser Funktion, die wir Aufrufen der `square` Funktion mit dem Argument `12`.</span><span class="sxs-lookup"><span data-stu-id="be367-156">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="be367-157">F#-Compiler weist den Typ des `square` werden `int -> int` (d. h. eine Funktion, die akzeptiert ein `int` und erzeugt eine `int`).</span><span class="sxs-lookup"><span data-stu-id="be367-157">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="be367-158">Der Aufruf von `printfn` ist eine formatierte Druckfunktion befindlichen eine Formatzeichenfolge, ähnlich wie bei Programmiersprachen C-Format verwenden, Parameter, der den angegebenen, in der Formatzeichenfolge entspricht, und gibt dann das Ergebnis und eine neue Zeile.</span><span class="sxs-lookup"><span data-stu-id="be367-158">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="be367-159">Ausführen des Codes</span><span class="sxs-lookup"><span data-stu-id="be367-159">Running your code</span></span>

<span data-ttu-id="be367-160">Sie können der Code ausgeführt und Ergebnisse durch Drücken von **Strg + f5**.</span><span class="sxs-lookup"><span data-stu-id="be367-160">You can run the code and see results by pressing **ctrl-f5**.</span></span>  <span data-ttu-id="be367-161">Dies wird das Programm ohne Debuggen auszuführen und ermöglicht Ihnen, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="be367-161">This will run the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="be367-162">Alternativ können Sie auch die **Debuggen** Menü der obersten Ebene in Visual Studio und wählen Sie **Starten ohne Debugging**.</span><span class="sxs-lookup"><span data-stu-id="be367-162">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="be367-163">Jetzt sollte gedruckt an das Konsolenfenster, das Visual Studio per POP, um ausgelesen Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="be367-163">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="be367-164">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="be367-164">Congratulations!</span></span>  <span data-ttu-id="be367-165">Erste f#-Projekts in Visual Studio erstellten haben, geschrieben, dass eine F#-Funktion die Ergebnisse der Aufrufe dieser Funktion gedruckt und führen Sie das Projekt, um einige Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="be367-165">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="be367-166">Verwenden von f# Interactive</span><span class="sxs-lookup"><span data-stu-id="be367-166">Using F# Interactive</span></span>

<span data-ttu-id="be367-167">Eine der besten Funktionen oder die Visual F#-Datenbanktools in Visual Studio ist das f# Interactive-Fenster.</span><span class="sxs-lookup"><span data-stu-id="be367-167">One of the best features of the Visual F# tooling in Visual Studio is the F# Interactive Window.</span></span>  <span data-ttu-id="be367-168">Sie können Sie Code über an einen Prozess zu senden, Sie diesen Code aufrufen können und das Ergebnis interaktiv angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be367-168">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="be367-169">Um zu beginnen, verwenden es, markieren Sie die `square` Funktion, die in Ihrem Code definiert.</span><span class="sxs-lookup"><span data-stu-id="be367-169">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="be367-170">Halten Sie als Nächstes die **Alt** Schlüssel, und drücken Sie **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="be367-170">Next, hold the **Alt** key and press **Enter**.</span></span>  <span data-ttu-id="be367-171">Dies führt den Code in der f# Interactive-Fenster.</span><span class="sxs-lookup"><span data-stu-id="be367-171">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="be367-172">Daraufhin sollte das f# Interactive-Fenster mit den folgenden darin angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="be367-172">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="be367-173">Dies zeigt die gleiche Funktionssignatur für die `square` -Funktion, die Sie zuvor gesehen haben, wenn Sie über die Funktion gezeigt.</span><span class="sxs-lookup"><span data-stu-id="be367-173">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="be367-174">Da `square` ist nun in der f# Interactive-Prozess definiert, können Sie es mit unterschiedlichen Werten aufrufen:</span><span class="sxs-lookup"><span data-stu-id="be367-174">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="be367-175">Dies führt die Funktion, bindet das Ergebnis in einen neuen Namen `it`, und zeigt den Typ und Wert des `it`.</span><span class="sxs-lookup"><span data-stu-id="be367-175">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="be367-176">Beachten Sie, dass Sie jede Zeile mit beenden müssen `;;`.</span><span class="sxs-lookup"><span data-stu-id="be367-176">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="be367-177">Dies ist wie f# Interactive weiß, wenn der Funktionsaufruf abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="be367-177">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="be367-178">Sie können auch neue Funktionen in f# Interactive definieren:</span><span class="sxs-lookup"><span data-stu-id="be367-178">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="be367-179">Die oben genannten definiert eine neue Funktion `isOdd`, nimmt ein `int` und prüft, ob es ungerade ist!</span><span class="sxs-lookup"><span data-stu-id="be367-179">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span> <span data-ttu-id="be367-180">Sie können diese Funktion, um festzustellen, was es mit unterschiedlichen Eingaben zurückgibt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="be367-180">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="be367-181">Sie können Funktionen in Funktionsaufrufen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="be367-181">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="be367-182">Sie können auch die [Pipe-Forward-Operator](../language-reference/symbol-and-operator-reference/index.md) pipeline den Wert in die zwei Funktionen für:</span><span class="sxs-lookup"><span data-stu-id="be367-182">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="be367-183">Der Pipe-Forward-Operator und vieles mehr, werden in späteren Lernprogrammen behandelt.</span><span class="sxs-lookup"><span data-stu-id="be367-183">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="be367-184">Dies ist nur einen Einblick in die Verwendungsmöglichkeiten mit f# Interactive.</span><span class="sxs-lookup"><span data-stu-id="be367-184">This is only a glimpse into what you can do with F# Interactive.</span></span> <span data-ttu-id="be367-185">Weitere Auschecken [Interaktive Programmierung mit F#-](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="be367-185">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="be367-186">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="be367-186">Next steps</span></span>

<span data-ttu-id="be367-187">Wenn Sie nicht bereits getan haben, sehen Sie sich die [Tour von F#-](../tour.md), die behandelt einige der wichtigsten Funktionen der Programmiersprache f#.</span><span class="sxs-lookup"><span data-stu-id="be367-187">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="be367-188">Er bieten Ihnen einen Überblick über die Funktionen von f#, und gibt ausreichend Codebeispiele, die Sie in Visual Studio kopieren und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="be367-188">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="be367-189">Es gibt auch einige sehr hilfreiche externe Ressourcen, die Sie verwenden können, präsentiert, in der [F#-Handbuch](../index.md).</span><span class="sxs-lookup"><span data-stu-id="be367-189">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="be367-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be367-190">See also</span></span>
 [<span data-ttu-id="be367-191">Visual F#</span><span class="sxs-lookup"><span data-stu-id="be367-191">Visual F#</span></span>](index.md)  
 [<span data-ttu-id="be367-192">Einführung in F#</span><span class="sxs-lookup"><span data-stu-id="be367-192">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="be367-193">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="be367-193">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="be367-194">Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="be367-194">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="be367-195">Symbol und dem Operator-Referenz</span><span class="sxs-lookup"><span data-stu-id="be367-195">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
