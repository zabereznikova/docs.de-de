---
title: 'C#-Programmierhandbuch: Hallo Welt – Ihr erstes Programm mit Visual Studio unter Windows oder Mac'
ms.custom: seodec18
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: edab64bf02a2b60cce21af536d2da98193dea9a1
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73196215"
---
# <a name="hello-world----your-first-program"></a>Ihr erstes Programm: Hallo Welt

In diesem Artikel verwenden Sie Visual Studio zum Erstellen eines traditionellen Hallo Welt -Programms. Visual Studio ist eine professionelle IDE (integrierte Entwicklungsumgebung) mit vielen Features, die für die .NET-Entwicklung konzipiert wurden. Zum Erstellen dieses Programms verwenden Sie nur wenige dieser Features. Weitere Informationen zu Visual Studio finden Sie unter [Erste Schritte mit Visual C#](/visualstudio/ide/quickstart-csharp-console).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a>Erstellen einer neuen Anwendung

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

Starten Sie Visual Studio. Unter Windows wird Folgendes angezeigt:

![Visual Studio-Willkommensbildschirm unter Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

Klicken Sie in der unteren rechten Ecke auf **Neues Projekt erstellen**. Daraufhin zeigt Visual Studio das Dialogfeld **Neues Projekt** an:

![Anzeige „Neues Projekt“ in Visual Studio unter Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> Wenn Sie Visual Studio zum ersten Mal starten, ist die Liste **Zuletzt verwendete Projektvorlagen** leer.

Wählen Sie „Konsolen-App (.NET Core)“ im Dialogfeld „Neues Projekt“ aus, und klicken Sie dann auf **Weiter**. Geben Sie Ihrem Projekt einen Namen, z. B. „HalloWelt“, und klicken Sie dann auf **Erstellen**.

Visual Studio öffnet Ihr Projekt. Dieses ist bereits ein grundlegendes „Hallo Welt“- Beispiel. Drücken Sie `Ctrl` + `F5`, um das Projekt auszuführen. Visual Studio erstellt Ihr Projekt und konvertiert den Quellcode in eine ausführbare Datei. Dann wird ein Befehlsfenster gestartet, das Ihre neue Anwendung ausführt. Der folgende Text sollte im Fenster angezeigt werden:

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

Drücken Sie eine beliebige Taste, um das Fenster zu schließen.

# <a name="macostabmacos"></a>[macOS](#tab/macos)

Starten Sie Visual Studio für Mac. Unter Mac wird Folgendes angezeigt:

![Visual Studio-Willkommensbildschirm unter Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> Wenn Sie Visual Studio für Mac zum ersten Mal starten, ist die Liste **Zuletzt geöffnete Projekte** leer.

Klicken Sie oben rechts auf **Neu**. Daraufhin zeigt Visual Studio für Mac das Dialogfeld **Neues Projekt** an:

![Anzeige „Neues Projekt“ in Visual Studio für Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

Wählen Sie im Dialogfeld „Neues Projekt“ die Option „.NET Core“ und dann „Konsolen-App“ aus, und klicken Sie dann auf **Weiter**. Daraufhin müssen Sie ein Zielframework auswählen. Hier können Sie die Standardeinstellung beibehalten, klicken Sie also auf „Weiter“. Geben Sie Ihrem Projekt einen Namen, z. B. „HalloWelt“, und klicken Sie dann auf **Erstellen**. Sie können den Standardprojektspeicherort verwenden. Fügen Sie dieses Projekt nicht zur Quellcodeverwaltung hinzu.

Visual Studio für Mac öffnet Ihr Projekt. Dieses ist bereits ein grundlegendes „Hallo Welt“- Beispiel. Drücken Sie `Ctrl` + `Fn` + `F5`, um das Projekt auszuführen. Visual Studio für Mac erstellt Ihr Projekt und konvertiert den Quellcode in eine ausführbare Datei. Dann wird ein Befehlsfenster gestartet, das Ihre neue Anwendung ausführt. Der folgende Text sollte im Fenster angezeigt werden:

```console
Hello World!

Press any key to close this window . . .
```

Drücken Sie eine beliebige Taste, um die Sitzung zu beenden.

---

## <a name="elements-of-a-c-program"></a>Elemente eines C#-Programms

Im Folgenden werden die wichtigen Bestandteile dieses Programms untersucht. Die erste Zeile enthält einen Kommentar. Durch die Zeichen `//` wird die restliche Zeile in einen Kommentar konvertiert.

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

Sie können auch einen Kommentar aus einem Textblock einfügen, indem Sie ihn zwischen den Zeichen `/*` und `*/` einschließen. Dies wird im folgenden Beispiel gezeigt.

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

Eine C#-Konsolenanwendung muss eine `Main`-Methode enthalten, in der die Steuerung beginnt und endet. Innerhalb der `Main`-Methode erstellen Sie Objekte und führen andere Methoden aus.

Bei der `Main`-Methode handelt es sich um eine [statische](../../language-reference/keywords/static.md) Methode, die sich innerhalb einer Klasse oder Struktur befindet. Im vorherigen „Hello World!“-Beispiel befindet sie sich in einer Klasse namens `Hello`. Sie können die `Main`-Methode auf eine der folgenden Arten deklarieren:

- Es kann `void` zurückgegeben werden. Das heißt, Ihr Programm gibt keinen Wert zurück.

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- Zudem kann eine ganze Zahl zurückgegeben werden. Der Integer stellt den **Exitcode** Ihrer Anwendung dar.

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- Bei beiden Rückgabetypen können Argumente verwendet werden.

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

Oder

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

Der Parameter der `Main`-Methode, `args`, ist ein `string`-Array, das die Befehlszeilenargumente enthält, die zum Aufrufen des Programms verwendet werden.

Weitere Informationen zur Verwendung von Befehlszeilenargumenten finden Sie in den Beispielen unter [Main() und Befehlszeilenargumente](../main-and-command-args/index.md).

## <a name="input-and-output"></a>Eingabe und Ausgabe

C#-Programme verwenden im Allgemeinen die Eingabe-/Ausgabedienste der Laufzeitbibliothek von .NET Framework. Die Anweisung `System.Console.WriteLine("Hello World!");` verwendet die <xref:System.Console.WriteLine%2A>-Methode. Dies ist eine der Ausgabemethoden der <xref:System.Console>-Klasse in der Laufzeit-Bibliothek. Bei dieser Methode wird der Zeichenfolgenparameter für den Standardausgabestream gefolgt von einer neuen Zeile angezeigt. Für andere Eingabe-/Ausgabevorgänge sind andere <xref:System.Console>-Methoden verfügbar. Wenn Sie die `using System;`-Direktive am Anfang des Programms einfügen, können Sie die <xref:System>-Klassen und -Methoden direkt verwenden, ohne sie voll zu qualifizieren. Zum Beispiel können Sie `Console.WriteLine` statt `System.Console.WriteLine` aufrufen:

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

Weitere Informationen zu Eingabe-/Ausgabemethoden finden Sie unter <xref:System.IO>.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Beispiele und Tutorials](../../../samples-and-tutorials/index.md)
- [Main() und Befehlszeilenargumente](../main-and-command-args/index.md)
- [Erste Schritte mit Visual C#](/visualstudio/ide/quickstart-csharp-console)
