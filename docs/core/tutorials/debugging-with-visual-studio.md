---
title: Debuggen Ihrer Hello World-Anwendung (.NET Core) mit Visual Studio
description: Sie erfahren, wie Sie eine in C# oder Visual Basic geschriebene Hello World-App mit Visual Studio debuggen.
ms.date: 12/05/2019
ms.custom: vs-dotnet
ms.openlocfilehash: b2ee1401fc89f990c5f930d80d1a510a117e63a0
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156672"
---
# <a name="debug-your-c-or-visual-basic-net-core-hello-world-application-using-visual-studio"></a>Debuggen einer Hello World-Anwendung (.NET Core) in C# oder Visual Basic mit Visual Studio

Bisher haben Sie die Schritte unter [Erstellen Ihrer ersten .NET Core-Konsolenanwendung in Visual Studio 2019](with-visual-studio.md) zum Erstellen und Ausführen einer einfachen Konsolenanwendung befolgt. Sobald Sie Ihre Anwendung kompiliert und geschrieben haben, können Sie beginnen, sie zu testen. Visual Studio enthält einen umfassenden Satz von Debugtools, die Sie bei der Problembehandlung Ihrer Anwendung verwenden können.

## <a name="debug-build-configuration"></a>Buildkonfiguration „Debuggen“

*Debuggen* und *Freigabe* sind zwei Standardbuildkonfigurationen von Visual Studio. Die aktuelle Buildkonfiguration wird auf der Symbolleiste angezeigt. Das folgende Symbolleistenbild zeigt, dass Visual Studio konfiguriert wurde, um die Debugversion Ihrer Anwendung zu kompilieren:

![Visual Studio-Symbolleiste mit hervorgehobenem Debuggen](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

Führen Sie zunächst die Debugversion Ihrer App aus. Die Debugbuildkonfiguration deaktiviert die meisten Compileroptimierungen und stellt ausführlichere Informationen während des Buildprozesses bereit.

## <a name="set-a-breakpoint"></a>Haltepunkt festlegen

Führen Sie Ihr Programm aus, und probieren Sie einige Debugfunktionen aus:

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

1. Legen Sie einen *Breakpoint* für die Zeile mit dem Text `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` fest, indem Sie auf den linken Rand des Codefensters in dieser Zeile klicken. Sie können auch einen Breakpoint festlegen, indem Sie die Einfügemarke in der Codezeile platzieren und dann **F9** drücken oder **Debuggen** > **Breakpoint umschalten** in der Menüleiste auswählen.

   Ein Breakpoint unterbricht vorübergehend die Ausführung der Anwendung, *bevor* die Zeile mit dem Breakpoint ausgeführt wird.

   Wie in der folgenden Abbildung gezeigt, hebt Visual Studio die Zeile hervor, in der der Haltepunkt festgelegt ist, und zeigt an ihrem linken Rand einen roten Kreis an.

   ![Visual Studio-Programmfenster mit festgelegtem Haltepunkt](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. Führen Sie das Programm durch Auswählen der Schaltfläche **HelloWorld** mit dem grünen Pfeil auf der Symbolleiste, Drücken von **F5** oder Auswählen von **Debuggen** > **Debuggen starten** aus.

1. Geben Sie eine Zeichenfolge im Konsolenfenster ein, wenn das Programm Sie zur Eingabe eines Namens auffordert, und drücken Sie dann die **EINGABETASTE**.

1. Die Ausführung des Programms endet, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird. Im Fenster **Lokal** werden die Werte von Variablen angezeigt, die in der gerade ausgeführten Methode definiert sind.

   ![Screenshot eines Breakpoints in Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. Das **Direktfenster** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen. Sie können den Wert von Variablen interaktiv ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt.

   1. Wenn das **Direktfenster** nicht angezeigt wird, zeigen Sie es durch Auswählen von **Debuggen** > **Fenster** > **Direkt** an.

   1. Geben Sie `name = "Gracie"` im **Direktfenster** ein, und drücken Sie die **EINGABETASTE**.

   1. Geben Sie `date = DateTime.Parse("11/16/2019 5:25 PM")` im **Direktfenster** ein, und drücken Sie die **EINGABETASTE**.

   Im **Direktfenster** werden der Wert der Zeichenfolgenvariablen und die Eigenschaften des <xref:System.DateTime>-Werts angezeigt. Darüber hinaus werden die Werte der Variablen im Fenster **Lokal** aktualisiert.

   ![Fenster „Lokal“ und „Direkt“ in Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. Setzen Sie die Ausführung des Programms durch Auswählen der Schaltfläche **Fortfahren** in der Symbolleiste oder durch Auswählen von **Debuggen** > **Fortsetzen** fort. Die im Konsolenfenster angezeigten Werte entsprechen auch den Änderungen im **Direktfenster**.

   ![Konsolenfenster mit den eingegebenen Werten](./media/debugging-with-visual-studio/console-window.png)

1. Drücken Sie eine beliebige Taste, um die Anwendung und das Debuggen zu beenden.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Legen Sie einen *Breakpoint* für die Zeile mit dem Text `Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")` fest, indem Sie auf den linken Rand des Codefensters in dieser Zeile klicken. Sie können auch einen Breakpoint festlegen, indem Sie die Einfügemarke in der gewünschten Zeile platzieren und dann **Debuggen** > **Breakpoint umschalten** in der Menüleiste auswählen.

   Ein Breakpoint unterbricht vorübergehend die Ausführung der Anwendung, *bevor* die Zeile mit dem Breakpoint ausgeführt wird.

   Wie in der folgenden Abbildung gezeigt, hebt Visual Studio die Zeile hervor, in der der Haltepunkt gesetzt ist, und zeigt an ihrem linken Rand einen roten Kreis an.

   ![Visual Studio-Programmfenster mit festgelegtem Haltepunkt](./media/debugging-with-visual-studio/vb/set-breakpoint-in-editor.png)

1. Führen Sie das Programm durch Auswählen der Schaltfläche **HelloWorld** mit dem grünen Pfeil auf der Symbolleiste, Drücken von **F5** oder Auswählen von **Debuggen** > **Debuggen starten** aus.

1. Geben Sie eine Zeichenfolge im Konsolenfenster ein, wenn das Programm Sie zur Eingabe eines Namens auffordert, und drücken Sie die **EINGABETASTE**.

1. Die Ausführung des Programms endet, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird. Im Fenster **Lokal** werden die Werte von Variablen angezeigt, die in der gerade ausgeführten Methode definiert sind.

1. Das **Direktfenster** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen. Sie können den Wert von Variablen interaktiv ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt.

   1. Wenn das **Direktfenster** nicht angezeigt wird, zeigen Sie es durch Auswählen von **Debuggen** > **Fenster** > **Direkt** an.

   1. Geben Sie `name = "Gracie"` im **Direktfenster** ein, und drücken Sie die **EINGABETASTE**.

   1. Geben Sie `date = DateTime.Parse("11/16/2019 5:25 PM")` im **Direktfenster** ein, und drücken Sie die **EINGABETASTE**.

   Die Werte der Variablen werden im Fenster **Lokal** aktualisiert.

1. Setzen Sie die Ausführung des Programms durch Auswählen der Schaltfläche **Fortfahren** in der Symbolleiste oder des Menüelements **Debuggen** > **Fortfahren** fort. Die im Konsolenfenster angezeigten Werte entsprechen auch den Änderungen im **Direktfenster**.

   ![Konsolenfenster mit den eingegebenen Werten](./media/debugging-with-visual-studio/console-window.png)

1. Drücken Sie eine beliebige Taste, um die Anwendung und das Debuggen zu beenden.

---

## <a name="set-a-conditional-breakpoint"></a>Festlegen eines bedingten Breakpoints

Ihr Programm zeigt die Zeichenfolge an, die der Benutzer eingibt. Aber was geschieht, wenn der Benutzer gar nichts eingibt? Sie können dies mit einer nützlichen Debugfunktion namens *bedingter Haltepunkt* testen. Dabei wird die Programmausführung angehalten, wenn mindestens eine Bedingung erfüllt wurde.

Um einen bedingten Haltepunkt festzulegen und zu testen, was geschieht, wenn der Benutzer keine Zeichenfolge eingibt, führen Sie folgende Schritte aus:

# <a name="c"></a>[C#](#tab/csharp)

1. Klicken Sie mit der rechten Maustaste auf den roten Punkt, der den Haltepunkt darstellt. Wählen Sie im Kontextmenü **Bedingungen...** zum Öffnen des Dialogfelds **Haltepunkteinstellungen** aus. Aktivieren Sie das Kontrollkästchen für **Bedingungen**, wenn es nicht bereits aktiviert ist.

   ![Editor mit dem Panel für Haltepunkteinstellungen – C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. Ersetzen Sie für **Bedingten Ausdruck** „e.g. x == 5“ durch Folgendes:

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   Sie prüfen auf eine Codebedingung, dass der `String.IsNullOrEmpty(name)`-Methodenaufruf `true` ist, weil entweder `name` kein Wert zugewiesen wurde, oder weil sein Wert eine leere Zeichenfolge („“) ist. Anstelle eines bedingten Ausdrucks können Sie auch eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung eine angegebene Anzahl von Malen ausgeführt wird, oder eine *Filterbedingung*, wodurch die Ausführung des Programms auf Basis von Attributen wie Threadbezeichner, Prozessname oder Threadname unterbrochen wird.

1. Klicken Sie auf **Schließen**, um das Dialogfeld zu schließen.

1. Starten Sie das Programm im Debugmodus, indem Sie **F5**drücken.

1. Drücken Sie im Konsolenfenster die **EINGABETASTE**, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.

1. Da die angegebene Bedingung erfüllt wurde (`name` ist entweder `null` oder <xref:System.String.Empty?displayProperty=nameWithType>), endet die Ausführung des Programms, wenn sie den Breakpoint erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.

1. Wählen Sie das Fenster **Lokal** aus, das die Werte der lokalen Variablen der aktuell ausgeführten Methode anzeigt. In diesem Fall ist `Main` die derzeit ausgeführte Methode. Stellen Sie sicher, dass der Wert der Variablen `name``""` bzw. <xref:System.String.Empty?displayProperty=nameWithType> ist.

1. Bestätigen Sie, dass der Wert eine leere Zeichenfolge ist, indem Sie die folgende Anweisung im **Direktfenster** eingeben und dann die **EINGABETASTE** drücken. Das Ergebnis ist `true`.

   ```csharp
   ? name == String.Empty
   ```

   ![Das Direktfenster, das einen Wert „true“ zurückgibt, nachdem die Anweisung ausgeführt wurde – C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. Wählen Sie die Schaltfläche **Fortfahren** auf der Symbolleiste, um die Ausführung des Programms fortzusetzen.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.

1. Löschen Sie den Breakpoint durch Klicken auf den Punkt am linken Rand des Codefensters oder durch Auswählen von **Debuggen > Haltepunkt umschalten**, während die Codezeile ausgewählt ist.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Klicken Sie mit der rechten Maustaste auf den roten Punkt, der den Haltepunkt darstellt. Wählen Sie im Kontextmenü **Bedingungen...** zum Öffnen des Dialogfelds **Haltepunkteinstellungen** aus. Aktivieren Sie das Feld für **Bedingungen**.

   ![Editor mit dem Panel für Haltepunkteinstellungen – Visual Basic](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. Ersetzen Sie für den **bedingten Ausdruck** „e.g. x = 5“ durch Folgendes:

   ```vb
   String.IsNullOrEmpty(name)
   ```

   Sie prüfen auf eine Codebedingung, dass der `String.IsNullOrEmpty(name)`-Methodenaufruf `true` ist, weil entweder `name` kein Wert zugewiesen wurde, oder weil sein Wert eine leere Zeichenfolge („“) ist. Anstelle eines bedingten Ausdrucks können Sie auch eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung eine angegebene Anzahl von Malen ausgeführt wird, oder eine *Filterbedingung*, wodurch die Ausführung des Programms auf Basis von Attributen wie Threadbezeichner, Prozessname oder Threadname unterbrochen wird.

1. Klicken Sie auf **Schließen**, um das Dialogfeld zu schließen.

1. Starten Sie das Programm im Debugmodus, indem Sie **F5**drücken.

1. Drücken Sie im Konsolenfenster die **EINGABETASTE**, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.

1. Da die angegebene Bedingung erfüllt wurde (`name` ist entweder `null` oder <xref:System.String.Empty?displayProperty=nameWithType>), endet die Ausführung des Programms, wenn sie den Breakpoint erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.

1. Wählen Sie das Fenster **Lokal** aus, das die Werte der lokalen Variablen der aktuell ausgeführten Methode anzeigt. In diesem Fall ist `Main` die derzeit ausgeführte Methode. Stellen Sie sicher, dass der Wert der Variablen `name``""` bzw. <xref:System.String.Empty?displayProperty=nameWithType> ist.

1. Bestätigen Sie, dass der Wert eine leere Zeichenfolge ist, indem Sie die folgende Anweisung im **Direktfenster** eingeben und dann die **EINGABETASTE** drücken. Das Ergebnis ist `true`.

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   ![Das Direktfenster, das einen Wert „true“ zurückgibt, nachdem die Anweisung ausgeführt wurde – Visual Basic](./media/debugging-with-visual-studio/vb/immediate-window-output.png)

1. Wählen Sie die Schaltfläche **Fortfahren** auf der Symbolleiste, um die Ausführung des Programms fortzusetzen.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.

1. Löschen Sie den Haltepunkt durch Klicken auf den Punkt am linken Rand des Codefensters oder Auswählen des Menüelements **Debuggen > Haltepunkt ein/aus** mit der ausgewählten Zeile.

---
## <a name="step-through-a-program"></a>Schrittweises Ausführen eines Programms

Mit Visual Studio können Sie ein Programm auch zeilenweise durchlaufen und die Ausführung jeder einzelnen Zeile überwachen. Normalerweise würden Sie einen Haltepunkt festlegen und mit diesem Feature den Programmablauf in einem kleinen Teil des Programmcodes verfolgen. Da unser Programm klein ist, können Sie das gesamte Programm schrittweise durchlaufen:

# <a name="c"></a>[C#](#tab/csharp)

1. Wählen Sie auf der Menüleiste **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio markiert einen Pfeil neben der nächsten Zeile der Ausführung und zeigt diesen an.

   ![Visual Studio-Einzelschrittausführung in Methode – C#](./media/debugging-with-visual-studio/step-into-method.png)

   An diesem Punkt zeigt das Fenster **Lokal**, dass in Ihrem Programm nur eine Variable definiert ist: `args`. Da Sie keine Befehlszeilenargumente an das Programm übergeben haben, ist ihr Wert ein leeres Zeichenfolgenarray. Darüber hinaus hat Visual Studio ein leeres Konsolenfenster geöffnet.

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio hebt nun die nächste auszuführende Zeile hervor. Wie die Abbildung zeigt, ist weniger als eine Millisekunde zum Ausführen des Codes zwischen der letzten Anweisung und dieser verstrichen. `args` bleibt die einzige deklarierte Variable, und das Konsolenfenster ist noch leer.

   ![Visual Studio-Einzelschrittausführung in Methodenquelle – C#](./media/debugging-with-visual-studio/step-into-source-method.png)

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `name` enthält. Das Fenster **Lokal** zeigt, dass `name` den Wert `null` aufweist, und das Konsolenfenster zeigt die Zeichenfolge „What is your name?“ an.

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie eine Zeichenfolge in das Konsolenfenster eingeben und die **EINGABETASTE** drücken. Die Konsole reagiert nicht, und die eingegebene Zeichenfolge wird nicht im Konsolenfenster angezeigt, aber die <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>-Methode wird dennoch Ihre Eingabe erfassen.

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `date` enthält. Das Fenster **Lokal** zeigt den vom Aufruf der Methode <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> zurückgegebenen Wert an. Im Konsolenfenster wird auch die Zeichenfolge angezeigt, die Sie an der Eingabeaufforderung eingegeben haben.

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Das Fenster **Lokal** zeigt den Wert der Variablen `date` nach der Zuweisung aus der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft an. Das Konsolenfenster ist unverändert.

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>-Methode auf. Das Konsolenfenster zeigt die formatierte Zeichenfolge an.

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie **UMSCHALT**+**F11**. Dadurch wird die schrittweise Ausführung beendet. Das Konsolenfenster zeigt eine Meldung an und wartet, bis Sie eine Taste drücken.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Wählen Sie auf der Menüleiste **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio markiert einen Pfeil neben der nächsten Zeile der Ausführung und zeigt diesen an.

   ![Visual Studio-Einzelschrittausführung in Methode – Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   An diesem Punkt zeigt das Fenster **Lokal**, dass in Ihrem Programm nur eine Variable definiert ist: `args`. Da Sie keine Befehlszeilenargumente an das Programm übergeben haben, ist ihr Wert ein leeres Zeichenfolgenarray. Darüber hinaus hat Visual Studio ein leeres Konsolenfenster geöffnet.

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio hebt nun die nächste auszuführende Zeile hervor. Wie die Abbildung zeigt, sind weniger als eine Millisekunde zum Ausführen des Codes zwischen der letzten Anweisung und dieser verstrichen. `args` bleibt die einzige deklarierte Variable, und das Konsolenfenster ist noch leer.

   ![Visual Studio-Einzelschrittausführung in Methodenquelle – Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `name` enthält. Das Fenster **Lokal** zeigt, dass `name` den Wert `Nothing` aufweist, und das Konsolenfenster zeigt die Zeichenfolge „What is your name?“ an.

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie eine Zeichenfolge in das Konsolenfenster eingeben und die **EINGABETASTE** drücken. Die Konsole reagieren nicht, und die eingegebene Zeichenfolge wird nicht im Konsolenfenster angezeigt, aber die <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>-Methode wird dennoch Ihre Eingabe erfassen.

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `currentDate` enthält. Das Fenster **Lokal** zeigt den vom Aufruf der Methode <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> zurückgegebenen Wert an. Das Konsolenfenster zeigt auch die Zeichenfolge an, die eingegeben wurde, als die Konsole zur Eingabe aufforderte.

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Das Konsolenfenster ist unverändert.

1. Wählen Sie **Debuggen** > **Einzelschritt** aus, oder drücken Sie **F11**. Visual Studio ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>-Methode auf. Das Konsolenfenster zeigt die formatierte Zeichenfolge an.

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie **UMSCHALT**+**F11**. Dadurch wird die schrittweise Ausführung beendet. Das Konsolenfenster zeigt eine Meldung an und wartet, bis Sie eine Taste drücken.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und das Debuggen zu beenden.

---

## <a name="build-a-release-version"></a>Erstellen einer Releaseversion

Nachdem Sie die Debugversion der Anwendung getestet haben, sollten Sie auch die Releaseversion kompilieren und testen. Die endgültige Releaseversion umfasst Compileroptimierungen, die manchmal das Verhalten einer Anwendung negativ beeinträchtigen können. Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z. B. Racebedingungen in Multithreadanwendungen erstellen.

Ändern Sie zum Erstellen und Testen der endgültigen Produktversion der Konsolenanwendung die Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.

![Visual Studio-Standardsymbolleiste mit hervorgehobenem Debuggen](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

Wenn Sie **F5** drücken oder **Projektmappe erstellen** im Menü **Build** auswählen, kompiliert Visual Studio die Releaseversion der Anwendung. Sie können sie dann wie die Debugversion testen.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Ihre Anwendung debuggt haben, ist der nächste Schritt das Veröffentlichen einer bereitstellbaren Version der App. Weitere Informationen dazu finden Sie unter [Veröffentlichen Ihrer Hello World-Anwendung (.NET Core) mit Visual Studio](publishing-with-visual-studio.md).
