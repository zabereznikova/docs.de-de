---
title: 'Hallo Welt: Ihr erstes Programm (C#-Programmierhandbuch)'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 9a50de0bb583a1dfccfa609be1cca732868505ba
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589377"
---
# <a name="hello-world----your-first-program-c-programming-guide"></a>Hallo Welt: Ihr erstes Programm (C#-Programmierhandbuch)

Die folgende Prozedur erstellt eine C#-Version des herkömmlichen „Hallo Welt!“ -Programms. Das Programm zeigt die Zeichenfolge `Hello World!` an.

Weitere Beispiele zu einführenden Konzepten finden Sie unter [Erste Schritte mit Visual C# und Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-and-run-a-console-application"></a>So erstellen Sie eine neue Konsolenanwendung und führen diese aus

1. Starten Sie Visual Studio.

2. Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.

     Das Dialogfeld **Neues Projekt** wird angezeigt.

3. Erweitern Sie nacheinander **Installiert**, **Vorlagen**, **Visual C#** , und wählen Sie dann **Konsolenanwendung** aus.

4. Geben Sie im Feld **Name** einen Namen für das Projekt an, und klicken Sie dann auf die Schaltfläche **OK**.

     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.

5. Wenn „Program.cs“ im **Code-Editor** nicht geöffnet ist, öffnen Sie das Kontextmenü für **Program.cs** im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen** aus.

6. Ersetzen Sie den Inhalt von Program.cs durch den folgenden Code.

     [!code-csharp[csProgGuide#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#21)]

7. Drücken Sie die Taste F5, um das Projekt auszuführen. Ein Eingabeaufforderungsfenster wird angezeigt, das die Zeile `Hello World!` enthält

Im nächsten Schritt werden die wichtigen Bereiche des Programms überprüft.

## <a name="comments"></a>Kommentare

Die erste Zeile enthält einen Kommentar. Durch die Zeichen `//` wird die restliche Zeile in einen Kommentar konvertiert.

 [!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

Sie können auch einen Kommentar aus einem Textblock einfügen, indem Sie ihn zwischen den Zeichen `/*` und `*/` einschließen. Dies wird im folgenden Beispiel gezeigt.

 [!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

## <a name="main-method"></a>Main-Methode

Eine C#-Konsolenanwendung muss eine `Main`-Methode enthalten, in der die Steuerung beginnt und endet. Innerhalb der `Main`-Methode erstellen Sie Objekte und führen andere Methoden aus.

Bei der `Main`-Methode handelt es sich um eine [statische](../../language-reference/keywords/static.md) Methode, die sich innerhalb einer Klasse oder Struktur befindet. Im vorherigen „Hello World!“-Beispiel befindet sie sich in einer Klasse namens `Hello`. Sie können die `Main`-Methode auf eine der folgenden Arten deklarieren:

- Es kann `void` zurückgegeben werden.

     [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- Zudem kann eine ganze Zahl zurückgegeben werden.

     [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- Bei beiden Rückgabetypen können Argumente verwendet werden.

     [!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

     Oder

     [!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

Der Parameter der `Main`-Methode, `args`, ist ein `string`-Array, das die Befehlszeilenargumente enthält, die zum Aufrufen des Programms verwendet werden. Im Gegensatz zu C++ enthält dieses Array nicht den Namen der ausführbaren Datei (EXE).

Weitere Informationen zur Verwendung von Befehlszeilenargumenten finden Sie unter [Main() und Befehlszeilenargumente](../main-and-command-args/index.md) und [Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).

Der Aufruf von <xref:System.Console.ReadKey%2A> am Ende der `Main`-Methode verhindert, dass das Konsolenfenster geschlossen wird, bevor Sie die Ausgabe lesen können, wenn Sie das Programm durch Drücken von F5 im Debugmodus ausführen.

## <a name="input-and-output"></a>Eingabe und Ausgabe

C#-Programme verwenden im Allgemeinen die Eingabe-/Ausgabedienste der Laufzeitbibliothek von .NET Framework. Die Anweisung `System.Console.WriteLine("Hello World!");` verwendet die <xref:System.Console.WriteLine%2A>-Methode. Dies ist eine der Ausgabemethoden der <xref:System.Console>-Klasse in der Laufzeit-Bibliothek. Bei dieser Methode wird der Zeichenfolgenparameter für den Standardausgabestream gefolgt von einer neuen Zeile angezeigt. Für andere Eingabe-/Ausgabevorgänge sind andere <xref:System.Console>-Methoden verfügbar. Wenn Sie die `using System;`-Direktive am Anfang des Programms einfügen, können Sie die <xref:System>-Klassen und -Methoden direkt verwenden, ohne sie voll zu qualifizieren. Zum Beispiel können Sie `Console.WriteLine` statt `System.Console.WriteLine` aufrufen:

 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

 [!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

Weitere Informationen zu Eingabe-/Ausgabemethoden finden Sie unter <xref:System.IO>.

## <a name="command-line-compilation-and-execution"></a>Befehlszeilenkompilierung und -ausführung

Sie können das „Hallo Welt“ -Programm über die Befehlszeile statt mit der integrierten Entwicklungsumgebung (IDE) von Visual Studio kompilieren.

### <a name="to-compile-and-run-from-a-command-prompt"></a>So funktionieren Kompilierungsvorgänge und Ausführungen von einer Eingabeaufforderung aus

1. Fügen Sie den Code aus der vorherigen Prozedur in einem beliebigen Text-Editor ein, und speichern Sie die Datei als Textdatei. Nennen Sie die Datei `Hello.cs`. C#-Quellcodedateien weisen die Erweiterung `.cs` auf.

2. Führen Sie einen der folgenden Schritte aus, um ein Eingabeaufforderungsfenster zu öffnen:

    - Suchen Sie in Windows 10 auf dem **Startbildmenü** nach `Developer Command Prompt`, und wählen Sie dann **Developer-Eingabeaufforderung für VS2017** aus.

         Ein Entwickler-Eingabeaufforderungsfenster wird angezeigt.

    - Öffnen Sie in Windows 7 das **Startmenü**, erweitern Sie den Ordner der aktuellen Version von Visual Studio, öffnen Sie das Kontextmenü für **Visual Studio-Tools**, und wählen Sie dann **Developer-Eingabeaufforderung für VS2017** aus.

         Ein Entwickler-Eingabeaufforderungsfenster wird angezeigt.

    - Aktivieren Sie Befehlszeilenbuilds von einem Standardeingabeaufforderungsfenster.

         Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](../../language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).

3. Navigieren Sie im Eingabeaufforderungsfenster zu dem Ordner, der die Datei `Hello.cs` enthält.

4. Geben Sie zum Kompilieren von `Hello.cs` den folgenden Befehl ein.

     `csc Hello.cs`

     Wenn das Programm keine Kompilierungsfehler aufweist, wird eine ausführbare Datei mit dem Namen `Hello.exe` erstellt.

5. Geben Sie den folgenden Befehl im Eingabeaufforderungsfenster ein, um das Programm auszuführen:

     `Hello`

 Weitere Informationen über den C#-Compiler und seine Optionen finden Sie unter [C#-Compileroptionen](../../language-reference/compiler-options/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Einblicke in ein C#-Programm](./index.md)
- [Zeichenfolgen](../strings/index.md)
- [Beispiele und Tutorials](../../../samples-and-tutorials/index.md)
- [C#-Referenz](../../language-reference/index.md)
- [Main() und Befehlszeilenargumente](../main-and-command-args/index.md)
- [Erste Schritte mit Visual C# und Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
