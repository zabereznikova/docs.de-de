---
title: Hello World – Ihr erstes Programm (C#-Programmierhandbuch)
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 904657175d87e0d78e518248ed89b3720227360f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="47978-102">Hello World – Ihr erstes Programm (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="47978-102">Hello World -- Your First Program (C# Programming Guide)</span></span>
<span data-ttu-id="47978-103">Die folgende Prozedur erstellt eine C#-Version des herkömmlichen „Hallo Welt!“</span><span class="sxs-lookup"><span data-stu-id="47978-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="47978-104">-Programms.</span><span class="sxs-lookup"><span data-stu-id="47978-104">program.</span></span> <span data-ttu-id="47978-105">Das Programm zeigt die Zeichenfolge `Hello World!` an.</span><span class="sxs-lookup"><span data-stu-id="47978-105">The program displays the string `Hello World!`</span></span>  
  
 <span data-ttu-id="47978-106">Weitere Beispiele zu einführenden Konzepten finden Sie unter [Erste Schritte mit Visual C# und Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="47978-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="47978-107">So erstellen Sie eine neue Konsolenanwendung und führen diese aus</span><span class="sxs-lookup"><span data-stu-id="47978-107">To create and run a console application</span></span>  
  
1.  <span data-ttu-id="47978-108">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="47978-108">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="47978-109">Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="47978-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="47978-110">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47978-110">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="47978-111">Erweitern Sie nacheinander **Installiert**, **Vorlagen**, **Visual C#**, und wählen Sie dann **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="47978-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4.  <span data-ttu-id="47978-112">Geben Sie im Feld **Name** einen Namen für das Projekt an, und klicken Sie dann auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="47978-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="47978-113">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47978-113">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="47978-114">Wenn „Program.cs“ im **Code-Editor** nicht geöffnet ist, öffnen Sie das Kontextmenü für **Program.cs** im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="47978-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="47978-115">Ersetzen Sie den Inhalt von Program.cs durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="47978-115">Replace the contents of Program.cs with the following code.</span></span>  
  
     [!code-csharp[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]  
  
7.  <span data-ttu-id="47978-116">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="47978-116">Choose the F5 key to run the project.</span></span> <span data-ttu-id="47978-117">Ein Eingabeaufforderungsfenster wird angezeigt, das die Zeile `Hello World!` enthält</span><span class="sxs-lookup"><span data-stu-id="47978-117">A Command Prompt window appears that contains the line `Hello World!`</span></span>  
  
 <span data-ttu-id="47978-118">Im nächsten Schritt werden die wichtigen Bereiche des Programms überprüft.</span><span class="sxs-lookup"><span data-stu-id="47978-118">Next, the important parts of this program are examined.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="47978-119">Kommentare</span><span class="sxs-lookup"><span data-stu-id="47978-119">Comments</span></span>  
 <span data-ttu-id="47978-120">Die erste Zeile enthält einen Kommentar.</span><span class="sxs-lookup"><span data-stu-id="47978-120">The first line contains a comment.</span></span> <span data-ttu-id="47978-121">Durch die Zeichen `//` wird die restliche Zeile in einen Kommentar konvertiert.</span><span class="sxs-lookup"><span data-stu-id="47978-121">The characters `//` convert the rest of the line to a comment.</span></span>  
  
 [!code-csharp[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]  
  
 <span data-ttu-id="47978-122">Sie können auch einen Kommentar aus einem Textblock einfügen, indem Sie ihn zwischen den Zeichen `/*` und `*/` einschließen.</span><span class="sxs-lookup"><span data-stu-id="47978-122">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="47978-123">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="47978-123">This is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]  
  
## <a name="main-method"></a><span data-ttu-id="47978-124">Die 'Main'-Methode</span><span class="sxs-lookup"><span data-stu-id="47978-124">Main Method</span></span>  
 <span data-ttu-id="47978-125">Eine C#-Konsolenanwendung muss eine `Main`-Methode enthalten, in der die Steuerung beginnt und endet.</span><span class="sxs-lookup"><span data-stu-id="47978-125">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="47978-126">Innerhalb der `Main`-Methode erstellen Sie Objekte und führen andere Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="47978-126">The `Main` method is where you create objects and execute other methods.</span></span>  
  
 <span data-ttu-id="47978-127">Bei der `Main`-Methode handelt es sich um eine [statische](../../../csharp/language-reference/keywords/static.md) Methode, die sich innerhalb einer Klasse oder Struktur befindet.</span><span class="sxs-lookup"><span data-stu-id="47978-127">The `Main` method is a [static](../../../csharp/language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="47978-128">Im vorherigen „Hello World!“-Beispiel</span><span class="sxs-lookup"><span data-stu-id="47978-128">In the previous "Hello World!"</span></span> <span data-ttu-id="47978-129">befindet sie sich in einer Klasse namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="47978-129">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="47978-130">Sie können die `Main`-Methode auf eine der folgenden Arten deklarieren:</span><span class="sxs-lookup"><span data-stu-id="47978-130">You can declare the `Main` method in one of the following ways:</span></span>  
  
-   <span data-ttu-id="47978-131">Es kann `void` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="47978-131">It can return `void`.</span></span>  
  
     [!code-csharp[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]  
  
-   <span data-ttu-id="47978-132">Zudem kann eine ganze Zahl zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="47978-132">It can also return an integer.</span></span>  
  
     [!code-csharp[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]  
  
-   <span data-ttu-id="47978-133">Bei beiden Rückgabetypen können Argumente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47978-133">With either of the return types, it can take arguments.</span></span>  
  
     [!code-csharp[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]  
  
     <span data-ttu-id="47978-134">- oder - </span><span class="sxs-lookup"><span data-stu-id="47978-134">-or-</span></span>  
  
     [!code-csharp[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]  
  
 <span data-ttu-id="47978-135">Der Parameter der `Main`-Methode, `args`, ist ein `string`-Array, das die Befehlszeilenargumente enthält, die zum Aufrufen des Programms verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47978-135">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="47978-136">Im Gegensatz zu C++ enthält dieses Array nicht den Namen der ausführbaren Datei (EXE).</span><span class="sxs-lookup"><span data-stu-id="47978-136">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>  
  
 <span data-ttu-id="47978-137">Weitere Informationen zur Verwendung von Befehlszeilenargumenten finden Sie unter [Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md) und [Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span><span class="sxs-lookup"><span data-stu-id="47978-137">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span></span>  
  
 <span data-ttu-id="47978-138">Der Aufruf von <xref:System.Console.ReadKey%2A> am Ende der `Main`-Methode verhindert, dass das Konsolenfenster geschlossen wird, bevor Sie die Ausgabe lesen können, wenn Sie das Programm durch Drücken von F5 im Debugmodus ausführen.</span><span class="sxs-lookup"><span data-stu-id="47978-138">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>  
  
## <a name="input-and-output"></a><span data-ttu-id="47978-139">Eingabe und Ausgabe</span><span class="sxs-lookup"><span data-stu-id="47978-139">Input and Output</span></span>  
 <span data-ttu-id="47978-140">C#-Programme verwenden im Allgemeinen die Eingabe-/Ausgabedienste der Laufzeitbibliothek von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47978-140">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="47978-141">Die Anweisung `System.Console.WriteLine("Hello World!");` verwendet die <xref:System.Console.WriteLine%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="47978-141">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="47978-142">Dies ist eine der Ausgabemethoden der <xref:System.Console>-Klasse in der Laufzeit-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="47978-142">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="47978-143">Bei dieser Methode wird der Zeichenfolgenparameter für den Standardausgabestream gefolgt von einer neuen Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47978-143">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="47978-144">Für andere Eingabe-/Ausgabevorgänge sind andere <xref:System.Console>-Methoden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="47978-144">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="47978-145">Wenn Sie die `using System;`-Direktive am Anfang des Programms einfügen, können Sie die <xref:System>-Klassen und -Methoden direkt verwenden, ohne sie voll zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="47978-145">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="47978-146">Zum Beispiel können Sie `Console.WriteLine` statt `System.Console.WriteLine` aufrufen:</span><span class="sxs-lookup"><span data-stu-id="47978-146">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]  
  
 [!code-csharp[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]  
  
 <span data-ttu-id="47978-147">Weitere Informationen zu Eingabe-/Ausgabemethoden finden Sie unter <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="47978-147">For more information about input/output methods, see <xref:System.IO>.</span></span>  
  
## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="47978-148">Befehlszeilenkompilierung und -ausführung</span><span class="sxs-lookup"><span data-stu-id="47978-148">Command-Line Compilation and Execution</span></span>  
 <span data-ttu-id="47978-149">Sie können das „Hallo Welt“</span><span class="sxs-lookup"><span data-stu-id="47978-149">You can compile the "Hello World!"</span></span> <span data-ttu-id="47978-150">-Programm über die Befehlszeile statt mit der integrierten Entwicklungsumgebung (IDE) von Visual Studio kompilieren.</span><span class="sxs-lookup"><span data-stu-id="47978-150">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>  
  
#### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="47978-151">So funktionieren Kompilierungsvorgänge und Ausführungen von einer Eingabeaufforderung aus</span><span class="sxs-lookup"><span data-stu-id="47978-151">To compile and run from a command prompt</span></span>  
  
1.  <span data-ttu-id="47978-152">Fügen Sie den Code aus der vorherigen Prozedur in einem beliebigen Text-Editor ein, und speichern Sie die Datei als Textdatei.</span><span class="sxs-lookup"><span data-stu-id="47978-152">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="47978-153">Nennen Sie die Datei `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="47978-153">Name the file `Hello.cs`.</span></span> <span data-ttu-id="47978-154">C#-Quellcodedateien weisen die Erweiterung `.cs` auf.</span><span class="sxs-lookup"><span data-stu-id="47978-154">C# source code files use the extension `.cs`.</span></span>  
  
2.  <span data-ttu-id="47978-155">Führen Sie einen der folgenden Schritte aus, um ein Eingabeaufforderungsfenster zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="47978-155">Perform one of the following steps to open a command-prompt window:</span></span>  
  
    -   <span data-ttu-id="47978-156">Suchen Sie in Windows 10 auf dem **Startbildmenü** nach `Developer Command Prompt`, und wählen Sie dann **Developer-Eingabeaufforderung für VS2017** aus.</span><span class="sxs-lookup"><span data-stu-id="47978-156">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="47978-157">Ein Entwickler-Eingabeaufforderungsfenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47978-157">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="47978-158">Öffnen Sie in Windows 7 das **Startmenü**, erweitern Sie den Ordner der aktuellen Version von Visual Studio, öffnen Sie das Kontextmenü für **Visual Studio-Tools**, und wählen Sie dann **Developer-Eingabeaufforderung für VS2017** aus.</span><span class="sxs-lookup"><span data-stu-id="47978-158">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="47978-159">Ein Entwickler-Eingabeaufforderungsfenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47978-159">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="47978-160">Aktivieren Sie Befehlszeilenbuilds von einem Standardeingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="47978-160">Enable command-line builds from a standard Command Prompt window.</span></span>  
  
         <span data-ttu-id="47978-161">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="47978-161">See [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>  
  
3.  <span data-ttu-id="47978-162">Navigieren Sie im Eingabeaufforderungsfenster zu dem Ordner, der die Datei `Hello.cs` enthält.</span><span class="sxs-lookup"><span data-stu-id="47978-162">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>  
  
4.  <span data-ttu-id="47978-163">Geben Sie zum Kompilieren von `Hello.cs` den folgenden Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="47978-163">Enter the following command to compile `Hello.cs`.</span></span>  
  
     `csc Hello.cs`  
  
     <span data-ttu-id="47978-164">Wenn das Programm keine Kompilierungsfehler aufweist, wird eine ausführbare Datei mit dem Namen `Hello.exe` erstellt.</span><span class="sxs-lookup"><span data-stu-id="47978-164">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>  
  
5.  <span data-ttu-id="47978-165">Geben Sie den folgenden Befehl im Eingabeaufforderungsfenster ein, um das Programm auszuführen:</span><span class="sxs-lookup"><span data-stu-id="47978-165">In the command-prompt window, enter the following command to run the program:</span></span>  
  
     `Hello`  
  
 <span data-ttu-id="47978-166">Weitere Informationen über den C#-Compiler und seine Optionen finden Sie unter [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md).</span><span class="sxs-lookup"><span data-stu-id="47978-166">For more information about the C# compiler and its options, see [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47978-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47978-167">See Also</span></span>  
 [<span data-ttu-id="47978-168">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="47978-168">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="47978-169">Einblicke in ein C#-Programm</span><span class="sxs-lookup"><span data-stu-id="47978-169">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
 [<span data-ttu-id="47978-170">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="47978-170">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="47978-171">\<paveover>Beispielanwendungen für C#</span><span class="sxs-lookup"><span data-stu-id="47978-171">\<paveover>C# Sample Applications</span></span>](http://msdn.microsoft.com/library/9a9d7aaa-51d3-4224-b564-95409b0f3e15)  
 [<span data-ttu-id="47978-172">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="47978-172">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="47978-173">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="47978-173">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [<span data-ttu-id="47978-174">Erste Schritte mit Visual C# und Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47978-174">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
