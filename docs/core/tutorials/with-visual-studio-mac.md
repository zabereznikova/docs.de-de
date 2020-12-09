---
title: Erstellen einer .NET-Konsolenanwendung mit Visual Studio für Mac
description: Erfahren Sie, wie Sie eine .NET-Konsolenanwendung mit Visual Studio für Mac erstellen.
ms.date: 11/30/2020
ms.openlocfilehash: 1351b06eec32cd8d3d9d44926655405fe2246f58
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599485"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="58510-103">Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="58510-103">Tutorial: Create a .NET console application using Visual Studio for Mac</span></span>

<span data-ttu-id="58510-104">In diesem Tutorial wird gezeigt, wie Sie eine .NET-Konsolenanwendung in Visual Studio für Mac erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="58510-104">This tutorial shows how to create and run a .NET console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="58510-105">Ihr Feedback ist uns sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="58510-105">Your feedback is highly valued.</span></span> <span data-ttu-id="58510-106">Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:</span><span class="sxs-lookup"><span data-stu-id="58510-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="58510-107">Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Ablegen eines Fehlerberichts geöffnet.</span><span class="sxs-lookup"><span data-stu-id="58510-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="58510-108">Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://aka.ms/feedback/report?space=41) verfolgen.</span><span class="sxs-lookup"><span data-stu-id="58510-108">You can track your feedback in the [Developer Community](https://aka.ms/feedback/report?space=41) portal.</span></span>
> * <span data-ttu-id="58510-109">Um einen Vorschlag zu machen, wählen Sie **Hilfe** > **Vorschlag senden** im Menü oder **Vorschlag senden** auf der Willkommensseite aus. Dadurch gelangen Sie zur Webseite [Visual Studio für Mac-Entwicklercommunity](https://aka.ms/feedback/suggest?space=41).</span><span class="sxs-lookup"><span data-stu-id="58510-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://aka.ms/feedback/suggest?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="58510-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="58510-110">Prerequisites</span></span>

* <span data-ttu-id="58510-111">[Visual Studio für Mac ab Version 8.8](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="58510-111">[Visual Studio for Mac version 8.8 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="58510-112">Wählen Sie die Option zum Installieren von .NET Core aus.</span><span class="sxs-lookup"><span data-stu-id="58510-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="58510-113">Die Installation von Xamarin ist für die Entwicklung mit .NET optional.</span><span class="sxs-lookup"><span data-stu-id="58510-113">Installing Xamarin is optional for .NET development.</span></span> <span data-ttu-id="58510-114">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="58510-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="58510-115">[Tutorial: Installieren von Visual Studio für Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="58510-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="58510-116">[Unterstützte macOS-Versionen](../install/windows.md)</span><span class="sxs-lookup"><span data-stu-id="58510-116">[Supported macOS versions](../install/windows.md).</span></span>
  * <span data-ttu-id="58510-117">[Von Visual Studio für Mac unterstützte .NET-Versionen](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="58510-117">[.NET versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="58510-118">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="58510-118">Create the app</span></span>

1. <span data-ttu-id="58510-119">Starten Sie Visual Studio für Mac.</span><span class="sxs-lookup"><span data-stu-id="58510-119">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="58510-120">Wählen Sie im Startfenster **Neu** aus.</span><span class="sxs-lookup"><span data-stu-id="58510-120">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Schaltfläche „Neu“ auf der Startseite von Visual Studio für Mac":::

1. <span data-ttu-id="58510-122">Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **Web und Konsole** die Option **App** aus.</span><span class="sxs-lookup"><span data-stu-id="58510-122">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="58510-123">Wählen Sie die Vorlage **Konsolenanwendung** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="58510-123">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Liste neuer Projektvorlagen":::

1. <span data-ttu-id="58510-125">Wählen Sie in der Dropdownliste **Zielframework** des Dialogfelds **Neue Konsolenanwendung konfigurieren** die Option **.NET 5.0** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="58510-125">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET 5.0**, and select **Next**.</span></span>

1. <span data-ttu-id="58510-126">Geben Sie in **Projektname** HelloWorld ein, und wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="58510-126">Type "HelloWorld" for the **Project Name**, and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Dialogfeld „Neue Konsolenanwendung konfigurieren“":::

<span data-ttu-id="58510-128">Die Vorlage erstellt eine einfache „Hello World“-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="58510-128">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="58510-129">Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="58510-129">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="58510-130">im Terminalfenster auf.</span><span class="sxs-lookup"><span data-stu-id="58510-130">in the terminal window.</span></span>

<span data-ttu-id="58510-131">Der Code der Vorlage definiert die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument verwendet:</span><span class="sxs-lookup"><span data-stu-id="58510-131">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="58510-132">`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="58510-132">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="58510-133">Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im Array `args` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58510-133">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="58510-134">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="58510-134">Run the app</span></span>

1. <span data-ttu-id="58510-135">Drücken Sie <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>OPTION</kbd>+<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>) zum Ausführen der App ohne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="58510-135">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="Im Terminal wird „Hello World!“ angezeigt":::

1. <span data-ttu-id="58510-137">Schließen Sie das Fenster **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="58510-137">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="58510-138">Optimieren der App</span><span class="sxs-lookup"><span data-stu-id="58510-138">Enhance the app</span></span>

<span data-ttu-id="58510-139">Erweitern Sie die Anwendung, um den Benutzer aufzufordern, seinen Namen einzugeben und diesen zusammen mit dem Datum und der Uhrzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="58510-139">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="58510-140">Ersetzen Sie in *Program.cs* den Inhalt der `Main`-Methode, der aus der Zeile besteht, die `Console.WriteLine` aufruft, durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="58510-140">In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="58510-141">Mit diesem Code wird eine Eingabeaufforderung im Konsolenfenster angezeigt und gewartet, bis der Benutzer eine Zeichenfolge eingibt und die <kbd>EINGABETASTE</kbd> drückt.</span><span class="sxs-lookup"><span data-stu-id="58510-141">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="58510-142">Der Code speichert diese Zeichenfolge in einer Variablen namens `name`.</span><span class="sxs-lookup"><span data-stu-id="58510-142">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="58510-143">Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu.</span><span class="sxs-lookup"><span data-stu-id="58510-143">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="58510-144">Außerdem werden diese Werte im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58510-144">And it displays these values in the console window.</span></span> <span data-ttu-id="58510-145">Schließlich wird eine Eingabeaufforderung im Konsolenfenster angezeigt, und die <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType>-Methode wird aufgerufen, um auf eine Benutzereingabe zu warten.</span><span class="sxs-lookup"><span data-stu-id="58510-145">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="58510-146">`\n` stellt ein Zeilenvorschubzeichen dar.</span><span class="sxs-lookup"><span data-stu-id="58510-146">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="58510-147">Mit dem Dollarzeichen (`$`) vor einer Zeichenfolge können Sie Ausdrücke wie Variablennamen in geschweifte Klammern in der Zeichenfolge einschließen.</span><span class="sxs-lookup"><span data-stu-id="58510-147">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="58510-148">Der Ausdruckswert wird anstelle des Ausdrucks in die Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58510-148">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="58510-149">Diese Syntax wird als [interpolierte Zeichenfolgen](../../csharp/language-reference/tokens/interpolated.md) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="58510-149">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="58510-150">Drücken Sie <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>OPTION</kbd>+<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>) zum Ausführen der App.</span><span class="sxs-lookup"><span data-stu-id="58510-150">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="58510-151">Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="58510-151">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Terminalfenster mit geänderter Programmausgabe":::

1. <span data-ttu-id="58510-153">Schließen Sie das Terminal.</span><span class="sxs-lookup"><span data-stu-id="58510-153">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="58510-154">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="58510-154">Next steps</span></span>

<span data-ttu-id="58510-155">In diesem Tutorial haben Sie eine .NET-Konsolenanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="58510-155">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="58510-156">Im nächsten Tutorial debuggen Sie die App.</span><span class="sxs-lookup"><span data-stu-id="58510-156">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="58510-157">Debuggen einer .NET-Konsolenanwendung mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="58510-157">Debug a .NET console application using Visual Studio for Mac</span></span>](debugging-with-visual-studio-mac.md)
