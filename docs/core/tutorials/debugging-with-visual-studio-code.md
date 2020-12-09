---
title: Debuggen einer .NET-Konsolenanwendung mit Visual Studio Code
description: Erfahren Sie, wie Sie eine .NET-Konsolen-App mit Visual Studio Code debuggen.
ms.date: 05/26/2020
ms.openlocfilehash: 7215ed4a93b31ebac313c04708734667148c4e02
ms.sourcegitcommit: 30fef5b0ed76e334377d28fa8e80159b29353e10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "96556108"
---
# <a name="tutorial-debug-a-net-console-application-using-visual-studio-code"></a><span data-ttu-id="a9705-103">Tutorial: Debuggen einer .NET-Konsolenanwendung mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9705-103">Tutorial: Debug a .NET console application using Visual Studio Code</span></span>

<span data-ttu-id="a9705-104">In diesem Tutorial werden die Debugtools vorgestellt, die in Visual Studio Code zum Arbeiten mit .NET-Apps verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a9705-104">This tutorial introduces the debugging tools available in Visual Studio Code for working with .NET apps.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9705-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a9705-105">Prerequisites</span></span>

- <span data-ttu-id="a9705-106">Dieses Tutorial kann mit der Konsolen-App durchgeführt werden, die Sie in [Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio Code](with-visual-studio-code.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9705-106">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="a9705-107">Verwenden der Debugbuildkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a9705-107">Use Debug build configuration</span></span>

<span data-ttu-id="a9705-108">*Debug* und *Release* sind in .NET Core integrierte Buildkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="a9705-108">*Debug* and *Release* are .NET Core's built-in build configurations.</span></span> <span data-ttu-id="a9705-109">Sie verwenden die Debugbuildkonfiguration zum Debuggen und die Releasekonfiguration für die endgültige Releaseverteilung.</span><span class="sxs-lookup"><span data-stu-id="a9705-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="a9705-110">In der Debugkonfiguration wird ein Programm mit vollständigen symbolischen Debuginformationen und ohne Optimierung kompiliert.</span><span class="sxs-lookup"><span data-stu-id="a9705-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="a9705-111">Die Optimierung gestaltet das Debuggen etwas schwieriger, da die Beziehung zwischen Quellcode und generierten Anweisungen komplexer ist.</span><span class="sxs-lookup"><span data-stu-id="a9705-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="a9705-112">Die Releasekonfiguration eines Programms verfügt über keine symbolischen Debuginformationen und wird vollständig optimiert.</span><span class="sxs-lookup"><span data-stu-id="a9705-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

<span data-ttu-id="a9705-113">Standardmäßig wird in den Visual Studio Code-Starteinstellungen die Debugbuildkonfiguration verwendet, sodass Sie diese Einstellung vor dem Debuggen nicht ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="a9705-113">By default, Visual Studio Code launch settings use the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="a9705-114">Starten Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a9705-114">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="a9705-115">Öffnen Sie den Ordner des Projekts, das Sie in [Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio Code](with-visual-studio-code.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a9705-115">Open the folder of the project that you created in [Create a .NET console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="a9705-116">Haltepunkt festlegen</span><span class="sxs-lookup"><span data-stu-id="a9705-116">Set a breakpoint</span></span>

<span data-ttu-id="a9705-117">Ein *Haltepunkt* unterbricht vorübergehend die Ausführung der Anwendung, bevor die Zeile mit dem Haltepunkt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9705-117">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="a9705-118">Öffnen Sie die Datei *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="a9705-118">Open the *Program.cs* file.</span></span>

1. <span data-ttu-id="a9705-119">Legen Sie einen *Breakpoint* in der Zeile fest, in der der Name, das Datum und die Uhrzeit angezeigt werden, indem Sie auf den linken Rand des Codefensters klicken.</span><span class="sxs-lookup"><span data-stu-id="a9705-119">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window.</span></span> <span data-ttu-id="a9705-120">Der linke Rand befindet sich links von den Zeilennummern.</span><span class="sxs-lookup"><span data-stu-id="a9705-120">The left margin is to the left of the line numbers.</span></span> <span data-ttu-id="a9705-121">Andere Möglichkeiten zum Festlegen eines Breakpoints bestehen darin, <kbd>F9</kbd> zu drücken oder **Ausführen** > **Haltepunkt umschalten** aus dem Menü auszuwählen, während die Codezeile ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a9705-121">Other ways to set a breakpoint are by pressing <kbd>F9</kbd> or choosing **Run** > **Toggle Breakpoint** from the menu while the line of code is selected.</span></span>

   <span data-ttu-id="a9705-122">Visual Studio Code gibt die Zeile an, in der der Haltepunkt festgelegt ist, indem ein roter Punkt am linken Rand angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a9705-122">Visual Studio Code indicates the line on which the breakpoint is set by displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="Festgelegter Haltepunkt":::

## <a name="set-up-for-terminal-input"></a><span data-ttu-id="a9705-124">Einrichtung für Terminaleingabe</span><span class="sxs-lookup"><span data-stu-id="a9705-124">Set up for terminal input</span></span>

<span data-ttu-id="a9705-125">Der Breakpoint befindet sich hinter einem `Console.ReadLine`-Methodenaufruf.</span><span class="sxs-lookup"><span data-stu-id="a9705-125">The breakpoint is located after a `Console.ReadLine` method call.</span></span> <span data-ttu-id="a9705-126">Die **Debugkonsole** akzeptiert keine Terminaleingaben für ein aktuell ausgeführtes Programm.</span><span class="sxs-lookup"><span data-stu-id="a9705-126">The **Debug Console** doesn't accept terminal input for a running program.</span></span> <span data-ttu-id="a9705-127">Zum Verarbeiten von Terminaleingaben beim Debuggen können Sie das integrierte Terminal (eines der Visual Studio Code-Fenster) oder ein externes Terminal verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9705-127">To handle terminal input while debugging, you can use the integrated terminal (one of the Visual Studio Code windows) or an external terminal.</span></span> <span data-ttu-id="a9705-128">In diesem Tutorial verwenden Sie das integrierte Terminal.</span><span class="sxs-lookup"><span data-stu-id="a9705-128">For this tutorial, you use the integrated terminal.</span></span>

1. <span data-ttu-id="a9705-129">Öffnen Sie *.vscode/launch.json*.</span><span class="sxs-lookup"><span data-stu-id="a9705-129">Open *.vscode/launch.json*.</span></span>

1. <span data-ttu-id="a9705-130">Ändern Sie die `console`-Einstellung von `internalConsole` in `integratedTerminal`:</span><span class="sxs-lookup"><span data-stu-id="a9705-130">Change the `console` setting from `internalConsole` to `integratedTerminal`:</span></span>

   ```json
   "console": "integratedTerminal",
   ```

1. <span data-ttu-id="a9705-131">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="a9705-131">Save your changes.</span></span>

## <a name="start-debugging"></a><span data-ttu-id="a9705-132">Debugging starten</span><span class="sxs-lookup"><span data-stu-id="a9705-132">Start debugging</span></span>

1. <span data-ttu-id="a9705-133">Öffnen Sie die Debugansicht, indem Sie im Menü auf der linken Seite das Debugsymbol auswählen.</span><span class="sxs-lookup"><span data-stu-id="a9705-133">Open the Debug view by selecting the Debugging icon on the left side menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Öffnen der Registerkarte „Debuggen“ in Visual Studio Code":::

1. <span data-ttu-id="a9705-135">Wählen Sie den grünen Pfeil am oberen Rand des Bereichs neben **.NET Core starten (Konsole)** aus.</span><span class="sxs-lookup"><span data-stu-id="a9705-135">Select the green arrow at the top of the pane, next to **.NET Core Launch (console)**.</span></span> <span data-ttu-id="a9705-136">Andere Möglichkeiten zum Starten des Programms im Debugmodus besteht darin, <kbd>F5</kbd> zu drücken oder **Ausführen** > **Debuggen starten** aus dem Menü auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a9705-136">Other ways to start the program in debugging mode are by pressing <kbd>F5</kbd> or choosing **Run** > **Start Debugging** from the menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="Starten des Debuggens":::

1. <span data-ttu-id="a9705-138">Wählen Sie die Registerkarte **Terminal** aus, um die Eingabeaufforderung „Wie heißen Sie?“</span><span class="sxs-lookup"><span data-stu-id="a9705-138">Select the **Terminal** tab to see the "What is your name?"</span></span> <span data-ttu-id="a9705-139">anzuzeigen, die das Programm anzeigt, bevor auf eine Antwort gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="a9705-139">prompt that the program displays before waiting for a response.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="Auswählen der Registerkarte „Terminal“":::

1. <span data-ttu-id="a9705-141">Geben Sie eine Zeichenfolge im Fenster **Terminal** als Antwort auf die Aufforderung zur Eingabe eines Namens ein, und drücken Sie dann die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-141">Enter a string in the **Terminal** window in response to the prompt for a name, and then press <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="a9705-142">Die Ausführung des Programms endet, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9705-142">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="a9705-143">Im Abschnitt **Lokal** des Fensters **Variablen** werden die Werte von Variablen angezeigt, die in der aktuell ausgeführten Methode definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a9705-143">The **Locals** section of the **Variables** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="Breakpointtreffer, der lokale Variablen anzeigt":::

## <a name="use-the-debug-console"></a><span data-ttu-id="a9705-145">Verwenden der Debugging-Konsole</span><span class="sxs-lookup"><span data-stu-id="a9705-145">Use the Debug Console</span></span>

<span data-ttu-id="a9705-146">Das Fenster **Debugging-Konsole** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen.</span><span class="sxs-lookup"><span data-stu-id="a9705-146">The **Debug Console** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="a9705-147">Sie können den Wert von Variablen ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt.</span><span class="sxs-lookup"><span data-stu-id="a9705-147">You can change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="a9705-148">Wählen Sie die Registerkarte **Debugging-Konsole** aus.</span><span class="sxs-lookup"><span data-stu-id="a9705-148">Select the **Debug Console** tab.</span></span>

1. <span data-ttu-id="a9705-149">Geben Sie `name = "Gracie"` an der Eingabeaufforderung am unteren Rand des Fensters **Debugging-Konsole** ein, und drücken Sie <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-149">Enter `name = "Gracie"` at the prompt at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="Ändern von Variablenwerten":::

1. <span data-ttu-id="a9705-151">Geben Sie `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` am unteren Rand des Fensters **Debugging-Konsole** ein, und drücken Sie <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-151">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="a9705-152">Im Fenster **Variablen** werden die neuen Werte der Variablen `name` und `date` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9705-152">The **Variables** window displays the new values of the `name` and `date` variables.</span></span>

1. <span data-ttu-id="a9705-153">Setzen Sie die Ausführung des Programms durch Auswählen der Schaltfläche **Fortsetzen** in der Symbolleiste fort.</span><span class="sxs-lookup"><span data-stu-id="a9705-153">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="a9705-154">Eine weitere Möglichkeit zum Fortsetzen besteht darin, <kbd>F5</kbd> zu drücken.</span><span class="sxs-lookup"><span data-stu-id="a9705-154">Another way to continue is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="Fortsetzen des Debuggens":::

1. <span data-ttu-id="a9705-156">Klicken Sie erneut auf die Registerkarte **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="a9705-156">Select the **Terminal** tab again.</span></span>

   <span data-ttu-id="a9705-157">Die im Konsolenfenster angezeigten Werte entsprechen den Änderungen im Fenster **Debugging-Konsole**.</span><span class="sxs-lookup"><span data-stu-id="a9705-157">The values displayed in the console window correspond to the changes you made in the **Debug Console**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="Terminalfenster mit den eingegebenen Werten":::

1. <span data-ttu-id="a9705-159">Drücken Sie eine beliebige Taste, um die Anwendung und das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a9705-159">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="a9705-160">Festlegen eines bedingten Breakpoints</span><span class="sxs-lookup"><span data-stu-id="a9705-160">Set a conditional breakpoint</span></span>

<span data-ttu-id="a9705-161">Das Programm zeigt die Zeichenfolge an, die der Benutzer eingibt.</span><span class="sxs-lookup"><span data-stu-id="a9705-161">The program displays the string that the user enters.</span></span> <span data-ttu-id="a9705-162">Aber was geschieht, wenn der Benutzer gar nichts eingibt?</span><span class="sxs-lookup"><span data-stu-id="a9705-162">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="a9705-163">Sie können dies mit einem nützlichen Debugfeature testen, das als *Bedingter Breakpoint* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a9705-163">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="a9705-164">Klicken Sie mit der rechten Maustaste (Klicken bei gedrückter <kbd>CTRL</kbd>-TASTE unter macOS) auf den roten Punkt, der den Breakpoint darstellt.</span><span class="sxs-lookup"><span data-stu-id="a9705-164">Right-click (<kbd>Ctrl</kbd>-click on macOS) on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="a9705-165">Wählen Sie im Kontextmenü **Breakpoint bearbeiten** aus, um ein Dialogfeld zu öffnen, in dem Sie einen bedingten Ausdruck eingeben können.</span><span class="sxs-lookup"><span data-stu-id="a9705-165">In the context menu, select **Edit Breakpoint** to open a dialog that lets you enter a conditional expression.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="Kontextmenü des Breakpoints":::

1. <span data-ttu-id="a9705-167">Wählen Sie in der Dropdownliste `Expression` aus, geben Sie den folgenden bedingten Ausdruck ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-167">Select `Expression` in the drop-down, enter the following conditional expression, and press <kbd>Enter</kbd>.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="Eingeben eines bedingten Ausdrucks":::

   <span data-ttu-id="a9705-169">Jedes Mal, wenn der Breakpoint erreicht wird, ruft der Debugger die `String.IsNullOrEmpty(name)`-Methode auf, und die Ausführung wird nur in dieser Zeile unterbrochen, wenn der Methodenaufruf `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a9705-169">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="a9705-170">Anstelle eines bedingten Ausdrucks können Sie eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung mit der angegebenen Häufigkeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9705-170">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span> <span data-ttu-id="a9705-171">Eine weitere Option ist das Angeben einer *Filterbedingung*, wodurch die Ausführung des Programms auf Basis von Attributen wie Threadbezeichner, Prozessname oder Threadname unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="a9705-171">Another option is to specify a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="a9705-172">Starten Sie das Programm im Debugmodus, indem Sie <kbd>F5</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="a9705-172">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="a9705-173">Drücken Sie auf der Registerkarte **Terminal** die <kbd>EINGABETASTE</kbd>, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="a9705-173">In the **Terminal** tab, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

   <span data-ttu-id="a9705-174">Da die angegebene Bedingung erfüllt wurde (`name` ist entweder `null` oder <xref:System.String.Empty?displayProperty=nameWithType>), endet die Ausführung des Programms, wenn sie den Breakpoint erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9705-174">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

   <span data-ttu-id="a9705-175">Im Fenster **Variablen** wird angezeigt, dass der Wert der `name`-Variablen `""` oder <xref:System.String.Empty?displayProperty=nameWithType> ist.</span><span class="sxs-lookup"><span data-stu-id="a9705-175">The **Variables** window shows that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="a9705-176">Bestätigen Sie, dass der Wert eine leere Zeichenfolge ist, indem Sie die folgende Anweisung an der Eingabeaufforderung **Debugging-Konsole** eingeben und dann die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="a9705-176">Confirm the value is an empty string by entering the following statement at the **Debug Console** prompt and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="a9705-177">Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="a9705-177">The result is `true`.</span></span>

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="Debugging-Konsole, die einen Wert TRUE zurückgibt, nachdem die Anweisung ausgeführt wurde":::

1. <span data-ttu-id="a9705-179">Wählen Sie die Schaltfläche **Fortfahren** auf der Symbolleiste, um die Ausführung des Programms fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="a9705-179">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="a9705-180">Wählen Sie die Registerkarte **Terminal** aus, und drücken Sie eine beliebige Taste, um das Programm und das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a9705-180">Select the **Terminal** tab, and press any key to exit the program and stop debugging.</span></span>

1. <span data-ttu-id="a9705-181">Löschen Sie den Breakpoint durch Klicken auf den Punkt am linken Rand des Codefensters.</span><span class="sxs-lookup"><span data-stu-id="a9705-181">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="a9705-182">Andere Möglichkeiten zum Löschen eines Haltepunkts bestehen darin, <kbd>F9</kbd> zu drücken oder bei ausgewählter Codezeile im Menü **Ausführen > Haltepunkt umschalten** zu wählen.</span><span class="sxs-lookup"><span data-stu-id="a9705-182">Other ways to clear a breakpoint are by pressing <kbd>F9</kbd> or choosing **Run > Toggle Breakpoint** from the menu while the line of code is selected.</span></span>

1. <span data-ttu-id="a9705-183">Wenn Sie eine Warnung erhalten, dass die Breakpointbedingung verloren geht, wählen Sie **Breakpoint entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="a9705-183">If you get a warning that the breakpoint condition will be lost, select **Remove Breakpoint**.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="a9705-184">Schrittweises Ausführen eines Programms</span><span class="sxs-lookup"><span data-stu-id="a9705-184">Step through a program</span></span>

<span data-ttu-id="a9705-185">Mit Visual Studio Code können Sie ein Programm auch zeilenweise durchlaufen und seine Ausführung überwachen.</span><span class="sxs-lookup"><span data-stu-id="a9705-185">Visual Studio Code also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="a9705-186">Normalerweise würden Sie einen Breakpoint festlegen und den Programmablauf in einem kleinen Teil des Programmcodes verfolgen.</span><span class="sxs-lookup"><span data-stu-id="a9705-186">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="a9705-187">Da dieses Programm klein ist, können Sie das gesamte Programm schrittweise durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a9705-187">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="a9705-188">Legen Sie einen Breakpoint bei der öffnenden geschweiften Klammer der `Main`-Methode fest.</span><span class="sxs-lookup"><span data-stu-id="a9705-188">Set a breakpoint on the opening curly brace of the `Main` method.</span></span>

1. <span data-ttu-id="a9705-189">Drücken Sie die Taste <kbd>F5</kbd> , um mit dem Debuggen zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="a9705-189">Press <kbd>F5</kbd> to start debugging.</span></span>

   <span data-ttu-id="a9705-190">Visual Studio Code hebt die Breakpointzeile hervor.</span><span class="sxs-lookup"><span data-stu-id="a9705-190">Visual Studio Code highlights the breakpoint line.</span></span>

   <span data-ttu-id="a9705-191">An diesem Punkt wird im Fenster **Variablen** angezeigt, dass das `args`-Array leer ist und `name` und `date` Standardwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a9705-191">At this point, the **Variables** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span>

1. <span data-ttu-id="a9705-192">Wählen Sie **Ausführen** > **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-192">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="Schaltfläche „Einzelschritt“":::

   <span data-ttu-id="a9705-194">Visual Studio Code hebt die nächste Zeile hervor.</span><span class="sxs-lookup"><span data-stu-id="a9705-194">Visual Studio Code highlights the next line.</span></span>

1. <span data-ttu-id="a9705-195">Wählen Sie **Ausführen** > **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-195">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a9705-196">Visual Studio Code führt die `Console.WriteLine` für die Aufforderung zur Eingabe des Namens aus und hebt die nächste Ausführungszeile hervor.</span><span class="sxs-lookup"><span data-stu-id="a9705-196">Visual Studio Code executes the `Console.WriteLine` for the name prompt and highlights the next line of execution.</span></span> <span data-ttu-id="a9705-197">Die nächste Zeile ist die `Console.ReadLine` für den `name`.</span><span class="sxs-lookup"><span data-stu-id="a9705-197">The next line is the `Console.ReadLine` for the `name`.</span></span> <span data-ttu-id="a9705-198">Das Fenster **Variablen** ist unverändert, und die Registerkarte **Terminal** zeigt die Eingabeaufforderung „Wie heißen Sie?“</span><span class="sxs-lookup"><span data-stu-id="a9705-198">The **Variables** window is unchanged, and the **Terminal** tab shows the "What is your name?"</span></span> <span data-ttu-id="a9705-199">an.</span><span class="sxs-lookup"><span data-stu-id="a9705-199">prompt.</span></span>

1. <span data-ttu-id="a9705-200">Wählen Sie **Ausführen** > **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-200">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a9705-201">Visual Studio hebt die Variablenzuweisung `name` hervor.</span><span class="sxs-lookup"><span data-stu-id="a9705-201">Visual Studio highlights the `name` variable assignment.</span></span> <span data-ttu-id="a9705-202">Im Fenster **Variablen** wird angezeigt, dass `name` noch immer `null`ist.</span><span class="sxs-lookup"><span data-stu-id="a9705-202">The **Variables** window shows that `name` is still `null`.</span></span>

1. <span data-ttu-id="a9705-203">Reagieren Sie auf die Eingabeaufforderung, indem Sie eine Zeichenfolge auf der Registerkarte „Terminal“ eingeben und die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="a9705-203">Respond to the prompt by entering a string in the Terminal tab and pressing <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="a9705-204">Auf der Registerkarte **Terminal** wird die Zeichenfolge während der Eingabe möglicherweise nicht angezeigt, aber die <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>-Methode erfasst Ihre Eingabe.</span><span class="sxs-lookup"><span data-stu-id="a9705-204">The **Terminal** tab might not display the string you enter while you're entering it, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will capture your input.</span></span>

1. <span data-ttu-id="a9705-205">Wählen Sie **Ausführen** > **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-205">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a9705-206">Visual Studio Code hebt die Variablenzuweisung `date` hervor.</span><span class="sxs-lookup"><span data-stu-id="a9705-206">Visual Studio Code highlights the `date` variable assignment.</span></span> <span data-ttu-id="a9705-207">Das Fenster **Variablen** zeigt den vom Aufruf der Methode <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> zurückgegebenen Wert an.</span><span class="sxs-lookup"><span data-stu-id="a9705-207">The **Variables** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a9705-208">Auf der Registerkarte **Terminal** wird die Zeichenfolge angezeigt, die Sie an der Eingabeaufforderung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a9705-208">The **Terminal** tab displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="a9705-209">Wählen Sie **Ausführen** > **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-209">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a9705-210">Das Fenster **Variablen** zeigt den Wert der Variablen `date` nach der Zuweisung aus der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="a9705-210">The **Variables** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span>

1. <span data-ttu-id="a9705-211">Wählen Sie **Ausführen** > **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-211">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="a9705-212">Visual Studio Code ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="a9705-212">Visual Studio Code calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a9705-213">Das Konsolenfenster zeigt die formatierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="a9705-213">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="a9705-214">Wählen Sie **Ausführen** > **Ausführen bis Rücksprung** aus, oder drücken Sie <kbd>UMSCHALT</kbd>+<kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a9705-214">Select **Run** > **Step Out** or press <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="Schaltfläche „Ausführen bis Rücksprung“":::

1. <span data-ttu-id="a9705-216">Wählen Sie die Registerkarte **Terminal** aus.</span><span class="sxs-lookup"><span data-stu-id="a9705-216">Select the **Terminal** tab.</span></span>

   <span data-ttu-id="a9705-217">Das Terminal zeigt „Drücken Sie zum Beenden eine beliebige Taste“ an.</span><span class="sxs-lookup"><span data-stu-id="a9705-217">The terminal displays "Press any key to exit..."</span></span>

1. <span data-ttu-id="a9705-218">Drücken Sie eine beliebige Taste, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a9705-218">Press any key to exit the program.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="a9705-219">Verwenden der Releasebuildkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a9705-219">Use Release build configuration</span></span>

<span data-ttu-id="a9705-220">Nachdem Sie die Debugversion der Anwendung getestet haben, sollten Sie auch die Releaseversion kompilieren und testen.</span><span class="sxs-lookup"><span data-stu-id="a9705-220">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="a9705-221">Die Releaseversion umfasst Compileroptimierungen, die das Verhalten einer Anwendung beeinträchtigen können.</span><span class="sxs-lookup"><span data-stu-id="a9705-221">The Release version incorporates compiler optimizations that can affect the behavior of an application.</span></span> <span data-ttu-id="a9705-222">Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z. B. Racebedingungen in Multithreadanwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9705-222">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="a9705-223">Um die Releaseversion Ihrer Konsolenanwendung zu erstellen und zu testen, öffnen Sie das **Terminal** und führen den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a9705-223">To build and test the Release version of your console application, open the **Terminal** and run the following command:</span></span>

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a><span data-ttu-id="a9705-224">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a9705-224">Additional resources</span></span>

* [<span data-ttu-id="a9705-225">Debuggen in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9705-225">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a><span data-ttu-id="a9705-226">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a9705-226">Next steps</span></span>

<span data-ttu-id="a9705-227">In diesem Tutorial haben Sie Debugtools von Visual Studio Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9705-227">In this tutorial, you used Visual Studio Code debugging tools.</span></span> <span data-ttu-id="a9705-228">Im nächsten Tutorial veröffentlichen Sie eine bereitstellbare Version der App.</span><span class="sxs-lookup"><span data-stu-id="a9705-228">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a9705-229">Veröffentlichen einer .NET-Konsolenanwendung mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9705-229">Publish a .NET console application using Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
