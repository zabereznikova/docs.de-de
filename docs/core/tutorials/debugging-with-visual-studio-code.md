---
title: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio Code
description: Erfahren Sie, wie Sie eine .NET Core-Konsolen-App mit Visual Studio Code debuggen.
ms.date: 05/26/2020
ms.openlocfilehash: 82b2798397d702aa2a50c04bf6e4d569b97e3666
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241512"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-code"></a>Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio Code

In diesem Tutorial werden die Debugtools vorgestellt, die in Visual Studio Code zum Arbeiten mit .NET Core-Apps verfügbar sind.

## <a name="prerequisites"></a>Voraussetzungen

- Dieses Tutorial funktioniert mit der Konsolen-App, die Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio Code](with-visual-studio-code.md) erstellen.

## <a name="use-debug-build-configuration"></a>Verwenden der Debugbuildkonfiguration

*Debuggen* und *Release* sind zwei Buildkonfigurationen von .NET Core. Sie verwenden die Debugbuildkonfiguration zum Debuggen und die Releasekonfiguration für die endgültige Releaseverteilung.

In der Debugkonfiguration wird ein Programm mit vollständigen symbolischen Debuginformationen und ohne Optimierung kompiliert. Die Optimierung gestaltet das Debuggen etwas schwieriger, da die Beziehung zwischen Quellcode und generierten Anweisungen komplexer ist. Die Releasekonfiguration eines Programms verfügt über keine symbolischen Debuginformationen und wird vollständig optimiert.

 Standardmäßig verwendet Visual Studio Code die Debugbuildkonfiguration, sodass Sie diese Einstellung vor dem Debuggen nicht ändern müssen.

## <a name="set-a-breakpoint"></a>Haltepunkt festlegen

Ein Breakpoint unterbricht vorübergehend die Ausführung der Anwendung, *bevor* die Zeile mit dem Breakpoint ausgeführt wird.

1. Öffnen Sie Visual Studio Code.

1. Öffnen Sie den *HelloWorld*-Projektordner, den Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio Code](with-visual-studio-code.md) erstellt haben.

1. Öffnen Sie die Datei *Program.cs*.

1. Legen Sie einen *Breakpoint* in der Zeile fest, in der der Name, das Datum und die Uhrzeit angezeigt werden, indem Sie auf den linken Rand des Codefensters klicken. Der linke Rand befindet sich links von den Zeilennummern. Eine weitere Möglichkeit zum Festlegen eines Breakpoints besteht darin, den Cursor in der Codezeile zu platzieren und dann <kbd>F9</kbd> zu drücken.

   Wie in der folgenden Abbildung gezeigt, gibt Visual Studio Code die Zeile an, in der der Breakpoint festgelegt ist, indem ein roter Punkt am linken Rand angezeigt wird.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="Festgelegter Breakpoint":::

## <a name="set-up-for-terminal-input"></a>Einrichtung für Terminaleingabe

Der Breakpoint befindet sich hinter einem `Console.ReadLine`-Methodenaufruf. Die **Debugkonsole** akzeptiert keine Terminaleingaben für ein aktuell ausgeführtes Programm. Zum Verarbeiten von Terminaleingaben beim Debuggen können Sie das integrierte Terminal (eines der Visual Studio Code-Fenster) oder ein externes Terminal verwenden. In diesem Tutorial verwenden Sie das integrierte Terminal.

1. Öffnen Sie *.vscode/launch.json*.

1. Ändern Sie die `console`-Einstellung in `integratedTerminal`.

   Von:

   ```
   "console": "internalConsole",
   ```

   Nach:

   ```
   "console": "integratedTerminal",
   ```

1. Speichern Sie die Änderungen.

## <a name="start-debugging"></a>Debugging starten

1. Öffnen Sie die Debugansicht, indem Sie im Menü auf der linken Seite das Debugsymbol auswählen.

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Öffnen der Registerkarte „Debuggen“ in Visual Studio Code":::

1. Starten Sie das Debuggen, indem Sie den grünen Pfeil am oberen Rand des Bereichs neben **.NET Core starten (Konsole)** auswählen.  Eine andere Möglichkeit zum Starten des Debuggens besteht darin, <kbd>F5</kbd> zu drücken.

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="Starten des Debuggens":::

1. Wählen Sie die Registerkarte **Terminal** aus, um die Eingabeaufforderung „Wie heißen Sie?“ anzuzeigen, die das Programm anzeigt, bevor auf eine Antwort gewartet wird.

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="Auswählen der Registerkarte „Terminal“":::

1. Geben Sie eine Zeichenfolge im Fenster **Terminal** als Antwort auf die Aufforderung zur Eingabe eines Namens ein, und drücken Sie dann die <kbd>EINGABETASTE</kbd>.

   Die Ausführung des Programms endet, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird. Im Abschnitt **Lokal** des Fensters **Variablen** werden die Werte von Variablen angezeigt, die in der aktuell ausgeführten Methode definiert sind.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="Breakpointtreffer, der lokale Variablen anzeigt":::

## <a name="change-variable-values"></a>Ändern von Variablenwerten

Das Fenster **Debugging-Konsole** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen. Sie können den Wert von Variablen ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt.

1. Wählen Sie die Registerkarte **Debugging-Konsole** aus.

1. Geben Sie `name = "Gracie"` an der Eingabeaufforderung am unteren Rand des Fensters **Debugging-Konsole** ein, und drücken Sie <kbd>EINGABETASTE</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="Ändern von Variablenwerten":::

1. Geben Sie `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` am unteren Rand des Fensters **Debugging-Konsole** ein, und drücken Sie <kbd>EINGABETASTE</kbd>.

   Im Fenster **Variablen** werden die neuen Werte der Variablen `name` und `date` angezeigt.

1. Setzen Sie die Ausführung des Programms durch Auswählen der Schaltfläche **Fortsetzen** in der Symbolleiste fort. Eine weitere Möglichkeit zum Fortsetzen besteht darin, <kbd>F5</kbd> zu drücken.

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="Fortsetzen des Debuggens":::

1. Klicken Sie erneut auf die Registerkarte **Terminal**.

   Die im Konsolenfenster angezeigten Werte entsprechen den Änderungen im Fenster **Debugging-Konsole**.

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="Terminalfenster mit den eingegebenen Werten":::

1. Drücken Sie eine beliebige Taste, um die Anwendung und das Debuggen zu beenden.

## <a name="set-a-conditional-breakpoint"></a>Festlegen eines bedingten Breakpoints

Das Programm zeigt die Zeichenfolge an, die der Benutzer eingibt. Aber was geschieht, wenn der Benutzer gar nichts eingibt? Sie können dies mit einem nützlichen Debugfeature testen, das als *Bedingter Breakpoint* bezeichnet wird.

1. Klicken Sie mit der rechten Maustaste (<kbd>STRG</kbd>+Klicken unter macOS) auf den roten Punkt, der den Breakpoint darstellt. Wählen Sie im Kontextmenü **Breakpoint bearbeiten** aus, um ein Dialogfeld zu öffnen, in dem Sie einen bedingten Ausdruck eingeben können.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="Kontextmenü des Breakpoints":::

1. Wählen Sie in der Dropdownliste `Expression` aus, geben Sie den folgenden bedingten Ausdruck ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="Eingeben eines bedingten Ausdrucks":::

   Jedes Mal, wenn der Breakpoint erreicht wird, ruft der Debugger die `String.IsNullOrEmpty(name)`-Methode auf, und die Ausführung wird nur in dieser Zeile unterbrochen, wenn der Methodenaufruf `true` zurückgibt.

   Anstelle eines bedingten Ausdrucks können Sie eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung eine angegebene Anzahl von Malen ausgeführt wird, oder eine *Filterbedingung*, wodurch die Ausführung des Programms auf Basis von Attributen wie Threadbezeichner, Prozessname oder Threadname unterbrochen wird.

1. Starten Sie das Programm im Debugmodus, indem Sie <kbd>F5</kbd>drücken.

1. Drücken Sie auf der Registerkarte **Terminal** die <kbd>EINGABETASTE</kbd>, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.

   Da die angegebene Bedingung erfüllt wurde (`name` ist `null` oder <xref:System.String.Empty?displayProperty=nameWithType>), wird die Ausführung des Programms beendet, wenn sie den Breakpoint erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.

   Im Fenster **Variablen** wird angezeigt, dass der Wert der `name`-Variablen `""` oder <xref:System.String.Empty?displayProperty=nameWithType> ist.

1. Bestätigen Sie, dass der Wert eine leere Zeichenfolge ist, indem Sie die folgende Anweisung an der Eingabeaufforderung **Debugging-Konsole** eingeben und dann die <kbd>EINGABETASTE</kbd> drücken. Das Ergebnis ist `true`.

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="Debugging-Konsole, die einen Wert TRUE zurückgibt, nachdem die Anweisung ausgeführt wurde":::

1. Wählen Sie die Schaltfläche **Fortfahren** auf der Symbolleiste, um die Ausführung des Programms fortzusetzen.

1. Wählen Sie die Registerkarte **Terminal** aus, und drücken Sie eine beliebige Taste, um das Programm und das Debuggen zu beenden.

1. Löschen Sie den Breakpoint durch Klicken auf den Punkt am linken Rand des Codefensters. Eine andere Möglichkeit, einen Breakpoint zu löschen, besteht darin, <kbd>F9</kbd> zu drücken, während die Codezeile ausgewählt ist.

1. Wenn Sie eine Warnung erhalten, dass die Breakpointbedingung verloren geht, wählen Sie **Breakpoint entfernen** aus.

## <a name="step-through-a-program"></a>Schrittweises Ausführen eines Programms

Mit Visual Studio Code können Sie ein Programm auch zeilenweise durchlaufen und seine Ausführung überwachen. Normalerweise würden Sie einen Breakpoint festlegen und den Programmablauf in einem kleinen Teil des Programmcodes verfolgen. Da dieses Programm klein ist, können Sie das gesamte Programm schrittweise durchlaufen.

1. Legen Sie einen Breakpoint bei der öffnenden geschweiften Klammer der `Main`-Methode fest.

1. Drücken Sie die Taste <kbd>F5</kbd> , um mit dem Debuggen zu beginnen.

   Visual Studio Code hebt die Breakpointzeile hervor.

   An diesem Punkt wird im Fenster **Variablen** angezeigt, dass das `args`-Array leer ist und `name` und `date` Standardwerte aufweisen.

1. Wählen Sie **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="Schaltfläche „Einzelschritt“":::

   Visual Studio Code hebt die nächste Zeile hervor.

1. Wählen Sie **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.

   Visual Studio Code führt die `Console.WriteLine` für die Aufforderung zur Eingabe des Namens aus und hebt die nächste Ausführungszeile hervor. Die nächste Zeile ist die `Console.ReadLine` für den `name`. Das Fenster **Variablen** ist unverändert, und die Registerkarte **Terminal** zeigt die Eingabeaufforderung „Wie heißen Sie?“ an.

1. Wählen Sie **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.

   Visual Studio hebt die Variablenzuweisung `name` hervor. Im Fenster **Variablen** wird angezeigt, dass `name` noch immer `null`ist.

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie eine Zeichenfolge auf der Registerkarte „Terminal“ eingeben und die <kbd>EINGABETASTE</kbd> drücken.

   Auf der Registerkarte **Terminal** wird die Zeichenfolge während der Eingabe möglicherweise nicht angezeigt, aber die <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>-Methode erfasst Ihre Eingabe.

1. Wählen Sie **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.

   Visual Studio Code hebt die Variablenzuweisung `date` hervor. Das Fenster **Variablen** zeigt den vom Aufruf der Methode <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> zurückgegebenen Wert an. Auf der Registerkarte **Terminal** wird die Zeichenfolge angezeigt, die Sie an der Eingabeaufforderung eingegeben haben.

1. Wählen Sie **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.

   Das Fenster **Variablen** zeigt den Wert der Variablen `date` nach der Zuweisung aus der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft an.

1. Wählen Sie **Einzelschritt** aus, oder drücken Sie <kbd>F11</kbd>.

   Visual Studio Code ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>-Methode auf. Das Konsolenfenster zeigt die formatierte Zeichenfolge an.

1. Wählen Sie **Ausführen bis Rücksprung** aus, oder drücken Sie <kbd>UMSCHALT</kbd>+<kbd>F11</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="Schaltfläche „Ausführen bis Rücksprung“":::

1. Wählen Sie die Registerkarte **Terminal** aus.

   Das Terminal zeigt „Drücken Sie zum Beenden eine beliebige Taste“ an.

1. Drücken Sie eine beliebige Taste, um das Programm zu beenden.

## <a name="select-release-build-configuration"></a>Auswählen der Releasebuildkonfiguration

Nachdem Sie die Debugversion der Anwendung getestet haben, sollten Sie auch die Releaseversion kompilieren und testen. Die Releaseversion umfasst Compileroptimierungen, die das Verhalten einer Anwendung beeinträchtigen können. Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z. B. Racebedingungen in Multithreadanwendungen erstellen.

Um die Releaseversion Ihrer Konsolenanwendung zu erstellen und zu testen, öffnen Sie das **Terminal** und führen den folgenden Befehl aus:

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Debuggen in Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Debugtools von Visual Studio Code verwendet. Im nächsten Tutorial veröffentlichen Sie eine bereitstellbare Version der App.

> [!div class="nextstepaction"]
> [Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio Code](publishing-with-visual-studio-code.md)
