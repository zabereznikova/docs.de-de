---
title: Erste Schritte mit F# in Visual Studio
description: Erfahren Sie, wie Sie F# in Visual Studio verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: e573af67a1fc00b0a340f8c73ab1ee0ed2b97810
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082695"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="a6076-103">Erste Schritte mit F# in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a6076-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="a6076-104">F# und die visuellen F#-Tools werden in der Visual Studio-IDE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a6076-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="a6076-105">Um zu beginnen, stellen Sie sicher, dass [Visual Studio zusammen mit F# installiert ist](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a6076-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="a6076-106">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="a6076-106">Creating a console application</span></span>

<span data-ttu-id="a6076-107">Eines der grundlegendsten Projekte in Visual Studio ist die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="a6076-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="a6076-108">Und so gehen Sie dabei vor.</span><span class="sxs-lookup"><span data-stu-id="a6076-108">Here's how to do it.</span></span>  <span data-ttu-id="a6076-109">Nachdem Visual Studio geöffnet wurde:</span><span class="sxs-lookup"><span data-stu-id="a6076-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="a6076-110">Zeigen Sie im Menü **Datei** auf **neu**, und wählen Sie dann **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="a6076-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="a6076-111">Im Dialogfeld Neues Projekt unter **Vorlagen**sollte **Visualisierung F#** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a6076-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="a6076-112">Wählen Sie diese Option aus F# , um die Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a6076-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="a6076-113">Wählen Sie entweder **Konsolen-App (.NET Core)** oder **Konsolen-App (.NET Framework)** aus.</span><span class="sxs-lookup"><span data-stu-id="a6076-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="a6076-114">Wählen Sie **OK**, um das F#-Projekt zu erstellen!</span><span class="sxs-lookup"><span data-stu-id="a6076-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="a6076-115">Ein F#-Projekt im Projektmappen-Explorer sollte nun angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a6076-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="a6076-116">Schreiben von Code</span><span class="sxs-lookup"><span data-stu-id="a6076-116">Writing your code</span></span>

<span data-ttu-id="a6076-117">Beginnen wir, indem wir zuerst Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="a6076-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="a6076-118">Stellen Sie sicher, dass die Datei `Program.fs` geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a6076-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="a6076-119">Im vorherigen Codebeispiel wurde eine Funktion `square` definiert, die eine Eingabe mit dem Namen `x` annimmt und diese mit sich selbst multipliziert.</span><span class="sxs-lookup"><span data-stu-id="a6076-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="a6076-120">Da F# [Typrückschluss](../language-reference/type-inference.md) verwendet, muss der Typ von `x` nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a6076-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="a6076-121">Der F#-Compiler versteht die Typen, bei denen eine Multiplikation gültig ist, und weist `x` basierend auf dem `square` Aufruf einen Typen zu.</span><span class="sxs-lookup"><span data-stu-id="a6076-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="a6076-122">Wenn Sie mit den Cursor auf `square` zeigen, sollte Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="a6076-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="a6076-123">Dies wird als Typsignatur der Funktion bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a6076-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="a6076-124">Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen" x "annimmt und eine ganze Zahl erstellt.</span><span class="sxs-lookup"><span data-stu-id="a6076-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="a6076-125">Beachten Sie, dass der `square` Compiler `int` den Typ für den Moment erteilt hat. Dies liegt daran, dass die Multiplikation nicht für *alle* Typen generisch ist, sondern für einen geschlossenen Satz von Typen generisch ist.</span><span class="sxs-lookup"><span data-stu-id="a6076-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="a6076-126">Der F# Compiler hat `int` an dieser Stelle gewählt, aber er passt die Typsignatur an, wenn `square` Sie mit einem `float`anderen Eingabetyp, z. b., aufruft.</span><span class="sxs-lookup"><span data-stu-id="a6076-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="a6076-127">Eine weitere Funktion `main` ist definiert und wurde mit dem `EntryPoint`-Attribut versehen, um dem F#-Compiler mitzuteilen, dass die Programmausführung hier gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6076-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="a6076-128">Der Ausdruck folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code (in der Regel `0`) zurück gegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a6076-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="a6076-129">In dieser Funktion wird die `square` Funktion mit einem Argument von `12`aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a6076-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="a6076-130">Der F# Compiler weist dann den Typ von `square` zu `int -> int` , d. h. eine Funktion, die einen `int` annimmt und einen `int`erzeugt.</span><span class="sxs-lookup"><span data-stu-id="a6076-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="a6076-131">Der-Befehl ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet, ähnlich wie Programmiersprachen im C-Stil, Parameter, die den in der Format Zeichenfolge angegebenen entsprechen, und dann das Ergebnis und eine neue Zeile ausgibt. `printfn`</span><span class="sxs-lookup"><span data-stu-id="a6076-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="a6076-132">Ausführen des Codes</span><span class="sxs-lookup"><span data-stu-id="a6076-132">Running your code</span></span>

<span data-ttu-id="a6076-133">Sie können den Code ausführen und die Ergebnisse anzeigen, indem Sie **STRG**+**F5** drücken.</span><span class="sxs-lookup"><span data-stu-id="a6076-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="a6076-134">Dadurch wird das Programm ohne Debuggen ausgeführt, und Sie können die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a6076-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="a6076-135">Alternativ können Sie in Visual Studio in der obersten Ebene das Menü-Element  **Debuggen** auswählen und dann **Starten ohne Debugging** auswählen.</span><span class="sxs-lookup"><span data-stu-id="a6076-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="a6076-136">Im Konsolenfenster, das durch Visual Studio anzeigt wird, sollte nun Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="a6076-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="a6076-137">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="a6076-137">Congratulations!</span></span>  <span data-ttu-id="a6076-138">Sie haben Ihr erstes F#-Projekt in Visual Studio erstellt, eine F#-Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion ausgegeben hat, und das Projekt ausgeführt, um einige Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a6076-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a6076-139">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a6076-139">Next steps</span></span>

<span data-ttu-id="a6076-140">Falls Sie es nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md)an. Diese behandelt einige der wichtigsten Funktionen der Sprache F#.</span><span class="sxs-lookup"><span data-stu-id="a6076-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="a6076-141">Es werden Ihnen einen Überblick über einige der Funktionen von F# mit reichlich Codebeispiele geboten, die Sie in Visual Studio kopieren und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="a6076-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="a6076-142">Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können und die in der Übersicht [Leitfaden für F#](../index.md) dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="a6076-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6076-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6076-143">See also</span></span>

- [<span data-ttu-id="a6076-144">Einführung in F#</span><span class="sxs-lookup"><span data-stu-id="a6076-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="a6076-145">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="a6076-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="a6076-146">Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="a6076-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="a6076-147">Symbol-und Operator Verweis</span><span class="sxs-lookup"><span data-stu-id="a6076-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
