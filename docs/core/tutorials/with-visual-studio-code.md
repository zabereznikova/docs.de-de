---
title: Erstellen einer Konsolenanwendung mit .NET Core mithilfe von Visual Studio Code
description: Erfahren Sie, wie Sie eine .NET Core-Konsolenanwendung mit Visual Studio Code und der .NET Core-CLI erstellen.
ms.date: 05/22/2020
ms.openlocfilehash: 673c4a639a2cab26261b7cdafd5d8e20acfafb94
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201705"
---
# <a name="tutorial-create-a-console-application-with-net-core-using-visual-studio-code"></a><span data-ttu-id="e26d3-103">Tutorial: Erstellen einer Konsolenanwendung mit .NET Core mithilfe von Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e26d3-103">Tutorial: Create a console application with .NET Core using Visual Studio Code</span></span>

<span data-ttu-id="e26d3-104">In diesem Tutorial wird gezeigt, wie Sie eine .NET Core-Konsolenanwendung erstellen und ausführen, indem Sie Visual Studio Code und die .NET Core-CLI verwenden.</span><span class="sxs-lookup"><span data-stu-id="e26d3-104">This tutorial shows how to create and run a .NET Core console application by using Visual Studio Code and the .NET Core CLI.</span></span> <span data-ttu-id="e26d3-105">Projektaufgaben, z. B. das Erstellen, Kompilieren und Ausführen eines Projekts, werden mithilfe der CLI durchgeführt, sodass Sie dieses Tutorial mit einem anderen Code-Editor nachvollziehen und Befehle in einem Terminal ausführen können, wenn Sie dies bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-105">Project tasks, such as creating, compiling, and running a project are done by using the CLI, so you can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e26d3-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e26d3-106">Prerequisites</span></span>

1. <span data-ttu-id="e26d3-107">[Visual Studio Code](https://code.visualstudio.com/) mit installierter [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="e26d3-107">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="e26d3-108">Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [Marketplace für VS Code-Erweiterungen](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="e26d3-108">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="e26d3-109">[.NET Core 3.1 SDK oder höher](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="e26d3-109">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="e26d3-110">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="e26d3-110">Create the app</span></span>

1. <span data-ttu-id="e26d3-111">Öffnen Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="e26d3-111">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="e26d3-112">Erstellen eines Projekts.</span><span class="sxs-lookup"><span data-stu-id="e26d3-112">Create a project.</span></span>

   1. <span data-ttu-id="e26d3-113">Wählen Sie **Datei** > **Ordner öffnen**/**Öffnen** im Hauptmenü aus, erstellen Sie einen Ordner *HelloWorld*, und klicken Sie dann auf **Ordner auswählen**/**Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="e26d3-113">Select **File** > **Open Folder**/**Open...** from the main menu, create a *HelloWorld* folder, and click **Select Folder**/**Open**.</span></span>

      <span data-ttu-id="e26d3-114">Der Name des Ordners wird standardmäßig zum Projektnamen und Namespacenamen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-114">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="e26d3-115">Sie fügen später in diesem Tutorial Code hinzu, der erwartet, dass der Projektnamespace `HelloWorld` ist.</span><span class="sxs-lookup"><span data-stu-id="e26d3-115">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

   1. <span data-ttu-id="e26d3-116">Öffnen Sie das **Terminal** in Visual Studio Code, indem Sie im Hauptmenü **Ansicht** > **Terminal** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-116">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

      <span data-ttu-id="e26d3-117">Das**Terminal** wird mit der Eingabeaufforderung im Ordner *HelloWorld* geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e26d3-117">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

   1. <span data-ttu-id="e26d3-118">Geben Sie im **Terminal** den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e26d3-118">In the **Terminal**, enter the following command:</span></span>

      ```dotnetcli
      dotnet new console
      ```

<span data-ttu-id="e26d3-119">Die Konsolenanwendungsvorlage für .NET Core definiert die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e26d3-119">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="e26d3-120">Die Datei *Program.cs* enthält den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e26d3-120">The *Program.cs* file has the following code:</span></span>

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

<span data-ttu-id="e26d3-121">`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="e26d3-121">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="e26d3-122">Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e26d3-122">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="e26d3-123">Die Vorlage erstellt eine einfache Anwendung, die die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode aufruft, um „Hello World!“ anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-123">The template creates a simple application that calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="e26d3-124">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-124">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="e26d3-125">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="e26d3-125">Run the app</span></span>

<span data-ttu-id="e26d3-126">Führen Sie die folgenden Befehle im **Terminal** aus:</span><span class="sxs-lookup"><span data-stu-id="e26d3-126">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="e26d3-127">Das Programm zeigt „Hello World!“ an.</span><span class="sxs-lookup"><span data-stu-id="e26d3-127">The program displays "Hello World!"</span></span> <span data-ttu-id="e26d3-128">und wird beendet.</span><span class="sxs-lookup"><span data-stu-id="e26d3-128">and ends.</span></span>

![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="e26d3-130">Optimieren der App</span><span class="sxs-lookup"><span data-stu-id="e26d3-130">Enhance the app</span></span>

<span data-ttu-id="e26d3-131">Erweitern Sie die Anwendung, um den Benutzer aufzufordern, seinen Namen einzugeben und diesen zusammen mit dem Datum und der Uhrzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-131">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="e26d3-132">Öffnen Sie *Program.cs*, indem Sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="e26d3-132">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="e26d3-133">Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](https://www.omnisharp.net/) im Editor geladen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-133">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="e26d3-135">Wählen Sie **Ja** aus, wenn Visual Studio Code Sie auffordert, die fehlenden Ressourcen zum Erstellen und Debuggen Ihrer App hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-135">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="e26d3-137">Ersetzen Sie den Inhalt der `Main`-Methode in *Program.cs*, der zurzeit nur aus der Zeile besteht, die `Console.WriteLine` aufruft, durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e26d3-137">Replace the contents of the `Main` method in *Program.cs*, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   <span data-ttu-id="e26d3-138">Dieser Code zeigt „What is your name?“</span><span class="sxs-lookup"><span data-stu-id="e26d3-138">This code displays "What is your name?"</span></span> <span data-ttu-id="e26d3-139">im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die **EINGABETASTE** gedrückt hat.</span><span class="sxs-lookup"><span data-stu-id="e26d3-139">in the console window and waits until the user enters a string followed by the **Enter** key.</span></span> <span data-ttu-id="e26d3-140">Der Code speichert diese Zeichenfolge in einer Variablen namens `name`.</span><span class="sxs-lookup"><span data-stu-id="e26d3-140">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="e26d3-141">Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu.</span><span class="sxs-lookup"><span data-stu-id="e26d3-141">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="e26d3-142">Schließlich werden diese Werte im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e26d3-142">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="e26d3-143">`\n` stellt ein Zeilenvorschubzeichen dar.</span><span class="sxs-lookup"><span data-stu-id="e26d3-143">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="e26d3-144">Mit dem Dollarzeichen (`$`) vor einer Zeichenfolge können Sie Ausdrücke wie Variablennamen in geschweifte Klammern in der Zeichenfolge einschließen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-144">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="e26d3-145">Der Ausdruckswert wird anstelle des Ausdrucks in die Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e26d3-145">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="e26d3-146">Diese Syntax wird als [interpolierte Zeichenfolgen](../../csharp/language-reference/tokens/interpolated.md) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e26d3-146">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="e26d3-147">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-147">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e26d3-148">In Visual Studio Code müssen Sie Änderungen explizit speichern.</span><span class="sxs-lookup"><span data-stu-id="e26d3-148">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="e26d3-149">Im Gegensatz zu Visual Studio werden Dateiänderungen nicht automatisch gespeichert, wenn Sie eine App erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-149">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="e26d3-150">Führen Sie das Programm erneut aus:</span><span class="sxs-lookup"><span data-stu-id="e26d3-150">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="e26d3-151">Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="e26d3-151">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Terminalfenster mit geänderter Programmausgabe":::

1. <span data-ttu-id="e26d3-153">Drücken Sie eine beliebige Taste, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="e26d3-153">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e26d3-154">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e26d3-154">Additional resources</span></span>

- [<span data-ttu-id="e26d3-155">Einrichten von Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e26d3-155">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a><span data-ttu-id="e26d3-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e26d3-156">Next steps</span></span>

<span data-ttu-id="e26d3-157">In diesem Tutorial haben Sie eine .NET Core-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="e26d3-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="e26d3-158">Im nächsten Tutorial debuggen Sie die App.</span><span class="sxs-lookup"><span data-stu-id="e26d3-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e26d3-159">Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e26d3-159">Debug a .NET Core console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
