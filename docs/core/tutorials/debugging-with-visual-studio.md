---
title: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio
description: Erfahren Sie, wie Sie eine .NET Core-Konsolen-App mit Visual Studio debuggen.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 743603cb037406948190c7090ca3527bfc40db18
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702066"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a>Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio

In diesem Tutorial werden die Debugtools vorgestellt, die in Visual Studio verfügbar sind.

## <a name="prerequisites"></a>Voraussetzungen

- Dieses Tutorial funktioniert mit der Konsolen-App, die Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio Code 2019](with-visual-studio.md) erstellen.

## <a name="use-debug-build-configuration"></a>Verwenden der Debugbuildkonfiguration

*Debug* und *Release* sind zwei Standardbuildkonfigurationen von Visual Studio. Sie verwenden die Debugbuildkonfiguration zum Debuggen und die Releasekonfiguration für die endgültige Releaseverteilung.

In der Debugkonfiguration wird ein Programm mit vollständigen symbolischen Debuginformationen und ohne Optimierung kompiliert. Die Optimierung gestaltet das Debuggen etwas schwieriger, da die Beziehung zwischen Quellcode und generierten Anweisungen komplexer ist. Die Releasekonfiguration eines Programms verfügt über keine symbolischen Debuginformationen und wird vollständig optimiert.

 Standardmäßig verwendet Visual Studio Code die Debugbuildkonfiguration, sodass Sie diese Einstellung vor dem Debuggen nicht ändern müssen.

1. Starten Sie Visual Studio.

1. Öffnen Sie das Projekt, das Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio 2019](with-visual-studio.md) erstellt haben.

   Die aktuelle Buildkonfiguration wird auf der Symbolleiste angezeigt. Das folgende Symbolleistenbild zeigt, dass Visual Studio konfiguriert wurde, um die Debugversion Ihrer Anwendung zu kompilieren:

   ![Visual Studio-Symbolleiste mit hervorgehobenem Debuggen](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

## <a name="set-a-breakpoint"></a>Haltepunkt festlegen

Ein *Haltepunkt* unterbricht vorübergehend die Ausführung der Anwendung, bevor die Zeile mit dem Haltepunkt ausgeführt wird.

1. Legen Sie einen *Haltepunkt* in der Zeile fest, in der der Name, das Datum und die Uhrzeit angezeigt werden, indem Sie in der betreffenden Zeile auf den linken Rand des Codefensters klicken. Der linke Rand befindet sich links von den Zeilennummern.  Sie können einen Haltepunkt auch festlegen, indem Sie den Cursor in der Codezeile platzieren und dann auf der Menüleiste **Debuggen** > **Haltepunkt umschalten** auswählen.

   Wie in der folgenden Abbildung gezeigt, hebt Visual Studio die Zeile hervor, in der der Breakpoint festgelegt ist, und zeigt am linken Rand einen roten Punkt an.

   ![Visual Studio-Programmfenster mit festgelegtem Haltepunkt](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. Drücken Sie <kbd>F5</kbd>, um das Programm im Debugmodus auszuführen. Eine andere Möglichkeit, das Debuggen zu starten, besteht darin, im Menü **Debuggen** > **Debuggen starten** zu wählen.

1. Geben Sie eine Zeichenfolge im Konsolenfenster ein, wenn das Programm Sie zur Eingabe eines Namens auffordert, und drücken Sie dann die <kbd>EINGABETASTE</kbd>.

1. Die Ausführung des Programms endet, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird. Im Fenster **Lokal** werden die Werte von Variablen angezeigt, die in der gerade ausgeführten Methode definiert sind.

   ![Screenshot eines Breakpoints in Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

## <a name="use-the-immediate-window"></a>Verwenden des Fensters „Direkt“

Das **Direktfenster** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen. Sie können den Wert von Variablen interaktiv ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt.

1. Wenn das **Direktfenster** nicht angezeigt wird, zeigen Sie es durch Auswählen von **Debuggen** > **Fenster** > **Direkt** an.

1. Geben Sie `name = "Gracie"` im **Direktfenster** ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

1. Geben Sie `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` im **Direktfenster** ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   Im **Direktfenster** werden der Wert der Zeichenfolgenvariablen und die Eigenschaften des <xref:System.DateTime>-Werts angezeigt. Darüber hinaus werden die Werte der Variablen im Fenster **Lokal** aktualisiert.

   ![Fenster „Lokal“ und „Direkt“ in Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. Drücken Sie <kbd>F5</kbd>, um die Ausführung des Programms fortzusetzen. Eine weitere Möglichkeit zum Fortsetzen besteht darin, im Menü **Debuggen** > **Fortsetzen** zu wählen.

   Die im Konsolenfenster angezeigten Werte entsprechen auch den Änderungen im **Direktfenster**.

   ![Konsolenfenster mit den eingegebenen Werten](./media/debugging-with-visual-studio/console-window.png)

1. Drücken Sie eine beliebige Taste, um die Anwendung und das Debuggen zu beenden.

## <a name="set-a-conditional-breakpoint"></a>Festlegen eines bedingten Breakpoints

Das Programm zeigt die Zeichenfolge an, die der Benutzer eingibt. Aber was geschieht, wenn der Benutzer gar nichts eingibt? Sie können dies mit einem nützlichen Debugfeature testen, das als *Bedingter Breakpoint* bezeichnet wird.

1. Klicken Sie mit der rechten Maustaste auf den roten Punkt, der den Haltepunkt darstellt. Wählen Sie im Kontextmenü **Bedingungen** zum Öffnen des Dialogfelds **Breakpointeinstellungen** aus. Aktivieren Sie das Kontrollkästchen für **Bedingungen**, wenn es nicht bereits aktiviert ist.

   ![Editor mit dem Panel für Haltepunkteinstellungen – C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. Geben Sie als **Bedingten Ausdruck** den folgenden Code in das Feld ein, der Beispielcode zeigt, der testet, ob `x` den Wert 5 aufweist. Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   Jedes Mal, wenn der Breakpoint erreicht wird, ruft der Debugger die `String.IsNullOrEmpty(name)`-Methode auf, und die Ausführung wird nur in dieser Zeile unterbrochen, wenn der Methodenaufruf `true` zurückgibt.

   Anstelle eines bedingten Ausdrucks können Sie eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung mit der angegebenen Häufigkeit ausgeführt wird. Eine weitere Option ist das Angeben einer *Filterbedingung*, wodurch die Ausführung des Programms auf Basis von Attributen wie Threadbezeichner, Prozessname oder Threadname unterbrochen wird.

1. Klicken Sie auf **Schließen**, um das Dialogfeld zu schließen.

1. Starten Sie das Programm im Debugmodus, indem Sie <kbd>F5</kbd>drücken.

1. Drücken Sie im Konsolenfenster die <kbd>EINGABETASTE</kbd>, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.

1. Da die angegebene Bedingung erfüllt wurde (`name` ist entweder `null` oder <xref:System.String.Empty?displayProperty=nameWithType>), endet die Ausführung des Programms, wenn sie den Breakpoint erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.

1. Wählen Sie das Fenster **Lokal** aus, das die Werte der lokalen Variablen der aktuell ausgeführten Methode anzeigt. In diesem Fall ist `Main` die derzeit ausgeführte Methode. Stellen Sie sicher, dass der Wert der Variablen `name``""` bzw. <xref:System.String.Empty?displayProperty=nameWithType> ist.

1. Bestätigen Sie, dass der Wert eine leere Zeichenfolge ist, indem Sie die folgende Anweisung im **Direktfenster** eingeben und dann die <kbd>EINGABETASTE</kbd> drücken. Das Ergebnis ist `true`.

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   Das Fragezeichen weist das Direktfenster an, [einen Ausdruck auszuwerten](/visualstudio/ide/reference/immediate-window#enter-commands).

   ![Das Direktfenster, das einen Wert „true“ zurückgibt, nachdem die Anweisung ausgeführt wurde – C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. Drücken Sie <kbd>F5</kbd>, um die Ausführung des Programms fortzusetzen.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.

1. Löschen Sie den Breakpoint durch Klicken auf den Punkt am linken Rand des Codefensters. Eine andere Möglichkeit, einen Breakpoint zu löschen, besteht darin, **Debuggen > Breakpoint umschalten** auszuwählen, während die Codezeile ausgewählt ist.

## <a name="step-through-a-program"></a>Schrittweises Ausführen eines Programms

Mit Visual Studio können Sie ein Programm auch zeilenweise durchlaufen und die Ausführung jeder einzelnen Zeile überwachen. Normalerweise würden Sie einen Breakpoint festlegen und den Programmablauf in einem kleinen Teil des Programmcodes verfolgen. Da dieses Programm klein ist, können Sie das gesamte Programm schrittweise durchlaufen.

1. Wählen Sie **Debuggen** > **Einzelschritt** aus. Eine andere Möglichkeit zum Debuggen jeweils einer Anweisung besteht darin, <kbd>F11</kbd> zu drücken.

   Visual Studio markiert einen Pfeil neben der nächsten Zeile der Ausführung und zeigt diesen an.

   C#

   ![Visual Studio-Einzelschrittausführung in Methode – C#](./media/debugging-with-visual-studio/step-into-method.png)

   Visual Basic

   ![Visual Studio-Einzelschrittausführung in Methode – Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   An diesem Punkt wird im Fenster **Lokal** angezeigt, dass das `args`-Array leer ist und `name` und `date` Standardwerte aufweisen. Darüber hinaus hat Visual Studio ein leeres Konsolenfenster geöffnet.

1. Drücken Sie die Taste <kbd>F11</kbd>. Visual Studio hebt nun die nächste auszuführende Zeile hervor. Das Fenster **Lokal** ist unverändert, und das Konsolenfenster bleibt leer.

   C#

   ![Visual Studio-Einzelschrittausführung in Methodenquelle – C#](./media/debugging-with-visual-studio/step-into-source-method.png)

   Visual Basic

   ![Visual Studio-Einzelschrittausführung in Methodenquelle – Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. Drücken Sie die Taste <kbd>F11</kbd>. Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `name` enthält. Das Fenster **Lokal** zeigt, dass `name` den Wert `null` aufweist, und das Konsolenfenster zeigt die Zeichenfolge „What is your name?“ an.

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie eine Zeichenfolge in das Konsolenfenster eingeben und die <kbd>EINGABETASTE</kbd> drücken. Die Konsole reagiert nicht, und die eingegebene Zeichenfolge wird nicht im Konsolenfenster angezeigt, aber die <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>-Methode wird dennoch Ihre Eingabe erfassen.

1. Drücken Sie die Taste <kbd>F11</kbd>. Visual Studio hebt die Anweisung hervor, die die Variablenzuweisung `date` (`currentDate` in Visual Basic) enthält. Das Fenster **Lokal** zeigt den vom Aufruf der Methode <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> zurückgegebenen Wert an. Im Konsolenfenster wird auch die Zeichenfolge angezeigt, die Sie an der Eingabeaufforderung eingegeben haben.

1. Drücken Sie die Taste <kbd>F11</kbd>. Das Fenster **Lokal** zeigt den Wert der Variablen `date` nach der Zuweisung aus der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft an. Das Konsolenfenster ist unverändert.

1. Drücken Sie die Taste <kbd>F11</kbd>. Visual Studio ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>-Methode auf. Das Konsolenfenster zeigt die formatierte Zeichenfolge an.

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus. Eine weitere Möglichkeit, die schrittweise Ausführung zu beenden, besteht darin, <kbd>UMSCHALT</kbd>+<kbd>F11</kbd> zu drücken.

   Das Konsolenfenster zeigt eine Meldung an und wartet, bis Sie eine Taste drücken.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.

## <a name="use-release-build-configuration"></a>Verwenden der Releasebuildkonfiguration

Nachdem Sie die Debugversion der Anwendung getestet haben, sollten Sie auch die Releaseversion kompilieren und testen. Die endgültige Releaseversion umfasst Compileroptimierungen, die manchmal das Verhalten einer Anwendung negativ beeinträchtigen können. Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z. B. Racebedingungen in Multithreadanwendungen erstellen.

Ändern Sie zum Erstellen und Testen der endgültigen Produktversion der Konsolenanwendung die Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.

![Visual Studio-Standardsymbolleiste mit hervorgehobenem Debuggen](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

Wenn Sie <kbd>F5</kbd> drücken oder **Projektmappe erstellen** im Menü **Build** auswählen, kompiliert Visual Studio die Releaseversion der Anwendung. Sie können sie dann wie die Debugversion testen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Debugtools von Visual Studio verwendet. Im nächsten Tutorial veröffentlichen Sie eine bereitstellbare Version der App.

> [!div class="nextstepaction"]
> [Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio](publishing-with-visual-studio.md)
