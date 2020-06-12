---
title: 'C#-Programmierhandbuch: Hallo Welt – Ihr erstes Programm mit Visual Studio unter Windows oder Mac'
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 6d78ec83fec72b30f5cee398af1816d0cac35886
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241863"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="f6bc0-102">Ihr erstes Programm: Hallo Welt</span><span class="sxs-lookup"><span data-stu-id="f6bc0-102">Hello World -- Your first program</span></span>

<span data-ttu-id="f6bc0-103">In diesem Artikel verwenden Sie Visual Studio zum Erstellen eines traditionellen Hallo Welt</span><span class="sxs-lookup"><span data-stu-id="f6bc0-103">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="f6bc0-104">-Programms.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-104">program.</span></span> <span data-ttu-id="f6bc0-105">Visual Studio ist eine professionelle IDE (integrierte Entwicklungsumgebung) mit vielen Features, die für die .NET-Entwicklung konzipiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-105">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="f6bc0-106">Zum Erstellen dieses Programms verwenden Sie nur wenige dieser Features.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-106">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="f6bc0-107">Weitere Informationen zu Visual Studio finden Sie unter [Erste Schritte mit Visual C#](/visualstudio/ide/quickstart-csharp-console).</span><span class="sxs-lookup"><span data-stu-id="f6bc0-107">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="f6bc0-108">Erstellen einer neuen Anwendung</span><span class="sxs-lookup"><span data-stu-id="f6bc0-108">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="f6bc0-109">Windows</span><span class="sxs-lookup"><span data-stu-id="f6bc0-109">Windows</span></span>](#tab/windows)

<span data-ttu-id="f6bc0-110">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-110">Start Visual Studio.</span></span> <span data-ttu-id="f6bc0-111">Unter Windows wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f6bc0-111">You'll see the following image on Windows:</span></span>

![Visual Studio-Willkommensbildschirm unter Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="f6bc0-113">Klicken Sie in der unteren rechten Ecke auf **Neues Projekt erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-113">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="f6bc0-114">Daraufhin zeigt Visual Studio das Dialogfeld **Neues Projekt** an:</span><span class="sxs-lookup"><span data-stu-id="f6bc0-114">Visual Studio displays the **New Project** dialog:</span></span>

![Anzeige „Neues Projekt“ in Visual Studio unter Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="f6bc0-116">Wenn Sie Visual Studio zum ersten Mal starten, ist die Liste **Zuletzt verwendete Projektvorlagen** leer.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-116">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="f6bc0-117">Wählen Sie „Konsolen-App (.NET Core)“ im Dialogfeld „Neues Projekt“ aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-117">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="f6bc0-118">Geben Sie Ihrem Projekt einen Namen, z. B. „HalloWelt“, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-118">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="f6bc0-119">Visual Studio öffnet Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-119">Visual Studio opens your project.</span></span> <span data-ttu-id="f6bc0-120">Dieses ist bereits ein grundlegendes „Hallo Welt“-</span><span class="sxs-lookup"><span data-stu-id="f6bc0-120">It's already a basic "Hello World!"</span></span> <span data-ttu-id="f6bc0-121">Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-121">example.</span></span> <span data-ttu-id="f6bc0-122">Drücken Sie `Ctrl` + `F5`, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-122">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="f6bc0-123">Visual Studio erstellt Ihr Projekt und konvertiert den Quellcode in eine ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-123">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="f6bc0-124">Dann wird ein Befehlsfenster gestartet, das Ihre neue Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-124">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="f6bc0-125">Der folgende Text sollte im Fenster angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="f6bc0-125">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="f6bc0-126">Drücken Sie eine beliebige Taste, um das Fenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-126">Press a key to close the window.</span></span>

# <a name="macos"></a>[<span data-ttu-id="f6bc0-127">macOS</span><span class="sxs-lookup"><span data-stu-id="f6bc0-127">macOS</span></span>](#tab/macos)

<span data-ttu-id="f6bc0-128">Starten Sie Visual Studio für Mac.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-128">Start Visual Studio for Mac.</span></span> <span data-ttu-id="f6bc0-129">Unter Mac wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f6bc0-129">You'll see the following image on Mac:</span></span>

![Visual Studio-Willkommensbildschirm unter Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="f6bc0-131">Wenn Sie Visual Studio für Mac zum ersten Mal starten, ist die Liste **Zuletzt geöffnete Projekte** leer.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-131">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="f6bc0-132">Klicken Sie oben rechts auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-132">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="f6bc0-133">Daraufhin zeigt Visual Studio für Mac das Dialogfeld **Neues Projekt** an:</span><span class="sxs-lookup"><span data-stu-id="f6bc0-133">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Anzeige „Neues Projekt“ in Visual Studio für Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="f6bc0-135">Wählen Sie im Dialogfeld „Neues Projekt“ die Option „.NET Core“ und dann „Konsolen-App“ aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-135">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="f6bc0-136">Daraufhin müssen Sie ein Zielframework auswählen.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-136">You'll need to select the target framework.</span></span> <span data-ttu-id="f6bc0-137">Hier können Sie die Standardeinstellung beibehalten, klicken Sie also auf „Weiter“.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-137">The default is fine, so press next.</span></span> <span data-ttu-id="f6bc0-138">Geben Sie Ihrem Projekt einen Namen, z. B. „HalloWelt“, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-138">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="f6bc0-139">Sie können den Standardprojektspeicherort verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-139">You can use the default project location.</span></span> <span data-ttu-id="f6bc0-140">Fügen Sie dieses Projekt nicht zur Quellcodeverwaltung hinzu.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-140">Don't add this project to source control.</span></span>

<span data-ttu-id="f6bc0-141">Visual Studio für Mac öffnet Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-141">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="f6bc0-142">Dieses ist bereits ein grundlegendes „Hallo Welt“-</span><span class="sxs-lookup"><span data-stu-id="f6bc0-142">It's already a basic "Hello World!"</span></span> <span data-ttu-id="f6bc0-143">Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-143">example.</span></span> <span data-ttu-id="f6bc0-144">Drücken Sie `Ctrl` + `Fn` + `F5`, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-144">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="f6bc0-145">Visual Studio für Mac erstellt Ihr Projekt und konvertiert den Quellcode in eine ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-145">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="f6bc0-146">Dann wird ein Befehlsfenster gestartet, das Ihre neue Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-146">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="f6bc0-147">Der folgende Text sollte im Fenster angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="f6bc0-147">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="f6bc0-148">Drücken Sie eine beliebige Taste, um die Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-148">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="f6bc0-149">Elemente eines C#-Programms</span><span class="sxs-lookup"><span data-stu-id="f6bc0-149">Elements of a C# program</span></span>

<span data-ttu-id="f6bc0-150">Im Folgenden werden die wichtigen Bestandteile dieses Programms untersucht.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-150">Let's examine the important parts of this program.</span></span> <span data-ttu-id="f6bc0-151">Die erste Zeile enthält einen Kommentar.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-151">The first line contains a comment.</span></span> <span data-ttu-id="f6bc0-152">Durch die Zeichen `//` wird die restliche Zeile in einen Kommentar konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-152">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="f6bc0-153">Sie können auch einen Kommentar aus einem Textblock einfügen, indem Sie ihn zwischen den Zeichen `/*` und `*/` einschließen.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-153">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="f6bc0-154">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-154">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="f6bc0-155">Eine C#-Konsolenanwendung muss eine `Main`-Methode enthalten, in der die Steuerung beginnt und endet.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-155">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="f6bc0-156">Innerhalb der `Main`-Methode erstellen Sie Objekte und führen andere Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-156">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="f6bc0-157">Bei der `Main`-Methode handelt es sich um eine [statische](../../language-reference/keywords/static.md) Methode, die sich innerhalb einer Klasse oder Struktur befindet.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-157">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="f6bc0-158">Im vorherigen „Hello World!“-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6bc0-158">In the previous "Hello World!"</span></span> <span data-ttu-id="f6bc0-159">befindet sie sich in einer Klasse namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-159">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="f6bc0-160">Sie können die `Main`-Methode auf eine der folgenden Arten deklarieren:</span><span class="sxs-lookup"><span data-stu-id="f6bc0-160">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="f6bc0-161">Es kann `void` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-161">It can return `void`.</span></span> <span data-ttu-id="f6bc0-162">Das heißt, Ihr Programm gibt keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-162">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="f6bc0-163">Zudem kann eine ganze Zahl zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-163">It can also return an integer.</span></span> <span data-ttu-id="f6bc0-164">Der Integer stellt den **Exitcode** Ihrer Anwendung dar.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-164">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="f6bc0-165">Bei beiden Rückgabetypen können Argumente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-165">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="f6bc0-166">- oder -</span><span class="sxs-lookup"><span data-stu-id="f6bc0-166">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="f6bc0-167">Der Parameter der `Main`-Methode, `args`, ist ein `string`-Array, das die Befehlszeilenargumente enthält, die zum Aufrufen des Programms verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-167">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="f6bc0-168">Weitere Informationen zur Verwendung von Befehlszeilenargumenten finden Sie in den Beispielen unter [Main() und Befehlszeilenargumente](../main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6bc0-168">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="f6bc0-169">Eingabe und Ausgabe</span><span class="sxs-lookup"><span data-stu-id="f6bc0-169">Input and output</span></span>

<span data-ttu-id="f6bc0-170">C#-Programme verwenden im Allgemeinen die Eingabe-/Ausgabedienste der Laufzeitbibliothek von .NET.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-170">C# programs generally use the input/output services provided by the run-time library of .NET.</span></span> <span data-ttu-id="f6bc0-171">Die Anweisung `System.Console.WriteLine("Hello World!");` verwendet die <xref:System.Console.WriteLine%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-171">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="f6bc0-172">Dies ist eine der Ausgabemethoden der <xref:System.Console>-Klasse in der Laufzeit-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-172">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="f6bc0-173">Bei dieser Methode wird der Zeichenfolgenparameter für den Standardausgabestream gefolgt von einer neuen Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-173">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="f6bc0-174">Für andere Eingabe-/Ausgabevorgänge sind andere <xref:System.Console>-Methoden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-174">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="f6bc0-175">Wenn Sie die `using System;`-Direktive am Anfang des Programms einfügen, können Sie die <xref:System>-Klassen und -Methoden direkt verwenden, ohne sie voll zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-175">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="f6bc0-176">Zum Beispiel können Sie `Console.WriteLine` statt `System.Console.WriteLine` aufrufen:</span><span class="sxs-lookup"><span data-stu-id="f6bc0-176">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="f6bc0-177">Weitere Informationen zu Eingabe-/Ausgabemethoden finden Sie unter <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-177">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6bc0-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6bc0-178">See also</span></span>

- [<span data-ttu-id="f6bc0-179">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f6bc0-179">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f6bc0-180">Beispiele und Tutorials</span><span class="sxs-lookup"><span data-stu-id="f6bc0-180">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="f6bc0-181">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="f6bc0-181">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="f6bc0-182">Erste Schritte mit Visual C#</span><span class="sxs-lookup"><span data-stu-id="f6bc0-182">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
