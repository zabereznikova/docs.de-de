---
title: Using Async for File Access (C#) (Verwenden von Async für Dateizugriff (C#))
description: Informationen zur Verwendung des Async-Features für den Zugriff auf Dateien in C# Sie können asynchrone Methoden aufrufen, ohne Rückrufe verwenden oder den Code methodenübergreifend aufteilen zu müssen.
ms.date: 07/20/2015
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: eb67bd408fe37b99e6c5ffdc2550e8f95110d7eb
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925123"
---
# <a name="using-async-for-file-access-c"></a>Using Async for File Access (C#) (Verwenden von Async für Dateizugriff (C#))
Sie können die Async-Funktion verwenden, um auf Dateien zuzugreifen. Mithilfe der Async-Funktion können Sie asynchrone Methoden aufrufen, ohne Rückrufe zu verwenden oder den Code über mehrere Methoden oder Lambdaausdrücke teilen zu müssen. Um synchronen Code asynchron auszuführen, rufen Sie einfach eine asynchrone Methode anstelle einer synchronen Methode auf und fügen Sie dem Code einige Schlüsselwörter hinzu.  
  
 Sie sollten die folgenden Gründe für das Hinzufügen von Asynchronie zu Dateizugriffsaufrufen in Betracht ziehen:  
  
- Durch Asynchronie kann die Reaktionsfähigkeit von UI-Anwendungen verbessert werden, da der UI-Thread, der den Vorgang startet, andere Aufgaben durchführen kann. Wenn der UI-Thread Code ausführt, der viel Zeit benötigt (z.B. mehr als 50 Millisekunden), kann die UI einfrieren, bis der E/A-Vorgang abgeschlossen ist und der UI-Thread wieder Tastatur- und Mauseingaben und andere Ereignisse verarbeiten kann.  
  
- Asynchronie verbessert die Skalierbarkeit von ASP.NET und anderen serverbasierten Anwendungen, indem die Notwendigkeit von Threads reduziert wird. Wenn die Anwendung einen dedizierten Thread pro Antwort verwendet und tausend Anforderungen gleichzeitig behandelt werden, werden auch tausend Threads benötigt. Asynchrone Vorgänge benötigen während der Wartezeit oft keinen Thread. Sie verwenden den vorhandenen E/A-Abschlussthread kurz am Ende.  
  
- Die Latenz von Dateizugriffsvorgängen kann unter bestimmten Umständen sehr niedrig sein, aber sie kann in Zukunft stark ansteigen. Eine Datei kann z.B. auf einen Server auf der anderen Seite der Erde verschoben werden.  
  
- Der zusätzliche Mehraufwand durch Verwendung der Async-Funktion ist gering.  
  
- Asynchrone Aufgaben können problemlos parallel ausgeführt werden.  
  
## <a name="running-the-examples"></a>Ausführen der Beispiele  
 Sie können eine **WPF-Anwendung** oder **Windows Forms-Anwendung** erstellen und dann eine **Schaltfläche** hinzufügen, um die Beispiele in diesem Thema auszuführen. Fügen Sie im `Click`-Ereignis der Schaltfläche einen Aufruf der ersten Methode jedes Beispiels hinzu.  
  
 Beziehen Sie in den folgenden Beispielen die `using`-Anweisungen ein.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Diagnostics;  
using System.IO;  
using System.Text;  
using System.Threading.Tasks;  
```  
  
## <a name="use-of-the-filestream-class"></a>Verwenden der FileStream-Klasse  
 In den Beispielen in diesem Thema wird die <xref:System.IO.FileStream>-Klasse verwendet, die über eine Option verfügt, die asynchrone E/A-Vorgänge auf Betriebssystemebene auslöst. Mit dieser Option können Sie das Blockieren eines ThreadPool-Threads in vielen Fällen vermeiden. Geben Sie zum Aktivieren dieser Option das Argument `useAsync=true` oder `options=FileOptions.Asynchronous` im Konstruktoraufruf an.  
  
 Sie können diese Option nicht mit <xref:System.IO.StreamReader> und <xref:System.IO.StreamWriter> verwenden, wenn Sie sie direkt öffnen, indem Sie einen Dateipfad angeben. Allerdings können Sie diese Option verwenden, wenn Sie ihnen ein <xref:System.IO.Stream> geben, das die <xref:System.IO.FileStream>-Klasse geöffnet hat. Beachten Sie, dass asynchrone Aufrufe in Anwendungsbenutzeroberflächen schneller sind, selbst wenn ein ThreadPool-Thread blockiert wird, da der UI-Thread während der Wartezeit nicht blockiert ist.  
  
## <a name="writing-text"></a>Schreiben von Text  
 Im folgenden Beispiel wird Text in eine Datei geschrieben. Bei jeder await-Anweisung wird die Methode sofort beendet. Wenn die Datei-E/A abgeschlossen ist, wird die Methode bei der Anweisung hinter der await-Anweisung fortgesetzt. Beachten Sie, dass sich der async-Modifizierer in der Definition der Methoden befindet, die die await-Anweisung verwenden.  
  
```csharp  
public async Task ProcessWriteAsync()  
{  
    string filePath = @"temp2.txt";  
    string text = "Hello World\r\n";  
  
    await WriteTextAsync(filePath, text);  
}  
  
private async Task WriteTextAsync(string filePath, string text)  
{  
    byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize: 4096, useAsync: true))  
    {  
        await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
    };  
}  
```  
  
 Das ursprüngliche Beispiel verfügt über die Anweisung `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, bei der es sich um eine Kontraktion der folgenden zwei Anweisungen handelt:  
  
```csharp  
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
await theTask;  
```  
  
 Die erste Anweisung gibt eine Aufgabe zurück und löst die Dateiverarbeitung aus. Die zweite await-Anweisung führt dazu, dass die Methode sofort beendet wird und eine andere Aufgabe zurückgibt. Wenn die Dateiverarbeitung später abgeschlossen wird, wird die Ausführung bei der Anweisung fortgesetzt, die auf die „await“-Anweisung folgt. Weitere Informationen finden Sie unter [Ablaufsteuerung in asynchronen Programmen (C#)](./control-flow-in-async-programs.md).  
  
## <a name="reading-text"></a>Lesen von Text  
 Im folgenden Beispiel wird Text aus einer Datei gelesen. Der Text wird gepuffert und in diesem Fall in <xref:System.Text.StringBuilder> abgelegt. Anders als im vorherigen Beispiel generiert die Auswertung von „await“ einen Wert. Die Methode <xref:System.IO.Stream.ReadAsync%2A> gibt ein <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>-Element zurück, sodass die Auswertung von „await“ einen `Int32`-Wert (`numRead`) erzeugt, nachdem der Vorgang abgeschlossen wurde. Weitere Informationen finden Sie unter [Async Return Types (C#) (Asynchrone Rückgabetypen (C#))](./async-return-types.md).  
  
```csharp  
public async Task ProcessReadAsync()  
{  
    string filePath = @"temp2.txt";  
  
    if (File.Exists(filePath) == false)  
    {  
        Debug.WriteLine("file not found: " + filePath);  
    }  
    else  
    {  
        try  
        {  
            string text = await ReadTextAsync(filePath);  
            Debug.WriteLine(text);  
        }  
        catch (Exception ex)  
        {  
            Debug.WriteLine(ex.Message);  
        }  
    }  
}  
  
private async Task<string> ReadTextAsync(string filePath)  
{  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize: 4096, useAsync: true))  
    {  
        StringBuilder sb = new StringBuilder();  
  
        byte[] buffer = new byte[0x1000];  
        int numRead;  
        while ((numRead = await sourceStream.ReadAsync(buffer, 0, buffer.Length)) != 0)  
        {  
            string text = Encoding.Unicode.GetString(buffer, 0, numRead);  
            sb.Append(text);  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
## <a name="parallel-asynchronous-io"></a>Parallele Asynchrone E/A  
 Das folgende Beispiel zeigt die parallele Verarbeitung durch das Schreiben von zehn Textdateien. Die Methode <xref:System.IO.Stream.WriteAsync%2A> gibt für jede Datei eine Aufgabe zurück, die anschließend zu einer Liste von Aufgaben hinzugefügt wird. Die `await Task.WhenAll(tasks);`-Anweisung beendet die Methode und wird innerhalb der Methode fortgesetzt, wenn die Dateiverarbeitung für alle Aufgaben abgeschlossen ist.  
  
 Im Beispiel werden alle <xref:System.IO.FileStream>-Instanzen in einem `finally`-Block geschlossen, nachdem die Aufgaben abgeschlossen sind. Wenn jeder `FileStream` stattdessen in einer `using`-Anweisung erstellt wurde, kann `FileStream` verworfen werden, bevor die Aufgabe abgeschlossen ist.  
  
 Beachten Sie, dass sich eine Steigerung der Leistung fast ausschließlich aus der parallelen und nicht der asynchronen Verarbeitung ergibt. Die Vorteile der Asynchronie sind, dass sie nicht mehrere Threads und den Benutzeroberflächenthread bindet.  
  
```csharp  
public async Task ProcessWriteMultAsync()  
{  
    string folder = @"tempfolder\";  
    List<Task> tasks = new List<Task>();  
    List<FileStream> sourceStreams = new List<FileStream>();  
  
    try  
    {  
        for (int index = 1; index <= 10; index++)  
        {  
            string text = "In file " + index.ToString() + "\r\n";  
  
            string fileName = "thefile" + index.ToString("00") + ".txt";  
            string filePath = folder + fileName;  
  
            byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
            FileStream sourceStream = new FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize: 4096, useAsync: true);  
  
            Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
            sourceStreams.Add(sourceStream);  
  
            tasks.Add(theTask);  
        }  
  
        await Task.WhenAll(tasks);  
    }  
  
    finally  
    {  
        foreach (FileStream sourceStream in sourceStreams)  
        {  
            sourceStream.Close();  
        }  
    }  
}  
```  
  
 Bei Verwendung der Methoden <xref:System.IO.Stream.WriteAsync%2A> und <xref:System.IO.Stream.ReadAsync%2A> können Sie einen <xref:System.Threading.CancellationToken> angeben, mit dem Sie den Vorgang in der Mitte des Streams beenden können. Weitere Informationen finden Sie unter [Fine-Tuning Your Async Application (C#) (Abstimmen der asynchronen Anwendung (C#))](./fine-tuning-your-async-application.md) und [Abbruch in verwalteten Threads](../../../../standard/threading/cancellation-in-managed-threads.md).  
  
## <a name="see-also"></a>Siehe auch

- [Asynchrone Programmierung mit „async“ und „await“ (C#)](./index.md)
- [Asynchrone Rückgabetypen (C#)](./async-return-types.md)
- [Ablaufsteuerung in asynchronen Programmen (C#)](./control-flow-in-async-programs.md)
