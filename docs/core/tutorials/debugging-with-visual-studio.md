---
title: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio
description: Erfahren Sie, wie Sie eine .NET Core-Konsolen-App mit Visual Studio debuggen.
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4bd2a8a0e4b3cea55e209306dd3788552e4b61f3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005413"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="437d2-103">Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="437d2-103">Tutorial: Debug a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="437d2-104">In diesem Tutorial werden die Debugtools vorgestellt, die in Visual Studio verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="437d2-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="437d2-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="437d2-105">Prerequisites</span></span>

- <span data-ttu-id="437d2-106">Dieses Tutorial funktioniert mit der Konsolen-App, die Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio Code 2019](with-visual-studio.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="437d2-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="debug-build-configuration"></a><span data-ttu-id="437d2-107">Buildkonfiguration „Debuggen“</span><span class="sxs-lookup"><span data-stu-id="437d2-107">Debug build configuration</span></span>

<span data-ttu-id="437d2-108">*Debuggen* und *Freigabe* sind zwei Standardbuildkonfigurationen von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="437d2-108">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="437d2-109">Die aktuelle Buildkonfiguration wird auf der Symbolleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="437d2-109">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="437d2-110">Das folgende Symbolleistenbild zeigt, dass Visual Studio konfiguriert wurde, um die Debugversion Ihrer Anwendung zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="437d2-110">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

![Visual Studio-Symbolleiste mit hervorgehobenem Debuggen](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

<span data-ttu-id="437d2-112">Führen Sie zunächst die Debugversion der App aus.</span><span class="sxs-lookup"><span data-stu-id="437d2-112">Begin by running the Debug version of the app.</span></span> <span data-ttu-id="437d2-113">Die Debugbuildkonfiguration deaktiviert die meisten Compileroptimierungen und stellt ausführlichere Informationen während des Buildprozesses bereit.</span><span class="sxs-lookup"><span data-stu-id="437d2-113">The Debug build configuration turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="437d2-114">Haltepunkt festlegen</span><span class="sxs-lookup"><span data-stu-id="437d2-114">Set a breakpoint</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="437d2-115">Legen Sie einen *Breakpoint* in der Zeile fest, in der der Name, das Datum und die Uhrzeit angezeigt werden, indem Sie in der betreffenden Zeile auf den linken Rand des Codefensters klicken.</span><span class="sxs-lookup"><span data-stu-id="437d2-115">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="437d2-116">Sie können einen Breakpoint auch festlegen, indem Sie den Cursor in der Codezeile platzieren und dann **F9** drücken oder **Debuggen** > **Breakpoint umschalten** in der Menüleiste auswählen.</span><span class="sxs-lookup"><span data-stu-id="437d2-116">Another way to set a breakpoint is by placing the cursor in the line of code and then pressing **F9** or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="437d2-117">Ein Breakpoint unterbricht vorübergehend die Ausführung der Anwendung, *bevor* die Zeile mit dem Breakpoint ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="437d2-117">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="437d2-118">Wie in der folgenden Abbildung gezeigt, hebt Visual Studio die Zeile hervor, in der der Breakpoint festgelegt ist, und zeigt am linken Rand einen roten Punkt an.</span><span class="sxs-lookup"><span data-stu-id="437d2-118">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   ![Visual Studio-Programmfenster mit festgelegtem Haltepunkt](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="437d2-120">Führen Sie das Programm im Debugmodus aus, indem Sie auf der Symbolleiste die Schaltfläche **HelloWorld** mit dem grünen Pfeil auswählen.</span><span class="sxs-lookup"><span data-stu-id="437d2-120">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span> <span data-ttu-id="437d2-121">Weitere Möglichkeiten zum Starten des Debuggens sind das Drücken von **F5** oder das Auswählen von **Debuggen** > **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="437d2-121">Other ways to start debugging are by pressing **F5** or by choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="437d2-122">Geben Sie eine Zeichenfolge im Konsolenfenster ein, wenn das Programm Sie zur Eingabe eines Namens auffordert, und drücken Sie dann die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="437d2-122">Enter a string in the console window when the program prompts for a name, and then press **Enter**.</span></span>

1. <span data-ttu-id="437d2-123">Die Ausführung des Programms endet, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="437d2-123">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="437d2-124">Im Fenster **Lokal** werden die Werte von Variablen angezeigt, die in der gerade ausgeführten Methode definiert sind.</span><span class="sxs-lookup"><span data-stu-id="437d2-124">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Screenshot eines Breakpoints in Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. <span data-ttu-id="437d2-126">Das **Direktfenster** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen.</span><span class="sxs-lookup"><span data-stu-id="437d2-126">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="437d2-127">Sie können den Wert von Variablen interaktiv ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt.</span><span class="sxs-lookup"><span data-stu-id="437d2-127">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="437d2-128">Wenn das **Direktfenster** nicht angezeigt wird, zeigen Sie es durch Auswählen von **Debuggen** > **Fenster** > **Direkt** an.</span><span class="sxs-lookup"><span data-stu-id="437d2-128">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="437d2-129">Geben Sie `name = "Gracie"` im **Direktfenster** ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="437d2-129">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="437d2-130">Geben Sie `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` im **Direktfenster** ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="437d2-130">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="437d2-131">Im **Direktfenster** werden der Wert der Zeichenfolgenvariablen und die Eigenschaften des <xref:System.DateTime>-Werts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="437d2-131">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="437d2-132">Darüber hinaus werden die Werte der Variablen im Fenster **Lokal** aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="437d2-132">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Fenster „Lokal“ und „Direkt“ in Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="437d2-134">Setzen Sie die Ausführung des Programms durch Auswählen der Schaltfläche **Fortsetzen** in der Symbolleiste fort.</span><span class="sxs-lookup"><span data-stu-id="437d2-134">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="437d2-135">Eine weitere Möglichkeit zum Fortsetzen besteht darin, **Debuggen** > **Fortsetzen** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="437d2-135">Another way to continue is by choosing **Debug** > **Continue**.</span></span>

   <span data-ttu-id="437d2-136">Die im Konsolenfenster angezeigten Werte entsprechen auch den Änderungen im **Direktfenster**.</span><span class="sxs-lookup"><span data-stu-id="437d2-136">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![Konsolenfenster mit den eingegebenen Werten](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="437d2-138">Drücken Sie eine beliebige Taste, um die Anwendung und das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="437d2-138">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="437d2-139">Festlegen eines bedingten Breakpoints</span><span class="sxs-lookup"><span data-stu-id="437d2-139">Set a conditional breakpoint</span></span>

<span data-ttu-id="437d2-140">Das Programm zeigt die Zeichenfolge an, die der Benutzer eingibt.</span><span class="sxs-lookup"><span data-stu-id="437d2-140">The program displays the string that the user enters.</span></span> <span data-ttu-id="437d2-141">Aber was geschieht, wenn der Benutzer gar nichts eingibt?</span><span class="sxs-lookup"><span data-stu-id="437d2-141">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="437d2-142">Sie können dies mit einer nützlichen Debugfunktion namens *bedingter Haltepunkt* testen. Dabei wird die Programmausführung angehalten, wenn mindestens eine Bedingung erfüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="437d2-142">You can test this with a useful debugging feature called a *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="437d2-143">Um einen bedingten Haltepunkt festzulegen und zu testen, was geschieht, wenn der Benutzer keine Zeichenfolge eingibt, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="437d2-143">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

1. <span data-ttu-id="437d2-144">Klicken Sie mit der rechten Maustaste auf den roten Punkt, der den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="437d2-144">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="437d2-145">Wählen Sie im Kontextmenü **Bedingungen** zum Öffnen des Dialogfelds **Breakpointeinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="437d2-145">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="437d2-146">Aktivieren Sie das Kontrollkästchen für **Bedingungen**, wenn es nicht bereits aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="437d2-146">Select the box for **Conditions** if it's not already selected.</span></span>

   ![Editor mit dem Panel für Haltepunkteinstellungen – C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="437d2-148">Geben Sie als **Bedingten Ausdruck** den folgenden Code in das Feld ein, der Beispielcode zeigt, der testet, ob `x` den Wert 5 aufweist.</span><span class="sxs-lookup"><span data-stu-id="437d2-148">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="437d2-149">Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="437d2-149">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="437d2-150">Jedes Mal, wenn der Breakpoint erreicht wird, ruft der Debugger die `String.IsNullOrEmpty(name)`-Methode auf, und die Ausführung wird nur in dieser Zeile unterbrochen, wenn der Methodenaufruf `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="437d2-150">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="437d2-151">Anstelle eines bedingten Ausdrucks können Sie eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung eine angegebene Anzahl von Malen ausgeführt wird, oder eine *Filterbedingung*, wodurch die Ausführung des Programms auf Basis von Attributen wie Threadbezeichner, Prozessname oder Threadname unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="437d2-151">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="437d2-152">Klicken Sie auf **Schließen**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="437d2-152">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="437d2-153">Starten Sie das Programm im Debugmodus, indem Sie **F5**drücken.</span><span class="sxs-lookup"><span data-stu-id="437d2-153">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="437d2-154">Drücken Sie im Konsolenfenster die **EINGABETASTE**, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="437d2-154">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="437d2-155">Da die angegebene Bedingung erfüllt wurde (`name` ist entweder `null` oder <xref:System.String.Empty?displayProperty=nameWithType>), endet die Ausführung des Programms, wenn sie den Breakpoint erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="437d2-155">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="437d2-156">Wählen Sie das Fenster **Lokal** aus, das die Werte der lokalen Variablen der aktuell ausgeführten Methode anzeigt.</span><span class="sxs-lookup"><span data-stu-id="437d2-156">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="437d2-157">In diesem Fall ist `Main` die derzeit ausgeführte Methode.</span><span class="sxs-lookup"><span data-stu-id="437d2-157">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="437d2-158">Stellen Sie sicher, dass der Wert der Variablen `name``""` bzw. <xref:System.String.Empty?displayProperty=nameWithType> ist.</span><span class="sxs-lookup"><span data-stu-id="437d2-158">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="437d2-159">Bestätigen Sie, dass der Wert eine leere Zeichenfolge ist, indem Sie die folgende Anweisung im **Direktfenster** eingeben und dann die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="437d2-159">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="437d2-160">Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="437d2-160">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="437d2-161">Das Fragezeichen weist das Direktfenster an, [einen Ausdruck auszuwerten](/visualstudio/ide/reference/immediate-window#enter-commands).</span><span class="sxs-lookup"><span data-stu-id="437d2-161">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   ![Das Direktfenster, das einen Wert „true“ zurückgibt, nachdem die Anweisung ausgeführt wurde – C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="437d2-163">Wählen Sie die Schaltfläche **Fortfahren** auf der Symbolleiste, um die Ausführung des Programms fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="437d2-163">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="437d2-164">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="437d2-164">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="437d2-165">Löschen Sie den Breakpoint durch Klicken auf den Punkt am linken Rand des Codefensters.</span><span class="sxs-lookup"><span data-stu-id="437d2-165">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="437d2-166">Eine andere Möglichkeit, einen Breakpoint zu löschen, besteht darin, **Debuggen > Breakpoint umschalten** auszuwählen, während die Codezeile ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="437d2-166">Another way to clear a breakpoint is by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="437d2-167">Schrittweises Ausführen eines Programms</span><span class="sxs-lookup"><span data-stu-id="437d2-167">Step through a program</span></span>

<span data-ttu-id="437d2-168">Mit Visual Studio können Sie ein Programm auch zeilenweise durchlaufen und die Ausführung jeder einzelnen Zeile überwachen.</span><span class="sxs-lookup"><span data-stu-id="437d2-168">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="437d2-169">Normalerweise würden Sie einen Breakpoint festlegen und den Programmablauf in einem kleinen Teil des Programmcodes verfolgen.</span><span class="sxs-lookup"><span data-stu-id="437d2-169">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="437d2-170">Da unser Programm klein ist, können Sie das gesamte Programm schrittweise durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="437d2-170">Since your program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="437d2-171">Wählen Sie **Debuggen** > **Einzelschritt** aus.</span><span class="sxs-lookup"><span data-stu-id="437d2-171">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="437d2-172">Eine andere Möglichkeit zum Debuggen jeweils einer Anweisung besteht darin, **F11** zu drücken.</span><span class="sxs-lookup"><span data-stu-id="437d2-172">Another way to debug one statement at a time is by pressing **F11**.</span></span>

   <span data-ttu-id="437d2-173">Visual Studio markiert einen Pfeil neben der nächsten Zeile der Ausführung und zeigt diesen an.</span><span class="sxs-lookup"><span data-stu-id="437d2-173">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="437d2-174">C#</span><span class="sxs-lookup"><span data-stu-id="437d2-174">C#</span></span>

   ![Visual Studio-Einzelschrittausführung in Methode – C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="437d2-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="437d2-176">Visual Basic</span></span>

   ![Visual Studio-Einzelschrittausführung in Methode – Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="437d2-178">An diesem Punkt wird im Fenster **Lokal** angezeigt, dass das `args`-Array leer ist und `name` und `date` Standardwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="437d2-178">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="437d2-179">Darüber hinaus hat Visual Studio ein leeres Konsolenfenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="437d2-179">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="437d2-180">Drücken Sie die Taste **F11**.</span><span class="sxs-lookup"><span data-stu-id="437d2-180">Press **F11**.</span></span> <span data-ttu-id="437d2-181">Visual Studio hebt nun die nächste auszuführende Zeile hervor.</span><span class="sxs-lookup"><span data-stu-id="437d2-181">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="437d2-182">Das Fenster **Lokal** ist unverändert, und das Konsolenfenster bleibt leer.</span><span class="sxs-lookup"><span data-stu-id="437d2-182">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="437d2-183">C#</span><span class="sxs-lookup"><span data-stu-id="437d2-183">C#</span></span>

   ![Visual Studio-Einzelschrittausführung in Methodenquelle – C#](./media/debugging-with-visual-studio/step-into-source-method.png)

   <span data-ttu-id="437d2-185">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="437d2-185">Visual Basic</span></span>

   ![Visual Studio-Einzelschrittausführung in Methodenquelle – Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="437d2-187">Drücken Sie die Taste **F11**.</span><span class="sxs-lookup"><span data-stu-id="437d2-187">Press **F11**.</span></span> <span data-ttu-id="437d2-188">Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `name` enthält.</span><span class="sxs-lookup"><span data-stu-id="437d2-188">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="437d2-189">Das Fenster **Lokal** zeigt, dass `name` den Wert `null` aufweist, und das Konsolenfenster zeigt die Zeichenfolge „What is your name?“ an.</span><span class="sxs-lookup"><span data-stu-id="437d2-189">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="437d2-190">Reagieren Sie auf die Eingabeaufforderung, indem Sie eine Zeichenfolge in das Konsolenfenster eingeben und die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="437d2-190">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="437d2-191">Die Konsole reagiert nicht, und die eingegebene Zeichenfolge wird nicht im Konsolenfenster angezeigt, aber die <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>-Methode wird dennoch Ihre Eingabe erfassen.</span><span class="sxs-lookup"><span data-stu-id="437d2-191">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="437d2-192">Drücken Sie die Taste **F11**.</span><span class="sxs-lookup"><span data-stu-id="437d2-192">Press **F11**.</span></span> <span data-ttu-id="437d2-193">Visual Studio hebt die Anweisung hervor, die die Variablenzuweisung `date` (`currentDate` in Visual Basic) enthält.</span><span class="sxs-lookup"><span data-stu-id="437d2-193">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="437d2-194">Das Fenster **Lokal** zeigt den vom Aufruf der Methode <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> zurückgegebenen Wert an.</span><span class="sxs-lookup"><span data-stu-id="437d2-194">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="437d2-195">Im Konsolenfenster wird auch die Zeichenfolge angezeigt, die Sie an der Eingabeaufforderung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="437d2-195">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="437d2-196">Drücken Sie die Taste **F11**.</span><span class="sxs-lookup"><span data-stu-id="437d2-196">Press **F11**.</span></span> <span data-ttu-id="437d2-197">Das Fenster **Lokal** zeigt den Wert der Variablen `date` nach der Zuweisung aus der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="437d2-197">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="437d2-198">Das Konsolenfenster ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="437d2-198">The console window is unchanged.</span></span>

1. <span data-ttu-id="437d2-199">Drücken Sie die Taste **F11**.</span><span class="sxs-lookup"><span data-stu-id="437d2-199">Press **F11**.</span></span> <span data-ttu-id="437d2-200">Visual Studio ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="437d2-200">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="437d2-201">Das Konsolenfenster zeigt die formatierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="437d2-201">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="437d2-202">Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus. Eine weitere Möglichkeit, die schrittweise Ausführung zu beenden, besteht darin, **UMSCHALT**+**F11** zu drücken.</span><span class="sxs-lookup"><span data-stu-id="437d2-202">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing **Shift**+**F11**.</span></span>

   <span data-ttu-id="437d2-203">Das Konsolenfenster zeigt eine Meldung an und wartet, bis Sie eine Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="437d2-203">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="437d2-204">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="437d2-204">Press any key to close the console window and stop debugging.</span></span>

## <a name="build-a-release-version"></a><span data-ttu-id="437d2-205">Erstellen einer Releaseversion</span><span class="sxs-lookup"><span data-stu-id="437d2-205">Build a Release version</span></span>

<span data-ttu-id="437d2-206">Nachdem Sie die Debugversion der Anwendung getestet haben, sollten Sie auch die Releaseversion kompilieren und testen.</span><span class="sxs-lookup"><span data-stu-id="437d2-206">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="437d2-207">Die endgültige Releaseversion umfasst Compileroptimierungen, die manchmal das Verhalten einer Anwendung negativ beeinträchtigen können.</span><span class="sxs-lookup"><span data-stu-id="437d2-207">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="437d2-208">Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z. B. Racebedingungen in Multithreadanwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="437d2-208">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="437d2-209">Ändern Sie zum Erstellen und Testen der endgültigen Produktversion der Konsolenanwendung die Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="437d2-209">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![Visual Studio-Standardsymbolleiste mit hervorgehobenem Debuggen](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="437d2-211">Wenn Sie **F5** drücken oder **Projektmappe erstellen** im Menü **Build** auswählen, kompiliert Visual Studio die Releaseversion der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="437d2-211">When you press **F5** or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="437d2-212">Sie können sie dann wie die Debugversion testen.</span><span class="sxs-lookup"><span data-stu-id="437d2-212">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="437d2-213">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="437d2-213">Next steps</span></span>

<span data-ttu-id="437d2-214">In diesem Tutorial haben Sie Debugtools von Visual Studio verwendet.</span><span class="sxs-lookup"><span data-stu-id="437d2-214">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="437d2-215">Im nächsten Tutorial veröffentlichen Sie eine bereitstellbare Version der App.</span><span class="sxs-lookup"><span data-stu-id="437d2-215">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="437d2-216">Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="437d2-216">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
