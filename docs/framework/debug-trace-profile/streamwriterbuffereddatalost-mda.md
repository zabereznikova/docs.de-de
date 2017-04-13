---
title: "streamWriterBufferedDataLost MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "StreamWriter class, data buffering problems"
  - "managed debugging assistants (MDAs), StreamWriter data buffering"
  - "buffers, StreamWriter problems"
  - "MDAs (managed debugging assistants), StreamWriter data buffering"
  - "StreamWriter buffered data lost"
  - "data buffering problems"
  - "streamWriterBufferedDataLost MDA"
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# streamWriterBufferedDataLost MDA
Der `streamWriterBufferedDataLost`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn in einen <xref:System.IO.StreamWriter> geschrieben wird, jedoch anschließend kein Aufruf der <xref:System.IO.StreamWriter.Flush%2A>\-Methode oder der <xref:System.IO.StreamWriter.Close%2A>\-Methode erfolgt, bevor die Instanz von <xref:System.IO.StreamWriter> zerstört wird.  Wenn dieser MDA bereitgestellt wurde, bestimmt die Laufzeit, ob im <xref:System.IO.StreamWriter> immer noch gepufferten Daten vorhanden sind.  Wenn gepufferte Daten vorhanden sind, wird der MDA aktiviert.  Durch Aufrufen der <xref:System.GC.Collect%2A>\-Methode und der <xref:System.GC.WaitForPendingFinalizers%2A>\-Methode kann das Ausführen von Finalizern erzwungen werden.  Andernfalls werden Finalizer zu scheinbar beliebigen Zeiten und beim Prozessende möglicherweise gar nicht ausgeführt.  Um diese Art von Problem zuverlässiger zu reproduzieren, ist es nützlich, Finalizer ausdrücklich aufzurufen und diesen MDA bereitzustellen.  
  
## Symptome  
 Ein <xref:System.IO.StreamWriter> schreibt die letzten 1\-4 KB Daten nicht in eine Datei.  
  
## Ursache  
 Der <xref:System.IO.StreamWriter> puffert die Daten intern. Daher ist es erforderlich, die <xref:System.IO.StreamWriter.Close%2A>\-Methode oder die <xref:System.IO.StreamWriter.Flush%2A>\-Methode aufzurufen, damit die gepufferten Daten in den zugrunde liegenden Datenspeicher geschrieben werden.  Wenn kein entsprechender Aufruf von <xref:System.IO.StreamWriter.Close%2A> oder <xref:System.IO.StreamWriter.Flush%2A> erfolgt, werden die in der <xref:System.IO.StreamWriter>\-Instanz gepufferten Daten möglicherweise nicht erwartungsgemäß geschrieben.  
  
 Das folgende Beispiel stellt schlecht geschriebenen Code dar, der von diesem MDA abgefangen werden sollte.  
  
```  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 Der Code im vorausgegangenen Beispiel aktiviert diesen MDA zuverlässiger, wenn eine Garbage Collection ausgelöst und dann unterbrochen wird, bis die Finalizer beendet wurden.  Um dieser Art von Problem auf die Spur zu kommen, können Sie in einem Debugbuild den Code aus dem folgenden Beispiel an das Ende der Methode aus dem vorausgegangenen Beispiel anhängen.  Dadurch wird der MDA zuverlässiger aktiviert \(aber natürlich nicht die Ursache des Problems behoben\).  
  
```  
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## Lösung  
 Stellen Sie sicher, dass ein Aufruf von <xref:System.IO.StreamWriter.Close%2A> oder <xref:System.IO.StreamWriter.Flush%2A> für den <xref:System.IO.StreamWriter> erfolgt, bevor die Anwendung bzw. jeder Codeblock geschlossen wird, in der bzw. dem eine Instanz eines <xref:System.IO.StreamWriter> verwendet wird.  Am besten erreichen Sie dies, indem Sie die Instanz mit einem `using`\-Block von C\# erstellen \(`Using` in Visual Basic\). Dadurch wird sichergestellt, dass die <xref:System.IO.StreamWriter.Dispose%2A>\-Methode für den Writer aufgerufen und die Instanz somit ordnungsgemäß geschlossen wird.  
  
```  
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 Im folgenden Codebeispiel wird dieselbe Lösung veranschaulicht, jedoch mit `try/finally` statt mit `using`.  
  
```  
StreamWriter sw;  
try   
{  
    sw = new StreamWriter("file.txt"));  
    sw.WriteLine("Data");  
}  
finally   
{  
    if (sw != null)  
        sw.Close();  
}  
```  
  
 Wenn keine dieser Lösungen verwendet werden kann, z. B. weil ein <xref:System.IO.StreamWriter> in einer statischen Variablen gespeichert ist und am Ende seiner Lebensdauer nicht einfach Code ausgeführt werden kann, rufen Sie nach dessen letzter Verwendung <xref:System.IO.StreamWriter.Flush%2A> für den <xref:System.IO.StreamWriter> auf, oder legen Sie vor dessen erster Verwendung die <xref:System.IO.StreamWriter.AutoFlush%2A>\-Eigenschaft auf `true` fest, um dieses Problem zu vermeiden.  
  
```  
private static StreamWriter log;  
// static class constructor.  
static WriteToFile()   
{  
    StreamWriter sw = new StreamWriter("log.txt");  
    sw.AutoFlush = true;  
  
    // Publish the StreamWriter for other threads.  
    log = sw;  
}  
```  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die Laufzeit.  
  
## Ausgabe  
 Eine Meldung, die angibt, dass diese Verletzung aufgetreten ist.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.IO.StreamWriter>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)