---
title: Erstellen einer .NET-Konsolenanwendung mit Visual Studio Code
description: Hier erfahren Sie, wie Sie eine .NET-Konsolenanwendung mit Visual Studio Code und der .NET-CLI erstellen.
ms.date: 11/17/2020
ms.openlocfilehash: dbbdf88b0c84089249eb7e446c25eddc11543c1a
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915868"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-code"></a><span data-ttu-id="addbc-103">Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="addbc-103">Tutorial: Create a .NET console application using Visual Studio Code</span></span>

<span data-ttu-id="addbc-104">In diesem Tutorial wird gezeigt, wie Sie eine .NET-Konsolenanwendung erstellen und ausführen, indem Sie Visual Studio Code und die .NET-CLI verwenden.</span><span class="sxs-lookup"><span data-stu-id="addbc-104">This tutorial shows how to create and run a .NET console application by using Visual Studio Code and the .NET CLI.</span></span> <span data-ttu-id="addbc-105">Projektaufgaben wie das Erstellen, Kompilieren und Ausführen eines Projekts erfolgen mithilfe der .NET-CLI.</span><span class="sxs-lookup"><span data-stu-id="addbc-105">Project tasks, such as creating, compiling, and running a project are done by using the .NET CLI.</span></span> <span data-ttu-id="addbc-106">Sie können nach Wunsch dieses Tutorial mit einem anderen Code-Editor nachvollziehen und Befehle in einem Terminal ausführen.</span><span class="sxs-lookup"><span data-stu-id="addbc-106">You can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="addbc-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="addbc-107">Prerequisites</span></span>

1. <span data-ttu-id="addbc-108">[Visual Studio Code](https://code.visualstudio.com/) mit installierter [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="addbc-108">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="addbc-109">Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [Marketplace für VS Code-Erweiterungen](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="addbc-109">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="addbc-110">Das [.NET 5.0 SDK oder höher](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="addbc-110">The [.NET 5.0 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="addbc-111">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="addbc-111">Create the app</span></span>

<span data-ttu-id="addbc-112">Erstellen Sie ein .NET-Konsolen-App-Projekt mit dem Namen „HelloWorld“.</span><span class="sxs-lookup"><span data-stu-id="addbc-112">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="addbc-113">Starten Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="addbc-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="addbc-114">Wählen Sie im Hauptmenü **Datei** > **Ordner öffnen** (**Datei** > **Öffnen...** unter macOS) aus.</span><span class="sxs-lookup"><span data-stu-id="addbc-114">Select **File** > **Open Folder** (**File** > **Open...** on macOS) from the main menu.</span></span>

1. <span data-ttu-id="addbc-115">Erstellen Sie im Dialogfeld **Ordner öffnen** den Ordner *HelloWorld*, und klicken Sie auf **Ordner auswählen** (**Öffnen** unter macOS).</span><span class="sxs-lookup"><span data-stu-id="addbc-115">In the **Open Folder** dialog, create a *HelloWorld* folder and click **Select Folder** (**Open** on macOS).</span></span>

   <span data-ttu-id="addbc-116">Der Name des Ordners wird standardmäßig zum Projektnamen und Namespacenamen.</span><span class="sxs-lookup"><span data-stu-id="addbc-116">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="addbc-117">Sie fügen später in diesem Tutorial Code hinzu, der erwartet, dass der Projektnamespace `HelloWorld` ist.</span><span class="sxs-lookup"><span data-stu-id="addbc-117">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="addbc-118">Öffnen Sie das **Terminal** in Visual Studio Code, indem Sie im Hauptmenü **Ansicht** > **Terminal** auswählen.</span><span class="sxs-lookup"><span data-stu-id="addbc-118">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="addbc-119">Das **Terminal** wird mit der Eingabeaufforderung im Ordner *HelloWorld* geöffnet.</span><span class="sxs-lookup"><span data-stu-id="addbc-119">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="addbc-120">Geben Sie im **Terminal** den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="addbc-120">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new console
   ```

<span data-ttu-id="addbc-121">Die Vorlage erstellt eine einfache „Hello World“-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="addbc-121">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="addbc-122">Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um „:::no-loc text="Hello World!":::“ im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="addbc-122">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display ":::no-loc text="Hello World!":::" in the console window.</span></span>

<span data-ttu-id="addbc-123">Der Code der Vorlage definiert die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument verwendet:</span><span class="sxs-lookup"><span data-stu-id="addbc-123">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="addbc-124">`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="addbc-124">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="addbc-125">Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.</span><span class="sxs-lookup"><span data-stu-id="addbc-125">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="addbc-126">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="addbc-126">Run the app</span></span>

<span data-ttu-id="addbc-127">Führen Sie die folgenden Befehle im **Terminal** aus:</span><span class="sxs-lookup"><span data-stu-id="addbc-127">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="addbc-128">Das Programm zeigt „Hello World!“ an.</span><span class="sxs-lookup"><span data-stu-id="addbc-128">The program displays "Hello World!"</span></span> <span data-ttu-id="addbc-129">und wird beendet.</span><span class="sxs-lookup"><span data-stu-id="addbc-129">and ends.</span></span>

![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="addbc-131">Optimieren der App</span><span class="sxs-lookup"><span data-stu-id="addbc-131">Enhance the app</span></span>

<span data-ttu-id="addbc-132">Erweitern Sie die Anwendung, um den Benutzer aufzufordern, seinen Namen einzugeben und diesen zusammen mit dem Datum und der Uhrzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="addbc-132">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="addbc-133">Öffnen Sie *Program.cs*, indem Sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="addbc-133">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="addbc-134">Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](https://www.omnisharp.net/) im Editor geladen.</span><span class="sxs-lookup"><span data-stu-id="addbc-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="addbc-136">Wählen Sie **Ja** aus, wenn Visual Studio Code Sie auffordert, die fehlenden Ressourcen zum Erstellen und Debuggen Ihrer App hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="addbc-136">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="addbc-138">Ersetzen Sie den Inhalt der `Main`-Methode in *Program.cs*, der aus der Zeile besteht, die `Console.WriteLine` aufruft, durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="addbc-138">Replace the contents of the `Main` method in *Program.cs*, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="addbc-139">Mit diesem Code wird eine Eingabeaufforderung im Konsolenfenster angezeigt und gewartet, bis der Benutzer eine Zeichenfolge eingibt und die <kbd>EINGABETASTE</kbd> drückt.</span><span class="sxs-lookup"><span data-stu-id="addbc-139">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="addbc-140">Der Code speichert diese Zeichenfolge in einer Variablen namens `name`.</span><span class="sxs-lookup"><span data-stu-id="addbc-140">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="addbc-141">Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu.</span><span class="sxs-lookup"><span data-stu-id="addbc-141">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="addbc-142">Außerdem werden diese Werte im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="addbc-142">And it displays these values in the console window.</span></span> <span data-ttu-id="addbc-143">Schließlich wird eine Eingabeaufforderung im Konsolenfenster angezeigt, und die <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType>-Methode wird aufgerufen, um auf eine Benutzereingabe zu warten.</span><span class="sxs-lookup"><span data-stu-id="addbc-143">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="addbc-144">`\n` stellt ein Zeilenvorschubzeichen dar.</span><span class="sxs-lookup"><span data-stu-id="addbc-144">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="addbc-145">Mit dem Dollarzeichen (`$`) vor einer Zeichenfolge können Sie Ausdrücke wie Variablennamen in geschweifte Klammern in der Zeichenfolge einschließen.</span><span class="sxs-lookup"><span data-stu-id="addbc-145">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="addbc-146">Der Ausdruckswert wird anstelle des Ausdrucks in die Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="addbc-146">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="addbc-147">Diese Syntax wird als [interpolierte Zeichenfolgen](../../csharp/language-reference/tokens/interpolated.md) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="addbc-147">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="addbc-148">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="addbc-148">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="addbc-149">In Visual Studio Code müssen Sie Änderungen explizit speichern.</span><span class="sxs-lookup"><span data-stu-id="addbc-149">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="addbc-150">Im Gegensatz zu Visual Studio werden Dateiänderungen nicht automatisch gespeichert, wenn Sie eine App erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="addbc-150">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="addbc-151">Führen Sie das Programm erneut aus:</span><span class="sxs-lookup"><span data-stu-id="addbc-151">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="addbc-152">Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="addbc-152">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Terminalfenster mit geänderter Programmausgabe":::

1. <span data-ttu-id="addbc-154">Drücken Sie eine beliebige Taste, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="addbc-154">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="addbc-155">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="addbc-155">Additional resources</span></span>

- [<span data-ttu-id="addbc-156">Einrichten von Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="addbc-156">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a><span data-ttu-id="addbc-157">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="addbc-157">Next steps</span></span>

<span data-ttu-id="addbc-158">In diesem Tutorial haben Sie eine .NET-Konsolenanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="addbc-158">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="addbc-159">Im nächsten Tutorial debuggen Sie die App.</span><span class="sxs-lookup"><span data-stu-id="addbc-159">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="addbc-160">Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="addbc-160">Debug a .NET console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
