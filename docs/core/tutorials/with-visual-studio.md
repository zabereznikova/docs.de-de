---
title: Erstellen einer .NET-Konsolenanwendung mit Visual Studio
description: Hier erfahren Sie, wie Sie mithilfe von Visual Studio eine .NET-Konsolenanwendung mit C# oder Visual Basic erstellen.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e395122e59f17ed66bbd9d83b01610993f663ce1
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915919"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio"></a><span data-ttu-id="8b518-103">Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8b518-103">Tutorial: Create a .NET console application using Visual Studio</span></span>

<span data-ttu-id="8b518-104">In diesem Tutorial wird gezeigt, wie Sie eine .NET-Konsolenanwendung in Visual Studio 2019 erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="8b518-104">This tutorial shows how to create and run a .NET console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b518-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8b518-105">Prerequisites</span></span>

- <span data-ttu-id="8b518-106">[Visual Studio 2019 Version 16.8 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**.</span><span class="sxs-lookup"><span data-stu-id="8b518-106">[Visual Studio 2019 version 16.8 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="8b518-107">Das .NET 5.0 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.</span><span class="sxs-lookup"><span data-stu-id="8b518-107">The .NET 5.0 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="8b518-108">Weitere Informationen finden Sie unter [Installieren mit Visual Studio](../install/windows.md#install-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="8b518-108">For more information, see [Install the .NET SDK with Visual Studio](../install/windows.md#install-with-visual-studio).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="8b518-109">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="8b518-109">Create the app</span></span>

<span data-ttu-id="8b518-110">Erstellen Sie ein .NET-Konsolen-App-Projekt mit dem Namen „HelloWorld“.</span><span class="sxs-lookup"><span data-stu-id="8b518-110">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="8b518-111">Starten Sie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="8b518-111">Start Visual Studio 2019.</span></span>

1. <span data-ttu-id="8b518-112">Klicken Sie auf **Extras** > **Optionen** > **Umgebung** > **Previewfeatures**, und aktivieren Sie dann **Show all .NET Core templates in the New project (requires restart)** (Alle .NET Core-Vorlagen im neuen Projekt anzeigen (Neustart erforderlich)).</span><span class="sxs-lookup"><span data-stu-id="8b518-112">Select **Tools** > **Options** > **Environment** > **Preview features**, and then select **Show all .NET Core templates in the New project (requires restart)**.</span></span>

   :::image type="content" source="media/with-visual-studio/dotnet-options.png" alt-text="Anzeigen aller .NET-Vorlagenoptionen":::

1. <span data-ttu-id="8b518-114">Schließen Sie Visual Studio, und öffnen Sie es wieder.</span><span class="sxs-lookup"><span data-stu-id="8b518-114">Close and reopen Visual Studio.</span></span>

1. <span data-ttu-id="8b518-115">Wählen Sie auf der Startseite **Neues Projekt erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="8b518-115">On the start page, choose **Create a new project**.</span></span>

   :::image type="content" source="./media/with-visual-studio/start-window.png" alt-text="Schaltfläche „Neues Projekt erstellen“, die auf der Visual Studio-Startseite ausgewählt ist":::

1. <span data-ttu-id="8b518-117">Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Konsole** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="8b518-117">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="8b518-118">Wählen Sie dann **C#** oder **Visual Basic** in der Liste der Sprachen und **Alle Plattformen** in der Liste der Plattformen aus.</span><span class="sxs-lookup"><span data-stu-id="8b518-118">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="8b518-119">Wählen Sie die Vorlage **Konsolenanwendung** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8b518-119">Choose the **Console Application** template, and then choose **Next**.</span></span>

   :::image type="content" source="./media/with-visual-studio/create-new-project.png" alt-text="Erstellen eines neuen Projektfenster mit ausgewählten Filtern":::

   > [!TIP]
   > <span data-ttu-id="8b518-121">Wenn die .NET-Vorlagen nicht angezeigt werden, fehlt möglicherweise die erforderliche Workload.</span><span class="sxs-lookup"><span data-stu-id="8b518-121">If you don't see the .NET templates, you're probably missing the required workload.</span></span> <span data-ttu-id="8b518-122">Wählen Sie unter der Meldung **Sie finden nicht, wonach Sie suchen?** den Link **Weitere Tools und Features installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="8b518-122">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="8b518-123">Der Visual Studio-Installer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8b518-123">The Visual Studio Installer opens.</span></span> <span data-ttu-id="8b518-124">Stellen Sie sicher, dass Sie die Workload **Plattformübergreifende .NET Core-Entwicklung** installiert haben.</span><span class="sxs-lookup"><span data-stu-id="8b518-124">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

1. <span data-ttu-id="8b518-125">Geben Sie im Dialogfeld **Neues Projekt konfigurieren** in das Feld **Projektname** den Text **HelloWorld** ein.</span><span class="sxs-lookup"><span data-stu-id="8b518-125">In the **Configure your new project** dialog,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="8b518-126">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="8b518-126">Then choose **Create**.</span></span>

   :::image type="content" source="./media/with-visual-studio/configure-new-project.png" alt-text="Konfigurieren Sie das Fenster für das neue Projekt mit den Feldern „Projektname“, „Speicherort“ und „Projektmappenname“.":::

1. <span data-ttu-id="8b518-128">Wählen Sie im Dialogfeld **Zusätzliche Informationen** die Option **.NET 5.0 (Current)** (.NET 5.0 (aktuell)) aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="8b518-128">In the **Additional information** dialog, select **.NET 5.0 (Current)**, and then select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio/additional-info.png" alt-text="Dialogfeld „Zusätzliche Informationen“":::

<span data-ttu-id="8b518-130">Die Vorlage erstellt eine einfache „Hello World“-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8b518-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="8b518-131">Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="8b518-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="8b518-132">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8b518-132">in the console window.</span></span>

<span data-ttu-id="8b518-133">Der Code der Vorlage definiert die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument verwendet:</span><span class="sxs-lookup"><span data-stu-id="8b518-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="8b518-134">`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="8b518-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="8b518-135">Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8b518-135">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="8b518-136">Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="8b518-136">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="8b518-137">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="8b518-137">Run the app</span></span>

1. <span data-ttu-id="8b518-138">Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8b518-138">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

   <span data-ttu-id="8b518-139">Ein Konsolenfenster wird geöffnet, das den Text „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="8b518-139">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="8b518-140">auf dem Bildschirm anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8b518-140">printed on the screen.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-console.png" alt-text="Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt":::

1. <span data-ttu-id="8b518-142">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8b518-142">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="8b518-143">Optimieren der App</span><span class="sxs-lookup"><span data-stu-id="8b518-143">Enhance the app</span></span>

<span data-ttu-id="8b518-144">Erweitern Sie die Anwendung, um den Benutzer aufzufordern, seinen Namen einzugeben und diesen zusammen mit dem Datum und der Uhrzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8b518-144">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="8b518-145">Ersetzen Sie in *Program.cs* oder *Program.vb* den Inhalt der `Main`-Methode, d. h. der Zeile, in der `Console.WriteLine` aufgerufen wird, durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="8b518-145">In *Program.cs* or *Program.vb*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   <span data-ttu-id="8b518-146">Mit diesem Code wird eine Eingabeaufforderung im Konsolenfenster angezeigt und gewartet, bis der Benutzer eine Zeichenfolge eingibt und die <kbd>EINGABETASTE</kbd> drückt.</span><span class="sxs-lookup"><span data-stu-id="8b518-146">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="8b518-147">Der Code speichert diese Zeichenfolge in einer Variablen namens `name`.</span><span class="sxs-lookup"><span data-stu-id="8b518-147">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="8b518-148">Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` (`currentDate` in Visual Basic) zu.</span><span class="sxs-lookup"><span data-stu-id="8b518-148">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="8b518-149">Außerdem werden diese Werte im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8b518-149">And it displays these values in the console window.</span></span> <span data-ttu-id="8b518-150">Schließlich wird eine Eingabeaufforderung im Konsolenfenster angezeigt, und die <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType>-Methode wird aufgerufen, um auf eine Benutzereingabe zu warten.</span><span class="sxs-lookup"><span data-stu-id="8b518-150">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="8b518-151">`\n` (`vbCrLf` in Visual Basic) stellt ein Zeilenvorschubzeichen dar.</span><span class="sxs-lookup"><span data-stu-id="8b518-151">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="8b518-152">Mit dem Dollarzeichen (`$`) vor einer Zeichenfolge können Sie Ausdrücke wie Variablennamen in geschweifte Klammern in der Zeichenfolge einschließen.</span><span class="sxs-lookup"><span data-stu-id="8b518-152">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="8b518-153">Der Ausdruckswert wird anstelle des Ausdrucks in die Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="8b518-153">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="8b518-154">Diese Syntax wird als [interpolierte Zeichenfolgen](../../csharp/language-reference/tokens/interpolated.md) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8b518-154">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="8b518-155">Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8b518-155">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

1. <span data-ttu-id="8b518-156">Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="8b518-156">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-update.png" alt-text="Konsolenfenster mit veränderter Programmausgabe":::

1. <span data-ttu-id="8b518-158">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8b518-158">Press any key to close the console window.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8b518-159">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8b518-159">Additional resources</span></span>

- [<span data-ttu-id="8b518-160">Aktuelle Releases und langfristige Supportreleases</span><span class="sxs-lookup"><span data-stu-id="8b518-160">Current releases and long-term support releases</span></span>](../releases-and-support.md#net-core-and-net-5-version-lifecycles)

## <a name="next-steps"></a><span data-ttu-id="8b518-161">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8b518-161">Next steps</span></span>

<span data-ttu-id="8b518-162">In diesem Tutorial haben Sie eine .NET-Konsolenanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="8b518-162">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="8b518-163">Im nächsten Tutorial debuggen Sie die App.</span><span class="sxs-lookup"><span data-stu-id="8b518-163">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8b518-164">Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8b518-164">Debug a .NET console application using Visual Studio</span></span>](debugging-with-visual-studio.md)
