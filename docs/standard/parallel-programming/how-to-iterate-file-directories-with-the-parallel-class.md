---
title: 'Gewusst wie: Iterieren von Dateiverzeichnissen der Parallel-Klasse'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to iterate directories
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
ms.openlocfilehash: fda8443666d1c90b31cf02c2f925d1c89243a8e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091318"
---
# <a name="how-to-iterate-file-directories-with-the-parallel-class"></a>Gewusst wie: Iterieren von Dateiverzeichnissen der Parallel-Klasse
In vielen Fällen lässt sich die Dateiiteration problemlos parallelisieren. Das Thema [Gewusst wie: Iterieren von Dateiverzeichnissen mit PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) zeigt die einfachste Möglichkeit zum Ausführen dieser Aufgabe für viele Szenarien. Wenn der Code die vielen Arten von Ausnahmen behandeln muss, die auftreten können, wenn der Zugriff über das Dateisystem erfolgt, können jedoch Komplikationen auftreten. Im folgenden Beispiel wird ein Verfahren zum Lösen des Problems gezeigt. Alle Dateien und Ordner in einem angegebenen Verzeichnis werden mit stapelbasierte Iteration durchlaufen, und der Code kann verschiedene Ausnahmen abfangen und behandeln. Wie die Ausnahmen behandelt werden, müssen natürlich Sie bestimmen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Verzeichnissen sequenziell durchlaufen, aber die Dateien werden parallel verarbeitet. Dies ist wahrscheinlich die optimale Vorgehensweise, wenn die Anzahl der Dateien im Verhältnis zur Anzahl der Verzeichnisse sehr hoch ist. Es ist auch möglich, die Verzeichnisiteration zu parallelisieren und auf die einzelnen Dateien sequenziell zuzugreifen. Wahrscheinlich ist es nicht effizient, beide Schleifen zu parallelisieren, es sei denn, dies soll auf einem Computer mit einer großen Anzahl von Prozessoren erfolgen. In allen Fällen sollten Sie jedoch die Anwendung gründlich testen, um die beste Vorgehensweise zu bestimmen.  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 In diesem Beispiel wird die Datei-E/A synchron ausgeführt. Bei großen Dateien oder langsamen Netzwerkverbindungen empfiehlt sich möglicherweise ein asynchroner Zugriff auf die Dateien. Sie können Verfahren für asynchrone E/A mit paralleler Iteration kombinieren. Weitere Informationen finden Sie unter [TPL und herkömmliche asynchrone .NET Framework-Programmierung](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md).  
  
 Im Beispiel wird die lokale Variable `fileCount` verwendet, um eine Zählung der Gesamtanzahl der verarbeiteten Dateien zu verwalten. Da auf die Variable möglicherweise gleichzeitig von mehreren Aufgaben zugegriffen wird, wird der Zugriff darauf synchronisiert, indem die <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType>-Methode aufgerufen wird.  
  
 Beachten Sie, dass die Ausführung der von der <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Methode gestarteten Threads möglicherweise fortgesetzt wird, wenn im Hauptthread eine Ausnahme ausgelöst wird. Um diese Threads zu beenden, können Sie in den Ausnahmehandlern eine boolesche Variable festlegen und in jeder Iteration der parallelen Schleife den Wert dieser Variablen überprüfen. Wenn der Wert angibt, dass eine Ausnahme ausgelöst wurde, verwenden Sie die <xref:System.Threading.Tasks.ParallelLoopState>-Variable, um die Schleife zu beenden oder zu verlassen. Weitere Informationen finden Sie unter [Gewusst wie: Beenden oder Verlassen einer Parallel.For-Schleife](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd460721(v=vs.100)).  
  
## <a name="see-also"></a>Weitere Informationen

- [Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
