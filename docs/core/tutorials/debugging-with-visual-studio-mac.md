---
title: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac
description: Erfahren Sie, wie Sie eine .NET Core-Konsolen-App mit Visual Studio für Mac debuggen.
ms.date: 06/08/2020
ms.openlocfilehash: 7e2a25266fab40b5ef1d0a38b8bbf06a6843746b
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416021"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="d6691-103">Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="d6691-103">Tutorial: Debug a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="d6691-104">In diesem Tutorial werden die Debugtools vorgestellt, die in Visual Studio für Mac verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d6691-104">This tutorial introduces the debugging tools available in Visual Studio for Mac.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6691-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d6691-105">Prerequisites</span></span>

- <span data-ttu-id="d6691-106">Dieses Tutorial funktioniert mit der Konsolen-App, die Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio für Mac](with-visual-studio-mac.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6691-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="d6691-107">Verwenden der Debugbuildkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d6691-107">Use Debug build configuration</span></span>

<span data-ttu-id="d6691-108">*Debug* und *Release* sind zwei Standardbuildkonfigurationen von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6691-108">*Debug* and *Release* are Visual Studio's built-in build configurations.</span></span> <span data-ttu-id="d6691-109">Sie verwenden die Debugbuildkonfiguration zum Debuggen und die Releasekonfiguration für die endgültige Releaseverteilung.</span><span class="sxs-lookup"><span data-stu-id="d6691-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="d6691-110">In der Debugkonfiguration wird ein Programm mit vollständigen symbolischen Debuginformationen und ohne Optimierung kompiliert.</span><span class="sxs-lookup"><span data-stu-id="d6691-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="d6691-111">Die Optimierung gestaltet das Debuggen etwas schwieriger, da die Beziehung zwischen Quellcode und generierten Anweisungen komplexer ist.</span><span class="sxs-lookup"><span data-stu-id="d6691-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="d6691-112">Die Releasekonfiguration eines Programms verfügt über keine symbolischen Debuginformationen und wird vollständig optimiert.</span><span class="sxs-lookup"><span data-stu-id="d6691-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

<span data-ttu-id="d6691-113">Standardmäßig verwendet Visual Studio die Debugbuildkonfiguration, sodass Sie diese Einstellung vor dem Debuggen nicht ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="d6691-113">By default, Visual Studio uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="d6691-114">Starten Sie Visual Studio für Mac.</span><span class="sxs-lookup"><span data-stu-id="d6691-114">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="d6691-115">Öffnen Sie das Projekt, das Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio für Mac](with-visual-studio-mac.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d6691-115">Open the project that you created in [Create a .NET Core console application in Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

   <span data-ttu-id="d6691-116">Die aktuelle Buildkonfiguration wird auf der Symbolleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6691-116">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="d6691-117">Das folgende Symbolleistenbild zeigt, dass Visual Studio konfiguriert wurde, um die Debugversion Ihrer Anwendung zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="d6691-117">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-debug.png" alt-text="Visual Studio-Symbolleiste mit hervorgehobenem Debuggen":::

## <a name="set-a-breakpoint"></a><span data-ttu-id="d6691-119">Haltepunkt festlegen</span><span class="sxs-lookup"><span data-stu-id="d6691-119">Set a breakpoint</span></span>

<span data-ttu-id="d6691-120">Ein *Haltepunkt* unterbricht vorübergehend die Ausführung der Anwendung, bevor die Zeile mit dem Haltepunkt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6691-120">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="d6691-121">Legen Sie einen Haltepunkt in der Zeile fest, in der der Name, das Datum und die Uhrzeit angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d6691-121">Set a breakpoint on the line that displays the name, date, and time.</span></span> <span data-ttu-id="d6691-122">Platzieren Sie hierzu den Cursor in der Codezeile, und drücken Sie <kbd>⌘</kbd><kbd>\\</kbd> (<kbd>BEFEHL</kbd>+<kbd>\\</kbd>).</span><span class="sxs-lookup"><span data-stu-id="d6691-122">To do that, place the cursor in the line of code and press <kbd>⌘</kbd><kbd>\\</kbd> (<kbd>command</kbd>+<kbd>\\</kbd>).</span></span> <span data-ttu-id="d6691-123">Eine andere Möglichkeit zum Festlegen eines Haltepunkts besteht darin, im Menü **Ausführen** > **Haltepunkt umschalten** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d6691-123">Another way to set a breakpoint is by selecting **Run** > **Toggle Breakpoint** from the menu.</span></span>

   <span data-ttu-id="d6691-124">Visual Studio hebt die Zeile hervor, in der der Haltepunkt festgelegt ist, und zeigt am linken Rand einen roten Punkt an.</span><span class="sxs-lookup"><span data-stu-id="d6691-124">Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/set-breakpoint-in-editor.png" alt-text="Visual Studio-Programmfenster mit festgelegtem Haltepunkt":::

1. <span data-ttu-id="d6691-126">Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>) ein, um das Programm im Debugmodus zu starten.</span><span class="sxs-lookup"><span data-stu-id="d6691-126">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start the program in debugging mode.</span></span> <span data-ttu-id="d6691-127">Eine andere Möglichkeit, das Debuggen zu starten, besteht darin, im Menü **Ausführen** > **Debuggen starten** zu wählen.</span><span class="sxs-lookup"><span data-stu-id="d6691-127">Another way to start debugging is by choosing **Run** > **Start Debugging** from the menu.</span></span>

1. <span data-ttu-id="d6691-128">Geben Sie eine Zeichenfolge im Terminalfenster ein, wenn das Programm Sie zur Eingabe eines Namens auffordert, und drücken Sie dann die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6691-128">Enter a string in the terminal window when the program prompts for a name, and then press <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="d6691-129">Die Ausführung des Programms endet, wenn es den Haltepunkt erreicht, bevor die `Console.WriteLine`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6691-129">Program execution stops when it reaches the breakpoint, before the `Console.WriteLine` method executes.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-hit.png" alt-text="Screenshot eines Haltepunkts in Visual Studio":::

## <a name="use-the-immediate-window"></a><span data-ttu-id="d6691-131">Verwenden des Fensters „Direkt“</span><span class="sxs-lookup"><span data-stu-id="d6691-131">Use the Immediate window</span></span>

<span data-ttu-id="d6691-132">Das **Direktfenster** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen.</span><span class="sxs-lookup"><span data-stu-id="d6691-132">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="d6691-133">Sie können den Wert von Variablen interaktiv ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt.</span><span class="sxs-lookup"><span data-stu-id="d6691-133">You can interactively change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="d6691-134">Wenn das Fenster **Direkt** nicht angezeigt wird, zeigen Sie es durch Auswählen von **Ansicht** > **Debugbereiche** > **Direkt** an.</span><span class="sxs-lookup"><span data-stu-id="d6691-134">If the **Immediate** window is not visible, display it by choosing **View** > **Debug Pads** > **Immediate**.</span></span>

1. <span data-ttu-id="d6691-135">Geben Sie `name = "Gracie"` im Fenster **Direkt** ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6691-135">Enter `name = "Gracie"` in the **Immediate** window and press <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="d6691-136">Geben Sie `date = date.AddDays(1)` im Fenster **Direkt** ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d6691-136">Enter `date = date.AddDays(1)` in the **Immediate** window and press <kbd>enter</kbd>.</span></span>

   <span data-ttu-id="d6691-137">Im Fenster **Direkt** werden der Wert der Zeichenfolgenvariablen und die Eigenschaften des <xref:System.DateTime>-Werts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6691-137">The **Immediate** window displays the new value of the string variable and the properties of the <xref:System.DateTime> value.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window.png" alt-text="Fenster „Direkt“ in Visual Studio":::

   <span data-ttu-id="d6691-139">Im Fenster **Lokale Variablen** werden die Werte von Variablen angezeigt, die in der gerade ausgeführten Methode definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d6691-139">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span> <span data-ttu-id="d6691-140">Die Werte der Variablen, die Sie gerade geändert haben, werden im Fenster **Lokale Variablen** aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d6691-140">The values of the variables that you just changed are updated in the **Locals** window.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/locals-window.png" alt-text="Fenster „Lokale Variablen“ in Visual Studio":::

1. <span data-ttu-id="d6691-142">Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>), um das Debuggen fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="d6691-142">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to continue debugging.</span></span>

   <span data-ttu-id="d6691-143">Die im Terminal gezeigten Werte entsprechen Ihren Änderungen im Fenster **Direkt**.</span><span class="sxs-lookup"><span data-stu-id="d6691-143">The values displayed in the terminal correspond to the changes you made in the **Immediate** window.</span></span>

   <span data-ttu-id="d6691-144">Wenn das Terminal nicht angezeigt wird, wählen Sie auf der unteren Navigationsleiste **Terminal – HelloWorld** aus.</span><span class="sxs-lookup"><span data-stu-id="d6691-144">If you don't see the Terminal, select **Terminal - HelloWorld** in the bottom navigation bar.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/terminal-hello-world.png" alt-text="„Terminal – HelloWorld“ auf der unteren Navigationsleiste":::

1. <span data-ttu-id="d6691-146">Drücken Sie eine beliebige Taste, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="d6691-146">Press any key to exit the program.</span></span>

1. <span data-ttu-id="d6691-147">Schließen Sie das Terminalfenster.</span><span class="sxs-lookup"><span data-stu-id="d6691-147">Close the terminal window.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="d6691-148">Festlegen eines bedingten Breakpoints</span><span class="sxs-lookup"><span data-stu-id="d6691-148">Set a conditional breakpoint</span></span>

<span data-ttu-id="d6691-149">Das Programm zeigt eine Zeichenfolge an, die der Benutzer eingibt.</span><span class="sxs-lookup"><span data-stu-id="d6691-149">The program displays a string that the user enters.</span></span> <span data-ttu-id="d6691-150">Aber was geschieht, wenn der Benutzer gar nichts eingibt?</span><span class="sxs-lookup"><span data-stu-id="d6691-150">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="d6691-151">Sie können dies mit einem nützlichen Debugfeature testen, das als *Bedingter Breakpoint* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="d6691-151">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="d6691-152">Klicken Sie bei gedrückter <kbd>CTRL</kbd>-Taste auf den roten Punkt, der den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="d6691-152"><kbd>ctrl</kbd>-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="d6691-153">Wählen Sie im Kontextmenü **Haltepunkt bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d6691-153">In the context menu, select **Edit Breakpoint**.</span></span>

1. <span data-ttu-id="d6691-154">Geben Sie im Dialogfeld **Haltepunkt bearbeiten** den folgenden Code in das folgende Feld ein **Und die folgende Bedingung „True“ ist**, und wählen Sie **Anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="d6691-154">In the **Edit Breakpoint** dialog, enter the following code in the field that follows **And the following condition is true**, and select **Apply**.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-settings.png" alt-text="Editor mit dem Panel für Haltepunkteinstellungen":::

   <span data-ttu-id="d6691-156">Jedes Mal, wenn der Breakpoint erreicht wird, ruft der Debugger die `String.IsNullOrEmpty(name)`-Methode auf, und die Ausführung wird nur in dieser Zeile unterbrochen, wenn der Methodenaufruf `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d6691-156">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="d6691-157">Anstelle eines bedingten Ausdrucks können Sie eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung mit der angegebenen Häufigkeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6691-157">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span>

1. <span data-ttu-id="d6691-158">Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>), um das Debuggen zu starten.</span><span class="sxs-lookup"><span data-stu-id="d6691-158">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start debugging.</span></span>

1. <span data-ttu-id="d6691-159">Drücken Sie im Terminalfenster die <kbd>EINGABETASTE</kbd>, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="d6691-159">In the terminal window, press <kbd>enter</kbd> when prompted to enter your name.</span></span>

   <span data-ttu-id="d6691-160">Da die angegebene Bedingung erfüllt wurde (`name` ist entweder `null` oder <xref:System.String.Empty?displayProperty=nameWithType>), endet die Ausführung des Programms, wenn der Haltepunkt erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="d6691-160">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint.</span></span>

1. <span data-ttu-id="d6691-161">Wählen Sie das Fenster **Lokale Variablen** aus, das die Werte der lokalen Variablen der aktuell ausgeführten Methode anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d6691-161">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="d6691-162">In diesem Fall ist `Main` die derzeit ausgeführte Methode.</span><span class="sxs-lookup"><span data-stu-id="d6691-162">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="d6691-163">Stellen Sie sicher, dass die Variable `name` den Wert `""`, d. h. <xref:System.String.Empty?displayProperty=nameWithType>, hat.</span><span class="sxs-lookup"><span data-stu-id="d6691-163">Observe that the value of the `name` variable is `""`, that is, <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="d6691-164">Sie können auch erkennen, dass der Wert eine leere Zeichenfolge ist, indem Sie den Namen der Variablen `name` in das Fenster **Direkt** eingeben und die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="d6691-164">You can also see that the value is an empty string by entering the `name` variable name in the **Immediate** window and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window-output.png" alt-text="Fenster „Direkt“ mit leerer Zeichenfolge als Name":::

1. <span data-ttu-id="d6691-166">Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>), um das Debuggen fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="d6691-166">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to continue debugging.</span></span>

1. <span data-ttu-id="d6691-167">Drücken Sie im Terminalfenster eine beliebige Taste, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="d6691-167">In the terminal window, press any key to exit the program.</span></span>

1. <span data-ttu-id="d6691-168">Schließen Sie das Terminalfenster.</span><span class="sxs-lookup"><span data-stu-id="d6691-168">Close the terminal window.</span></span>

1. <span data-ttu-id="d6691-169">Löschen Sie den Haltepunkt durch Klicken auf den Punkt am linken Rand des Codefensters.</span><span class="sxs-lookup"><span data-stu-id="d6691-169">Clear the breakpoint by clicking on the red dot in the left margin of the code window.</span></span> <span data-ttu-id="d6691-170">Eine andere Möglichkeit, einen Haltepunkt zu löschen, besteht darin, **Debuggen > Haltepunkt umschalten** auszuwählen, während die Codezeile ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d6691-170">Another way to clear a breakpoint is by choosing **Run > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="d6691-171">Schrittweises Ausführen eines Programms</span><span class="sxs-lookup"><span data-stu-id="d6691-171">Step through a program</span></span>

<span data-ttu-id="d6691-172">Mit Visual Studio können Sie ein Programm auch zeilenweise durchlaufen und die Ausführung jeder einzelnen Zeile überwachen.</span><span class="sxs-lookup"><span data-stu-id="d6691-172">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="d6691-173">Normalerweise würden Sie einen Breakpoint festlegen und den Programmablauf in einem kleinen Teil des Programmcodes verfolgen.</span><span class="sxs-lookup"><span data-stu-id="d6691-173">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="d6691-174">Da dieses Programm klein ist, können Sie das gesamte Programm schrittweise durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="d6691-174">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="d6691-175">Legen Sie einen Haltepunkt auf der geschweiften Klammer fest, die den Anfang der `Main`-Methode markiert (drücken Sie <kbd>Befehl</kbd>+<kbd>\\</kbd>).</span><span class="sxs-lookup"><span data-stu-id="d6691-175">Set a breakpoint on the curly brace that marks the start of the `Main` method (press <kbd>command</kbd>+<kbd>\\</kbd>).</span></span>

1. <span data-ttu-id="d6691-176">Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>), um das Debuggen zu starten.</span><span class="sxs-lookup"><span data-stu-id="d6691-176">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start debugging.</span></span>

   <span data-ttu-id="d6691-177">Visual Studio wird in der Zeile mit dem Haltepunkt angehalten.</span><span class="sxs-lookup"><span data-stu-id="d6691-177">Visual Studio stops on the line with the breakpoint.</span></span>

1. <span data-ttu-id="d6691-178">Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>UMSCHALT</kbd>+<kbd>BEFEHL</kbd>+<kbd>I</kbd>), oder wählen Sie **Ausführen** > **Einzelschritt**, um eine Zeile weiterzugehen.</span><span class="sxs-lookup"><span data-stu-id="d6691-178">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>) or select **Run** > **Step Into** to advance one line.</span></span>

   <span data-ttu-id="d6691-179">Visual Studio markiert einen Pfeil neben der nächsten Zeile der Ausführung und zeigt diesen an.</span><span class="sxs-lookup"><span data-stu-id="d6691-179">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/step-into-method.png" alt-text="Visual Studio-Methode „Einzelschritt“":::

   <span data-ttu-id="d6691-181">An diesem Punkt wird im Fenster **Lokale Variablen** angezeigt, dass das `args`-Array leer ist und `name` und `date` Standardwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d6691-181">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="d6691-182">Darüber hinaus hat Visual Studio ein leeres Terminal geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d6691-182">In addition, Visual Studio has opened a blank terminal.</span></span>

1. <span data-ttu-id="d6691-183">Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>UMSCHALT</kbd>+<kbd>Befehl</kbd>+<kbd>I</kbd>).</span><span class="sxs-lookup"><span data-stu-id="d6691-183">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="d6691-184">Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `name` enthält.</span><span class="sxs-lookup"><span data-stu-id="d6691-184">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="d6691-185">Das Fenster **Lokale Variablen** zeigt, dass `name` den Wert `null` aufweist, und das Konsolenfenster zeigt die Zeichenfolge „What is your name?“ an.</span><span class="sxs-lookup"><span data-stu-id="d6691-185">The **Locals** window shows that `name` is `null`, and the terminal displays the string "What is your name?".</span></span>

1. <span data-ttu-id="d6691-186">Reagieren Sie auf die Eingabeaufforderung, indem Sie eine Zeichenfolge in das Konsolenfenster eingeben und die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="d6691-186">Respond to the prompt by entering a string in the console window and pressing <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="d6691-187">Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>UMSCHALT</kbd>+<kbd>Befehl</kbd>+<kbd>I</kbd>).</span><span class="sxs-lookup"><span data-stu-id="d6691-187">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="d6691-188">Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `date` enthält.</span><span class="sxs-lookup"><span data-stu-id="d6691-188">Visual Studio highlights the statement that includes the `date` variable assignment.</span></span> <span data-ttu-id="d6691-189">Das Fenster **Lokale Variablen** zeigt den vom Aufruf der Methode <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> zurückgegebenen Wert an.</span><span class="sxs-lookup"><span data-stu-id="d6691-189">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d6691-190">Im Terminal wird die Zeichenfolge angezeigt, die Sie an der Eingabeaufforderung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="d6691-190">The terminal displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="d6691-191">Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>UMSCHALT</kbd>+<kbd>Befehl</kbd>+<kbd>I</kbd>).</span><span class="sxs-lookup"><span data-stu-id="d6691-191">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="d6691-192">Das Fenster **Lokale Variablen** zeigt den Wert der Variablen `date` nach der Zuweisung aus der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d6691-192">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d6691-193">Das Terminal ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="d6691-193">The terminal is unchanged.</span></span>

1. <span data-ttu-id="d6691-194">Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>UMSCHALT</kbd>+<kbd>Befehl</kbd>+<kbd>I</kbd>).</span><span class="sxs-lookup"><span data-stu-id="d6691-194">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="d6691-195">Visual Studio ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d6691-195">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d6691-196">Das Terminal zeigt die formatierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="d6691-196">The terminal displays the formatted string.</span></span>

1. <span data-ttu-id="d6691-197">Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>u</kbd> (<kbd>UMSCHALT</kbd>+<kbd>BEFEHL</kbd>+<kbd>U</kbd>), oder wählen Sie **Ausführen** > **Rücksprung** aus.</span><span class="sxs-lookup"><span data-stu-id="d6691-197">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>U</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>U</kbd>) or select **Run** > **Step Out**.</span></span>

   <span data-ttu-id="d6691-198">Das Terminal zeigt eine Meldung an und wartet, bis Sie eine Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="d6691-198">The terminal displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="d6691-199">Drücken Sie eine beliebige Taste, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="d6691-199">Press any key to exit the program.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="d6691-200">Verwenden der Releasebuildkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d6691-200">Use Release build configuration</span></span>

<span data-ttu-id="d6691-201">Nachdem Sie die Debugversion der Anwendung getestet haben, sollten Sie auch die Releaseversion kompilieren und testen.</span><span class="sxs-lookup"><span data-stu-id="d6691-201">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="d6691-202">Die endgültige Releaseversion umfasst Compileroptimierungen, die das Verhalten einer Anwendung beeinträchtigen können.</span><span class="sxs-lookup"><span data-stu-id="d6691-202">The Release version incorporates compiler optimizations that can negatively affect the behavior of an application.</span></span> <span data-ttu-id="d6691-203">Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z. B. Racebedingungen in Multithreadanwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6691-203">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="d6691-204">Um die Releaseversion Ihrer Konsolenanwendung zu erstellen und zu testen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d6691-204">To build and test the Release version of the console application, do the following steps:</span></span>

1. <span data-ttu-id="d6691-205">Ändern Sie die Buildkonfiguration auf der Symbolleiste von **Debug** in **Release**.</span><span class="sxs-lookup"><span data-stu-id="d6691-205">Change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Visual Studio-Standardsymbolleiste mit hervorgehobenem Debug":::

1. <span data-ttu-id="d6691-207">Drücken Sie <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>OPTION</kbd>+<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>) zum Ausführen ohne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="d6691-207">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run without debugging.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d6691-208">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d6691-208">Next steps</span></span>

<span data-ttu-id="d6691-209">In diesem Tutorial haben Sie Debugtools von Visual Studio verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6691-209">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="d6691-210">Im nächsten Tutorial veröffentlichen Sie eine bereitstellbare Version der App.</span><span class="sxs-lookup"><span data-stu-id="d6691-210">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d6691-211">Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="d6691-211">Publish a .NET Core console application with Visual Studio for Mac</span></span>](publishing-with-visual-studio-mac.md)
