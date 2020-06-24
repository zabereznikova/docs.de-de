---
title: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac
description: Erfahren Sie, wie Sie eine .NET Core-Konsolen-App mit Visual Studio für Mac debuggen.
ms.date: 06/08/2020
ms.openlocfilehash: 4941605923a9897d481aca4ec31408ab62e873f3
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713484"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-for-mac"></a>Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac

In diesem Tutorial werden die Debugtools vorgestellt, die in Visual Studio für Mac verfügbar sind.

## <a name="prerequisites"></a>Voraussetzungen

- Dieses Tutorial funktioniert mit der Konsolen-App, die Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio für Mac](using-on-mac-vs.md) erstellen.

## <a name="use-debug-build-configuration"></a>Verwenden der Debugbuildkonfiguration

*Debug* und *Release* sind zwei Standardbuildkonfigurationen von Visual Studio. Sie verwenden die Debugbuildkonfiguration zum Debuggen und die Releasekonfiguration für die endgültige Releaseverteilung.

In der Debugkonfiguration wird ein Programm mit vollständigen symbolischen Debuginformationen und ohne Optimierung kompiliert. Die Optimierung gestaltet das Debuggen etwas schwieriger, da die Beziehung zwischen Quellcode und generierten Anweisungen komplexer ist. Die Releasekonfiguration eines Programms verfügt über keine symbolischen Debuginformationen und wird vollständig optimiert.

Standardmäßig verwendet Visual Studio die Debugbuildkonfiguration, sodass Sie diese Einstellung vor dem Debuggen nicht ändern müssen.

1. Starten Sie Visual Studio für Mac.

1. Öffnen Sie das Projekt, das Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio für Mac](using-on-mac-vs.md) erstellt haben.

   Die aktuelle Buildkonfiguration wird auf der Symbolleiste angezeigt. Das folgende Symbolleistenbild zeigt, dass Visual Studio konfiguriert wurde, um die Debugversion Ihrer Anwendung zu kompilieren:

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-debug.png" alt-text="Visual Studio-Symbolleiste mit hervorgehobenem Debuggen":::

## <a name="set-a-breakpoint"></a>Haltepunkt festlegen

Ein *Haltepunkt* unterbricht vorübergehend die Ausführung der Anwendung, bevor die Zeile mit dem Haltepunkt ausgeführt wird.

1. Legen Sie einen Haltepunkt in der Zeile fest, in der der Name, das Datum und die Uhrzeit angezeigt werden. Platzieren Sie hierzu den Cursor in der Codezeile, und drücken Sie <kbd>⌘</kbd><kbd>\\</kbd> (<kbd>BEFEHL</kbd>+<kbd>\\</kbd>). Eine andere Möglichkeit zum Festlegen eines Haltepunkts besteht darin, im Menü **Ausführen** > **Haltepunkt umschalten** auszuwählen.

   Visual Studio hebt die Zeile hervor, in der der Haltepunkt festgelegt ist, und zeigt am linken Rand einen roten Punkt an.

   :::image type="content" source="media/debugging-with-visual-studio-mac/set-breakpoint-in-editor.png" alt-text="Visual Studio-Programmfenster mit festgelegtem Haltepunkt":::

1. Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>) ein, um das Programm im Debugmodus zu starten. Eine andere Möglichkeit, das Debuggen zu starten, besteht darin, im Menü **Ausführen** > **Debuggen starten** zu wählen.

1. Geben Sie eine Zeichenfolge im Terminalfenster ein, wenn das Programm Sie zur Eingabe eines Namens auffordert, und drücken Sie dann die <kbd>EINGABETASTE</kbd>.

1. Die Ausführung des Programms endet, wenn es den Haltepunkt erreicht, bevor die `Console.WriteLine`-Methode ausgeführt wird.

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-hit.png" alt-text="Screenshot eines Haltepunkts in Visual Studio":::

## <a name="use-the-immediate-window"></a>Verwenden des Fensters „Direkt“

Das **Direktfenster** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen. Sie können den Wert von Variablen interaktiv ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt.

1. Wenn das Fenster **Direkt** nicht angezeigt wird, zeigen Sie es durch Auswählen von **Ansicht** > **Debugbereiche** > **Direkt** an.

1. Geben Sie `name = "Gracie"` im Fenster **Direkt** ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

1. Geben Sie `date = date.AddDays(1)` im Fenster **Direkt** ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   Im Fenster **Direkt** werden der Wert der Zeichenfolgenvariablen und die Eigenschaften des <xref:System.DateTime>-Werts angezeigt.

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window.png" alt-text="Fenster „Direkt“ in Visual Studio":::

   Im Fenster **Lokale Variablen** werden die Werte von Variablen angezeigt, die in der gerade ausgeführten Methode definiert sind. Die Werte der Variablen, die Sie gerade geändert haben, werden im Fenster **Lokale Variablen** aktualisiert.

   :::image type="content" source="media/debugging-with-visual-studio-mac/locals-window.png" alt-text="Fenster „Lokale Variablen“ in Visual Studio":::

1. Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>), um das Debuggen fortzusetzen.

   Die im Terminal gezeigten Werte entsprechen Ihren Änderungen im Fenster **Direkt**.

   Wenn das Terminal nicht angezeigt wird, wählen Sie auf der unteren Navigationsleiste **Terminal – HelloWorld** aus.

   :::image type="content" source="media/debugging-with-visual-studio-mac/terminal-hello-world.png" alt-text="„Terminal – HelloWorld“ auf der unteren Navigationsleiste":::

1. Drücken Sie eine beliebige Taste, um das Programm zu beenden.

1. Schließen Sie das Terminalfenster.

## <a name="set-a-conditional-breakpoint"></a>Festlegen eines bedingten Breakpoints

Das Programm zeigt eine Zeichenfolge an, die der Benutzer eingibt. Aber was geschieht, wenn der Benutzer gar nichts eingibt? Sie können dies mit einem nützlichen Debugfeature testen, das als *Bedingter Breakpoint* bezeichnet wird.

1. Klicken Sie bei gedrückter <kbd>CTRL</kbd>-Taste auf den roten Punkt, der den Haltepunkt darstellt. Wählen Sie im Kontextmenü **Haltepunkt bearbeiten** aus.

1. Geben Sie im Dialogfeld **Haltepunkt bearbeiten** den folgenden Code in das folgende Feld ein **Und die folgende Bedingung „True“ ist**, und wählen Sie **Anwenden** aus.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-settings.png" alt-text="Editor mit dem Panel für Haltepunkteinstellungen":::

   Jedes Mal, wenn der Breakpoint erreicht wird, ruft der Debugger die `String.IsNullOrEmpty(name)`-Methode auf, und die Ausführung wird nur in dieser Zeile unterbrochen, wenn der Methodenaufruf `true` zurückgibt.

   Anstelle eines bedingten Ausdrucks können Sie eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung mit der angegebenen Häufigkeit ausgeführt wird.

1. Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>), um das Debuggen zu starten.

1. Drücken Sie im Terminalfenster die <kbd>EINGABETASTE</kbd>, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.

   Da die angegebene Bedingung erfüllt wurde (`name` ist entweder `null` oder <xref:System.String.Empty?displayProperty=nameWithType>), endet die Ausführung des Programms, wenn der Haltepunkt erreicht wird.

1. Wählen Sie das Fenster **Lokale Variablen** aus, das die Werte der lokalen Variablen der aktuell ausgeführten Methode anzeigt. In diesem Fall ist `Main` die derzeit ausgeführte Methode. Stellen Sie sicher, dass die Variable `name` den Wert `""`, d. h. <xref:System.String.Empty?displayProperty=nameWithType>, hat.

1. Sie können auch erkennen, dass der Wert eine leere Zeichenfolge ist, indem Sie den Namen der Variablen `name` in das Fenster **Direkt** eingeben und die <kbd>EINGABETASTE</kbd> drücken.

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window-output.png" alt-text="Fenster „Direkt“ mit leerer Zeichenfolge als Name":::

1. Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>), um das Debuggen fortzusetzen.

1. Drücken Sie im Terminalfenster eine beliebige Taste, um das Programm zu beenden.

1. Schließen Sie das Terminalfenster.

1. Löschen Sie den Haltepunkt durch Klicken auf den Punkt am linken Rand des Codefensters. Eine andere Möglichkeit, einen Haltepunkt zu löschen, besteht darin, **Debuggen > Haltepunkt umschalten** auszuwählen, während die Codezeile ausgewählt ist.

## <a name="step-through-a-program"></a>Schrittweises Ausführen eines Programms

Mit Visual Studio können Sie ein Programm auch zeilenweise durchlaufen und die Ausführung jeder einzelnen Zeile überwachen. Normalerweise würden Sie einen Breakpoint festlegen und den Programmablauf in einem kleinen Teil des Programmcodes verfolgen. Da dieses Programm klein ist, können Sie das gesamte Programm schrittweise durchlaufen.

1. Legen Sie einen Haltepunkt auf der geschweiften Klammer fest, die den Anfang der `Main`-Methode markiert (drücken Sie <kbd>Befehl</kbd>+<kbd>\\</kbd>).

1. Drücken Sie <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>), um das Debuggen zu starten.

   Visual Studio wird in der Zeile mit dem Haltepunkt angehalten.

1. Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>UMSCHALT</kbd>+<kbd>BEFEHL</kbd>+<kbd>I</kbd>), oder wählen Sie **Ausführen** > **Einzelschritt**, um eine Zeile weiterzugehen.

   Visual Studio markiert einen Pfeil neben der nächsten Zeile der Ausführung und zeigt diesen an.

   :::image type="content" source="media/debugging-with-visual-studio-mac/step-into-method.png" alt-text="Visual Studio-Methode „Einzelschritt“":::

   An diesem Punkt wird im Fenster **Lokale Variablen** angezeigt, dass das `args`-Array leer ist und `name` und `date` Standardwerte aufweisen. Darüber hinaus hat Visual Studio ein leeres Terminal geöffnet.

1. Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>UMSCHALT</kbd>+<kbd>Befehl</kbd>+<kbd>I</kbd>).

   Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `name` enthält. Das Fenster **Lokale Variablen** zeigt, dass `name` den Wert `null` aufweist, und das Konsolenfenster zeigt die Zeichenfolge „What is your name?“ an.

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie eine Zeichenfolge in das Konsolenfenster eingeben und die <kbd>EINGABETASTE</kbd> drücken.

1. Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>UMSCHALT</kbd>+<kbd>Befehl</kbd>+<kbd>I</kbd>).

   Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `date` enthält. Das Fenster **Lokale Variablen** zeigt den vom Aufruf der Methode <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> zurückgegebenen Wert an. Im Terminal wird die Zeichenfolge angezeigt, die Sie an der Eingabeaufforderung eingegeben haben.

1. Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>UMSCHALT</kbd>+<kbd>Befehl</kbd>+<kbd>I</kbd>).

   Das Fenster **Lokale Variablen** zeigt den Wert der Variablen `date` nach der Zuweisung aus der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft an. Das Terminal ist unverändert.

1. Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>UMSCHALT</kbd>+<kbd>Befehl</kbd>+<kbd>I</kbd>).

   Visual Studio ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>-Methode auf. Das Terminal zeigt die formatierte Zeichenfolge an.

1. Drücken Sie <kbd>⇧</kbd><kbd>⌘</kbd><kbd>u</kbd> (<kbd>UMSCHALT</kbd>+<kbd>BEFEHL</kbd>+<kbd>U</kbd>), oder wählen Sie **Ausführen** > **Rücksprung** aus.

   Das Terminal zeigt eine Meldung an und wartet, bis Sie eine Taste drücken.

1. Drücken Sie eine beliebige Taste, um das Programm zu beenden.

## <a name="use-release-build-configuration"></a>Verwenden der Releasebuildkonfiguration

Nachdem Sie die Debugversion der Anwendung getestet haben, sollten Sie auch die Releaseversion kompilieren und testen. Die endgültige Releaseversion umfasst Compileroptimierungen, die das Verhalten einer Anwendung beeinträchtigen können. Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z. B. Racebedingungen in Multithreadanwendungen erstellen.

Um die Releaseversion Ihrer Konsolenanwendung zu erstellen und zu testen, führen Sie die folgenden Schritte aus:

1. Ändern Sie die Buildkonfiguration auf der Symbolleiste von **Debug** in **Release**.

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Visual Studio-Standardsymbolleiste mit hervorgehobenem Debug":::

1. Drücken Sie <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>OPTION</kbd>+<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>) zum Ausführen ohne Debuggen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Debugtools von Visual Studio verwendet. Im nächsten Tutorial veröffentlichen Sie eine bereitstellbare Version der App.

> [!div class="nextstepaction"]
> [Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac](publishing-with-visual-studio-mac.md)
