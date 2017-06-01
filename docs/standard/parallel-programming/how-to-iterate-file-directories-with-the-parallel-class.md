---
title: "Gewusst wie: Iterieren von Dateiverzeichnissen der Parallel-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Parallele Schleifen, Durchlaufen von Verzeichnissen"
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Iterieren von Dateiverzeichnissen der Parallel-Klasse
In vielen Fällen lässt sich die Dateiiteration problemlos parallelisieren.  Im Thema [How to: Iterate File Directories with PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) wird gezeigt, wie diese Aufgabe in vielen Szenarien am einfachsten ausgeführt werden kann.  Wenn der Code die vielen Arten von Ausnahmen behandeln muss, die auftreten können, wenn der Zugriff über das Dateisystem erfolgt, können jedoch Komplikationen auftreten.  Im folgenden Beispiel wird ein Verfahren zum Lösen des Problems gezeigt.  Alle Dateien und Ordner in einem angegebenen Verzeichnis werden mit stapelbasierte Iteration durchlaufen, und der Code kann verschiedene Ausnahmen abfangen und behandeln.  Wie die Ausnahmen behandelt werden, müssen natürlich Sie bestimmen.  
  
## Beispiel  
 Im folgenden Beispiel werden die Verzeichnissen sequenziell durchlaufen, aber die Dateien werden parallel verarbeitet.  Dies ist wahrscheinlich die optimale Vorgehensweise, wenn die Anzahl der Dateien im Verhältnis zur Anzahl der Verzeichnisse sehr hoch ist.  Es ist auch möglich, die Verzeichnisiteration zu parallelisieren und auf die einzelnen Dateien sequenziell zuzugreifen.  Wahrscheinlich ist es nicht effizient, beide Schleifen zu parallelisieren, es sei denn, dies soll auf einem Computer mit einer großen Anzahl von Prozessoren erfolgen.  In allen Fällen sollten Sie jedoch die Anwendung gründlich testen, um die beste Vorgehensweise zu bestimmen.  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 In diesem Beispiel wird die Datei\-E\/A synchron ausgeführt.  Bei großen Dateien oder langsamen Netzwerkverbindungen empfiehlt sich möglicherweise ein asynchroner Zugriff auf die Dateien.  Sie können Verfahren für asynchrone E\/A mit paralleler Iteration kombinieren.  Weitere Informationen finden Sie unter [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md).  
  
 Im Beispiel wird die lokale Variable `fileCount` verwendet, um eine Zählung der Gesamtanzahl der verarbeiteten Dateien zu verwalten.  Da auf die Variable möglicherweise gleichzeitig von mehreren Aufgaben zugegriffen wird, wird der Zugriff darauf synchronisiert, indem die <xref:System.Threading.Interlocked.Add%2A?displayProperty=fullName>\-Methode aufgerufen wird.  
  
 Beachten Sie, dass die Ausführung der von der <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Methode gestarteten Threads möglicherweise fortgesetzt wird, wenn im Hauptthread eine Ausnahme ausgelöst wird.  Um diese Threads zu beenden, können Sie in den Ausnahmehandlern eine boolesche Variable festlegen und in jeder Iteration der parallelen Schleife den Wert dieser Variablen überprüfen.  Wenn der Wert angibt, dass eine Ausnahme ausgelöst wurde, verwenden Sie die <xref:System.Threading.Tasks.ParallelLoopState>\-Variable, um die Schleife zu beenden oder zu verlassen.  Weitere Informationen finden Sie unter [How to: Stop or Break from a Parallel.For Loop](http://msdn.microsoft.com/de-de/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e).  
  
## Siehe auch  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)