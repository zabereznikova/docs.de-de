---
title: "Hello World – Ihr erstes Programm (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: get-started-article
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
dev_langs:
- CSharp
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: b7cb84362c96dac50ae5136334138b55ed1ce00b
ms.openlocfilehash: 03891f83885cf41ab157ebd78ef7e72767b4b163
ms.contentlocale: de-de
ms.lasthandoff: 07/31/2017

---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="fecb7-102">Hello World – Ihr erstes Programm (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fecb7-102">Hello World -- Your First Program (C# Programming Guide)</span></span>
<span data-ttu-id="fecb7-103">Die folgende Prozedur erstellt eine C#-Version des herkömmlichen „Hallo Welt!“</span><span class="sxs-lookup"><span data-stu-id="fecb7-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="fecb7-104">-Programms.</span><span class="sxs-lookup"><span data-stu-id="fecb7-104">program.</span></span> <span data-ttu-id="fecb7-105">Das Programm zeigt die Zeichenfolge `Hello World!` an.</span><span class="sxs-lookup"><span data-stu-id="fecb7-105">The program displays the string `Hello World!`</span></span>  
  
 <span data-ttu-id="fecb7-106">Weitere Beispiele zu einführenden Konzepten finden Sie unter [Erste Schritte mit Visual C# und Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fecb7-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="fecb7-107">So erstellen Sie eine neue Konsolenanwendung und führen diese aus</span><span class="sxs-lookup"><span data-stu-id="fecb7-107">To create and run a console application</span></span>  
  
1.  <span data-ttu-id="fecb7-108">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fecb7-108">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="fecb7-109">Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="fecb7-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="fecb7-110">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fecb7-110">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="fecb7-111">Erweitern Sie nacheinander **Installiert**, **Vorlagen**, **Visual C#**, und wählen Sie dann **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="fecb7-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4.  <span data-ttu-id="fecb7-112">Geben Sie im Feld **Name** einen Namen für das Projekt an, und klicken Sie dann auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="fecb7-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="fecb7-113">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fecb7-113">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="fecb7-114">Wenn „Program.cs“ im **Code-Editor** nicht geöffnet ist, öffnen Sie das Kontextmenü für **Program.cs** im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="fecb7-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="fecb7-115">Ersetzen Sie den Inhalt von Program.cs durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="fecb7-115">Replace the contents of Program.cs with the following code.</span></span>  
  
     <span data-ttu-id="fecb7-116">[!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fecb7-116">[!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]</span></span>  
  
7.  <span data-ttu-id="fecb7-117">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fecb7-117">Choose the F5 key to run the project.</span></span> <span data-ttu-id="fecb7-118">Ein Eingabeaufforderungsfenster wird angezeigt, das die Zeile `Hello World!` enthält</span><span class="sxs-lookup"><span data-stu-id="fecb7-118">A Command Prompt window appears that contains the line `Hello World!`</span></span>  
  
 <span data-ttu-id="fecb7-119">Im nächsten Schritt werden die wichtigen Bereiche des Programms überprüft.</span><span class="sxs-lookup"><span data-stu-id="fecb7-119">Next, the important parts of this program are examined.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="fecb7-120">Kommentare</span><span class="sxs-lookup"><span data-stu-id="fecb7-120">Comments</span></span>  
 <span data-ttu-id="fecb7-121">Die erste Zeile enthält einen Kommentar.</span><span class="sxs-lookup"><span data-stu-id="fecb7-121">The first line contains a comment.</span></span> <span data-ttu-id="fecb7-122">Durch die Zeichen `//` wird die restliche Zeile in einen Kommentar konvertiert.</span><span class="sxs-lookup"><span data-stu-id="fecb7-122">The characters `//` convert the rest of the line to a comment.</span></span>  
  
 <span data-ttu-id="fecb7-123">[!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fecb7-123">[!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]</span></span>  
  
 <span data-ttu-id="fecb7-124">Sie können auch einen Kommentar aus einem Textblock einfügen, indem Sie ihn zwischen den Zeichen `/*` und `*/` einschließen.</span><span class="sxs-lookup"><span data-stu-id="fecb7-124">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="fecb7-125">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fecb7-125">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="fecb7-126">[!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fecb7-126">[!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]</span></span>  
  
## <a name="main-method"></a><span data-ttu-id="fecb7-127">Die 'Main'-Methode</span><span class="sxs-lookup"><span data-stu-id="fecb7-127">Main Method</span></span>  
 <span data-ttu-id="fecb7-128">Eine C#-Konsolenanwendung muss eine `Main`-Methode enthalten, in der die Steuerung beginnt und endet.</span><span class="sxs-lookup"><span data-stu-id="fecb7-128">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="fecb7-129">Innerhalb der `Main`-Methode erstellen Sie Objekte und führen andere Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="fecb7-129">The `Main` method is where you create objects and execute other methods.</span></span>  
  
 <span data-ttu-id="fecb7-130">Bei der `Main`-Methode handelt es sich um eine [statische](../../../csharp/language-reference/keywords/static.md) Methode, die sich innerhalb einer Klasse oder Struktur befindet.</span><span class="sxs-lookup"><span data-stu-id="fecb7-130">The `Main` method is a [static](../../../csharp/language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="fecb7-131">Im vorherigen „Hello World!“-Beispiel</span><span class="sxs-lookup"><span data-stu-id="fecb7-131">In the previous "Hello World!"</span></span> <span data-ttu-id="fecb7-132">befindet sie sich in einer Klasse namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="fecb7-132">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="fecb7-133">Sie können die `Main`-Methode auf eine der folgenden Arten deklarieren:</span><span class="sxs-lookup"><span data-stu-id="fecb7-133">You can declare the `Main` method in one of the following ways:</span></span>  
  
-   <span data-ttu-id="fecb7-134">Es kann `void` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fecb7-134">It can return `void`.</span></span>  
  
     <span data-ttu-id="fecb7-135">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="fecb7-135">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]</span></span>  
  
-   <span data-ttu-id="fecb7-136">Zudem kann eine ganze Zahl zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fecb7-136">It can also return an integer.</span></span>  
  
     <span data-ttu-id="fecb7-137">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="fecb7-137">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]</span></span>  
  
-   <span data-ttu-id="fecb7-138">Bei beiden Rückgabetypen können Argumente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fecb7-138">With either of the return types, it can take arguments.</span></span>  
  
     <span data-ttu-id="fecb7-139">[!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="fecb7-139">[!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]</span></span>  
  
     <span data-ttu-id="fecb7-140">- oder - </span><span class="sxs-lookup"><span data-stu-id="fecb7-140">-or-</span></span>  
  
     <span data-ttu-id="fecb7-141">[!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="fecb7-141">[!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]</span></span>  
  
 <span data-ttu-id="fecb7-142">Der Parameter der `Main`-Methode, `args`, ist ein `string`-Array, das die Befehlszeilenargumente enthält, die zum Aufrufen des Programms verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fecb7-142">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="fecb7-143">Im Gegensatz zu C++ enthält dieses Array nicht den Namen der ausführbaren Datei (EXE).</span><span class="sxs-lookup"><span data-stu-id="fecb7-143">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>  
  
 <span data-ttu-id="fecb7-144">Weitere Informationen zur Verwendung von Befehlszeilenargumenten finden Sie unter [Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md) und [Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span><span class="sxs-lookup"><span data-stu-id="fecb7-144">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span></span>  
  
 <span data-ttu-id="fecb7-145">Der Aufruf von <xref:System.Console.ReadKey%2A> am Ende der `Main`-Methode verhindert, dass das Konsolenfenster geschlossen wird, bevor Sie die Ausgabe lesen können, wenn Sie das Programm durch Drücken von F5 im Debugmodus ausführen.</span><span class="sxs-lookup"><span data-stu-id="fecb7-145">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>  
  
## <a name="input-and-output"></a><span data-ttu-id="fecb7-146">Eingabe und Ausgabe</span><span class="sxs-lookup"><span data-stu-id="fecb7-146">Input and Output</span></span>  
 <span data-ttu-id="fecb7-147">C#-Programme verwenden im Allgemeinen die Eingabe-/Ausgabedienste der Laufzeitbibliothek von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fecb7-147">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="fecb7-148">Die Anweisung `System.Console.WriteLine("Hello World!");` verwendet die <xref:System.Console.WriteLine%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="fecb7-148">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="fecb7-149">Dies ist eine der Ausgabemethoden der <xref:System.Console>-Klasse in der Laufzeit-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="fecb7-149">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="fecb7-150">Bei dieser Methode wird der Zeichenfolgenparameter für den Standardausgabestream gefolgt von einer neuen Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fecb7-150">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="fecb7-151">Für andere Eingabe-/Ausgabevorgänge sind andere <xref:System.Console>-Methoden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fecb7-151">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="fecb7-152">Wenn Sie die `using System;`-Direktive am Anfang des Programms einfügen, können Sie die <xref:System>-Klassen und -Methoden direkt verwenden, ohne sie voll zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="fecb7-152">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="fecb7-153">Zum Beispiel können Sie `Console.WriteLine` statt `System.Console.WriteLine` aufrufen:</span><span class="sxs-lookup"><span data-stu-id="fecb7-153">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>  
  
 <span data-ttu-id="fecb7-154">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="fecb7-154">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]</span></span>  
  
 <span data-ttu-id="fecb7-155">[!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="fecb7-155">[!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]</span></span>  
  
 <span data-ttu-id="fecb7-156">Weitere Informationen zu Eingabe-/Ausgabemethoden finden Sie unter <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="fecb7-156">For more information about input/output methods, see <xref:System.IO>.</span></span>  
  
## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="fecb7-157">Befehlszeilenkompilierung und -ausführung</span><span class="sxs-lookup"><span data-stu-id="fecb7-157">Command-Line Compilation and Execution</span></span>  
 <span data-ttu-id="fecb7-158">Sie können das „Hallo Welt“</span><span class="sxs-lookup"><span data-stu-id="fecb7-158">You can compile the "Hello World!"</span></span> <span data-ttu-id="fecb7-159">-Programm über die Befehlszeile statt mit der integrierten Entwicklungsumgebung (IDE) von Visual Studio kompilieren.</span><span class="sxs-lookup"><span data-stu-id="fecb7-159">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>  
  
#### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="fecb7-160">So funktionieren Kompilierungsvorgänge und Ausführungen von einer Eingabeaufforderung aus</span><span class="sxs-lookup"><span data-stu-id="fecb7-160">To compile and run from a command prompt</span></span>  
  
1.  <span data-ttu-id="fecb7-161">Fügen Sie den Code aus der vorherigen Prozedur in einem beliebigen Text-Editor ein, und speichern Sie die Datei als Textdatei.</span><span class="sxs-lookup"><span data-stu-id="fecb7-161">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="fecb7-162">Nennen Sie die Datei `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="fecb7-162">Name the file `Hello.cs`.</span></span> <span data-ttu-id="fecb7-163">C#-Quellcodedateien weisen die Erweiterung `.cs` auf.</span><span class="sxs-lookup"><span data-stu-id="fecb7-163">C# source code files use the extension `.cs`.</span></span>  
  
2.  <span data-ttu-id="fecb7-164">Führen Sie einen der folgenden Schritte aus, um ein Eingabeaufforderungsfenster zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="fecb7-164">Perform one of the following steps to open a command-prompt window:</span></span>  
  
    -   <span data-ttu-id="fecb7-165">Suchen Sie in Windows 10 auf dem **Startbildmenü** nach `Developer Command Prompt`, und wählen Sie dann **Developer-Eingabeaufforderung für VS2017** aus.</span><span class="sxs-lookup"><span data-stu-id="fecb7-165">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="fecb7-166">Ein Entwickler-Eingabeaufforderungsfenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fecb7-166">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="fecb7-167">Öffnen Sie in Windows 7 das **Startmenü**, erweitern Sie den Ordner der aktuellen Version von Visual Studio, öffnen Sie das Kontextmenü für **Visual Studio-Tools**, und wählen Sie dann **Developer-Eingabeaufforderung für VS2017** aus.</span><span class="sxs-lookup"><span data-stu-id="fecb7-167">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="fecb7-168">Ein Entwickler-Eingabeaufforderungsfenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fecb7-168">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="fecb7-169">Aktivieren Sie Befehlszeilenbuilds von einem Standardeingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="fecb7-169">Enable command-line builds from a standard Command Prompt window.</span></span>  
  
         <span data-ttu-id="fecb7-170">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="fecb7-170">See [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>  
  
3.  <span data-ttu-id="fecb7-171">Navigieren Sie im Eingabeaufforderungsfenster zu dem Ordner, der die Datei `Hello.cs` enthält.</span><span class="sxs-lookup"><span data-stu-id="fecb7-171">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>  
  
4.  <span data-ttu-id="fecb7-172">Geben Sie zum Kompilieren von `Hello.cs` den folgenden Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="fecb7-172">Enter the following command to compile `Hello.cs`.</span></span>  
  
     `csc Hello.cs`  
  
     <span data-ttu-id="fecb7-173">Wenn das Programm keine Kompilierungsfehler aufweist, wird eine ausführbare Datei mit dem Namen `Hello.exe` erstellt.</span><span class="sxs-lookup"><span data-stu-id="fecb7-173">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>  
  
5.  <span data-ttu-id="fecb7-174">Geben Sie den folgenden Befehl im Eingabeaufforderungsfenster ein, um das Programm auszuführen:</span><span class="sxs-lookup"><span data-stu-id="fecb7-174">In the command-prompt window, enter the following command to run the program:</span></span>  
  
     `Hello`  
  
 <span data-ttu-id="fecb7-175">Weitere Informationen über den C#-Compiler und seine Optionen finden Sie unter [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md).</span><span class="sxs-lookup"><span data-stu-id="fecb7-175">For more information about the C# compiler and its options, see [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fecb7-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fecb7-176">See Also</span></span>  
 <span data-ttu-id="fecb7-177">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fecb7-177">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fecb7-178">[Einblicke in ein C#-Programm](../../../csharp/programming-guide/inside-a-program/index.md) </span><span class="sxs-lookup"><span data-stu-id="fecb7-178">[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md) </span></span>  
 <span data-ttu-id="fecb7-179">[Zeichenfolgen](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="fecb7-179">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="fecb7-180">[\<paveover>Beispielanwendungen für C#](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15) </span><span class="sxs-lookup"><span data-stu-id="fecb7-180">[\<paveover>C# Sample Applications](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15) </span></span>  
 <span data-ttu-id="fecb7-181">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fecb7-181">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fecb7-182">[Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="fecb7-182">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 [<span data-ttu-id="fecb7-183">Erste Schritte mit Visual C# und Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fecb7-183">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)

