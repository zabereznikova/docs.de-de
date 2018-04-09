---
title: Erstellen einer „Hallo Welt“-Anwendung mit .NET Core und Visual Basic in Visual Studio 2017
description: Erfahren Sie, wie Sie mithilfe von Visual Studio 2017 eine einfache .NET Core-Konsolenanwendung in Visual Basic erstellen.
keywords: .NET Core, .NET Core-Konsolenanwendung, Visual Studio 2017
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-vb
dev_langs:
- vb
ms.workload:
- dotnetcore
ms.openlocfilehash: c3775fccf8d6e7c544cbd0b05df7043752e8bef9
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="build-a-visual-basic-hello-world-application-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="5e209-104">Erstellen einer „Hallo Welt“-Anwendung in Visual Basic mit .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5e209-104">Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="5e209-105">Dieses Thema ist eine grundlegende Einführung in das Erstellen, Debuggen und Veröffentlichen einer einfachen .NET Core-Konsolenanwendung in Visual Basic mithilfe von Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="5e209-105">This topic provides a step-by-step introduction to building, debugging, and publishing a simple .NET Core console application using Visual Basic in Visual Studio 2017.</span></span> <span data-ttu-id="5e209-106">Visual Studio 2017 bietet eine Entwicklungsumgebung mit vollem Funktionsumfang für die Erstellung von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="5e209-106">Visual Studio 2017 provides a full-featured development environment for building .NET Core applications.</span></span> <span data-ttu-id="5e209-107">Sofern die Anwendung keine plattformspezifischen Abhängigkeiten aufweist, kann sie auf jeder von .NET Core unterstützten Plattform und in jedem System mit installiertem .NET Core ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5e209-107">As long as the application doesn't have platform-specific dependencies, the application can run on any platform that .NET Core targets and on any system that has .NET Core installed.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e209-108">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="5e209-108">Prerequisites</span></span>

<span data-ttu-id="5e209-109">[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) mit installierter Arbeitsauslastung für die „plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="5e209-109">[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) with the ".NET Core cross-platform development" workload installed.</span></span> <span data-ttu-id="5e209-110">Sie können Ihre App mit .NET Core 2.0 entwickeln.</span><span class="sxs-lookup"><span data-stu-id="5e209-110">You can develop your app with .NET Core 2.0.</span></span>

<span data-ttu-id="5e209-111">Weitere Informationen finden Sie unter [Prerequisites for .NET Core on Mac (Erforderliche Komponenten für .NET Core unter Mac)](../../core/windows-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="5e209-111">For more information, see [Prerequisites for .NET Core on Windows](../../core/windows-prerequisites.md).</span></span>

## <a name="a-simple-hello-world-application"></a><span data-ttu-id="5e209-112">Eine einfache „Hello World“-Anwendung</span><span class="sxs-lookup"><span data-stu-id="5e209-112">A simple Hello World application</span></span>

<span data-ttu-id="5e209-113">Beginnen Sie, indem Sie eine einfache „Hello World“-Konsolenanwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="5e209-113">Begin by creating a simple "Hello World" console application.</span></span> <span data-ttu-id="5e209-114">Führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5e209-114">Follow these steps:</span></span>

1. <span data-ttu-id="5e209-115">Starten Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="5e209-115">Launch Visual Studio 2017.</span></span> <span data-ttu-id="5e209-116">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="5e209-116">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="5e209-117">Klicken Sie im Dialogfeld *Neues Projekt*\* auf den Knoten **Visual Basic** und anschließend auf den Knoten **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="5e209-117">In the *New Project*\* dialog, select the **Visual Basic** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="5e209-118">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="5e209-118">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="5e209-119">Geben Sie im Textfeld **Name** „HelloWorld“ ein.</span><span class="sxs-lookup"><span data-stu-id="5e209-119">In the **Name** text box, type "HelloWorld".</span></span> <span data-ttu-id="5e209-120">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e209-120">Select the **OK** button.</span></span>

   ![Dialogfeld „Neues Projekt“, in dem die Konsolen-App ausgewählt ist](./media/vb-with-visual-studio/new-project.png)
   
1. <span data-ttu-id="5e209-122">Visual Studio verwendet die Vorlage, um Ihr Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5e209-122">Visual Studio uses the template to create your project.</span></span> <span data-ttu-id="5e209-123">Die Visual Basic-Konsolenanwendungsvorlage für .NET Core definiert automatisch die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String> Array als Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="5e209-123">The Visual Basic Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="5e209-124">`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="5e209-124">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="5e209-125">Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5e209-125">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio und das neue HelloWorld-Projekt](./media/vb-with-visual-studio/devenv.png)

   <span data-ttu-id="5e209-127">Die Vorlage erstellt eine einfache „Hello World“-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5e209-127">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="5e209-128">Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um die literale Zeichenfolge „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="5e209-128">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="5e209-129">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5e209-129">in the console window.</span></span> <span data-ttu-id="5e209-130">Indem Sie auf der Symbolleiste die **HelloWorld**-Schaltfläche mit dem grünen Pfeil auswählen, können Sie das Programm im Debugmodus ausführen.</span><span class="sxs-lookup"><span data-stu-id="5e209-130">By selecting the **HelloWorld** button with the green arrow on the toolbar, you can run the program in Debug mode.</span></span> <span data-ttu-id="5e209-131">In diesem Fall ist das Konsolenfenster nur sehr kurz zu sehen und wird wieder geschlossen.</span><span class="sxs-lookup"><span data-stu-id="5e209-131">If you do, the console window is visible for only a brief time interval before it closes.</span></span> <span data-ttu-id="5e209-132">Dies liegt daran, dass die Methode `Main` beendet wird und die Anwendung endet, sobald die einzige Anweisung in der `Main`-Methode ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5e209-132">This occurs because the `Main` method terminates and the application ends as soon as the single statement in the `Main` method executes.</span></span>

1. <span data-ttu-id="5e209-133">Damit die Anwendung anhält, bevor sie das Konsolenfenster schließt, fügen Sie den folgenden Code sofort nach dem Aufruf der <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="5e209-133">To cause the application to pause before it closes the console window, add the following code immediately after the call to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method:</span></span>

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   <span data-ttu-id="5e209-134">Dieser Code fordert den Benutzer auf, eine beliebige Taste zu drücken, und hält das Programm an, bis eine Taste gedrückt wurde.</span><span class="sxs-lookup"><span data-stu-id="5e209-134">This code prompts the user to press any key and then pauses the program until a key is pressed.</span></span>

1. <span data-ttu-id="5e209-135">Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="5e209-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="5e209-136">Dies kompiliert Ihr Programm in eine Zwischensprache (IL), die dann von einem JIT-Compiler (Just in Time) in Binärcode konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="5e209-136">This compiles your program into an intermediate language (IL) that's converted into binary code by a just-in-time (JIT) compiler.</span></span>

1. <span data-ttu-id="5e209-137">Führen Sie das Programm aus, indem Sie auf der Symbolleiste die **HelloWorld**-Schaltfläche mit dem grünen Pfeil auswählen.</span><span class="sxs-lookup"><span data-stu-id="5e209-137">Run the program by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span>

   ![Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt](./media/with-visual-studio/helloworld1.png)

1. <span data-ttu-id="5e209-139">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5e209-139">Press any key to close the console window.</span></span>

## <a name="enhancing-the-hello-world-application"></a><span data-ttu-id="5e209-140">Erweitern der Hello World-Anwendung</span><span class="sxs-lookup"><span data-stu-id="5e209-140">Enhancing the Hello World application</span></span>

<span data-ttu-id="5e209-141">Erweitern Sie Ihre Anwendung, um die Benutzer aufzufordern, seinen oder ihren Namen einzugeben und diesen mit dem Datum und der Uhrzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5e209-141">Enhance your application to prompt the user for his or her name and to display it along with the date and time.</span></span> <span data-ttu-id="5e209-142">Um das Programm zu ändern und zu testen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="5e209-142">To modify and test the program, do the following:</span></span>

1. <span data-ttu-id="5e209-143">Geben Sie im Codefenster unmittelbar nach der öffnenden geschweiften Klammer, die auf die Zeile `Sub Main(args As String())` folgt, und vor der ersten schließenden geschweiften Klammer den folgenden Visual Basic-Code ein:</span><span class="sxs-lookup"><span data-stu-id="5e209-143">Enter the following Visual Basic code in the code window immediately after the opening bracket that follows the `Sub Main(args As String())` line and before the first closing bracket:</span></span>

   [!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="5e209-144">Dieser Code ersetzt die bestehenden Anweisungen <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, <xref:System.Console.Write%2A?displayProperty=nameWithType> und <xref:System.Console.ReadKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5e209-144">This code replaces the existing <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, <xref:System.Console.Write%2A?displayProperty=nameWithType>, and <xref:System.Console.ReadKey%2A?displayProperty=nameWithType> statements.</span></span>

   ![Visual Studio-Programmdatei mit aktualisierter Main-Methode](./media/vb-with-visual-studio/codewindow.png)

   <span data-ttu-id="5e209-146">Dieser Code zeigt „What is your name?“</span><span class="sxs-lookup"><span data-stu-id="5e209-146">This code displays "What is your name?"</span></span> <span data-ttu-id="5e209-147">im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat.</span><span class="sxs-lookup"><span data-stu-id="5e209-147">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="5e209-148">Der Code speichert diese Zeichenfolge in einer Variablen namens `name`.</span><span class="sxs-lookup"><span data-stu-id="5e209-148">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="5e209-149">Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `currentDate` zu.</span><span class="sxs-lookup"><span data-stu-id="5e209-149">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `currentDate`.</span></span> <span data-ttu-id="5e209-150">Schließlich verwendet der Code eine [interpolierte Zeichenfolge](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), um diese Werte im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5e209-150">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="5e209-151">Kompilieren Sie das Programm durch Auswählen von **Erstellen** > **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5e209-151">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="5e209-152">Führen Sie das Programm in Visual Studio im Debugmodus aus, indem Sie den grünen Pfeil auf der Symbolleiste auswählen, F5 drücken oder das Menüelement **Debuggen** > **Debuggen starten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="5e209-152">Run the program in Debug mode in Visual Studio by selecting the green arrow on the toolbar, pressing F5, or choosing the **Debug** > **Start Debugging** menu item.</span></span> <span data-ttu-id="5e209-153">Reagieren Sie auf die Aufforderung, indem Sie einen Namen eingeben und die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="5e209-153">Respond to the prompt by entering a name and pressing the Enter key.</span></span>

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/helloworld2.png)

1. <span data-ttu-id="5e209-155">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5e209-155">Press any key to close the console window.</span></span>

<span data-ttu-id="5e209-156">Sie haben Ihre Anwendung erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5e209-156">You've created and run your application.</span></span> <span data-ttu-id="5e209-157">Wenn Sie professionelle Anwendungen erstellen möchten, führen Sie einige weitere Schritte aus, um Ihre Anwendung für die Veröffentlichung bereit zu machen:</span><span class="sxs-lookup"><span data-stu-id="5e209-157">To develop a professional application, take some additional steps to make your application ready for release:</span></span>

- <span data-ttu-id="5e209-158">Informationen zum Debuggen Ihrer Anwendung finden Sie unter [Debuggen Ihrer C#-Anwendung „Hello World“ mit Visual Studio 2017](debugging-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="5e209-158">For information on debugging your application, see [Debugging your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md).</span></span>

- <span data-ttu-id="5e209-159">Informationen zum Entwickeln und Veröffentlichen einer bereitstellbaren Version Ihrer Anwendung finden Sie unter [Publishing your C# Hello World application with Visual Studio 2017 (Veröffentlichen Ihrer „Hallo Welt“-Anwendung in C# mit Visual Studio 2017)](publishing-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="5e209-159">For information on developing and publishing a distributable version of your application, see [Publishing your C# Hello World application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

<!--
## Related topics

Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017. For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).

You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor. For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md). -->
