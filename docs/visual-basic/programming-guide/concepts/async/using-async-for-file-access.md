---
title: "Verwenden von Async für Dateizugriff (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e0e548989b1d2c32b9faf5ce0dd90ae371dfc028
ms.lasthandoff: 03/13/2017

---
# <a name="using-async-for-file-access-visual-basic"></a>Using Async for File Access (Visual Basic) (Verwenden von Async für Dateizugriff (Visual Basic))
Sie können die Async-Funktion verwenden, auf Dateien zugreifen. Mithilfe der Async-Funktion können Sie asynchrone Methoden aufrufen, ohne Rückrufe zu verwenden oder den Code über mehrere Methoden oder Lambdaausdrücke teilen zu müssen. Um synchronen Code asynchron auszuführen, Sie nur eine asynchrone Methode anstelle einer synchronen Methode aufrufen und dem Code einige Schlüsselwörter hinzuzufügen.  
  
 Sie sollten die folgenden Gründe für die Datei Aufrufe Asynchronie hinzugefügt:  
  
-   Asynchronie können UI-Anwendungen besser, da der UI-Thread, der den Vorgang startet, andere Aufgaben durchführen kann. Wenn Code im UI-Thread ausgeführt werden muss, die viel Zeit (z. B. mehr als 50 Millisekunden), die Benutzeroberfläche reagiert möglicherweise nicht mehr, bis die e/a abgeschlossen ist, und im UI-Thread erneut verarbeiten Tastatur und Maus Eingabe- und andere Ereignisse.  
  
-   Asynchronie verbessert die Skalierbarkeit von ASP.NET und andere serverbasierte Anwendung, indem reduziert die Notwendigkeit für Threads. Wenn die Anwendung einen dedizierten Thread pro Antwort verwendet Tausend Anforderungen gleichzeitig verarbeitet werden werden, sind mehr als tausend Threads erforderlich. Asynchrone Vorgänge müssen häufig einen Thread während der Wartezeit zu verwenden. Verwendung der vorhandene e/a-Abschlussthread kurz am Ende.  
  
-   Die Latenz von Dateien Zugriff kann nur noch sehr wenig aktuelle ausgelastet sein, aber die Wartezeit kann in Zukunft beträchtlich. Beispielsweise kann eine Datei auf einen Server verschoben werden, die auf der ganzen Welt.  
  
-   Der zusätzliche Verwaltungsaufwand durch Verwendung der Async-Funktion klein ist.  
  
-   Asynchrone Aufgaben können problemlos parallel ausgeführt werden.  
  
## <a name="running-the-examples"></a>Ausführen der Beispiele  
 Zum Ausführen der Beispiele in diesem Thema erstellen Sie eine **WPF-Anwendung** oder **Windows Forms-Anwendung** und fügen Sie dann eine **Schaltfläche**. Die Schaltfläche `Click` Ereignis, fügen Sie einen Aufruf an die erste Methode in jedem Beispiel.  
  
 In den folgenden Beispielen gehören `Imports` Anweisungen.  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a>Verwenden der FileStream-Klasse  
 In den Beispielen in diesem Thema die <xref:System.IO.FileStream>-Klasse, die Option verfügt, die bewirkt, dass asynchrone e/a auf der Betriebssystemebene auftreten.</xref:System.IO.FileStream> Mit dieser Option können Sie die Blockierung von einem Threadpool in vielen Fällen vermeiden. Wenn Sie diese Option aktivieren, geben Sie die `useAsync=true` oder `options=FileOptions.Asynchronous` Argument im Konstruktoraufruf.  
  
 Diese Option können Sie keine und <xref:System.IO.StreamReader> <xref:System.IO.StreamWriter>Öffnen sie direkt, indem Sie einen Dateipfad angeben</xref:System.IO.StreamWriter> </xref:System.IO.StreamReader> Allerdings können Sie diese Option verwenden, wenn Sie ihnen geben eine <xref:System.IO.Stream>, die <xref:System.IO.FileStream>Klasse geöffnet.</xref:System.IO.FileStream> </xref:System.IO.Stream> Beachten Sie, dass asynchrone Aufrufe in Anwendungsbenutzeroberflächen schneller sind, selbst wenn ein ThreadPool-Thread blockiert wird, da während der Wartezeit nicht im UI-Thread blockiert ist.  
  
## <a name="writing-text"></a>Schreiben von Text  
 Das folgende Beispiel schreibt Text in eine Datei. An jedem await-Anweisung, die Methode sofort beendet. Wenn die Datei-e/a abgeschlossen ist, wird die Methode bei der Anweisung, die die Await-Anweisung folgt fortgesetzt. Beachten Sie, dass die Async-Modifizierer in der Definition der Methoden, die die Await-Anweisung verwenden.  
  
```vb  
Public Async Sub ProcessWrite()  
    Dim filePath = "temp2.txt"  
    Dim text = "Hello World" & ControlChars.CrLf  
  
    Await WriteTextAsync(filePath, text)  
End Sub  
  
Private Async Function WriteTextAsync(filePath As String, text As String) As Task  
    Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize:=4096, useAsync:=True)  
  
        Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
    End Using  
End Function  
```  
  
 Das ursprüngliche Beispiel wurde die Anweisung `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, also ein Zusammenschluss der beiden folgenden Anweisungen:  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 Die erste Anweisung eine Aufgabe zurück und bewirkt die dateiverarbeitung zu starten. Die zweite Anweisung mit der "await" bewirkt, dass die Methode sofort beendet und eine andere Aufgabe zurück. Wenn die Datei später Verarbeitung abgeschlossen ist, gibt die Ausführung an die Anweisung nach dem await-Ausdruck. Weitere Informationen finden Sie unter [Ablaufsteuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
## <a name="reading-text"></a>Lesen von Text  
 Im folgenden Beispiel wird Text aus einer Datei gelesen. Der Text wird gepuffert und in diesem Fall eine <xref:System.Text.StringBuilder>.</xref:System.Text.StringBuilder> abgelegt Im Gegensatz zu im vorherigen Beispiel erzeugt die Auswertung der await-Ausdruck einen Wert. Die <xref:System.IO.Stream.ReadAsync%2A>-Methode gibt ein <xref:System.Threading.Tasks.Task> \< <xref:System.Int32>>, sodass die Auswertung der await-Anweisung erzeugt einen `Int32` Wert (`numRead`) nach Abschluss des Vorgangs.</xref:System.Int32> </xref:System.Threading.Tasks.Task> </xref:System.IO.Stream.ReadAsync%2A> Weitere Informationen finden Sie unter [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
```vb  
Public Async Sub ProcessRead()  
    Dim filePath = "temp2.txt"  
  
    If File.Exists(filePath) = False Then  
        Debug.WriteLine("file not found: " & filePath)  
    Else  
        Try  
            Dim text As String = Await ReadTextAsync(filePath)  
            Debug.WriteLine(text)  
        Catch ex As Exception  
            Debug.WriteLine(ex.Message)  
        End Try  
    End If  
End Sub  
  
Private Async Function ReadTextAsync(filePath As String) As Task(Of String)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize:=4096, useAsync:=True)  
  
        Dim sb As New StringBuilder  
  
        Dim buffer As Byte() = New Byte(&H1000) {}  
        Dim numRead As Integer  
        numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        While numRead <> 0  
            Dim text As String = Encoding.Unicode.GetString(buffer, 0, numRead)  
            sb.Append(text)  
  
            numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        End While  
  
        Return sb.ToString  
    End Using  
End Function  
```  
  
## <a name="parallel-asynchronous-io"></a>Parallele asynchrone e/a  
 Das folgende Beispiel zeigt die parallelen Verarbeitung von 10 Textdateien schreiben. Für jede Datei die <xref:System.IO.Stream.WriteAsync%2A>-Methode gibt einen Task, der eine Liste von Aufgaben hinzugefügt wird.</xref:System.IO.Stream.WriteAsync%2A> Die `Await Task.WhenAll(tasks)` Anweisung wird die Methode beendet und nimmt innerhalb der Methode, wenn die dateiverarbeitung ist für alle Aufgaben abgeschlossen.  
  
 Das Beispiel schließt alle <xref:System.IO.FileStream>Instanzen in einer `Finally` blockieren, wenn die Aufgaben abgeschlossen sind.</xref:System.IO.FileStream> Wenn alle `FileStream` wurde stattdessen erstellt eine `Imports` -Anweisung, die `FileStream` möglicherweise der verworfen werden, bevor der Task abgeschlossen wurde.  
  
 Beachten Sie, dass Leistungssteigerung fast vollständig von der parallelen Verarbeitung und nicht die asynchrone Verarbeitung. Die Vorteile der Asynchronie sind, dass es mehreren Threads blockieren nicht, und es Thread der Benutzeroberfläche gebunden wird.  
  
```vb  
Public Async Sub ProcessWriteMult()  
    Dim folder = "tempfolder\"  
    Dim tasks As New List(Of Task)  
    Dim sourceStreams As New List(Of FileStream)  
  
    Try  
        For index = 1 To 10  
            Dim text = "In file " & index.ToString & ControlChars.CrLf  
  
            Dim fileName = "thefile" & index.ToString("00") & ".txt"  
            Dim filePath = folder & fileName  
  
            Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
            Dim sourceStream As New FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize:=4096, useAsync:=True)  
  
            Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
            sourceStreams.Add(sourceStream)  
  
            tasks.Add(theTask)  
        Next  
  
        Await Task.WhenAll(tasks)  
    Finally  
        For Each sourceStream As FileStream In sourceStreams  
            sourceStream.Close()  
        Next  
    End Try  
End Sub  
```  
  
 Bei Verwendung der <xref:System.IO.Stream.WriteAsync%2A>und <xref:System.IO.Stream.ReadAsync%2A>Methoden können Sie angeben, einen <xref:System.Threading.CancellationToken>, mit Mid-Streams Vorgang abbrechen.</xref:System.Threading.CancellationToken> </xref:System.IO.Stream.ReadAsync%2A> </xref:System.IO.Stream.WriteAsync%2A> Weitere Informationen finden Sie unter [Optimieren der asynchronen Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) und [Abbruch in verwalteten Threads](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Asynchrone Rückgabetypen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [Ablaufsteuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)
