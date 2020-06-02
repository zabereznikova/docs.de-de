---
title: Erstellen einer Konsolenanwendung mit .NET Core in Visual Studio
description: Erfahren Sie, wie Sie mithilfe von Visual Studio eine .NET-Konsolenanwendung mit C# oder Visual Basic erstellen.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 9c3456cd8c940e53e8a70c1d3a7c3b09de77c21d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201585"
---
# <a name="tutorial-create-a-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="04718-103">Tutorial: Erstellen einer .NET Core-Konsolenanwendung in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="04718-103">Tutorial: Create a .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="04718-104">In diesem Tutorial wird gezeigt, wie Sie eine .NET Core-Konsolenanwendung in Visual Studio 2019 erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="04718-104">This tutorial shows how to create and run a .NET Core console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="04718-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="04718-105">Prerequisites</span></span>

- <span data-ttu-id="04718-106">[Visual Studio 2019 Version 16.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**.</span><span class="sxs-lookup"><span data-stu-id="04718-106">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="04718-107">Das .NET Core 3.1 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.</span><span class="sxs-lookup"><span data-stu-id="04718-107">The .NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="04718-108">Weitere Informationen finden Sie im Abschnitt [Installieren mit Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) des Artikels [Installieren des .NET Core SDK](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="04718-108">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="04718-109">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="04718-109">Create the app</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="04718-110">Öffnen Sie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="04718-110">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="04718-111">Erstellen Sie ein neues .NET Core-Konsolen-App-Projekt mit dem Namen „HelloWorld“.</span><span class="sxs-lookup"><span data-stu-id="04718-111">Create a new .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="04718-112">Wählen Sie auf der Startseite **Neues Projekt erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="04718-112">On the start page, choose **Create a new project**.</span></span>

      ![Schaltfläche „Neues Projekt erstellen“, die auf der Visual Studio-Startseite ausgewählt ist](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="04718-114">Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Konsole** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="04718-114">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="04718-115">Wählen Sie dann **C#** oder **Visual Basic** in der Liste der Sprachen und **Alle Plattformen** in der Liste der Plattformen aus.</span><span class="sxs-lookup"><span data-stu-id="04718-115">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="04718-116">Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="04718-116">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Erstellen eines neuen Projektfenster mit ausgewählten Filtern](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="04718-118">Wenn die .NET Core-Vorlagen nicht angezeigt werden, fehlt möglicherweise die erforderliche Workload.</span><span class="sxs-lookup"><span data-stu-id="04718-118">If you don't see the .NET Core templates, you're probably missing the required workload.</span></span> <span data-ttu-id="04718-119">Wählen Sie unter der Meldung **Sie finden nicht, wonach Sie suchen?** den Link **Weitere Tools und Features installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="04718-119">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="04718-120">Der Visual Studio-Installer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="04718-120">The Visual Studio Installer opens.</span></span> <span data-ttu-id="04718-121">Stellen Sie sicher, dass Sie die Workload **Plattformübergreifende .NET Core-Entwicklung** installiert haben.</span><span class="sxs-lookup"><span data-stu-id="04718-121">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="04718-122">Geben Sie **HelloWorld** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="04718-122">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="04718-123">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="04718-123">Then choose **Create**.</span></span>

      ![Konfigurieren Sie das Fenster für das neue Projekt mit den Feldern „Projektname“, „Speicherort“ und „Projektmappenname“.](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="04718-125">Die Konsolenanwendungsvorlage für .NET Core definiert die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="04718-125">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="04718-126">`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="04718-126">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="04718-127">Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.</span><span class="sxs-lookup"><span data-stu-id="04718-127">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   <span data-ttu-id="04718-128">Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="04718-128">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   using System;

   namespace HelloWorld
   {
       class Program
       {
           static void Main(string[] args)
           {
               Console.WriteLine("Hello World!");
           }
       }
   }
   ```

   ```vb
   Imports System

   Module Program
       Sub Main(args As String())
           Console.WriteLine("Hello World!")
       End Sub
   End Module
   ```

   <span data-ttu-id="04718-129">Die Vorlage erstellt eine einfache „Hello World“-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="04718-129">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="04718-130">Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="04718-130">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="04718-131">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04718-131">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="04718-132">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="04718-132">Run the app</span></span>

1. <span data-ttu-id="04718-133">Um das Programm auszuführen, wählen Sie **HelloWorld** auf der Symbolleiste aus, oder drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="04718-133">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![Visual Studio-Symbolleiste mit ausgewählter Schaltfläche zum Ausführen von HelloWorld](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="04718-135">Ein Konsolenfenster wird geöffnet, das den Text „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="04718-135">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="04718-136">auf dem Bildschirm sowie einige Visual Studio-Debuginformationen ausgibt.</span><span class="sxs-lookup"><span data-stu-id="04718-136">printed on the screen and some Visual Studio debug information.</span></span>

   ![Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="04718-138">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="04718-138">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="04718-139">Optimieren der App</span><span class="sxs-lookup"><span data-stu-id="04718-139">Enhance the app</span></span>

<span data-ttu-id="04718-140">Erweitern Sie die Anwendung, um den Benutzer aufzufordern, seinen Namen einzugeben und diesen zusammen mit dem Datum und der Uhrzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04718-140">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="04718-141">Die folgenden Anleitungen ändern die App und führen sie erneut aus:</span><span class="sxs-lookup"><span data-stu-id="04718-141">The following instructions modify the app and run it again:</span></span>

1. <span data-ttu-id="04718-142">Ersetzen Sie den Inhalt der `Main`-Methode, die derzeit nur aus der Zeile besteht, die `Console.WriteLine`aufruft, durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="04718-142">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="Snippet1":::

   <span data-ttu-id="04718-143">Dieser Code zeigt „What is your name?“</span><span class="sxs-lookup"><span data-stu-id="04718-143">This code displays "What is your name?"</span></span> <span data-ttu-id="04718-144">im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat.</span><span class="sxs-lookup"><span data-stu-id="04718-144">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="04718-145">Der Code speichert diese Zeichenfolge in einer Variablen namens `name`.</span><span class="sxs-lookup"><span data-stu-id="04718-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="04718-146">Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` (`currentDate` in Visual Basic) zu.</span><span class="sxs-lookup"><span data-stu-id="04718-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="04718-147">Schließlich werden diese Werte im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04718-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="04718-148">`\n` (`vbCrLf` in Visual Basic) stellt ein Zeilenvorschubzeichen dar.</span><span class="sxs-lookup"><span data-stu-id="04718-148">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="04718-149">Mit dem Dollarzeichen (`$`) vor einer Zeichenfolge können Sie Ausdrücke wie Variablennamen in geschweifte Klammern in der Zeichenfolge einschließen.</span><span class="sxs-lookup"><span data-stu-id="04718-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="04718-150">Der Ausdruckswert wird anstelle des Ausdrucks in die Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="04718-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="04718-151">Diese Syntax wird als [interpolierte Zeichenfolgen](../../csharp/language-reference/tokens/interpolated.md) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="04718-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="04718-152">Um das Programm auszuführen, wählen Sie **HelloWorld** auf der Symbolleiste aus, oder drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="04718-152">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="04718-153">Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="04718-153">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="04718-155">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="04718-155">Press any key to close the console window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="04718-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="04718-156">Next steps</span></span>

<span data-ttu-id="04718-157">In diesem Tutorial haben Sie eine .NET Core-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="04718-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="04718-158">Im nächsten Tutorial debuggen Sie die App.</span><span class="sxs-lookup"><span data-stu-id="04718-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="04718-159">Debuggen einer .NET Core-Konsolenanwendung in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04718-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio.md)
