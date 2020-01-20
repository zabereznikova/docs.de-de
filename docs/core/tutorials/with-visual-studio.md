---
title: Erstellen einer Hello World-Anwendung mit .NET Core in Visual Studio
description: Erfahren Sie, wie Sie mithilfe von Visual Studio Ihre erste .NET-Konsolenanwendung mit C# oder Visual Basic erstellen.
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ba996e4add1cfe44681154b00a6530b1f3e70b37
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714001"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="c36cf-103">Tutorial: Ihre erste .NET Core-Konsolenanwendung in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c36cf-103">Tutorial: Create your first .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="c36cf-104">Dieser Artikel bietet eine schrittweise Einführung in das Erstellen und Ausführen einer .NET Core-Konsolenanwendung „Hello World“ in Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="c36cf-104">This article provides a step-by-step introduction to create and run a Hello World .NET Core console application in Visual Studio 2019.</span></span> <span data-ttu-id="c36cf-105">Eine Hello World-Anwendung wird normalerweise verwendet, um Einsteiger in eine neue Programmiersprache einzuführen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-105">A Hello World application is traditionally used to introduce beginners to a new programming language.</span></span> <span data-ttu-id="c36cf-106">Dieses Programm zeigt einfach den Text „Hello World“ an.</span><span class="sxs-lookup"><span data-stu-id="c36cf-106">This program simply displays the phrase "Hello World!"</span></span> <span data-ttu-id="c36cf-107">auf dem Bildschirm ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c36cf-107">on the screen.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c36cf-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c36cf-108">Prerequisites</span></span>

- <span data-ttu-id="c36cf-109">[Visual Studio 2019 Version 16.4 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**.</span><span class="sxs-lookup"><span data-stu-id="c36cf-109">[Visual Studio 2019 version 16.4 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="c36cf-110">Das .NET Core 3.1 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

<span data-ttu-id="c36cf-111">Weitere Informationen finden Sie im Abschnitt [Installieren mit Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) des Artikels [Installieren des .NET Core SDK](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="c36cf-111">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="c36cf-112">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="c36cf-112">Create the app</span></span>

<span data-ttu-id="c36cf-113">In den folgenden Anleitungen wird eine einfache Hello World-Konsolenanwendung erstellt:</span><span class="sxs-lookup"><span data-stu-id="c36cf-113">The following instructions create a simple Hello World console application:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="c36cf-114">C#</span><span class="sxs-lookup"><span data-stu-id="c36cf-114">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="c36cf-115">Öffnen Sie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="c36cf-115">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="c36cf-116">Erstellen Sie ein neues C# .NET Core-Konsolenanwendungsprojekt mit dem Namen „HelloWorld“.</span><span class="sxs-lookup"><span data-stu-id="c36cf-116">Create a new C# .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="c36cf-117">Wählen Sie im Startfenster **Neues Projekt erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-117">On the start window, choose **Create a new project**.</span></span>

      ![Schaltfläche „Neues Projekt erstellen“, die im Visual Studio-Startfenster ausgewählt ist](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="c36cf-119">Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Konsole** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="c36cf-119">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="c36cf-120">Wählen Sie anschließend in der Liste der Sprachen **C#** und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-120">Next, choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="c36cf-121">Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-121">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Erstellen eines neuen Projektfenster mit ausgewählten Filtern](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="c36cf-123">Wenn die .NET Core-Vorlagen nicht angezeigt werden, ist möglicherweise die erforderliche Workload nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="c36cf-123">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="c36cf-124">Wählen Sie unter der Meldung **Sie finden nicht, wonach Sie suchen?** den Link **Weitere Tools und Features installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-124">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="c36cf-125">Der Visual Studio-Installer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c36cf-125">The Visual Studio Installer opens.</span></span> <span data-ttu-id="c36cf-126">Stellen Sie sicher, dass Sie die Workload **Plattformübergreifende .NET Core-Entwicklung** installiert haben.</span><span class="sxs-lookup"><span data-stu-id="c36cf-126">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="c36cf-127">Geben Sie **HelloWorld** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="c36cf-127">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="c36cf-128">Wählen Sie anschließend **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-128">Then, choose **Create**.</span></span>

      ![Konfigurieren Sie das Fenster für das neue Projekt mit den Feldern „Projektname“, „Speicherort“ und „Projektmappenname“.](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="c36cf-130">Die C#-Konsolenanwendungsvorlage für .NET Core definiert automatisch die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String> Array als Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c36cf-130">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="c36cf-131">`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="c36cf-131">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="c36cf-132">Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c36cf-132">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio und das neue HelloWorld-Projekt](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basictabvb"></a>[<span data-ttu-id="c36cf-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c36cf-134">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="c36cf-135">Öffnen Sie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="c36cf-135">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="c36cf-136">Erstellen Sie ein neues Visual Basic .NET Core-Konsolenanwendungsprojekt mit dem Namen „HelloWorld“.</span><span class="sxs-lookup"><span data-stu-id="c36cf-136">Create a new Visual Basic .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="c36cf-137">Wählen Sie im Startfenster **Neues Projekt erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-137">On the start window, choose **Create a new project**.</span></span>

      ![Schaltfläche „Neues Projekt erstellen“, die im Visual Studio-Startfenster ausgewählt ist](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="c36cf-139">Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Konsole** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="c36cf-139">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="c36cf-140">Wählen Sie **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-140">Next, choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="c36cf-141">Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-141">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Auswählen der Visual Basic-Vorlage für die Konsolen-App (.NET Framework)](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="c36cf-143">Wenn die .NET Core-Vorlagen nicht angezeigt werden, ist möglicherweise die erforderliche Workload nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="c36cf-143">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="c36cf-144">Wählen Sie unter der Meldung **Sie finden nicht, wonach Sie suchen?** den Link **Weitere Tools und Features installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-144">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="c36cf-145">Der Visual Studio-Installer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c36cf-145">The Visual Studio Installer opens.</span></span> <span data-ttu-id="c36cf-146">Stellen Sie sicher, dass Sie die Workload **Plattformübergreifende .NET Core-Entwicklung** installiert haben.</span><span class="sxs-lookup"><span data-stu-id="c36cf-146">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="c36cf-147">Geben Sie **HelloWorld** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="c36cf-147">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="c36cf-148">Wählen Sie anschließend **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="c36cf-148">Then, choose **Create**.</span></span>

   <span data-ttu-id="c36cf-149">Die Konsolenanwendungsvorlage für .NET Core definiert automatisch die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument annimmt.</span><span class="sxs-lookup"><span data-stu-id="c36cf-149">The console app template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="c36cf-150">`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="c36cf-150">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="c36cf-151">Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im `args`-Parameter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c36cf-151">Any command-line arguments supplied when the application is launched are available in the `args` parameter.</span></span>

   ![Visual Studio und das neue HelloWorld-Projekt](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   <span data-ttu-id="c36cf-153">Die Vorlage erstellt eine einfache „Hello World“-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c36cf-153">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="c36cf-154">Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um die literale Zeichenfolge „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="c36cf-154">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="c36cf-155">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-155">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="c36cf-156">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="c36cf-156">Run the app</span></span>

1. <span data-ttu-id="c36cf-157">Um das Programm auszuführen, wählen Sie **HelloWorld** auf der Symbolleiste aus, oder drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="c36cf-157">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![Visual Studio-Symbolleiste mit ausgewählter Schaltfläche zum Ausführen von HelloWorld](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="c36cf-159">Ein Konsolenfenster wird geöffnet, das den Text „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="c36cf-159">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="c36cf-160">auf dem Bildschirm sowie einige Visual Studio-Debuginformationen ausgibt.</span><span class="sxs-lookup"><span data-stu-id="c36cf-160">printed on the screen and some Visual Studio debug information.</span></span>

   ![Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="c36cf-162">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-162">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="c36cf-163">Optimieren der App</span><span class="sxs-lookup"><span data-stu-id="c36cf-163">Enhance the app</span></span>

<span data-ttu-id="c36cf-164">Erweitern Sie ihre Anwendung, um die Benutzer aufzufordern, Ihren Namen einzugeben und diesen mit dem Datum und der Uhrzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-164">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="c36cf-165">Die folgenden Anleitungen ändern und führen die App erneut aus:</span><span class="sxs-lookup"><span data-stu-id="c36cf-165">The following instructions modify and run the app again:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="c36cf-166">C#</span><span class="sxs-lookup"><span data-stu-id="c36cf-166">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="c36cf-167">Ersetzen Sie den Inhalt der `Main`-Methode, die derzeit nur aus der Zeile besteht, die `Console.WriteLine`aufruft, durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="c36cf-167">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   <span data-ttu-id="c36cf-168">Dieser Code zeigt „What is your name?“</span><span class="sxs-lookup"><span data-stu-id="c36cf-168">This code displays "What is your name?"</span></span> <span data-ttu-id="c36cf-169">im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat.</span><span class="sxs-lookup"><span data-stu-id="c36cf-169">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="c36cf-170">Der Code speichert diese Zeichenfolge in einer Variablen namens `name`.</span><span class="sxs-lookup"><span data-stu-id="c36cf-170">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="c36cf-171">Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu.</span><span class="sxs-lookup"><span data-stu-id="c36cf-171">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="c36cf-172">Schließlich verwendet der Code eine [interpolierte Zeichenfolge](../../csharp/language-reference/tokens/interpolated.md), um diese Werte im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-172">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="c36cf-173">Kompilieren Sie das Programm durch Auswählen von **Erstellen** > **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c36cf-173">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="c36cf-174">Um das Programm auszuführen, wählen Sie **HelloWorld** auf der Symbolleiste aus, oder drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="c36cf-174">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="c36cf-175">Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="c36cf-175">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="c36cf-177">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-177">Press any key to close the console window.</span></span>

# <a name="visual-basictabvb"></a>[<span data-ttu-id="c36cf-178">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c36cf-178">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="c36cf-179">Ersetzen Sie den Inhalt der `Main`-Methode, die derzeit nur aus der Zeile besteht, die `Console.WriteLine`aufruft, durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="c36cf-179">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="c36cf-180">Dieser Code zeigt „What is your name?“</span><span class="sxs-lookup"><span data-stu-id="c36cf-180">This code displays "What is your name?"</span></span> <span data-ttu-id="c36cf-181">im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat.</span><span class="sxs-lookup"><span data-stu-id="c36cf-181">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="c36cf-182">Der Code speichert diese Zeichenfolge in einer Variablen namens `name`.</span><span class="sxs-lookup"><span data-stu-id="c36cf-182">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="c36cf-183">Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu.</span><span class="sxs-lookup"><span data-stu-id="c36cf-183">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="c36cf-184">Schließlich verwendet der Code eine [interpolierte Zeichenfolge](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), um diese Werte im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-184">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="c36cf-185">Kompilieren Sie das Programm durch Auswählen von **Erstellen** > **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c36cf-185">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="c36cf-186">Um das Programm auszuführen, wählen Sie **HelloWorld** auf der Symbolleiste aus, oder drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="c36cf-186">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="c36cf-187">Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="c36cf-187">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="c36cf-189">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-189">Press any key to close the console window.</span></span>

---

## <a name="next-steps"></a><span data-ttu-id="c36cf-190">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c36cf-190">Next steps</span></span>

<span data-ttu-id="c36cf-191">In diesem Artikel haben Sie Ihre erste .NET Core-Anwendung erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c36cf-191">In this article, you've created and run your first .NET Core application.</span></span> <span data-ttu-id="c36cf-192">Im nächsten Schritt debuggen Sie Ihre App.</span><span class="sxs-lookup"><span data-stu-id="c36cf-192">In the next step, you debug your app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c36cf-193">Debuggen einer Hello World-Anwendung (.NET Core) in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c36cf-193">Debug a .NET Core Hello World application in Visual Studio</span></span>](debugging-with-visual-studio.md)
