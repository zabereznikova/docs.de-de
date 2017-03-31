---
title: "Debuggen Ihrer C#-Anwendung „Hello World“ mit Visual Studio 2017"
description: "Sie erfahren, wie Sie eine in C# geschriebene „Hello World“-App mit Visual Studio 2017 debuggen."
keywords: .NET Core, .NET Core-Konsolenanwendung, Debuggen von .NET Core
author: stevehoag
ms.author: shoag
ms.date: 10/24/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: cb213625-cc60-438b-9b9e-49aed0e4a974
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6a6a461984c140d180cf70cd7a1a33818a40b451
ms.lasthandoff: 03/13/2017

---

# <a name="debugging-your-c-hello-world-application-with-visual-studio-2017"></a>Debuggen Ihrer C#-Anwendung „Hello World“ mit Visual Studio 2017 #

Bisher haben Sie die Schritte unter [Building a c# Hello World Application with .NET Core in Visual Studio 2017](.\with-visual-studio-2017.md) (Erstellen einer „Hello World“-Anwendung in C# mit .NET Core in Visual Studio 2017) zum Erstellen und Ausführen einer einfachen Konsolenanwendung befolgt. Sobald Sie eine Anwendung kompiliert und geschrieben haben, können Sie beginnen, sie zu testen. Visual Studio enthält einen umfassenden Satz von Debugtools, die Sie beim Testen Ihrer Anwendung und der Problembehandlung verwenden können. Sie werden einige von ihnen beim Debuggen unserer Anwendung kennenlernen.

## <a name="debugging-in-debug-mode"></a>Debuggen im Debugmodus ##

Der Debugmodus ist eine der beiden standardmäßigen Buildkonfigurationen von Visual Studio. (Die andere ist der Releasemodus.) Die aktuelle Buildkonfiguration wird auf der Symbolleiste angezeigt. Die folgende Abbildung zeigt, dass unsere Anwendung im Debugmodus kompiliert wird.

   ![Bild](./media/debugmode.jpg)

Sie sollten Ihr Programm immer zunächst im Debugmodus testen. Im Debugmodus sind die meisten Compileroptimierungen deaktiviert, und die Ausgabe des Buildprozesses in der Symboldatenbankdatei (PDB-Datei) bietet umfassendere Informationen.

## <a name="setting-a-breakpoint"></a>Festlegen eines Haltepunkts ##

Wir führen unser Programm im Debugmodus aus und probieren ein paar Debugfunktionen aus:

1. Festlegen eines Haltepunkts durch Positionieren des Cursors in der Zeile `Console.WriteLine("\nHello, {0}, on {1:d} at {1:t}", name, date);` und Klicken auf den linken Rand des Codefensters oder durch Auswählen des Menüelements **Debuggen**, **Haltepunkt ein/aus**. (Ein Haltepunkt unterbricht vorübergehend die Ausführung der Anwendung, *bevor* die Zeile mit dem Haltepunkt ausgeführt wird.) Wie in der folgenden Abbildung gezeigt, hebt Visual Studio die Zeile hervor, in der der Haltepunkt gesetzt ist, und zeigt an ihrem linken Rand einen roten Kreis an.

   ![Bild](./media/setbreakpoint_2017.jpg)

1. Führen Sie das Programm durch Auswählen der Schaltfläche „HelloWorld“ mit dem grünen Pfeil auf der Symbolleiste, Drücken von F5 oder Auswahl von **Debuggen**, **Debuggen starten** im Debugmodus aus.

1. Geben Sie eine Zeichenfolge im Konsolenfenster ein, wenn das Programm Sie zur Eingabe eines Namens auffordert, und drücken Sie die EINGABETASTE.

1. Die Ausführung des Programms endet, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird. Visual Studio sollte in etwa der folgenden Abbildung entsprechen. Beachten Sie, dass im Fenster **Auto** die Werte der im Bereich der aktuellen Zeile verwendeten Variablen angezeigt werden. (Im Fenster **Lokal** werden die Werte von Variablen angezeigt, die in der gerade ausgeführten Methode definiert sind.)

   ![Bild](./media/breakpoint_2017.jpg)

1. Wir versuchen nun, den Wert der Variablen zu ändern, um zu sehen, wie sich dies auf unsere Anwendung auswirkt. Wenn das **Direktfenster** nicht angezeigt wird, zeigen Sie es durch Auswahl des Menüelements **Debuggen**, **Fenster**, **Direkt** an. Das **Direktfenster** dient Ihrer Interaktion mit der Anwendung, die Sie debuggen.

1. Sie können die Werte der Variablen interaktiv ändern. Geben Sie `name = "Yuma"` im Direktfenster ein, und drücken Sie die EINGABETASTE.

1. Geben Sie `date = new DateTime(2016,11,01,11,59,00)` im Direktfenster ein, und drücken Sie die EINGABETASTE.

   Die folgende Abbildung zeigt das **Direktfenster**:

   ![Bild](./media/immediatewindow.jpg)

   Beachten Sie, dass im Fenster der Wert der Zeichenfolgenvariablen und die Eigenschaften des @System.DateTime-Werts angezeigt werden. Darüber hinaus wird der Wert der Variablen in den Fenstern **Auto** und **Lokal** aktualisiert.

1. Setzen Sie die Ausführung des Programms durch Auswählen der Schaltfläche **Fortfahren** in der Symbolleiste oder des Menüelements **Debuggen**, **Fortfahren** fort. Das resultierende Konsolenfenster sollte der folgenden Abbildung ähneln. Beachten Sie, dass die in der Konsole angezeigten Werte auch unseren Änderungen im **Direktfenster** entsprechen.

   ![Bild](./media/changed.jpg)

1. Drücken Sie eine beliebige Taste, um die Anwendung und den Debugmodus zu beenden.

## <a name="setting-a-conditional-breakpoint"></a>Festlegen eines bedingten Haltepunkts ##

Jetzt wissen wir, dass unser Programm die Zeichenfolge, die der Benutzer eingibt, ordnungsgemäß anzeigt. Aber was geschieht, wenn der Benutzer gar nichts eingibt? Wir können dies testen und hierbei eine andere Debugfunktion verwenden – die Möglichkeit, einen bedingten Haltepunkt festzulegen.

Um einen bedingten Haltepunkt festzulegen und zu testen, was geschieht, wenn der Benutzer keine Zeichenfolge eingibt, führen Sie folgende Schritte aus:

1. Klicken Sie mit der rechten Maustaste auf den roten Punkt, der den Haltepunkt darstellt. Wählen Sie im Kontextmenü **Bedingungen...** zum Öffnen des in der folgenden Abbildung dargestellten Dialogfelds **Haltepunkteinstellungen**.

   ![Bild](./media/breakpoint_settings.jpg)

1. Geben Sie in das Textfeld mit dem Inhalt „e.g. x == 5“ Folgendes ein:

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   Hier bezieht sich der Test auf eine Codebedingung. Wir können auch eine Trefferanzahl angeben, wodurch die Ausführung des Programms unterbrochen wird, bevor eine Anweisung eine angegebene Anzahl von Malen ausgeführt wird, oder eine Filterbedingung, wodurch die Ausführung des Programms auf Basis von Attributen wie Threadbezeichner, Prozessname und Threadname unterbrochen wird.

1. Wählen Sie die Schaltfläche **Schließen** aus, um das Dialogfeld zu schließen.

1. Führen Sie das Programm im Debugmodus aus.

1. Drücken Sie im Konsolenfenster die EINGABETASTE, wenn Sie zur Eingabe Ihres Namens aufgefordert werden.

1. Da die angegebene Bedingung erfüllt wurde – `name` ist entweder `null` oder [String.Empty](xref:System.String.Empty) – endet die Ausführung des Programms, wenn sie den Haltepunkt erreicht, und bevor die `Console.WriteLine`-Methode ausgeführt wird.

1. Wählen Sie das Fenster **Lokal**, das die Werte der lokalen Variablen der momentan ausgeführten Methode anzeigt, in diesem Fall der `Main`-Methode.

1. Beachten Sie, dass der Wert der Variablen `name` "" bzw. [String.Empty](xref:System.String.Empty) ist. Bestätigen Sie dies, indem Sie die folgende Anweisung im **Direktfenster** eingeben:

   ```csharp
   ? name == String.Empty
   ```

   Die folgende Abbildung zeigt das Ergebnis.

   ![Bild](./media/emptystring.jpg)

1. Wählen Sie die Schaltfläche **Fortfahren** auf der Symbolleiste, um die Ausführung des Programms fortzusetzen.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und den Debugmodus zu beenden.

1. Löschen Sie den Haltepunkt durch Klicken auf den Punkt am linken Rand des Codefensters oder Auswählen des Menüelements **Debuggen**, **Haltepunkt ein/aus**.

## <a name="stepping-through-a-program"></a>Schrittweises Ausführen eines Programms ##

Mit Visual Studio können Sie ein Programm auch zeilenweise durchlaufen und die Ausführung jeder einzelnen Zeile überwachen. Normalerweise würden Sie einen Haltepunkt festlegen und mit diesem Feature den Programmablauf in einem kleinen Teil des Programmcodes verfolgen. Da unser Programm klein ist, gehen wir folgendermaßen das gesamte Programm durch:

1. Wählen Sie auf der Menüleiste **Debuggen**, **Einzelschritt** aus, oder drücken Sie die Taste F11. Visual Studio hebt die nächste auszuführende Codezeile hervor und zeigt einen Pfeil neben ihr an, wie in der folgenden Abbildung dargestellt.

   ![Bild](./media/step_into.jpg)

   An diesem Punkt zeigt das Fenster **Auto**, dass unser Programm nur eine Variable definiert hat, `args`. Da wir keine Befehlszeilenargumente an das Programm übergeben haben, ist ihr Wert ein leeres Zeichenfolgenarray. Darüber hinaus hat Visual Studio ein leeres Konsolenfenster geöffnet.

1. Wählen Sie **Debuggen**, **Einzelschritt** aus, oder drücken Sie die Taste F11. Visual Studio hebt nun die nächste auszuführende Zeile hervor. Wie die Abbildung zeigt, sind 3 Millisekunden zum Ausführen des Codes zwischen der letzten Anweisung und dieser verstrichen. `args` bleibt die einzige deklarierte Variable, und das Konsolenfenster ist noch leer.

   ![Bild](./media/step_into_2.jpg)

1. Wählen Sie **Debuggen**, **Einzelschritt** aus, oder drücken Sie die Taste F11. Visual Studio hebt die Anweisung hervor, die die `name`-Variablenzuweisung enthält. Das Fenster **Auto** zeigt, dass `name` `null` ist, und das Konsolenfenster zeigt die Zeichenfolge „What is your name?“ an.

1. Reagieren Sie auf die Aufforderung, indem Sie eine Zeichenfolge im Konsolenfenster eingeben und die EINGABETASTE drücken. Die Konsole wird nicht reagieren, und die eingegebene Zeichenfolge wird nicht im Konsolenfenster angezeigt, aber die [Console.ReadLine](xref:System.Console.ReadLine)-Methode wird dennoch Ihre Eingabe erfassen.

1. Wählen Sie **Debuggen**, **Einzelschritt** aus, oder drücken Sie die Taste F11. Visual Studio hebt die Anweisung hervor, die die Zuweisung der Variablen `date` enthält. Das Fenster **Auto** zeigt den [DateTime.Now](xref:System.DateTime.Now)-Eigenschaftswert und den nach Aufruf der [Console.ReadLine](xref:System.Console.ReadLine)-Methode zurückgegebenen Wert an. Das Konsolenfenster zeigt auch die Zeichenfolge an, die eingegeben wurde, als die Konsole zur Eingabe aufforderte.

1. Wählen Sie **Debuggen**, **Einzelschritt** aus, oder drücken Sie die Taste F11. Das Fenster **Auto** zeigt jetzt den Wert der Variablen `date` nach der Zuweisung von der [DateTime.Now](xref:System.DateTime.Now)-Eigenschaft an. Das Konsolenfenster ist unverändert.

1. Wählen Sie **Debuggen**, **Einzelschritt** aus, oder drücken Sie die Taste F11. Visual Studio ruft die [Console.WriteLine](xref:System.Console.WriteLine(System.String,System.Object,System.Object))-Methode auf. Die Werte der Variablen `date` und `name` werden im Fenster **Auto** angezeigt, und das Konsolenfenster zeigt die formatierte Zeichenfolge an.

1. Wählen Sie **Debuggen**, **Prozedurschritt**, oder drücken Sie UMSCHALT+ F11-Taste. Dadurch wird die schrittweise Ausführung beendet. Das Konsolenfenster zeigt eine Meldung an und wartet, bis wir eine Taste drücken.

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen und den Debugmodus zu beenden.

## <a name="building-a-release-version"></a>Erstellen einer endgültigen Produktversion ##

Nachdem Sie den Debugbuild der Anwendung getestet haben, sollten Sie auch die endgültige Produktversion kompilieren und testen. Die endgültige Produktversion umfasst Compileroptimierungen, die manchmal das Verhalten einer Anwendung beeinträchtigen können. Compileroptimierungen, die zur Verbesserung der Leistung entwickelt wurden, können z.B. in asynchronen oder Multithreadanwendungen Racebedingungen erstellen.

Ändern Sie zum Erstellen und Testen der endgültigen Produktversion der Konsolenanwendung die Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**, wie in der folgenden Abbildung dargestellt.

![Bild](./media/release.jpg)

Wenn Sie F5 drücken oder **Projektmappe erstellen** im Menü **Build** auswählen, kompiliert Visual Studio die endgültige Produktversion der Konsolenanwendung zum Testen. Sie können sie dann wie die Debugversion der Anwendung ausführen und testen.

Nachdem Sie das Debuggen der Anwendung abgeschlossen haben, ist der nächste Schritt das Veröffentlichen einer verteilbare Version der Anwendung. Informationen hierzu finden Sie unter [Publishing the C# Hello World application with Visual Studio 2017](./publishing-with-visual-studio-2017.md) (Veröffentlichen der „Hello World“-C#-Anwendung mit Visual Studio 2017).

