---
title: Erste Schritte mit f# in Visual Studio
description: Erfahren Sie, wie Sie f# in Visual Studio verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: 3dac8466501338873aeb308ceac9274a7934a8a9
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43872850"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="ef814-103">Erste Schritte mit f# in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ef814-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="ef814-104">F# und Visual F#-Tools werden in Visual Studio-IDE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ef814-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="ef814-105">Um zu beginnen, stellen Sie sicher, dass man [Visual Studio installiert, die mit f#](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ef814-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="ef814-106">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="ef814-106">Creating a console application</span></span>

<span data-ttu-id="ef814-107">Eine der grundlegendsten Projekte in Visual Studio ist die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="ef814-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="ef814-108">Und so gehen Sie dabei vor.</span><span class="sxs-lookup"><span data-stu-id="ef814-108">Here's how to do it.</span></span>  <span data-ttu-id="ef814-109">Sobald Visual Studio geöffnet ist:</span><span class="sxs-lookup"><span data-stu-id="ef814-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="ef814-110">Auf der **Datei** Startmenü **neu**, und wählen Sie dann **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="ef814-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="ef814-111">In das neue Projekt im Dialogfeld unter **Vorlagen**, sollte **Visual F#-**.</span><span class="sxs-lookup"><span data-stu-id="ef814-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="ef814-112">Wählen Sie diese Option, um die F#-Vorlagen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef814-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="ef814-113">Wählen Sie entweder **.NET Core-Konsolen-app** oder **Konsolen-app**.</span><span class="sxs-lookup"><span data-stu-id="ef814-113">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="ef814-114">Wählen Sie die **OK** klicken, um den f#-Projekt zu erstellen!</span><span class="sxs-lookup"><span data-stu-id="ef814-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="ef814-115">Eine f#-Projekt im Projektmappen-Explorer sollte nun angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef814-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="ef814-116">Das Schreiben von code</span><span class="sxs-lookup"><span data-stu-id="ef814-116">Writing your code</span></span>

<span data-ttu-id="ef814-117">Erste Schritte zunächst, Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ef814-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="ef814-118">Stellen Sie sicher, dass die `Program.fs` Datei geöffnet ist, und Ersetzen Sie deren Inhalt durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ef814-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="ef814-119">Im vorherigen Beispiel, eine Funktion `square` wurde der Eingabe mit dem Namen akzeptiert definiert `x` und von sich selbst multipliziert.</span><span class="sxs-lookup"><span data-stu-id="ef814-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="ef814-120">Da f# verwendet [Typrückschluss](../language-reference/type-inference.md), den Typ des `x` muss nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef814-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="ef814-121">F#-Compiler erkennt die Typen, in denen Multiplikation gültig ist, und weist einen Typ `x` basieren, wie `square` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ef814-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="ef814-122">Wenn Sie darauf zeigen `square`, sollte Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ef814-122">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="ef814-123">Dies ist als die Signatur der Funktion Typ bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ef814-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="ef814-124">Sie können wie folgt gelesen werden: "Quadrat ist eine Funktion, die eine ganze Zahl, die mit dem Namen akzeptiert x und erzeugt eine ganze Zahl".</span><span class="sxs-lookup"><span data-stu-id="ef814-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="ef814-125">Beachten Sie, die der Compiler hat `square` der `int` Typ vorerst - Dies liegt daran Multiplikation nicht für generische *alle* Typen, aber stattdessen über einen vollständigen Satz von Typen ist generisch.</span><span class="sxs-lookup"><span data-stu-id="ef814-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="ef814-126">Der F#-Compiler übernommen `int` an diesem Punkt, aber es passt die Datentyp-Signatur Aufrufen `square` mit einem anderen Eingabetyp, z. B. eine `float`.</span><span class="sxs-lookup"><span data-stu-id="ef814-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="ef814-127">Eine andere Funktion, `main`, definiert ist, wird die ergänzt, mit der `EntryPoint` Attribut, um dem F#-Compiler diese Ausführung des Programms sollte dort beginnen.</span><span class="sxs-lookup"><span data-stu-id="ef814-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="ef814-128">Dabei wird die gleiche Konvention wie andere [Programmiersprachen C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in dem Befehlszeilenargumente an diese Funktion übergeben werden können und ein ganzzahligen Code wird zurückgegeben (in der Regel `0`).</span><span class="sxs-lookup"><span data-stu-id="ef814-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="ef814-129">Es ist in dieser Funktion, die wir Aufrufen der `square` Funktion mit dem Argument `12`.</span><span class="sxs-lookup"><span data-stu-id="ef814-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="ef814-130">F#-Compiler weist dann den Typ des `square` sein `int -> int` (, also eine Funktion, die nimmt eine `int` und erzeugt eine `int`).</span><span class="sxs-lookup"><span data-stu-id="ef814-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="ef814-131">Der Aufruf von `printfn` ist eine formatierte drucken Funktion, die eine Formatzeichenfolge, die Programmiersprachen C-Stil, Parameter ähnelt, verwendet die in der Formatzeichenfolge angegeben entsprechen, und gibt dann das Ergebnis und eine neue Zeile.</span><span class="sxs-lookup"><span data-stu-id="ef814-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="ef814-132">Ausführen des Codes</span><span class="sxs-lookup"><span data-stu-id="ef814-132">Running your code</span></span>

<span data-ttu-id="ef814-133">Sie können den Code auszuführen und Ergebnisse angezeigt, durch Drücken von **STRG**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="ef814-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="ef814-134">Dies führt das Programm ohne Debuggen und ermöglicht Ihnen, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ef814-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="ef814-135">Alternativ können Sie auch die **Debuggen** Menü der obersten Ebene in Visual Studio, und wählen Sie **Starten ohne Debugging**.</span><span class="sxs-lookup"><span data-stu-id="ef814-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="ef814-136">Sie sollten jetzt sehen, dass die folgenden im Konsolenfenster anzuzeigen, die Visual Studio eingeblendet wird, wird ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="ef814-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="ef814-137">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="ef814-137">Congratulations!</span></span>  <span data-ttu-id="ef814-138">Sie haben Ihr erste F#-Projekt in Visual Studio erstellten, geschrieben, dass eine F#-Funktion die Ergebnisse des Aufrufs dieser Funktion ausgegeben und führen Sie das Projekt aus, um einige Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ef814-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ef814-139">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ef814-139">Next steps</span></span>

<span data-ttu-id="ef814-140">Wenn Sie nicht bereits getan haben, sehen Sie sich die [Einführung in f#](../tour.md), die behandelt einige der wichtigsten Funktionen der Sprache f#.</span><span class="sxs-lookup"><span data-stu-id="ef814-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="ef814-141">Es wird bieten Ihnen einen Überblick über einige der Funktionen von f# und bieten reichlich Codebeispiele, die Sie in Visual Studio kopieren und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="ef814-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="ef814-142">Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können, im gerätekatalog dargestellt die [Leitfaden für f#](../index.md).</span><span class="sxs-lookup"><span data-stu-id="ef814-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef814-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef814-143">See also</span></span>

- [<span data-ttu-id="ef814-144">Einführung in F#</span><span class="sxs-lookup"><span data-stu-id="ef814-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="ef814-145">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="ef814-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="ef814-146">Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="ef814-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="ef814-147">Symbol und dem Operator-Referenz</span><span class="sxs-lookup"><span data-stu-id="ef814-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
