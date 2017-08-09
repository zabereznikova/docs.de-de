---
title: "Erstellen einer „Hello World“-Anwendung in C# mit .NET Core in Visual Studio 2017"
description: Erfahren Sie, wie Sie mithilfe von Visual Studio 2017 eine einfache .NET Core-Konsolenanwendung erstellen.
keywords: .NET Core, .NET Core-Konsolenanwendung, Visual Studio 2017
author: BillWagner
ms.author: wiwagn
ms.date: 05/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 97aa50bf-bdf8-416d-a56c-ac77504c14ea
ms.translationtype: Human Translation
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b19bf07b2a2bba944bb33ddb1c887f77331ba8d1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="building-a-c-hello-world-application-with-net-core-in-visual-studio-2017"></a>Erstellen einer „Hello World“-Anwendung in C# mit .NET Core in Visual Studio 2017

Dieses Thema ist eine grundlegende Einführung in das Erstellen, Debuggen und Veröffentlichen einer einfachen .NET Core-Konsolenanwendung mithilfe von Visual Studio 2017. Visual Studio 2017 bietet eine Entwicklungsumgebung mit vollem Funktionsumfang für die Erstellung von .NET Core-Anwendungen. Sofern die Anwendung keine plattformspezifischen Abhängigkeiten aufweist, kann sie auf jeder von .NET Core unterstützten Plattform und in jedem System mit installiertem .NET Core ausgeführt werden.

## <a name="prerequisites"></a>Erforderliche Komponenten

[Visual Studio 2017](https://www.visualstudio.com/downloads/) mit installierter Arbeitsauslastung für die „plattformübergreifende .NET Core-Entwicklung“. 

Weitere Informationen finden Sie unter [Prerequisites for .NET Core on Mac (Erforderliche Komponenten für .NET Core unter Mac)](../../core/windows-prerequisites.md).

## <a name="a-simple-hello-world-application"></a>Eine einfache „Hello World“-Anwendung

Beginnen Sie, indem Sie eine einfache „Hello World“-Konsolenanwendung erstellen. Führen Sie folgende Schritte aus:

1. Starten Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** den Knoten **.NET Core**, gefolgt von der Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie im Textfeld **Name** „HelloWorld“ ein. Klicken Sie auf die Schaltfläche **OK**.

   ![Dialogfeld „Neues Projekt“, in dem die Konsolen-App ausgewählt ist](./media/with-visual-studio/newproject.png)
   
1. Visual Studio lädt die Entwicklungsumgebung. Die C#-Konsolenanwendungsvorlage für .NET Core definiert automatisch die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String> Array als Argument akzeptiert. `Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet. Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.

   ![Visual Studio und das neue HelloWorld-Projekt](./media/with-visual-studio/devenv.png)

   Die Vorlage erstellt eine einfache „Hello World“-Anwendung. Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=fullName>-Methode auf, um die literale Zeichenfolge „Hello World!“ im Konsolenfenster anzuzeigen. Indem Sie auf der Symbolleiste die **HelloWorld**-Schaltfläche mit dem grünen Pfeil auswählen, können Sie das Programm im Debugmodus ausführen. In diesem Fall ist das Konsolenfenster nur sehr kurz zu sehen und wird wieder geschlossen. Dies liegt daran, dass die Methode `Main` beendet wird und die Anwendung endet, sobald die einzige Anweisung in der `Main`-Methode ausgeführt wurde.

1. Damit die Anwendung anhält, bevor sie das Konsolenfenster schließt, fügen Sie den folgenden Code sofort nach dem Aufruf der <xref:System.Console.WriteLine(System.String)?displayProperty=fullName>-Methode hinzu:

   ```csharp
   Console.Write("Press any key to continue...");
   Console.ReadKey(true);
   ```
   Dieser Code fordert den Benutzer auf, eine beliebige Taste zu drücken, und hält das Programm an, bis eine Taste gedrückt wurde.

1. Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus. Dies kompiliert Ihr Programm in eine Zwischensprache (IL), die dann von einem JIT-Compiler (Just in Time) in Binärcode konvertiert wird.

1. Führen Sie das Programm aus, indem Sie auf der Symbolleiste die **HelloWorld**-Schaltfläche mit dem grünen Pfeil auswählen.

   ![Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt](./media/with-visual-studio/helloworld1.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

## <a name="enhancing-the-hello-world-application"></a>Erweitern der Hello World-Anwendung

Erweitern Sie ihre Anwendung, um die Benutzer aufzufordern, Ihren Namen einzugeben und diesen mit dem Datum und der Uhrzeit anzuzeigen. Um das Programm zu ändern und zu testen, gehen Sie folgendermaßen vor:

1. Geben Sie im Codefenster unmittelbar nach der öffnenden geschweiften Klammer, die auf die Zeile `public static void Main(string[] args)` folgt, und vor der ersten schließenden geschweiften Klammer den folgenden C#-Code ein:

   [!code-csharp[GettingStarted#1](../../../samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   ![C#-Programmdatei von Visual Studio mit aktualisierter Main-Methode](./media/with-visual-studio/codewindow.png)

   Dieser Code zeigt „What is your name?“ im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat. Der Code speichert diese Zeichenfolge in einer Variablen namens `name`. Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=fullName> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu. Schließlich verwendet der Code eine [zusammengesetzte Formatzeichenfolge](../../standard/base-types/composite-format.md), um diese Werte im Konsolenfenster anzuzeigen.

1. Kompilieren Sie das Programm durch Auswählen von **Erstellen** > **Projektmappe erstellen**.

1. Führen Sie das Programm in Visual Studio im Debugmodus aus, indem Sie den grünen Pfeil auf der Symbolleiste auswählen, F5 drücken oder das Menüelement **Debuggen** > **Debuggen starten** auswählen. Reagieren Sie auf die Aufforderung, indem Sie einen Namen eingeben und die EINGABETASTE drücken.

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/helloworld2.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

Sie haben Ihre Anwendung erstellt und ausgeführt. Wenn Sie professionelle Anwendungen erstellen möchten, führen Sie einige weitere Schritte aus, um Ihre Anwendung für die Veröffentlichung bereit zu machen:

- Informationen zum Debuggen Ihrer Anwendung finden Sie unter [Debuggen Ihrer C#-Anwendung „Hello World“ mit Visual Studio 2017](debugging-with-visual-studio.md).

- Informationen zum Entwickeln und Veröffentlichen einer bereitstellbaren Version Ihrer Anwendung finden Sie unter [Veröffentlichen Ihrer „Hello World“-Anwendung mit Visual Studio 2017](publishing-with-visual-studio.md).

## <a name="related-topics"></a>Verwandte Themen

Anstatt eine Konsolenanwendung zu verwenden, können Sie auch mit .NET Core und Visual Studio 2017 eine Klassenbibliothek erstellen. Eine Schrittanleitung dazu finden Sie im Thema [Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017](library-with-visual-studio.md).

Sie können auch mit [Visual Studio Code](https://code.visualstudio.com/), einem kostenlosen, herunterladbaren Code-Editor, eine .NET Core-Konsolen-App unter Mac, Linux oder Windows entwickeln. Ein Tutorial mit Schrittanleitungen finden Sie unter [Erste Schritte mit Visual Studio Code](with-visual-studio-code.md).
