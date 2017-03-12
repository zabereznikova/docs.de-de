---
title: "Hello World – Ihr erstes Programm (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "get-started-article"
f1_keywords: 
  - "cs.program"
  - "vs.csharp.startpage.firstapplication"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Beispiele [C#], Hello World"
  - "Hello World (Beispiel) [C#]"
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
caps.latest.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 39
---
# Hello World – Ihr erstes Programm (C#-Programmierhandbuch)
Mit der folgenden Prozedur wird eine C\#\-Version des herkömmlichen "Hello World\!"\-Programms erstellt.  Das Programm zeigt die Zeichenfolge `Hello World!` an.  
  
 Weitere Beispiele von einführenden Konzepten, finden Sie unter [Erste Schritte mit Visual C\# und Visual Basic](/visual-studio/ide/getting-started-with-visual-csharp-and-visual-basic).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### So erstellen Sie eine neue Konsolenanwendung und führen diese aus  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt** aus.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Erweitern Sie nacheinander **Installiert**, **Vorlagen**, **Visual C\#**, und wählen Sie dann **Konsolenanwendung** aus.  
  
4.  Geben Sie im Feld **Name** einen Namen für das Projekt an, und klicken Sie dann auf die Schaltfläche **OK**.  
  
     Das neue Projekt wird im **Projektmappen\-Explorer** angezeigt.  
  
5.  Wenn Program.cs im **Code\-Editor** nicht geöffnet ist, öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für **Program.cs**, und wählen Sie dann **Code anzeigen** aus.  
  
6.  Ersetzen Sie den Inhalt von Program.cs durch den folgenden Code.  
  
     [!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#21)]  
  
7.  Drücken Sie die Taste F5, um das Projekt auszuführen.  Ein Eingabeaufforderungsfenster wird angezeigt, das die Zeile `Hello World!` enthält  
  
 Im nächsten Schritt werden die wichtigen Bereiche des Programms überprüft.  
  
## Kommentare  
 Die erste Zeile enthält einen Kommentar.  Durch die Zeichen `//` wird die restliche Zeile in einen Kommentar konvertiert.  
  
 [!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#32)]  
  
 Sie können auch einen Kommentar aus einem Textblock einfügen, indem Sie ihn zwischen den Zeichen `/*` und `*/` einschließen.  Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#33)]  
  
## Die 'Main'\-Methode  
 Eine C\#\-Konsolenanwendung muss eine `Main`\-Methode enthalten, in der die Steuerung beginnt und endet.  Innerhalb der `Main`\-Methode erstellen Sie Objekte und führen andere Methoden aus.  
  
 Bei der `Main`\-Methode handelt es sich um eine [Statische](../../../csharp/language-reference/keywords/static.md)\-Methode, die sich innerhalb einer Klasse oder Struktur befindet.  Im vorherigen Beispiel "Hello World\!" befindet sie sich in der `Hello`\-Klasse.  Sie können die `Main`\-Methode auf eine der folgenden Arten deklarieren:  
  
-   Es kann `void` zurückgegeben werden.  
  
     [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/hello-world-your-first-p_4.cs)]  
  
-   Zudem kann eine ganze Zahl zurückgegeben werden.  
  
     [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/hello-world-your-first-p_5.cs)]  
  
-   Bei beiden Rückgabetypen können Argumente verwendet werden.  
  
     [!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/hello-world-your-first-p_6.cs)]  
  
     \-oder\-  
  
     [!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/hello-world-your-first-p_7.cs)]  
  
 Der Parameter der `Main`\-Methode, `args`, ist ein `string`\-Array, das die Befehlszeilenargumente enthält, die zum Aufrufen des Programms verwendet werden.  Im Gegensatz zu C\+\+ enthält dieses Array nicht den Namen der ausführbaren Datei \(EXE\).  
  
 Weitere Informationen zur Verwendung von Befehlszeilenargumenten finden Sie in den Beispielen unter [Main\(\) und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) und [Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Der Aufruf von <xref:System.Console.ReadKey%2A> am Ende der `Main`\-Methode verhindert, dass das Konsolenfenster geschlossen wird, bevor Sie die Ausgabe lesen können, wenn Sie das Programm durch Drücken von F5 im Debugmodus ausführen.  
  
## Eingabe und Ausgabe  
 C\#\-Programme verwenden im Allgemeinen die Eingabe\-\/Ausgabedienste der Laufzeitbibliothek von .NET Framework.  Die Anweisung `System.Console.WriteLine("Hello World!");` verwendet die <xref:System.Console.WriteLine%2A>\-Methode.  Dies ist eine der Ausgabemethoden der <xref:System.Console>\-Klasse in der Laufzeit\-Bibliothek.  Bei dieser Methode wird der Zeichenfolgenparameter für den Standardausgabestream gefolgt von einer neuen Zeile angezeigt.  Für andere Eingabe\-\/Ausgabevorgänge sind andere <xref:System.Console>\-Methoden verfügbar.  Wenn Sie die `using System;`\-Direktive am Anfang des Programms einfügen, können Sie die <xref:System>\-Klassen und \-Methoden direkt verwenden, ohne sie voll zu qualifizieren.  Zum Beispiel können Sie `Console.WriteLine` statt `System.Console.WriteLine` aufrufen:  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/using.cs#1)]  
  
 [!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#23)]  
  
 Weitere Informationen zu Eingabe\-\/Ausgabemethoden finden Sie unter <xref:System.IO>.  
  
## Befehlszeilenkompilierung und \-ausführung  
 Sie können das Programm "Hello, World\!" über die Befehlszeile statt mit der integrierten Entwicklungsumgebung \(IDE\) von Visual Studio kompilieren.  
  
#### So funktionieren Kompilierungsvorgänge und Ausführungen von einer Eingabeaufforderung aus  
  
1.  Fügen Sie den Code aus der vorherigen Prozedur in einem beliebigen Text\-Editor ein, und speichern Sie die Datei als Textdatei.  Nennen Sie die Datei `Hello.cs`.  C\#\-Quellcodedateien weisen die Erweiterung `.cs` auf.  
  
2.  Führen Sie einen der folgenden Schritte aus, um ein Eingabeaufforderungsfenster zu öffnen:  
  
    -   Suchen Sie in Windows 8 auf dem Bildschirm **Start** nach `Entwickler-Eingabeaufforderung`, und wählen Sie dann **Developer\-Eingabeaufforderung für VS2012** aus.  
  
         Ein Entwickler\-Eingabeaufforderungsfenster wird angezeigt.  
  
    -   Öffnen Sie in Windows 7 das Menü **Start**, erweitern Sie den Ordner für die aktuelle Version von Visual Studio, öffnen Sie das Kontextmenü für **Visual Studio\-Tools**, und wählen Sie dann **Developer\-Eingabeaufforderung für VS2012** aus.  
  
         Ein Entwickler\-Eingabeaufforderungsfenster wird angezeigt.  
  
    -   Aktivieren Sie Befehlszeilenbuilds von einem Standardeingabeaufforderungsfenster.  
  
         Siehe [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
3.  Navigieren Sie im Eingabeaufforderungsfenster zu dem Ordner, der die Datei `Hello.cs` enthält.  
  
4.  Geben Sie zum Kompilieren von `Hello.cs` den folgenden Befehl ein.  
  
     `csc Hello.cs`  
  
     Wenn das Programm keine Kompilierungsfehler aufweist, wird eine ausführbare Datei mit dem Namen `Hello.exe` erstellt.  
  
5.  Geben Sie den folgenden Befehl im Eingabeaufforderungsfenster ein, um das Programm auszuführen:  
  
     `Hello`  
  
 Weitere Informationen über den C\#\-Compiler und seine Optionen finden Sie unter [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).  
  
## Enthaltenes Buchkapitel  
 [Schreiben eines C\#\-Programms](http://go.microsoft.com/fwlink/?LinkId=221227) im Buch zum [Einstieg in Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einblicke in ein C\#\-Programm](../../../csharp/programming-guide/inside-a-program/index.md)   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)   
 [\<paveover\>C\# Sample Applications](http://msdn.microsoft.com/de-de/9a9d7aaa-51d3-4224-b564-95409b0f3e15)   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [Main\(\) und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Erste Schritte mit Visual C\# und Visual Basic](/visual-studio/ide/getting-started-with-visual-csharp-and-visual-basic)