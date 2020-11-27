---
title: Debuggen einer .NET-Konsolenanwendung mit Visual Studio
description: Hier erfahren Sie, wie Sie eine .NET-Konsolen-App mit Visual Studio debuggen.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 8a914dc6cf069c011ea5b077ada514bf8cec331d
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916188"
---
# <a name="tutorial-debug-a-net-console-application-using-visual-studio"></a><span data-ttu-id="24f3e-103">Tutorial: Debuggen einer .NET-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="24f3e-103">Tutorial: Debug a .NET console application using Visual Studio</span></span>

<span data-ttu-id="24f3e-104">In diesem Tutorial werden die Debugtools vorgestellt, die in Visual Studio verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="24f3e-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24f3e-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="24f3e-105">Prerequisites</span></span>

- <span data-ttu-id="24f3e-106">Dieses Tutorial kann mit der Konsolen-App durchgeführt werden, die Sie in [Tutorial: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio](with-visual-studio.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-106">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="24f3e-107">Verwenden der Debugbuildkonfiguration</span><span class="sxs-lookup"><span data-stu-id="24f3e-107">Use Debug build configuration</span></span>

<span data-ttu-id="24f3e-108">*Debug* und *Release* sind zwei Standardbuildkonfigurationen von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="24f3e-108">*Debug* and *Release* are Visual Studio's built-in build configurations.</span></span> <span data-ttu-id="24f3e-109">Sie verwenden die Debugbuildkonfiguration zum Debuggen und die Releasekonfiguration für die endgültige Releaseverteilung.</span><span class="sxs-lookup"><span data-stu-id="24f3e-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="24f3e-110">In der Debugkonfiguration wird ein Programm mit vollständigen symbolischen Debuginformationen und ohne Optimierung kompiliert.</span><span class="sxs-lookup"><span data-stu-id="24f3e-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="24f3e-111">Die Optimierung gestaltet das Debuggen etwas schwieriger, da die Beziehung zwischen Quellcode und generierten Anweisungen komplexer ist.</span><span class="sxs-lookup"><span data-stu-id="24f3e-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="24f3e-112">Die Releasekonfiguration eines Programms verfügt über keine symbolischen Debuginformationen und wird vollständig optimiert.</span><span class="sxs-lookup"><span data-stu-id="24f3e-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

 <span data-ttu-id="24f3e-113">Standardmäßig verwendet Visual Studio die Debugbuildkonfiguration, sodass Sie diese Einstellung vor dem Debuggen nicht ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-113">By default, Visual Studio uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="24f3e-114">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="24f3e-114">Start Visual Studio.</span></span>

1. <span data-ttu-id="24f3e-115">Öffnen Sie das Projekt, das Sie in [Tutorial: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio](with-visual-studio.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="24f3e-115">Open the project that you created in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

   <span data-ttu-id="24f3e-116">Die aktuelle Buildkonfiguration wird auf der Symbolleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24f3e-116">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="24f3e-117">Das folgende Symbolleistenbild zeigt, dass Visual Studio konfiguriert wurde, um die Debugversion Ihrer Anwendung zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="24f3e-117">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png" alt-text="Visual Studio-Symbolleiste mit hervorgehobenem Debuggen":::

## <a name="set-a-breakpoint"></a><span data-ttu-id="24f3e-119">Haltepunkt festlegen</span><span class="sxs-lookup"><span data-stu-id="24f3e-119">Set a breakpoint</span></span>

<span data-ttu-id="24f3e-120">Ein *Haltepunkt* unterbricht vorübergehend die Ausführung der Anwendung, bevor die Zeile mit dem Haltepunkt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24f3e-120">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="24f3e-121">Legen Sie einen *Haltepunkt* in der Zeile fest, in der der Name, das Datum und die Uhrzeit angezeigt werden, indem Sie in der betreffenden Zeile auf den linken Rand des Codefensters klicken.</span><span class="sxs-lookup"><span data-stu-id="24f3e-121">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="24f3e-122">Der linke Rand befindet sich links von den Zeilennummern.</span><span class="sxs-lookup"><span data-stu-id="24f3e-122">The left margin is to the left of the line numbers.</span></span>  <span data-ttu-id="24f3e-123">Sie können einen Breakpoint auch festlegen, indem Sie den Cursor in der Codezeile platzieren und dann <kbd>F9</kbd> drücken oder **Debuggen** > **Haltepunkt umschalten** in der Menüleiste auswählen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-123">Other ways to set a breakpoint are by placing the cursor in the line of code and then pressing <kbd>F9</kbd> or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="24f3e-124">Wie in der folgenden Abbildung gezeigt, hebt Visual Studio die Zeile hervor, in der der Breakpoint festgelegt ist, und zeigt am linken Rand einen roten Punkt an.</span><span class="sxs-lookup"><span data-stu-id="24f3e-124">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/set-breakpoint-in-editor.png" alt-text="Visual Studio-Programmfenster mit festgelegtem Haltepunkt":::

1. <span data-ttu-id="24f3e-126">Drücken Sie <kbd>F5</kbd>, um das Programm im Debugmodus auszuführen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-126">Press <kbd>F5</kbd> to run the program in Debug mode.</span></span> <span data-ttu-id="24f3e-127">Eine andere Möglichkeit, das Debuggen zu starten, besteht darin, im Menü **Debuggen** > **Debuggen starten** zu wählen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-127">Another way to start debugging is by choosing **Debug** > **Start Debugging** from the menu.</span></span>

1. <span data-ttu-id="24f3e-128">Geben Sie eine Zeichenfolge im Konsolenfenster ein, wenn das Programm Sie zur Eingabe eines Namens auffordert, und drücken Sie dann die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="24f3e-128">Enter a string in the console window when the program prompts for a name, and then press <kbd>Enter</kbd>.</span></span>

1. <span data-ttu-id="24f3e-129">Die Ausführung des Programms endet, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24f3e-129">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="24f3e-130">Im Fenster **Lokal** werden die Werte von Variablen angezeigt, die in der gerade ausgeführten Methode definiert sind.</span><span class="sxs-lookup"><span data-stu-id="24f3e-130">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/breakpoint-hit.png" alt-text="Screenshot eines Haltepunkts in Visual Studio":::

## <a name="use-the-immediate-window"></a><span data-ttu-id="24f3e-132">Verwenden des Fensters „Direkt“</span><span class="sxs-lookup"><span data-stu-id="24f3e-132">Use the Immediate window</span></span>

<span data-ttu-id="24f3e-133">Das **Direktfenster** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-133">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="24f3e-134">Sie können den Wert von Variablen interaktiv ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt.</span><span class="sxs-lookup"><span data-stu-id="24f3e-134">You can interactively change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="24f3e-135">Wenn das **Direktfenster** nicht angezeigt wird, zeigen Sie es durch Auswählen von **Debuggen** > **Fenster** > **Direkt** an.</span><span class="sxs-lookup"><span data-stu-id="24f3e-135">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

1. <span data-ttu-id="24f3e-136">Geben Sie `name = "Gracie"` im **Direktfenster** ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="24f3e-136">Enter `name = "Gracie"` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

1. <span data-ttu-id="24f3e-137">Geben Sie `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` im **Direktfenster** ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="24f3e-137">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="24f3e-138">Im **Direktfenster** werden der Wert der Zeichenfolgenvariablen und die Eigenschaften des <xref:System.DateTime>-Werts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24f3e-138">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="24f3e-139">Darüber hinaus werden die Werte der Variablen im Fenster **Lokal** aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="24f3e-139">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/locals-immediate-window.png" alt-text="Fenster „Lokal“ und „Direkt“ in Visual Studio 2019":::

1. <span data-ttu-id="24f3e-141">Drücken Sie <kbd>F5</kbd>, um die Ausführung des Programms fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-141">Press <kbd>F5</kbd> to continue program execution.</span></span> <span data-ttu-id="24f3e-142">Eine weitere Möglichkeit zum Fortsetzen besteht darin, im Menü **Debuggen** > **Fortsetzen** zu wählen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-142">Another way to continue is by choosing **Debug** > **Continue** from the menu.</span></span>

   <span data-ttu-id="24f3e-143">Die im Konsolenfenster angezeigten Werte entsprechen auch den Änderungen im **Direktfenster**.</span><span class="sxs-lookup"><span data-stu-id="24f3e-143">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/console-window.png" alt-text="Konsolenfenster mit den eingegebenen Werten":::

1. <span data-ttu-id="24f3e-145">Drücken Sie eine beliebige Taste, um die Anwendung und das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="24f3e-145">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="24f3e-146">Festlegen eines bedingten Breakpoints</span><span class="sxs-lookup"><span data-stu-id="24f3e-146">Set a conditional breakpoint</span></span>

<span data-ttu-id="24f3e-147">Das Programm zeigt die Zeichenfolge an, die der Benutzer eingibt.</span><span class="sxs-lookup"><span data-stu-id="24f3e-147">The program displays the string that the user enters.</span></span> <span data-ttu-id="24f3e-148">Aber was geschieht, wenn der Benutzer gar nichts eingibt?</span><span class="sxs-lookup"><span data-stu-id="24f3e-148">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="24f3e-149">Sie können dies mit einem nützlichen Debugfeature testen, das als *Bedingter Breakpoint* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="24f3e-149">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="24f3e-150">Klicken Sie mit der rechten Maustaste auf den roten Punkt, der den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="24f3e-150">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="24f3e-151">Wählen Sie im Kontextmenü **Bedingungen** zum Öffnen des Dialogfelds **Breakpointeinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="24f3e-151">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="24f3e-152">Aktivieren Sie das Kontrollkästchen für **Bedingungen**, wenn es nicht bereits aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="24f3e-152">Select the box for **Conditions** if it's not already selected.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/breakpoint-settings.png" alt-text="Editor mit dem Panel für Haltepunkteinstellungen – C#":::

1. <span data-ttu-id="24f3e-154">Geben Sie als **Bedingten Ausdruck** den folgenden Code in das Feld ein, der Beispielcode zeigt, der testet, ob `x` den Wert 5 aufweist.</span><span class="sxs-lookup"><span data-stu-id="24f3e-154">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="24f3e-155">Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="24f3e-155">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="24f3e-156">Jedes Mal, wenn der Breakpoint erreicht wird, ruft der Debugger die `String.IsNullOrEmpty(name)`-Methode auf, und die Ausführung wird nur in dieser Zeile unterbrochen, wenn der Methodenaufruf `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="24f3e-156">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="24f3e-157">Anstelle eines bedingten Ausdrucks können Sie eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung mit der angegebenen Häufigkeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24f3e-157">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span> <span data-ttu-id="24f3e-158">Eine weitere Option ist das Angeben einer *Filterbedingung*, wodurch die Ausführung des Programms auf Basis von Attributen wie Threadbezeichner, Prozessname oder Threadname unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="24f3e-158">Another option is to specify a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="24f3e-159">Klicken Sie auf **Schließen**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-159">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="24f3e-160">Starten Sie das Programm im Debugmodus, indem Sie <kbd>F5</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="24f3e-160">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="24f3e-161">Drücken Sie im Konsolenfenster die <kbd>EINGABETASTE</kbd>, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="24f3e-161">In the console window, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

1. <span data-ttu-id="24f3e-162">Da die angegebene Bedingung erfüllt wurde (`name` ist entweder `null` oder <xref:System.String.Empty?displayProperty=nameWithType>), endet die Ausführung des Programms, wenn sie den Breakpoint erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24f3e-162">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="24f3e-163">Wählen Sie das Fenster **Lokal** aus, das die Werte der lokalen Variablen der aktuell ausgeführten Methode anzeigt.</span><span class="sxs-lookup"><span data-stu-id="24f3e-163">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="24f3e-164">In diesem Fall ist `Main` die derzeit ausgeführte Methode.</span><span class="sxs-lookup"><span data-stu-id="24f3e-164">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="24f3e-165">Stellen Sie sicher, dass der Wert der Variablen `name``""` bzw. <xref:System.String.Empty?displayProperty=nameWithType> ist.</span><span class="sxs-lookup"><span data-stu-id="24f3e-165">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="24f3e-166">Bestätigen Sie, dass der Wert eine leere Zeichenfolge ist, indem Sie die folgende Anweisung im **Direktfenster** eingeben und dann die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="24f3e-166">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="24f3e-167">Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="24f3e-167">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="24f3e-168">Das Fragezeichen weist das Direktfenster an, [einen Ausdruck auszuwerten](/visualstudio/ide/reference/immediate-window#enter-commands).</span><span class="sxs-lookup"><span data-stu-id="24f3e-168">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/immediate-window-output.png" alt-text="Das Direktfenster, das einen Wert „true“ zurückgibt, nachdem die Anweisung ausgeführt wurde – C#":::

1. <span data-ttu-id="24f3e-170">Drücken Sie <kbd>F5</kbd>, um die Ausführung des Programms fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-170">Press <kbd>F5</kbd> to continue program execution.</span></span>

1. <span data-ttu-id="24f3e-171">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="24f3e-171">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="24f3e-172">Löschen Sie den Breakpoint durch Klicken auf den Punkt am linken Rand des Codefensters.</span><span class="sxs-lookup"><span data-stu-id="24f3e-172">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="24f3e-173">Andere Möglichkeiten zum Löschen eines Breakpoints bestehen darin, <kbd>F9</kbd> zu drücken oder **Debuggen > Haltepunkt umschalten** auszuwählen, während die Codezeile ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="24f3e-173">Other ways to clear a breakpoint are by pressing <kbd>F9</kbd> or choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="24f3e-174">Schrittweises Ausführen eines Programms</span><span class="sxs-lookup"><span data-stu-id="24f3e-174">Step through a program</span></span>

<span data-ttu-id="24f3e-175">Mit Visual Studio können Sie ein Programm auch zeilenweise durchlaufen und die Ausführung jeder einzelnen Zeile überwachen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-175">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="24f3e-176">Normalerweise würden Sie einen Breakpoint festlegen und den Programmablauf in einem kleinen Teil des Programmcodes verfolgen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-176">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="24f3e-177">Da dieses Programm klein ist, können Sie das gesamte Programm schrittweise durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-177">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="24f3e-178">Wählen Sie **Debuggen** > **Einzelschritt** aus.</span><span class="sxs-lookup"><span data-stu-id="24f3e-178">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="24f3e-179">Eine andere Möglichkeit zum Debuggen jeweils einer Anweisung besteht darin, <kbd>F11</kbd> zu drücken.</span><span class="sxs-lookup"><span data-stu-id="24f3e-179">Another way to debug one statement at a time is by pressing <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="24f3e-180">Visual Studio markiert einen Pfeil neben der nächsten Zeile der Ausführung und zeigt diesen an.</span><span class="sxs-lookup"><span data-stu-id="24f3e-180">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="24f3e-181">C#</span><span class="sxs-lookup"><span data-stu-id="24f3e-181">C#</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/step-into-method.png" alt-text="Visual Studio-Einzelschrittausführung in Methode – C#":::

   <span data-ttu-id="24f3e-183">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24f3e-183">Visual Basic</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/vb-step-into-method.png" alt-text="Visual Studio-Einzelschrittausführung in Methode – Visual Basic":::

   <span data-ttu-id="24f3e-185">An diesem Punkt wird im Fenster **Lokal** angezeigt, dass das `args`-Array leer ist und `name` und `date` Standardwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-185">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="24f3e-186">Darüber hinaus hat Visual Studio ein leeres Konsolenfenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="24f3e-186">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="24f3e-187">Drücken Sie die Taste <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="24f3e-187">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="24f3e-188">Visual Studio hebt nun die nächste auszuführende Zeile hervor.</span><span class="sxs-lookup"><span data-stu-id="24f3e-188">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="24f3e-189">Das Fenster **Lokal** ist unverändert, und das Konsolenfenster bleibt leer.</span><span class="sxs-lookup"><span data-stu-id="24f3e-189">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="24f3e-190">C#</span><span class="sxs-lookup"><span data-stu-id="24f3e-190">C#</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/step-into-source-method.png" alt-text="Visual Studio-Einzelschrittausführung in Methodenquelle – C#":::

   <span data-ttu-id="24f3e-192">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24f3e-192">Visual Basic</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/vb-step-into-source-method.png" alt-text="Visual Studio-Einzelschrittausführung in Methodenquelle – Visual Basic":::

1. <span data-ttu-id="24f3e-194">Drücken Sie die Taste <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="24f3e-194">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="24f3e-195">Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `name` enthält.</span><span class="sxs-lookup"><span data-stu-id="24f3e-195">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="24f3e-196">Das Fenster **Lokal** zeigt, dass `name` den Wert `null` aufweist, und das Konsolenfenster zeigt die Zeichenfolge „What is your name?“ an.</span><span class="sxs-lookup"><span data-stu-id="24f3e-196">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="24f3e-197">Reagieren Sie auf die Eingabeaufforderung, indem Sie eine Zeichenfolge in das Konsolenfenster eingeben und die <kbd>EINGABETASTE</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="24f3e-197">Respond to the prompt by entering a string in the console window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="24f3e-198">Die Konsole reagiert nicht, und die eingegebene Zeichenfolge wird nicht im Konsolenfenster angezeigt, aber die <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>-Methode wird dennoch Ihre Eingabe erfassen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-198">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="24f3e-199">Drücken Sie die Taste <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="24f3e-199">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="24f3e-200">Visual Studio hebt die Anweisung hervor, die die Variablenzuweisung `date` (`currentDate` in Visual Basic) enthält.</span><span class="sxs-lookup"><span data-stu-id="24f3e-200">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="24f3e-201">Das Fenster **Lokal** zeigt den vom Aufruf der Methode <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> zurückgegebenen Wert an.</span><span class="sxs-lookup"><span data-stu-id="24f3e-201">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="24f3e-202">Im Konsolenfenster wird auch die Zeichenfolge angezeigt, die Sie an der Eingabeaufforderung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="24f3e-202">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="24f3e-203">Drücken Sie die Taste <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="24f3e-203">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="24f3e-204">Das Fenster **Lokal** zeigt den Wert der Variablen `date` nach der Zuweisung aus der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="24f3e-204">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="24f3e-205">Das Konsolenfenster ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="24f3e-205">The console window is unchanged.</span></span>

1. <span data-ttu-id="24f3e-206">Drücken Sie die Taste <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="24f3e-206">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="24f3e-207">Visual Studio ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="24f3e-207">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="24f3e-208">Das Konsolenfenster zeigt die formatierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="24f3e-208">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="24f3e-209">Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus. Eine weitere Möglichkeit, die schrittweise Ausführung zu beenden, besteht darin, <kbd>UMSCHALT</kbd>+<kbd>F11</kbd> zu drücken.</span><span class="sxs-lookup"><span data-stu-id="24f3e-209">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   <span data-ttu-id="24f3e-210">Das Konsolenfenster zeigt eine Meldung an und wartet, bis Sie eine Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="24f3e-210">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="24f3e-211">Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="24f3e-211">Press any key to close the console window and stop debugging.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="24f3e-212">Verwenden der Releasebuildkonfiguration</span><span class="sxs-lookup"><span data-stu-id="24f3e-212">Use Release build configuration</span></span>

<span data-ttu-id="24f3e-213">Nachdem Sie die Debugversion der Anwendung getestet haben, sollten Sie auch die Releaseversion kompilieren und testen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-213">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="24f3e-214">Die endgültige Releaseversion umfasst Compileroptimierungen, die manchmal das Verhalten einer Anwendung negativ beeinträchtigen können.</span><span class="sxs-lookup"><span data-stu-id="24f3e-214">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="24f3e-215">Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z. B. Racebedingungen in Multithreadanwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-215">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="24f3e-216">Ändern Sie zum Erstellen und Testen der endgültigen Produktversion der Konsolenanwendung die Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="24f3e-216">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

:::image type="content" source="./media/debugging-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Visual Studio-Standardsymbolleiste mit hervorgehobenem Release":::

<span data-ttu-id="24f3e-218">Wenn Sie <kbd>F5</kbd> drücken oder **Projektmappe erstellen** im Menü **Build** auswählen, kompiliert Visual Studio die Releaseversion der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="24f3e-218">When you press <kbd>F5</kbd> or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="24f3e-219">Sie können sie dann wie die Debugversion testen.</span><span class="sxs-lookup"><span data-stu-id="24f3e-219">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="24f3e-220">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="24f3e-220">Next steps</span></span>

<span data-ttu-id="24f3e-221">In diesem Tutorial haben Sie Debugtools von Visual Studio verwendet.</span><span class="sxs-lookup"><span data-stu-id="24f3e-221">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="24f3e-222">Im nächsten Tutorial veröffentlichen Sie eine bereitstellbare Version der App.</span><span class="sxs-lookup"><span data-stu-id="24f3e-222">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="24f3e-223">Tutorial: Veröffentlichen einer .NET Core-Konsolenanwendung in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="24f3e-223">Publish a .NET console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
