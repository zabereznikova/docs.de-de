---
title: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio
description: Erfahren Sie, wie Sie mithilfe von Visual Studio eine .NET-Konsolenanwendung mit C# oder Visual Basic erstellen.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: fbe0b3491260e787c08b98b320b19408f2c897eb
ms.sourcegitcommit: 09bad6ec0cbf18be7cd7f62e77286d305a18b607
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87795384"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="9ea57-103">Tutorial: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9ea57-103">Tutorial: Create a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="9ea57-104">In diesem Tutorial wird gezeigt, wie Sie eine .NET Core-Konsolenanwendung in Visual Studio 2019 erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="9ea57-104">This tutorial shows how to create and run a .NET Core console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9ea57-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9ea57-105">Prerequisites</span></span>

- <span data-ttu-id="9ea57-106">[Visual Studio 2019 Version 16.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**.</span><span class="sxs-lookup"><span data-stu-id="9ea57-106">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="9ea57-107">Das .NET Core 3.1 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.</span><span class="sxs-lookup"><span data-stu-id="9ea57-107">The .NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="9ea57-108">Weitere Informationen finden Sie unter [Installieren des .NET Core SDK in Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="9ea57-108">For more information, see [Install the .NET Core SDK with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="9ea57-109">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="9ea57-109">Create the app</span></span>

<span data-ttu-id="9ea57-110">Erstellen Sie ein .NET Core-Konsolen-App-Projekt mit dem Namen HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="9ea57-110">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="9ea57-111">Starten Sie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="9ea57-111">Start Visual Studio 2019.</span></span>

1. <span data-ttu-id="9ea57-112">Wählen Sie auf der Startseite **Neues Projekt erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="9ea57-112">On the start page, choose **Create a new project**.</span></span>

   ![Schaltfläche „Neues Projekt erstellen“, die auf der Visual Studio-Startseite ausgewählt ist](./media/with-visual-studio/start-window.png)

1. <span data-ttu-id="9ea57-114">Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Konsole** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="9ea57-114">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="9ea57-115">Wählen Sie dann **C#** oder **Visual Basic** in der Liste der Sprachen und **Alle Plattformen** in der Liste der Plattformen aus.</span><span class="sxs-lookup"><span data-stu-id="9ea57-115">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="9ea57-116">Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="9ea57-116">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   ![Erstellen eines neuen Projektfenster mit ausgewählten Filtern](./media/with-visual-studio/create-new-project.png)

   > [!TIP]
   > <span data-ttu-id="9ea57-118">Wenn die .NET Core-Vorlagen nicht angezeigt werden, fehlt möglicherweise die erforderliche Workload.</span><span class="sxs-lookup"><span data-stu-id="9ea57-118">If you don't see the .NET Core templates, you're probably missing the required workload.</span></span> <span data-ttu-id="9ea57-119">Wählen Sie unter der Meldung **Sie finden nicht, wonach Sie suchen?** den Link **Weitere Tools und Features installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="9ea57-119">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="9ea57-120">Der Visual Studio-Installer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9ea57-120">The Visual Studio Installer opens.</span></span> <span data-ttu-id="9ea57-121">Stellen Sie sicher, dass Sie die Workload **Plattformübergreifende .NET Core-Entwicklung** installiert haben.</span><span class="sxs-lookup"><span data-stu-id="9ea57-121">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

1. <span data-ttu-id="9ea57-122">Geben Sie im Dialogfeld **Neues Projekt konfigurieren** in das Feld **Projektname** den Text **HelloWorld** ein.</span><span class="sxs-lookup"><span data-stu-id="9ea57-122">In the **Configure your new project** dialog,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="9ea57-123">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="9ea57-123">Then choose **Create**.</span></span>

   ![Konfigurieren Sie das Fenster für das neue Projekt mit den Feldern „Projektname“, „Speicherort“ und „Projektmappenname“.](./media/with-visual-studio/configure-new-project.png)

<span data-ttu-id="9ea57-125">Die Vorlage erstellt eine einfache „Hello World“-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9ea57-125">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="9ea57-126">Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="9ea57-126">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="9ea57-127">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9ea57-127">in the console window.</span></span>

<span data-ttu-id="9ea57-128">Der Code der Vorlage definiert die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument verwendet:</span><span class="sxs-lookup"><span data-stu-id="9ea57-128">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="9ea57-129">`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="9ea57-129">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="9ea57-130">Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9ea57-130">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="9ea57-131">Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="9ea57-131">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="9ea57-132">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="9ea57-132">Run the app</span></span>

1. <span data-ttu-id="9ea57-133">Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9ea57-133">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

   <span data-ttu-id="9ea57-134">Ein Konsolenfenster wird geöffnet, das den Text „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="9ea57-134">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="9ea57-135">auf dem Bildschirm sowie einige Visual Studio-Debuginformationen ausgibt.</span><span class="sxs-lookup"><span data-stu-id="9ea57-135">printed on the screen and some Visual Studio debug information.</span></span>

   ![Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="9ea57-137">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9ea57-137">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="9ea57-138">Optimieren der App</span><span class="sxs-lookup"><span data-stu-id="9ea57-138">Enhance the app</span></span>

<span data-ttu-id="9ea57-139">Erweitern Sie die Anwendung, um den Benutzer aufzufordern, seinen Namen einzugeben und diesen zusammen mit dem Datum und der Uhrzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9ea57-139">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="9ea57-140">Ersetzen Sie in *Program.cs* oder *Program.vb* den Inhalt der `Main`-Methode, d. h. der Zeile, in der `Console.WriteLine` aufgerufen wird, durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="9ea57-140">In *Program.cs* or *Program.vb*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   <span data-ttu-id="9ea57-141">Dieser Code zeigt „What is your name?“</span><span class="sxs-lookup"><span data-stu-id="9ea57-141">This code displays "What is your name?"</span></span> <span data-ttu-id="9ea57-142">im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die <kbd>EINGABETASTE</kbd> gedrückt hat.</span><span class="sxs-lookup"><span data-stu-id="9ea57-142">in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="9ea57-143">Der Code speichert diese Zeichenfolge in einer Variablen namens `name`.</span><span class="sxs-lookup"><span data-stu-id="9ea57-143">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="9ea57-144">Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` (`currentDate` in Visual Basic) zu.</span><span class="sxs-lookup"><span data-stu-id="9ea57-144">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="9ea57-145">Schließlich werden diese Werte im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ea57-145">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="9ea57-146">`\n` (`vbCrLf` in Visual Basic) stellt ein Zeilenvorschubzeichen dar.</span><span class="sxs-lookup"><span data-stu-id="9ea57-146">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="9ea57-147">Mit dem Dollarzeichen (`$`) vor einer Zeichenfolge können Sie Ausdrücke wie Variablennamen in geschweifte Klammern in der Zeichenfolge einschließen.</span><span class="sxs-lookup"><span data-stu-id="9ea57-147">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="9ea57-148">Der Ausdruckswert wird anstelle des Ausdrucks in die Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="9ea57-148">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="9ea57-149">Diese Syntax wird als [interpolierte Zeichenfolgen](../../csharp/language-reference/tokens/interpolated.md) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9ea57-149">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="9ea57-150">Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9ea57-150">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

1. <span data-ttu-id="9ea57-151">Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="9ea57-151">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="9ea57-153">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9ea57-153">Press any key to close the console window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ea57-154">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9ea57-154">Next steps</span></span>

<span data-ttu-id="9ea57-155">In diesem Tutorial haben Sie eine .NET Core-Konsolenanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="9ea57-155">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="9ea57-156">Im nächsten Tutorial debuggen Sie die App.</span><span class="sxs-lookup"><span data-stu-id="9ea57-156">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9ea57-157">Debuggen einer .NET Core-Konsolenanwendung in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9ea57-157">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio.md)
