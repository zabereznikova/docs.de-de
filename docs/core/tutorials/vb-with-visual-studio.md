---
title: „Hallo Welt“-Anwendung in Visual Basic mit .NET Core in Visual Studio 2017
description: Erfahren Sie, wie Sie mithilfe von Visual Studio 2017 eine einfache .NET Core-Konsolenanwendung in Visual Basic erstellen.
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 1200afb30c6bdebf66b2a1e080c62a776a7e9826
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100874"
---
# <a name="build-a-visual-basic-hello-world-application-with-the-net-core-sdk-in-visual-studio-2017"></a>Erstellen einer „Hallo Welt“-Anwendung in Visual Basic mit dem .NET Core SDK in Visual Studio 2017

Dieses Thema ist eine grundlegende Einführung in das Erstellen, Debuggen und Veröffentlichen einer einfachen .NET Core-Konsolenanwendung in Visual Basic mithilfe von Visual Studio 2017. Visual Studio 2017 bietet eine Entwicklungsumgebung mit vollem Funktionsumfang für die Erstellung von .NET Core-Anwendungen. Sofern die Anwendung keine plattformspezifischen Abhängigkeiten aufweist, kann sie auf jeder von .NET Core unterstützten Plattform und in jedem System mit installiertem .NET Core ausgeführt werden.

## <a name="prerequisites"></a>Erforderliche Komponenten

[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) mit installierter Arbeitsauslastung für die „plattformübergreifende .NET Core-Entwicklung“. Sie können Ihre App mit .NET Core 2.1 oder höher entwickeln.

Weitere Informationen finden Sie unter [Prerequisites for .NET Core on Mac (Erforderliche Komponenten für .NET Core unter Mac)](../windows-prerequisites.md).

## <a name="a-simple-hello-world-application"></a>Eine einfache „Hello World“-Anwendung

Beginnen Sie, indem Sie eine einfache „Hello World“-Konsolenanwendung erstellen. Führen Sie folgende Schritte aus:

1. Starten Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Klicken Sie im Dialogfeld *Neues Projekt** auf den Knoten **Visual Basic** und anschließend auf den Knoten **.NET Core**. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)** . Geben Sie im Textfeld **Name** „HelloWorld“ ein. Klicken Sie auf die Schaltfläche **OK**.

   ![Dialogfeld „Neues Projekt“, in dem die Konsolen-App ausgewählt ist](./media/vb-with-visual-studio/visual-studio-new-project.png)

1. Visual Studio verwendet die Vorlage, um Ihr Projekt zu erstellen. Die Visual Basic-Konsolenanwendungsvorlage für .NET Core definiert automatisch die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String> Array als Argument akzeptiert. `Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet. Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.

   ![Visual Studio und das neue HelloWorld-Projekt](./media/vb-with-visual-studio/visual-studio-main-window.png)

   Die Vorlage erstellt eine einfache „Hello World“-Anwendung. Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um die literale Zeichenfolge „Hello World!“ im Konsolenfenster anzuzeigen. Indem Sie auf der Symbolleiste die **HelloWorld**-Schaltfläche mit dem grünen Pfeil auswählen, können Sie das Programm im Debugmodus ausführen. In diesem Fall ist das Konsolenfenster nur sehr kurz zu sehen und wird wieder geschlossen. Dies liegt daran, dass die Methode `Main` beendet wird und die Anwendung endet, sobald die einzige Anweisung in der `Main`-Methode ausgeführt wurde.

1. Damit die Anwendung anhält, bevor sie das Konsolenfenster schließt, fügen Sie den folgenden Code sofort nach dem Aufruf der <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode hinzu:

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```

   Dieser Code fordert den Benutzer auf, eine beliebige Taste zu drücken, und hält das Programm an, bis eine Taste gedrückt wurde.

1. Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus. Dies kompiliert Ihr Programm in eine Zwischensprache (IL), die dann von einem JIT-Compiler (Just in Time) in Binärcode konvertiert wird.

1. Führen Sie das Programm aus, indem Sie auf der Symbolleiste die **HelloWorld**-Schaltfläche mit dem grünen Pfeil auswählen.

   ![Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt](./media/with-visual-studio/hello-world-console.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

## <a name="enhancing-the-hello-world-application"></a>Erweitern der Hello World-Anwendung

Erweitern Sie Ihre Anwendung, um die Benutzer aufzufordern, seinen oder ihren Namen einzugeben und diesen mit dem Datum und der Uhrzeit anzuzeigen. Um das Programm zu ändern und zu testen, gehen Sie folgendermaßen vor:

1. Geben Sie im Codefenster unmittelbar nach der öffnenden geschweiften Klammer, die auf die Zeile `Sub Main(args As String())` folgt, und vor der ersten schließenden geschweiften Klammer den folgenden Visual Basic-Code ein:

   [!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   Dieser Code ersetzt den Inhalt der `Main`-Methode.

   ![Visual Studio-Programmdatei mit aktualisierter Main-Methode](./media/vb-with-visual-studio/visual-basic-code-window.png)

   Dieser Code zeigt „What is your name?“ im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat. Der Code speichert diese Zeichenfolge in einer Variablen namens `name`. Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `currentDate` zu. Schließlich verwendet der Code eine [interpolierte Zeichenfolge](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), um diese Werte im Konsolenfenster anzuzeigen.

1. Kompilieren Sie das Programm durch Auswählen von **Erstellen** > **Projektmappe erstellen**.

1. Führen Sie das Programm in Visual Studio im Debugmodus aus, indem Sie den grünen Pfeil auf der Symbolleiste auswählen, F5 drücken oder das Menüelement **Debuggen** > **Debuggen starten** auswählen. Reagieren Sie auf die Aufforderung, indem Sie einen Namen eingeben und die EINGABETASTE drücken.

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/hello-world-update.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

Sie haben Ihre Anwendung erstellt und ausgeführt. Wenn Sie professionelle Anwendungen erstellen möchten, führen Sie einige weitere Schritte aus, um Ihre Anwendung für die Veröffentlichung bereit zu machen:

- Informationen zum Debuggen Ihrer Anwendung finden Sie unter [Debuggen Ihrer .NET Core-Anwendung „Hallo Welt“ mit Visual Studio 2017](debugging-with-visual-studio.md).

- Informationen zum Veröffentlichen einer bereitstellbaren Version Ihrer Anwendung finden Sie unter [Veröffentlichen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017](publishing-with-visual-studio.md).

## <a name="related-topics"></a>Verwandte Themen

Anstatt eine Konsolenanwendung zu verwenden, können Sie auch eine .NET Standard-Klassenbibliothek mit Visual Basic, .NET Core und Visual Studio 2017 erstellen. Eine schrittweise Einführung finden Sie unter [Erstellen einer .NET Standard-Bibliothek mit Visual Basic und .NET Core SDK in Visual Studio 2017](vb-library-with-visual-studio.md).
