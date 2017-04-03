---
title: "Erstellen einer „Hello World“-Anwendung in C# mit .NET Core in Visual Studio 2017"
description: Erfahren Sie, wie Sie mithilfe von Visual Studio 2017 eine einfache .NET Core-Konsolenanwendung erstellen.
keywords: .NET Core, .NET Core-Konsolenanwendung, Visual Studio 2017
author: stevehoag
ms.author: shoag
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 97aa50bf-bdf8-416d-a56c-ac77504c14ea
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f1a20f399b4ab34986d700622ff3bf3859b001bd
ms.lasthandoff: 03/13/2017

---

# <a name="building-a-c-hello-world-application-with-net-core-in-visual-studio-2017"></a>Erstellen einer „Hello World“-Anwendung in C# mit .NET Core in Visual Studio 2017 #

Dieses Thema ist eine grundlegende Einführung in das Erstellen, Debuggen und Veröffentlichen einer einfachen .NET Core-Konsolenanwendung mithilfe von Visual Studio 2017. Visual Studio 2017 bietet eine Entwicklungsumgebung mit vollem Funktionsumfang für die Erstellung von .NET Core-Anwendungen. Sofern die Anwendung keine plattformspezifischen Abhängigkeiten aufweist, kann sie auf jeder von .NET Core unterstützten Plattform und in jedem System mit installiertem .NET Core ausgeführt werden.

## <a name="prerequisites"></a>Erforderliche Komponenten ##

- [Visual Studio 2017](https://www.visualstudio.com/downloads/) mit installierter Arbeitsauslastung für die „plattformübergreifende .NET Core-Entwicklung“. 

Weitere Informationen finden Sie im Thema mit den Windows-Voraussetzungen im Abschnitt [Visual Studio 2017](../../core/windows-prerequisites.md).

## <a name="a-simple-hello-world-application"></a>Eine einfache „Hello World“-Anwendung ##

Beginnen wir, indem wir eine einfache „Hello World“-Konsolenanwendung erstellen. Folgende Schritte müssen ausgeführt werden:

1. Starten Sie Visual Studio, und wählen Sie im Menü **Datei** die Option **Neu** > **Projekt**. Erweitern Sie im Dialogfeld **Neues Projekt** im linken Bereich den Knoten **Visual C#**. Wählen Sie dann den Knoten **.NET Core** aus.

2. Wählen Sie im rechten Bereich die Option **Konsolen-App (.NET Core)** aus. Geben Sie den Projektnamen ein: `HelloWorld`. Stellen Sie sicher, dass das Kontrollkästchen **Projektmappenverzeichnis erstellen** aktiviert ist, wie in der folgenden Abbildung dargestellt.

   ![Screenshot mit dem Dialogfeld „Neues Projekt“, in dem die Konsolen-App ausgewählt ist](./media/with-visual-studio/vs_newproject.jpg)
   
3. Klicken Sie auf die Schaltfläche **OK** . Visual Studio zeigt die Entwicklungsumgebung mit zugehörigem Codefenster an, wie in der folgenden Abbildung dargestellt. Die C#-Konsolenanwendungsvorlage für .NET Core definiert automatisch die Klasse `Program` mit der einzelnen Methode `Main`, die ein @System.String-Array als Argument akzeptiert. `Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet. Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.

   ![Visual Studio und das neue HelloWorld-Projekt](./media/with-visual-studio/vs_devenv.jpg)

   Die Vorlage erstellt eine sehr einfache „Hello World“-Anwendung: Sie ruft die @System.Console.WriteLine(System.String)-Methode auf, um die Literalzeichenfolge „Hello World!“ im Konsolenfenster anzuzeigen. Indem Sie auf der Symbolleiste die „HelloWorld“-Schaltfläche mit dem grünen Pfeil auswählen, können Sie das Programm jetzt im Debugmodus ausführen. In diesem Fall ist das Konsolenfenster allerdings nur sehr kurz zu sehen und wird wieder geschlossen. Dies liegt daran, dass `Main` beendet wird und die Anwendung endet, sobald die einzige Anweisung in der `Main`-Methode ausgeführt wurde.

4. Wir möchten aber, dass unsere Anwendung anhält, bevor sie das Konsolenfenster schließt. Fügen Sie direkt nach dem Aufruf der @System.Console.WriteLine(System.String)-Methode folgenden Code ein:

   ```csharp
   Console.Write("Press any key to continue...");
   Console.ReadKey(true);
   ```
   Dieser Code fordert den Benutzer auf, eine beliebige Taste zu drücken, und hält das Programm an, bis eine Taste gedrückt wurde.

5. Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**. Dies kompiliert Ihr Programm in IL, eine Zwischensprache, die dann von einem JIT-Compiler (Just in Time) in Binärcode konvertiert wird.

6. Führen Sie das Programm aus, indem Sie auf der Symbolleiste die „HelloWorld“-Schaltfläche mit dem grünen Pfeil auswählen. Das Ergebnis ist in der folgenden Abbildung dargestellt.

   ![Bild](./media/with-visual-studio/simple_hello.jpg)

7. Drücken Sie eine beliebige Taste, um das Fenster zu schließen.

## <a name="enhancing-the-hello-world-application"></a>Erweitern der „Hello World“-Anwendung ##

Erweitern wir jetzt unsere Anwendung, um die Benutzer zur Eingabe ihres Namens aufzufordern und diesen dann zusammen mit Datum und Uhrzeit im Konsolenfenster anzuzeigen. Um das Programm zu ändern und zu testen, gehen Sie folgendermaßen vor:

1. Geben Sie im Codefenster unmittelbar nach der öffnenden geschweiften Klammer, die auf die Zeile `public static void Main(string[] args)` folgt, und vor der ersten schließenden geschweiften Klammer den folgenden C#-Code ein.

   [!CODE [GettingStarted#1](../../../samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   Die folgende Abbildung zeigt das resultierende Codefenster.

   ![Das geänderte Programm in der Ausführung](./media/with-visual-studio/codewindow.jpg)

   Dieser Code zeigt „What is your name?“ in der Konsole an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat. Der Code speichert diese Zeichenfolge in einer Variablen namens `name`. Er ruft auch den Wert der @System.DateTime.Now-Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu. Dann verwendet der Code eine [zusammengesetzte Formatzeichenfolge](../../standard/base-types/composite-format.md), um diese Werte in der Konsole anzuzeigen.

2. Kompilieren Sie das Programm durch Auswählen von **Erstellen** > **Projektmappe erstellen**. Dies kompiliert Ihr Programm in IL, eine Zwischensprache, die dann von einem JIT-Compiler (Just in Time) in Binärcode konvertiert wird.

3. Führen Sie das Programm in Visual Studio im Debugmodus aus, indem Sie den grünen Pfeil auf der Symbolleiste auswählen, F5 drücken oder das Menüelement **Debuggen** > **Debuggen starten** auswählen. Nachdem Sie gemäß Eingabeaufforderung einen Namen eingegeben und die EINGABETASTE gedrückt haben, sollte das Konsolenfenster in etwa wie folgt aussehen:

   ![Das geänderte Programm in der Ausführung](./media/with-visual-studio/console.jpg)

4. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen. Das beendet den Debugmodus.

Sie haben jetzt eine einfache Anwendung erstellt und ausgeführt. Wenn Sie professionelle Anwendungen erstellen möchten, sind noch einige weitere Schritte auszuführen, um Ihre Anwendung für die Veröffentlichung bereit zu machen:

- Informationen zum Debuggen Ihrer Anwendung finden Sie unter [Debuggen der „Hello World“-Anwendung](debugging-with-visual-studio-2017.md).

- Informationen zum Entwickeln und Veröffentlichen einer bereitstellbaren Version Ihrer Anwendung finden Sie unter [Veröffentlichen der „Hello World“-Anwendung](publishing-with-visual-studio-2017.md).

## <a name="related-topics"></a>Verwandte Themen ##

Anstatt eine Konsolenanwendung zu verwenden, können Sie auch mit .NET Core und Visual Studio 2017 eine Klassenbibliothek erstellen. Eine Schrittanleitung dazu finden Sie im Thema [Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017](library-with-visual-studio-2017.md).

Sie können auch mit Visual Studio Code, einem kostenlosen, herunterladbaren Code-Editor, eine .NET Core-Konsolen-App unter Mac, Linux oder Windows entwickeln. Ein Tutorial mit Schrittanleitungen finden Sie unter [Erste Schritte mit Visual Studio Code](with-visual-studio-code.md).

