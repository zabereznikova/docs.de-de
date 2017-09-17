---
title: "Debuggen Ihrer C#-Anwendung „Hallo Welt“ mit Visual Studio 2017"
description: "Sie erfahren, wie Sie eine in C# geschriebene „Hello World“-App mit Visual Studio 2017 debuggen."
keywords: .NET Core, .NET Core-Konsolenanwendung, Debuggen von .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: cb213625-cc60-438b-9b9e-49aed0e4a974
ms.translationtype: HT
ms.sourcegitcommit: e0271ba3392ce8861dc916714af8c16d4581ce4f
ms.openlocfilehash: 19744773d18f6ea43e4b4a7518405b60e6b53acf
ms.contentlocale: de-de
ms.lasthandoff: 08/13/2017

---

# <a name="debug-your-hello-world-application-with-visual-studio-2017"></a>Debuggen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017

Bisher haben Sie die Schritte unter [Building a C# Hello World Application with .NET Core in Visual Studio 2017 (Erstellen einer „Hello World“-Anwendung in C# mit .NET Core in Visual Studio 2017](.\with-visual-studio.md)) oder [Build a Visual Basic Hallo Welt Application with .NET Core in Visual Studio 2017 (Erstellen einer „Hallo Welt“-Anwendung in Visual Basic mit .NET Core in Visual Studio 2017)](vb-with-visual-studio.md) zum Erstellen und Ausführen einer einfachen Konsolenanwendung befolgt. Sobald Sie Ihre Anwendung kompiliert und geschrieben haben, können Sie beginnen, sie zu testen. Visual Studio enthält einen umfassenden Satz von Debugtools, die Sie beim Testen Ihrer Anwendung und der Problembehandlung verwenden können.

## <a name="debugging-in-debug-mode"></a>Debuggen im Debugmodus

*Debuggen* und *Freigabe* sind zwei Standardbuildkonfigurationen von Visual Studio. Die aktuelle Buildkonfiguration wird auf der Symbolleiste angezeigt. Das folgende Symbolleistenbild zeigt, dass Visual Studio konfiguriert wurde, um Ihre Anwendung im Modus **Debuggen** zu kompilieren.

   ![Visual Studio-Symbolleiste](./media/debugging-with-visual-studio/toolbar1.png)

Sie sollten immer beginnen, indem Sie Ihr Programm im Debugmodus testen. Im Debugmodus sind die meisten Compileroptimierungen deaktiviert, und werden ausführlichere Informationen während des Buildprozesses bereitgestellt.

## <a name="setting-a-breakpoint"></a>Festlegen eines Haltepunkts

Führen Sie Ihr Programm im Debugmodus aus, und probieren Sie ein paar Debugfunktionen aus:

1. Ein *Haltepunkt* unterbricht vorübergehend die Ausführung der Anwendung, *bevor* die Zeile mit dem Haltepunkt ausgeführt wird. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
   Legen sie einen Haltepunkt auf der Zeile `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` fest, indem Sie auf den linken Rand des Codefensters auf dieser Zeile klicken, oder indem Sie das Menüelement **Debuggen** > **Haltepunkt ein/aus** mit der ausgewählten Zeile auswählen. Wie in der folgenden Abbildung gezeigt, hebt Visual Studio die Zeile hervor, in der der Haltepunkt gesetzt ist, und zeigt an ihrem linken Rand einen roten Kreis an.

   ![Visual Studio-Programmfenster mit festgelegtem Haltepunkt](./media/debugging-with-visual-studio/setbreakpoint.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
   Legen sie einen Haltepunkt auf der Zeile `Console.WriteLine(vbCrLf + $"Hello, {name}, on {currentDate:d} at {currentDate:t}!")` fest, indem Sie auf den linken Rand des Codefensters auf dieser Zeile klicken, oder indem Sie das Menüelement **Debuggen** > **Haltepunkt ein/aus** mit der ausgewählten Zeile auswählen. Wie in der folgenden Abbildung gezeigt, hebt Visual Studio die Zeile hervor, in der der Haltepunkt gesetzt ist, und zeigt an ihrem linken Rand einen roten Kreis an.

   <a name="visual-studio-program-window-with-breakpoint-setmediadebugging-with-visual-studiovb-setbreakpointpng"></a>![Visual Studio-Programmfenster mit festgelegtem Haltepunkt](./media/debugging-with-visual-studio/vb-setbreakpoint.png)
---

1. Führen Sie das Programm durch Auswählen der Schaltfläche **HelloWorld** mit dem grünen Pfeil auf der Symbolleiste, Drücken von F5 oder Auswahl von **Debuggen** > **Debuggen starten** im Debugmodus aus.

1. Geben Sie eine Zeichenfolge im Konsolenfenster ein, wenn das Programm Sie zur Eingabe eines Namens auffordert, und drücken Sie die EINGABETASTE.

1. Die Ausführung des Programms endet, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird. Im Fenster **Auto** werden die Werte der im Bereich der aktuellen Zeile verwendeten Variablen angezeigt. Im Fenster **Lokal** (das Sie anzeigen können, indem Sie auf die Registerkarte **Lokal** klicken) werden die Werte von Variablen angezeigt, die in der gerade ausgeführten Methode definiert sind.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
   ![Visual Studio-Anwendungsfenster](./media/debugging-with-visual-studio/break.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
   <a name="visual-studio-application-windowmediadebugging-with-visual-studiovb-breakpng"></a>![Visual Studio-Anwendungsfenster](./media/debugging-with-visual-studio/vb-break.png)
---

1. Sie können den Wert der Variablen ändern, um zu sehen, wie sich dies auf Ihr Programm auswirkt. Wenn das **Direktfenster** nicht angezeigt wird, zeigen Sie es durch Auswahl des Menüelements **Debuggen** > **Fenster** > **Direkt** an. Das **Direktfenster** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen.

1. Sie können die Werte der Variablen interaktiv ändern. Geben Sie `name = "Gracie"` im **Direktfenster** ein, und drücken Sie die EINGABETASTE.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Geben Sie `date = new DateTime(2016,11,01,11,59,00)` im **Direktfenster** ein, und drücken Sie die EINGABETASTE.

   Im **Direktfenster** werden der Wert der Zeichenfolgenvariablen und die Eigenschaften des @System.DateTime -Werts angezeigt. Darüber hinaus wird der Wert der Variablen in den Fenstern **Auto** und **Lokal** aktualisiert.

   ![Auto-Fenster und Direktfenster](./media/debugging-with-visual-studio/autosimmediate.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Geben Sie `currentDate = new DateTime(2016,11,01,11,59,00)` im **Direktfenster** ein, und drücken Sie die EINGABETASTE.

<!-- The **Immediate Window** displays the value of the string variable and the properties of the @System.DateTime value. In addition, the value of the variables is updated in the **Autos** and **Locals** windows.

   ![Autos window and Immediate Window](./media/debugging-with-visual-studio/vb-autosimmediate.png)
-->
---

1. Setzen Sie die Ausführung des Programms durch Auswählen der Schaltfläche **Fortfahren** in der Symbolleiste oder des Menüelements **Debuggen** > **Fortfahren** fort. Die im Konsolenfenster angezeigten Werte entsprechen auch den Änderungen im **Direktfenster**.

   ![Konsolenfenster, das den getippten Wert „Jack“ in der Aufforderung „Wie lautet Ihr Name?“ zeigt, gefolgt von „Hallo Gracie“ am 1.11.2016 um 11:59 Uhr](./media/debugging-with-visual-studio/changed.png)

1. Drücken Sie eine beliebige Taste, um die Anwendung und den Debugmodus zu beenden.

## <a name="setting-a-conditional-breakpoint"></a>Festlegen eines bedingten Haltepunkts

Ihr Programm zeigt die Zeichenfolge an, die der Benutzer eingibt. Aber was geschieht, wenn der Benutzer gar nichts eingibt? Sie können dies mit einer nützlichen Debugfunktion, dem *bedingten Haltepunkt*, testen, der die Programmausführung anhält, wenn mindestens eine Bedingung erfüllt wurde.

Um einen bedingten Haltepunkt festzulegen und zu testen, was geschieht, wenn der Benutzer keine Zeichenfolge eingibt, führen Sie folgende Schritte aus:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Klicken Sie mit der rechten Maustaste auf den roten Punkt, der den Haltepunkt darstellt. Wählen Sie im Kontextmenü **Bedingungen...** zum Öffnen des Dialogfelds **Haltepunkteinstellungen** aus. Aktivieren Sie das Feld für **Bedingungen**.

   ![Panel für Haltepunkteinstellungen](./media/debugging-with-visual-studio/breakpointsettings.png)

1. Ersetzen Sie für den **bedingten Ausdruck** „e.g. x == 5“ mit Folgendem:

   ```csharp
   String.IsNullOrEmpty(name)
   ```
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Klicken Sie mit der rechten Maustaste auf den roten Punkt, der den Haltepunkt darstellt. Wählen Sie im Kontextmenü **Bedingungen...** zum Öffnen des Dialogfelds **Haltepunkteinstellungen** aus. Aktivieren Sie das Feld für **Bedingungen**.

   ![Panel für Haltepunkteinstellungen](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. Ersetzen Sie für den **bedingten Ausdruck** „e.g. x = 5“ durch Folgendes:

   ```vb
   String.IsNullOrEmpty(name)
   ```
---

   Sie prüfen auf eine Codebedingung, dass der `String.IsNullOrEmpty(name)`-Methodenaufruf `true` ist, weil entweder *Name* kein Wert zugewiesen wurde, oder weil sein Wert eine leere Zeichenfolge ist („“). Sie können auch eine *Trefferanzahl* angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung eine angegebene Anzahl von Malen ausgeführt wird, oder eine *Filterbedingung*, wodurch die Ausführung des Programms auf Basis von Attributen wie Threadbezeichner, Prozessname oder Threadname unterbrochen wird.

1. Wählen Sie die Schaltfläche **Schließen** aus, um das Dialogfeld zu schließen.

1. Führen Sie das Programm im Debugmodus aus.

1. Drücken Sie im Konsolenfenster die EINGABETASTE, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.

1. Da die angegebene Bedingung erfüllt wurde – `name` ist entweder `null` oder <xref:System.String.Empty?displayProperty=fullName> – endet die Ausführung des Programms, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.

1. Wählen Sie das Fenster **Lokal**, das die Werte der lokalen Variablen der momentan ausgeführten Methode anzeigt, in diesem Fall der `Main`-Methode in Ihrem Programm. Stellen Sie sicher, dass der Wert der Variablen `name` `""` bzw. <xref:System.String.Empty?displayProperty=fullName> ist.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Bestätigen Sie, dass der Wert eine leere Zeichenfolge ist, indem Sie die folgende Anweisung im **Direktfenster** eingeben. Das Ergebnis ist `true`.

   ```csharp
   ? name == String.Empty
   ```

   ![Das Direktfenster, das einen Wert „true“ zurückgibt, nachdem die Anweisung ausgeführt wurde](./media/debugging-with-visual-studio/emptystring.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Bestätigen Sie, dass der Wert eine leere Zeichenfolge ist, indem Sie die folgende Anweisung im **Direktfenster** eingeben. Das Ergebnis ist `true`.

   ```vb
   ? String.IsNullOrEmpty(name)
   ```
  ![Das Direktfenster, das einen Wert „true“ zurückgibt, nachdem die Anweisung ausgeführt wurde](./media/debugging-with-visual-studio/vb-emptystring.png)
---

1. Wählen Sie die Schaltfläche **Fortfahren** auf der Symbolleiste, um die Ausführung des Programms fortzusetzen.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und den Debugmodus zu beenden.

1. Löschen Sie den Haltepunkt durch Klicken auf den Punkt am linken Rand des Codefensters oder Auswählen des Menüelements **Debuggen > Haltepunkt ein/aus** mit der ausgewählten Zeile.

---
## <a name="stepping-through-a-program"></a>Schrittweises Ausführen eines Programms

Mit Visual Studio können Sie ein Programm auch zeilenweise durchlaufen und die Ausführung jeder einzelnen Zeile überwachen. Normalerweise würden Sie einen Haltepunkt festlegen und mit diesem Feature den Programmablauf in einem kleinen Teil des Programmcodes verfolgen. Da unser Programm klein ist, können folgendermaßen das gesamte Programm durcharbeiten:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Wählen Sie auf der Menüleiste **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie die Taste F11. Visual Studio markiert einen Pfeil neben der nächsten Zeile der Ausführung und zeigt diesen an.

   ![Visual Studio-Fenster](./media/debugging-with-visual-studio/stepinto1.png)

   An diesem Punkt zeigt das Fenster **Auto**, dass Ihr Programm nur eine Variable definiert hat, `args`. Da Sie keine Befehlszeilenargumente an das Programm übergeben haben, ist ihr Wert ein leeres Zeichenfolgenarray. Darüber hinaus hat Visual Studio ein leeres Konsolenfenster geöffnet.

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie die Taste F11. Visual Studio hebt nun die nächste auszuführende Zeile hervor. Wie die Abbildung zeigt, sind weniger als eine Millisekunde zum Ausführen des Codes zwischen der letzten Anweisung und dieser verstrichen. `args` bleibt die einzige deklarierte Variable, und das Konsolenfenster ist noch leer.

   ![Visual Studio-Fenster](./media/debugging-with-visual-studio/stepinto2.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Wählen Sie auf der Menüleiste **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie die Taste F11. Visual Studio markiert einen Pfeil neben der nächsten Zeile der Ausführung und zeigt diesen an.

   ![Visual Studio-Fenster](./media/debugging-with-visual-studio/vb-stepinto1.png)

   Nun wird im Fenster **Auto** angezeigt, dass der Wert der `args`-Variablen ein leeres Zeichenfolgenarray ist, weil Sie dem Programm keine Befehlszeilenargumente übergeben haben. Darüber hinaus hat Visual Studio ein leeres Konsolenfenster geöffnet.

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie die Taste F11. Visual Studio hebt nun die nächste auszuführende Zeile hervor. Wie die Abbildung zeigt, sind weniger als eine Millisekunde zum Ausführen des Codes zwischen der letzten Anweisung und dieser verstrichen. `args` bleibt die einzige deklarierte Variable, und das Konsolenfenster ist noch leer.

   ![Visual Studio-Fenster](./media/debugging-with-visual-studio/vb-stepinto2.png)
---

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie die Taste F11. Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `name` enthält. Das Fenster **Auto** zeigt, dass `name` `null` (in C#) oder `Nothing` (in Visual Basic) ist, und das Konsolenfenster zeigt die Zeichenfolge „What is your name?“ an.

1. Reagieren Sie auf die Aufforderung, indem Sie eine Zeichenfolge im Konsolenfenster eingeben und die EINGABETASTE drücken. Die Konsole reagieren nicht, und die eingegebene Zeichenfolge wird nicht im Konsolenfenster angezeigt, aber die <xref:System.Console.ReadLine%2A?displayProperty=fullName>-Methode wird dennoch Ihre Eingabe erfassen.

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie die Taste F11. Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `date` (in C#) oder `currentDate` (in Visual Basic) enthält. Das Fenster **Auto** zeigt den <xref:System.DateTime.Now?displayProperty=fullName>-Eigenschaftswert und den nach Aufruf der <xref:System.Console.ReadLine%2A?displayProperty=fullName>-Methode zurückgegebenen Wert an. Das Konsolenfenster zeigt auch die Zeichenfolge an, die eingegeben wurde, als die Konsole zur Eingabe aufforderte.

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie die Taste F11. Das Fenster **Auto** zeigt den Wert der Variablen `date` nach der Zuweisung von der <xref:System.DateTime.Now?displayProperty=fullName>-Eigenschaft an. Das Konsolenfenster ist unverändert.

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung** aus, oder drücken Sie die Taste F11. Visual Studio ruft die <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=fullName>-Methode auf. Die Werte der Variablen `date` (oder `currentDate`) und `name` werden im Fenster **Auto** angezeigt, und das Konsolenfenster zeigt die formatierte Zeichenfolge an.

1. Wählen Sie **Debuggen** > **Ausführen bis Rücksprung**, oder drücken Sie UMSCHALT+ F11-Taste. Dadurch wird die schrittweise Ausführung beendet. Das Konsolenfenster zeigt eine Meldung an und wartet, bis Sie eine Taste drücken.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und den Debugmodus zu beenden.

## <a name="building-a-release-version"></a>Erstellen einer endgültigen Releaseversion

Nachdem Sie den Debugbuild der Anwendung getestet haben, sollten Sie auch die endgültige Releaseversion kompilieren und testen. Die endgültige Releaseversion umfasst Compileroptimierungen, die manchmal das Verhalten einer Anwendung negativ beeinträchtigen können. Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z.B. in asynchronen oder Multithreadanwendungen Racebedingungen erstellen.

Ändern Sie zum Erstellen und Testen der endgültigen Produktversion der Konsolenanwendung die Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.

![Bild](./media/debugging-with-visual-studio/toolbar2.png)

Wenn Sie F5 drücken oder **Projektmappe erstellen** im Menü **Build** auswählen, kompiliert Visual Studio die endgültige Releaseversion der Konsolenanwendung zum Testen. Sie können sie dann wie die Debugversion der Anwendung testen.

Nachdem Sie das Debuggen der Anwendung abgeschlossen haben, ist der nächste Schritt das Veröffentlichen einer verteilbare Version der Anwendung. Informationen hierzu finden Sie unter [Publish the Hello World application with Visual Studio 2017 (Veröffentlichen der „Hallo Welt“-Anwendung mit Visual Studio 2017)](./publishing-with-visual-studio.md).

