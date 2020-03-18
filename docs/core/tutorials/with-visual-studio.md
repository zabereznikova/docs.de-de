---
title: Erstellen einer Hello World-Anwendung mit .NET Core in Visual Studio
description: Erfahren Sie, wie Sie mithilfe von Visual Studio Ihre erste .NET-Konsolenanwendung mit C# oder Visual Basic erstellen.
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ba996e4add1cfe44681154b00a6530b1f3e70b37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714001"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a>Tutorial: Ihre erste .NET Core-Konsolenanwendung in Visual Studio 2019

Dieser Artikel bietet eine schrittweise Einführung in das Erstellen und Ausführen einer .NET Core-Konsolenanwendung „Hello World“ in Visual Studio 2019. Eine Hello World-Anwendung wird normalerweise verwendet, um Einsteiger in eine neue Programmiersprache einzuführen. Dieses Programm zeigt einfach den Text „Hello World“ an. auf dem Bildschirm ausgegeben.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019 Version 16.4 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**. Das .NET Core 3.1 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.

Weitere Informationen finden Sie im Abschnitt [Installieren mit Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) des Artikels [Installieren des .NET Core SDK](../install/sdk.md?pivots=os-windows).

## <a name="create-the-app"></a>Erstellen der App

In den folgenden Anleitungen wird eine einfache Hello World-Konsolenanwendung erstellt:

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

1. Öffnen Sie Visual Studio 2019.

1. Erstellen Sie ein neues C# .NET Core-Konsolenanwendungsprojekt mit dem Namen „HelloWorld“.

   1. Wählen Sie im Startfenster **Neues Projekt erstellen** aus.

      ![Schaltfläche „Neues Projekt erstellen“, die im Visual Studio-Startfenster ausgewählt ist](./media/with-visual-studio/start-window.png)

   1. Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Konsole** in das Suchfeld ein. Wählen Sie anschließend in der Liste der Sprachen **C#** und dann in der Liste der Plattformen **Alle Plattformen** aus. Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.

      ![Erstellen eines neuen Projektfenster mit ausgewählten Filtern](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > Wenn die .NET Core-Vorlagen nicht angezeigt werden, ist möglicherweise die erforderliche Workload nicht installiert. Wählen Sie unter der Meldung **Sie finden nicht, wonach Sie suchen?** den Link **Weitere Tools und Features installieren** aus. Der Visual Studio-Installer wird geöffnet. Stellen Sie sicher, dass Sie die Workload **Plattformübergreifende .NET Core-Entwicklung** installiert haben.

   1. Geben Sie **HelloWorld** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein. Wählen Sie anschließend **Erstellen** aus.

      ![Konfigurieren Sie das Fenster für das neue Projekt mit den Feldern „Projektname“, „Speicherort“ und „Projektmappenname“.](./media/with-visual-studio/configure-new-project.png)

   Die C#-Konsolenanwendungsvorlage für .NET Core definiert automatisch die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String> Array als Argument akzeptiert. `Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet. Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.

   ![Visual Studio und das neue HelloWorld-Projekt](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Öffnen Sie Visual Studio 2019.

1. Erstellen Sie ein neues Visual Basic .NET Core-Konsolenanwendungsprojekt mit dem Namen „HelloWorld“.

   1. Wählen Sie im Startfenster **Neues Projekt erstellen** aus.

      ![Schaltfläche „Neues Projekt erstellen“, die im Visual Studio-Startfenster ausgewählt ist](./media/with-visual-studio/start-window.png)

   1. Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Konsole** in das Suchfeld ein. Wählen Sie **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus. Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.

      ![Auswählen der Visual Basic-Vorlage für die Konsolen-App (.NET Framework)](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > Wenn die .NET Core-Vorlagen nicht angezeigt werden, ist möglicherweise die erforderliche Workload nicht installiert. Wählen Sie unter der Meldung **Sie finden nicht, wonach Sie suchen?** den Link **Weitere Tools und Features installieren** aus. Der Visual Studio-Installer wird geöffnet. Stellen Sie sicher, dass Sie die Workload **Plattformübergreifende .NET Core-Entwicklung** installiert haben.

   1. Geben Sie **HelloWorld** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein. Wählen Sie anschließend **Erstellen** aus.

   Die Konsolenanwendungsvorlage für .NET Core definiert automatisch die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument annimmt. `Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet. Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im `args`-Parameter verfügbar.

   ![Visual Studio und das neue HelloWorld-Projekt](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   Die Vorlage erstellt eine einfache „Hello World“-Anwendung. Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um die literale Zeichenfolge „Hello World!“ im Konsolenfenster anzuzeigen.

## <a name="run-the-app"></a>Ausführen der App

1. Um das Programm auszuführen, wählen Sie **HelloWorld** auf der Symbolleiste aus, oder drücken Sie **F5**.

   ![Visual Studio-Symbolleiste mit ausgewählter Schaltfläche zum Ausführen von HelloWorld](./media/with-visual-studio/run-program.png)

   Ein Konsolenfenster wird geöffnet, das den Text „Hello World!“ auf dem Bildschirm sowie einige Visual Studio-Debuginformationen ausgibt.

   ![Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt](./media/with-visual-studio/hello-world-console.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

## <a name="enhance-the-app"></a>Optimieren der App

Erweitern Sie ihre Anwendung, um die Benutzer aufzufordern, Ihren Namen einzugeben und diesen mit dem Datum und der Uhrzeit anzuzeigen. Die folgenden Anleitungen ändern und führen die App erneut aus:

# <a name="c"></a>[C#](#tab/csharp)

1. Ersetzen Sie den Inhalt der `Main`-Methode, die derzeit nur aus der Zeile besteht, die `Console.WriteLine`aufruft, durch den folgenden Code:

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   Dieser Code zeigt „What is your name?“ im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat. Der Code speichert diese Zeichenfolge in einer Variablen namens `name`. Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu. Schließlich verwendet der Code eine [interpolierte Zeichenfolge](../../csharp/language-reference/tokens/interpolated.md), um diese Werte im Konsolenfenster anzuzeigen.

1. Kompilieren Sie das Programm durch Auswählen von **Erstellen** > **Projektmappe erstellen**.

1. Um das Programm auszuführen, wählen Sie **HelloWorld** auf der Symbolleiste aus, oder drücken Sie **F5**.

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die **EINGABETASTE** drücken.

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/hello-world-update.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Ersetzen Sie den Inhalt der `Main`-Methode, die derzeit nur aus der Zeile besteht, die `Console.WriteLine`aufruft, durch den folgenden Code:

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   Dieser Code zeigt „What is your name?“ im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die EINGABETASTE gedrückt hat. Der Code speichert diese Zeichenfolge in einer Variablen namens `name`. Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu. Schließlich verwendet der Code eine [interpolierte Zeichenfolge](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), um diese Werte im Konsolenfenster anzuzeigen.

1. Kompilieren Sie das Programm durch Auswählen von **Erstellen** > **Projektmappe erstellen**.

1. Um das Programm auszuführen, wählen Sie **HelloWorld** auf der Symbolleiste aus, oder drücken Sie **F5**.

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die **EINGABETASTE** drücken.

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/hello-world-update.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

---

## <a name="next-steps"></a>Nächste Schritte

In diesem Artikel haben Sie Ihre erste .NET Core-Anwendung erstellt und ausgeführt. Im nächsten Schritt debuggen Sie Ihre App.

> [!div class="nextstepaction"]
> [Debuggen einer Hello World-Anwendung (.NET Core) in Visual Studio](debugging-with-visual-studio.md)
