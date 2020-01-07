---
title: Erste Schritte mit F# in Visual Studio
description: Erfahren Sie, wie Sie F# in Visual Studio verwenden.
ms.date: 12/20/2019
ms.openlocfilehash: 9bf47fb08ea3df0aa0d5064043d94f030d45d568
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337349"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="f898d-103">Erste Schritte mit F# in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f898d-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="f898d-104">F#und die visuellen F# Tools werden in der integrierten Entwicklungsumgebung (IDE) von Visual Studio unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f898d-104">F# and the Visual F# tooling are supported in the Visual Studio integrated development environment (IDE).</span></span>

<span data-ttu-id="f898d-105">Vergewissern Sie sich zunächst, dass [Visual Studio mit F# Unterstützung installiert](install-fsharp.md#install-f-with-visual-studio)ist.</span><span class="sxs-lookup"><span data-stu-id="f898d-105">To begin, ensure that you have [Visual Studio installed with F# support](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f898d-106">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="f898d-106">Create a console application</span></span>

<span data-ttu-id="f898d-107">Eines der grundlegendsten Projekte in Visual Studio ist die Konsolen-app.</span><span class="sxs-lookup"><span data-stu-id="f898d-107">One of the most basic projects in Visual Studio is the console app.</span></span> <span data-ttu-id="f898d-108">Gehen Sie zum Erstellen wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="f898d-108">Here's how to create one:</span></span>

1. <span data-ttu-id="f898d-109">Öffnen Sie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="f898d-109">Open Visual Studio 2019.</span></span>

2. <span data-ttu-id="f898d-110">Wählen Sie im Startfenster **Neues Projekt erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f898d-110">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="f898d-111">Wählen Sie **F#** auf der Seite **Neues Projekt erstellen** aus der Liste Sprache aus.</span><span class="sxs-lookup"><span data-stu-id="f898d-111">On the **Create a new project** page, choose **F#** from the Language list.</span></span>

4. <span data-ttu-id="f898d-112">Wählen Sie die Vorlage **Konsolen-app (.net Core)** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f898d-112">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

5. <span data-ttu-id="f898d-113">Geben Sie auf der Seite **Neues Projekt konfigurieren** einen Namen in das Feld **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="f898d-113">On the **Configure your new project** page, enter a name in the **Project name** box.</span></span> <span data-ttu-id="f898d-114">Wählen Sie anschließend **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f898d-114">Then, choose **Create**.</span></span>

   <span data-ttu-id="f898d-115">Visual Studio erstellt das neue F# Projekt.</span><span class="sxs-lookup"><span data-stu-id="f898d-115">Visual Studio creates the new F# project.</span></span> <span data-ttu-id="f898d-116">Sie können Sie im Projektmappen-Explorer Fenster sehen.</span><span class="sxs-lookup"><span data-stu-id="f898d-116">You can see it in the Solution Explorer window.</span></span>

## <a name="write-the-code"></a><span data-ttu-id="f898d-117">Den Code schreiben</span><span class="sxs-lookup"><span data-stu-id="f898d-117">Write the code</span></span>

<span data-ttu-id="f898d-118">Wir beginnen mit dem Schreiben von Code.</span><span class="sxs-lookup"><span data-stu-id="f898d-118">Let's get started by writing some code.</span></span> <span data-ttu-id="f898d-119">Stellen Sie sicher, dass die Datei `Program.fs` geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f898d-119">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="f898d-120">Im vorherigen Codebeispiel wird eine Funktion mit dem Namen "`square`" definiert, die eine Eingabe mit dem Namen "`x`" annimmt und Sie selbst multipliziert.</span><span class="sxs-lookup"><span data-stu-id="f898d-120">The previous code sample defines a function called `square` that takes an input named `x` and multiplies it by itself.</span></span> <span data-ttu-id="f898d-121">Da F# den [Typrückschluss](../language-reference/type-inference.md)verwendet, muss der Typ der `x` nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f898d-121">Because F# uses [Type inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span> <span data-ttu-id="f898d-122">Der F# Compiler versteht die Typen, bei denen Multiplikation gültig ist, und weist `x` basierend auf der Aufruf `square` einen Typ zu.</span><span class="sxs-lookup"><span data-stu-id="f898d-122">The F# compiler understands the types where multiplication is valid and assigns a type to `x` based on how `square` is called.</span></span> <span data-ttu-id="f898d-123">Wenn Sie mit den Cursor auf `square` zeigen, sollte Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="f898d-123">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="f898d-124">Dies wird als Typsignatur der Funktion bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f898d-124">This is what is known as the function's type signature.</span></span> <span data-ttu-id="f898d-125">Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen x annimmt und eine ganze Zahl erzeugt."</span><span class="sxs-lookup"><span data-stu-id="f898d-125">It can be read like this: "Square is a function that takes an integer named x and produces an integer".</span></span> <span data-ttu-id="f898d-126">Der Compiler hat dem `int`-Typ jetzt `square`. Dies liegt daran, dass die Multiplikation nicht in *allen* Typen generisch ist, sondern eher ein geschlossener Satz von Typen.</span><span class="sxs-lookup"><span data-stu-id="f898d-126">The compiler gave `square` the `int` type for now; this is because multiplication is not generic across *all* types but rather a closed set of types.</span></span> <span data-ttu-id="f898d-127">Der F# Compiler passt die Typsignatur an, wenn Sie `square` mit einem anderen Eingabetyp (z. b. einer `float`) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f898d-127">The F# compiler will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="f898d-128">Eine weitere Funktion, `main`, ist definiert und wird mit dem `EntryPoint`-Attribut ergänzt.</span><span class="sxs-lookup"><span data-stu-id="f898d-128">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute.</span></span> <span data-ttu-id="f898d-129">Dieses Attribut weist den F# Compiler an, dass die Programmausführung gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f898d-129">This attribute tells the F# compiler that program execution should start there.</span></span> <span data-ttu-id="f898d-130">Der Ausdruck folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code (in der Regel `0`) zurück gegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f898d-130">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="f898d-131">Sie befindet sich in der Einstiegspunkt Funktion `main`, dass Sie die `square`-Funktion mit einem Argument von `12`aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f898d-131">It is in the entry point function, `main`, that you call the `square` function with an argument of `12`.</span></span> <span data-ttu-id="f898d-132">Der F# Compiler weist dann den Typ des `square` zu, der `int -> int` werden soll (d. h. eine Funktion, die eine `int` annimmt und eine `int`erzeugt).</span><span class="sxs-lookup"><span data-stu-id="f898d-132">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function that takes an `int` and produces an `int`).</span></span> <span data-ttu-id="f898d-133">Der `printfn`-Aufrufe ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet und das Ergebnis (und eine neue Zeile) ausgibt.</span><span class="sxs-lookup"><span data-stu-id="f898d-133">The call to `printfn` is a formatted printing function that uses a format string and prints the result (and a new line).</span></span> <span data-ttu-id="f898d-134">Die Format Zeichenfolge, ähnlich wie Programmiersprachen im C-Stil, verfügt über Parameter (`%d`), die den an Sie über gebenden Argumenten entsprechen, in diesem Fall `12` und `(square 12)`.</span><span class="sxs-lookup"><span data-stu-id="f898d-134">The format string, similar to C-style programming languages, has parameters (`%d`) that correspond to the arguments that are passed to it, in this case, `12` and `(square 12)`.</span></span>

## <a name="run-the-code"></a><span data-ttu-id="f898d-135">Ausführen des Codes</span><span class="sxs-lookup"><span data-stu-id="f898d-135">Run the code</span></span>

<span data-ttu-id="f898d-136">Sie können den Code ausführen und die Ergebnisse anzeigen, indem Sie **STRG**+**F5**drücken.</span><span class="sxs-lookup"><span data-stu-id="f898d-136">You can run the code and see the results by pressing **Ctrl**+**F5**.</span></span> <span data-ttu-id="f898d-137">Alternativ können Sie das **Debuggen** > **Starten ohne Debuggen** in der Menüleiste der obersten Ebene auswählen.</span><span class="sxs-lookup"><span data-stu-id="f898d-137">Alternatively, you can choose the **Debug** > **Start Without Debugging** from the top-level menu bar.</span></span> <span data-ttu-id="f898d-138">Dadurch wird das Programm ohne Debuggen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f898d-138">This runs the program without debugging.</span></span>

<span data-ttu-id="f898d-139">Die folgende Ausgabe wird im Konsolenfenster ausgegeben, das von Visual Studio geöffnet wurde:</span><span class="sxs-lookup"><span data-stu-id="f898d-139">The following output prints to the console window that Visual Studio opened:</span></span>

```console
12 squared is: 144!
```

<span data-ttu-id="f898d-140">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="f898d-140">Congratulations!</span></span> <span data-ttu-id="f898d-141">Sie haben ihr erstes F# Projekt in Visual Studio erstellt, eine F# Funktion geschrieben, die einen Wert berechnet und druckt, und das Projekt ausführen, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f898d-141">You've created your first F# project in Visual Studio, written an F# function that calculates and prints a value, and run the project to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f898d-142">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f898d-142">Next steps</span></span>

<span data-ttu-id="f898d-143">Falls Sie es nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md)an. Diese behandelt einige der wichtigsten Funktionen der Sprache F#.</span><span class="sxs-lookup"><span data-stu-id="f898d-143">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span> <span data-ttu-id="f898d-144">Es bietet eine Übersicht über einige der Funktionen von F# und zahlreiche Codebeispiele, die Sie in Visual Studio kopieren und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="f898d-144">It provides an overview of some of the capabilities of F# and ample code samples that you can copy into Visual Studio and run.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f898d-145">Einführung in F#</span><span class="sxs-lookup"><span data-stu-id="f898d-145">Tour of F#</span></span>](../tour.md)

## <a name="see-also"></a><span data-ttu-id="f898d-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f898d-146">See also</span></span>

- [<span data-ttu-id="f898d-147">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="f898d-147">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="f898d-148">Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="f898d-148">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="f898d-149">Symbol-und Operator Verweis</span><span class="sxs-lookup"><span data-stu-id="f898d-149">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
