---
title: Erstellen einer „Hallo Welt“-Anwendung in C# mit .NET Core in Visual Studio 2017
description: Erfahren Sie, wie Sie mithilfe von Visual Studio 2017 eine einfache .NET Core-Konsolenanwendung mit C# erstellen.
author: BillWagner
ms.author: wiwagn
ms.date: 09/13/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: cc7d78006998b79fe9d522e71883ce1af817c051
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428560"
---
# <a name="build-a-c-hello-world-application-with-the-net-core-sdk-in-visual-studio-2017"></a>Erstellen einer „Hallo Welt“-Anwendung in C# mit dem .NET Core SDK in Visual Studio 2017

Dieser Artikel bietet eine grundlegende Einführung in das Erstellen, Debuggen und Veröffentlichen einer einfachen .NET Core-Konsolenanwendung in C# mithilfe von Visual Studio 2017. Visual Studio 2017 bietet eine Entwicklungsumgebung mit vollem Funktionsumfang für die Erstellung von .NET Core-Anwendungen. Sofern die Anwendung keine plattformspezifischen Abhängigkeiten aufweist, kann sie auf jeder von .NET Core unterstützten Plattform und in jedem System mit installiertem .NET Core ausgeführt werden.

## <a name="prerequisites"></a>Erforderliche Komponenten

[Visual Studio 2017 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“ Sie können Ihre App mit .NET Core 2.1 oder höher entwickeln.

Weitere Informationen finden Sie im Artikel [.NET Core-Abhängigkeiten und -Anforderungen](../install/sdk.md?tabs=netcore30&pivots=os-windows#install-with-visual-studio).

## <a name="a-simple-hello-world-application"></a>Eine einfache „Hello World“-Anwendung

Beginnen Sie, indem Sie eine einfache „Hello World“-Konsolenanwendung erstellen. Führen Sie folgende Schritte aus:

1. Starten Sie Visual Studio. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)** . Geben Sie im Textfeld **Name** „HelloWorld“ ein. Klicken Sie auf die Schaltfläche **OK**.

   ![Dialogfeld „Neues Projekt“, in dem die Konsolen-App ausgewählt ist](./media/with-visual-studio/visual-studio-new-project.png)

1. Visual Studio verwendet die Vorlage, um Ihr Projekt zu erstellen. Die C#-Konsolenanwendungsvorlage für .NET Core definiert automatisch die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String> Array als Argument akzeptiert. `Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet. Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.

   ![Visual Studio und das neue HelloWorld-Projekt](./media/with-visual-studio/visual-studio-main-window.png)

   Die Vorlage erstellt eine einfache „Hello World“-Anwendung. Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um die literale Zeichenfolge „Hello World!“ im Konsolenfenster anzuzeigen. Indem Sie auf der Symbolleiste die **HelloWorld**-Schaltfläche mit dem grünen Pfeil auswählen, können Sie das Programm im Debugmodus ausführen. In diesem Fall ist das Konsolenfenster nur sehr kurz zu sehen und wird wieder geschlossen. Dies liegt daran, dass die Methode `Main` beendet wird und die Anwendung endet, sobald die einzige Anweisung in der `Main`-Methode ausgeführt wurde.

1. Damit die Anwendung anhält, bevor sie das Konsolenfenster schließt, fügen Sie den folgenden Code sofort nach dem Aufruf der <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode hinzu:

   ```csharp
   Console.Write("Press any key to continue...");
   Console.ReadKey(true);
   ```

   Dieser Code fordert den Benutzer auf, eine beliebige Taste zu drücken, und hält das Programm an, bis eine Taste gedrückt wurde.

1. Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus. Dies kompiliert Ihr Programm in eine Zwischensprache (IL), die dann von einem JIT-Compiler (Just in Time) in Binärcode konvertiert wird.

1. Führen Sie das Programm aus, indem Sie auf der Symbolleiste die **HelloWorld**-Schaltfläche mit dem grünen Pfeil auswählen.

   ![Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt](./media/with-visual-studio/hello-world-console.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

## <a name="enhancing-the-hello-world-application"></a>Erweitern der Hello World-Anwendung

Erweitern Sie ihre Anwendung, um die Benutzer aufzufordern, Ihren Namen einzugeben und diesen mit dem Datum und der Uhrzeit anzuzeigen. Um das Programm zu ändern und zu testen, gehen Sie folgendermaßen vor:

1. Geben Sie im Codefenster unmittelbar nach der öffnenden geschweiften Klammer, die auf die Zeile `static void Main(string[] args)` folgt, und vor der ersten schließenden geschweiften Klammer den folgenden C#-Code ein:

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   Dieser Code ersetzt den Inhalt der `Main`-Methode.

   ![C#-Programmdatei von Visual Studio mit aktualisierter Main-Methode](./media/with-visual-studio/visual-csharp-code-window.png)

   Dieser Code zeigt „What is your name?“ im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat. Der Code speichert diese Zeichenfolge in einer Variablen namens `name`. Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu. Schließlich verwendet der Code eine [interpolierte Zeichenfolge](../../csharp/language-reference/tokens/interpolated.md), um diese Werte im Konsolenfenster anzuzeigen.

1. Kompilieren Sie das Programm durch Auswählen von **Erstellen** > **Projektmappe erstellen**.

1. Führen Sie das Programm in Visual Studio im Debugmodus aus, indem Sie den grünen Pfeil auf der Symbolleiste auswählen, F5 drücken oder das Menüelement **Debuggen** > **Debuggen starten** auswählen. Reagieren Sie auf die Aufforderung, indem Sie einen Namen eingeben und die EINGABETASTE drücken.

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/hello-world-update.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

Sie haben Ihre Anwendung erstellt und ausgeführt. Wenn Sie professionelle Anwendungen erstellen möchten, führen Sie einige weitere Schritte aus, um Ihre Anwendung für die Veröffentlichung bereit zu machen:

- Informationen zum Debuggen Ihrer Anwendung finden Sie unter [Debuggen Ihrer .NET Core-Anwendung „Hello World“ mit Visual Studio 2017](debugging-with-visual-studio.md).

- Informationen zum Entwickeln und Veröffentlichen einer bereitstellbaren Version Ihrer Anwendung finden Sie unter [Veröffentlichen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017](publishing-with-visual-studio.md).

## <a name="related-articles"></a>Verwandte Artikel

Anstatt eine Konsolenanwendung zu verwenden, können Sie auch mit .NET Core und Visual Studio 2017 eine Klassenbibliothek erstellen. Eine Schrittanleitung dazu finden Sie im Thema [Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017](library-with-visual-studio.md).

Sie können auch mit [Visual Studio Code](https://code.visualstudio.com/), einem kostenlosen, herunterladbaren Code-Editor, eine .NET Core-Konsolen-App unter Mac, Linux oder Windows entwickeln. Ein Tutorial mit Schrittanleitungen finden Sie unter [Erste Schritte mit Visual Studio Code](with-visual-studio-code.md).
