---
title: 'C#-Programmierhandbuch: Hallo Welt – Ihr erstes Programm mit Visual Studio unter Windows oder Mac'
description: Visual Studio ist eine professionelle Entwicklungsumgebung mit vielen Features für die .NET-Entwicklung. Verwenden Sie Visual Studio, um eine C#-Version eines Hallo Welt-Programms zu erstellen.
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: b78937b8ba1c7d4718bfb6252dac705945336d2a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301826"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="b1d2a-104">Ihr erstes Programm: Hallo Welt</span><span class="sxs-lookup"><span data-stu-id="b1d2a-104">Hello World -- Your first program</span></span>

<span data-ttu-id="b1d2a-105">In diesem Artikel verwenden Sie Visual Studio zum Erstellen eines traditionellen Hallo Welt</span><span class="sxs-lookup"><span data-stu-id="b1d2a-105">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="b1d2a-106">-Programms.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-106">program.</span></span> <span data-ttu-id="b1d2a-107">Visual Studio ist eine professionelle IDE (integrierte Entwicklungsumgebung) mit vielen Features, die für die .NET-Entwicklung konzipiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-107">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="b1d2a-108">Zum Erstellen dieses Programms verwenden Sie nur wenige dieser Features.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-108">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="b1d2a-109">Weitere Informationen zu Visual Studio finden Sie unter [Erste Schritte mit Visual C#](/visualstudio/ide/quickstart-csharp-console).</span><span class="sxs-lookup"><span data-stu-id="b1d2a-109">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="b1d2a-110">Erstellen einer neuen Anwendung</span><span class="sxs-lookup"><span data-stu-id="b1d2a-110">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="b1d2a-111">Windows</span><span class="sxs-lookup"><span data-stu-id="b1d2a-111">Windows</span></span>](#tab/windows)

<span data-ttu-id="b1d2a-112">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-112">Start Visual Studio.</span></span> <span data-ttu-id="b1d2a-113">Unter Windows wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b1d2a-113">You'll see the following image on Windows:</span></span>

![Visual Studio-Willkommensbildschirm unter Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="b1d2a-115">Klicken Sie in der unteren rechten Ecke auf **Neues Projekt erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-115">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="b1d2a-116">Daraufhin zeigt Visual Studio das Dialogfeld **Neues Projekt** an:</span><span class="sxs-lookup"><span data-stu-id="b1d2a-116">Visual Studio displays the **New Project** dialog:</span></span>

![Anzeige „Neues Projekt“ in Visual Studio unter Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="b1d2a-118">Wenn Sie Visual Studio zum ersten Mal starten, ist die Liste **Zuletzt verwendete Projektvorlagen** leer.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-118">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="b1d2a-119">Wählen Sie „Konsolen-App (.NET Core)“ im Dialogfeld „Neues Projekt“ aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-119">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="b1d2a-120">Geben Sie Ihrem Projekt einen Namen, z. B. „HalloWelt“, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-120">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="b1d2a-121">Visual Studio öffnet Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-121">Visual Studio opens your project.</span></span> <span data-ttu-id="b1d2a-122">Dieses ist bereits ein grundlegendes „Hallo Welt“-</span><span class="sxs-lookup"><span data-stu-id="b1d2a-122">It's already a basic "Hello World!"</span></span> <span data-ttu-id="b1d2a-123">Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-123">example.</span></span> <span data-ttu-id="b1d2a-124">Drücken Sie `Ctrl` + `F5`, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-124">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="b1d2a-125">Visual Studio erstellt Ihr Projekt und konvertiert den Quellcode in eine ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-125">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="b1d2a-126">Dann wird ein Befehlsfenster gestartet, das Ihre neue Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-126">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="b1d2a-127">Der folgende Text sollte im Fenster angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="b1d2a-127">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="b1d2a-128">Drücken Sie eine beliebige Taste, um das Fenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-128">Press a key to close the window.</span></span>

# <a name="macos"></a>[<span data-ttu-id="b1d2a-129">macOS</span><span class="sxs-lookup"><span data-stu-id="b1d2a-129">macOS</span></span>](#tab/macos)

<span data-ttu-id="b1d2a-130">Starten Sie Visual Studio für Mac.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-130">Start Visual Studio for Mac.</span></span> <span data-ttu-id="b1d2a-131">Unter Mac wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b1d2a-131">You'll see the following image on Mac:</span></span>

![Visual Studio-Willkommensbildschirm unter Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="b1d2a-133">Wenn Sie Visual Studio für Mac zum ersten Mal starten, ist die Liste **Zuletzt geöffnete Projekte** leer.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-133">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="b1d2a-134">Klicken Sie oben rechts auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-134">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="b1d2a-135">Daraufhin zeigt Visual Studio für Mac das Dialogfeld **Neues Projekt** an:</span><span class="sxs-lookup"><span data-stu-id="b1d2a-135">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Anzeige „Neues Projekt“ in Visual Studio für Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="b1d2a-137">Wählen Sie im Dialogfeld „Neues Projekt“ die Option „.NET Core“ und dann „Konsolen-App“ aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-137">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="b1d2a-138">Daraufhin müssen Sie ein Zielframework auswählen.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-138">You'll need to select the target framework.</span></span> <span data-ttu-id="b1d2a-139">Hier können Sie die Standardeinstellung beibehalten, klicken Sie also auf „Weiter“.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-139">The default is fine, so press next.</span></span> <span data-ttu-id="b1d2a-140">Geben Sie Ihrem Projekt einen Namen, z. B. „HalloWelt“, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-140">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="b1d2a-141">Sie können den Standardprojektspeicherort verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-141">You can use the default project location.</span></span> <span data-ttu-id="b1d2a-142">Fügen Sie dieses Projekt nicht zur Quellcodeverwaltung hinzu.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-142">Don't add this project to source control.</span></span>

<span data-ttu-id="b1d2a-143">Visual Studio für Mac öffnet Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-143">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="b1d2a-144">Dieses ist bereits ein grundlegendes „Hallo Welt“-</span><span class="sxs-lookup"><span data-stu-id="b1d2a-144">It's already a basic "Hello World!"</span></span> <span data-ttu-id="b1d2a-145">Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-145">example.</span></span> <span data-ttu-id="b1d2a-146">Drücken Sie `Ctrl` + `Fn` + `F5`, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-146">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="b1d2a-147">Visual Studio für Mac erstellt Ihr Projekt und konvertiert den Quellcode in eine ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-147">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="b1d2a-148">Dann wird ein Befehlsfenster gestartet, das Ihre neue Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-148">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="b1d2a-149">Der folgende Text sollte im Fenster angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="b1d2a-149">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="b1d2a-150">Drücken Sie eine beliebige Taste, um die Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-150">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="b1d2a-151">Elemente eines C#-Programms</span><span class="sxs-lookup"><span data-stu-id="b1d2a-151">Elements of a C# program</span></span>

<span data-ttu-id="b1d2a-152">Im Folgenden werden die wichtigen Bestandteile dieses Programms untersucht.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-152">Let's examine the important parts of this program.</span></span> <span data-ttu-id="b1d2a-153">Die erste Zeile enthält einen Kommentar.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-153">The first line contains a comment.</span></span> <span data-ttu-id="b1d2a-154">Durch die Zeichen `//` wird die restliche Zeile in einen Kommentar konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-154">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="b1d2a-155">Sie können auch einen Kommentar aus einem Textblock einfügen, indem Sie ihn zwischen den Zeichen `/*` und `*/` einschließen.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-155">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="b1d2a-156">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-156">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="b1d2a-157">Eine C#-Konsolenanwendung muss eine `Main`-Methode enthalten, in der die Steuerung beginnt und endet.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-157">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="b1d2a-158">Innerhalb der `Main`-Methode erstellen Sie Objekte und führen andere Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-158">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="b1d2a-159">Bei der `Main`-Methode handelt es sich um eine [statische](../../language-reference/keywords/static.md) Methode, die sich innerhalb einer Klasse oder Struktur befindet.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-159">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="b1d2a-160">Im vorherigen „Hello World!“-Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1d2a-160">In the previous "Hello World!"</span></span> <span data-ttu-id="b1d2a-161">befindet sie sich in einer Klasse namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-161">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="b1d2a-162">Sie können die `Main`-Methode auf eine der folgenden Arten deklarieren:</span><span class="sxs-lookup"><span data-stu-id="b1d2a-162">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="b1d2a-163">Es kann `void` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-163">It can return `void`.</span></span> <span data-ttu-id="b1d2a-164">Das heißt, Ihr Programm gibt keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-164">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="b1d2a-165">Zudem kann eine ganze Zahl zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-165">It can also return an integer.</span></span> <span data-ttu-id="b1d2a-166">Der Integer stellt den **Exitcode** Ihrer Anwendung dar.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-166">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="b1d2a-167">Bei beiden Rückgabetypen können Argumente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-167">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="b1d2a-168">- oder -</span><span class="sxs-lookup"><span data-stu-id="b1d2a-168">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="b1d2a-169">Der Parameter der `Main`-Methode, `args`, ist ein `string`-Array, das die Befehlszeilenargumente enthält, die zum Aufrufen des Programms verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-169">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="b1d2a-170">Weitere Informationen zur Verwendung von Befehlszeilenargumenten finden Sie in den Beispielen unter [Main() und Befehlszeilenargumente](../main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="b1d2a-170">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="b1d2a-171">Eingabe und Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b1d2a-171">Input and output</span></span>

<span data-ttu-id="b1d2a-172">C#-Programme verwenden im Allgemeinen die Eingabe-/Ausgabedienste der Laufzeitbibliothek von .NET.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-172">C# programs generally use the input/output services provided by the run-time library of .NET.</span></span> <span data-ttu-id="b1d2a-173">Die Anweisung `System.Console.WriteLine("Hello World!");` verwendet die <xref:System.Console.WriteLine%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-173">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="b1d2a-174">Dies ist eine der Ausgabemethoden der <xref:System.Console>-Klasse in der Laufzeit-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-174">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="b1d2a-175">Bei dieser Methode wird der Zeichenfolgenparameter für den Standardausgabestream gefolgt von einer neuen Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-175">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="b1d2a-176">Für andere Eingabe-/Ausgabevorgänge sind andere <xref:System.Console>-Methoden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-176">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="b1d2a-177">Wenn Sie die `using System;`-Direktive am Anfang des Programms einfügen, können Sie die <xref:System>-Klassen und -Methoden direkt verwenden, ohne sie voll zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-177">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="b1d2a-178">Zum Beispiel können Sie `Console.WriteLine` statt `System.Console.WriteLine` aufrufen:</span><span class="sxs-lookup"><span data-stu-id="b1d2a-178">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="b1d2a-179">Weitere Informationen zu Eingabe-/Ausgabemethoden finden Sie unter <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="b1d2a-179">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1d2a-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1d2a-180">See also</span></span>

- [<span data-ttu-id="b1d2a-181">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b1d2a-181">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b1d2a-182">Beispiele und Tutorials</span><span class="sxs-lookup"><span data-stu-id="b1d2a-182">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="b1d2a-183">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="b1d2a-183">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="b1d2a-184">Erste Schritte mit Visual C#</span><span class="sxs-lookup"><span data-stu-id="b1d2a-184">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
