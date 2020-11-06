---
title: 'Vorgehensweise: Durchlaufen von Dateiverzeichnissen mit PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
ms.openlocfilehash: 5033cc24fce5fc17a950e4797de1ef4071e2b98a
ms.sourcegitcommit: 6d09ae36acba0b0e2ba47999f8f1a725795462a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2020
ms.locfileid: "92925375"
---
# <a name="how-to-iterate-file-directories-with-plinq"></a>Vorgehensweise: Durchlaufen von Dateiverzeichnissen mit PLINQ

In diesem Artikel werden zwei einfache Möglichkeiten gezeigt, um Vorgänge für Dateiverzeichnisse zu parallelisieren. Die erste Abfrage füllt mit der <xref:System.IO.Directory.GetFiles%2A>-Methode ein Array von Dateinamen in einem Verzeichnis und allen Unterverzeichnissen. Diese Methode kann am Anfang des Vorgangs zu Wartezeit führen, da sie erst eine Rückgabe erzeugt, wenn das gesamte Array aufgefüllt ist. Sobald das Array aufgefüllt ist, kann PLINQ es jedoch schnell parallel verarbeiten.  
  
Die zweite Abfrage verwendet die statische <xref:System.IO.Directory.EnumerateDirectories%2A>- und <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>-Methode, die sofort beginnen, Ergebnisse zurückzugeben. Dieser Ansatz kann bei Iterationen über umfangreiche Verzeichnisstrukturen schneller sein, die Verarbeitungszeit im Vergleich zum ersten Beispiel hängt jedoch von vielen Faktoren ab.  
  
> [!NOTE]
> Diese Beispiele sollen die Nutzung darstellen und werden möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="getfiles-example"></a>GetFiles-Beispiel

 Dieses Beispiel zeigt die Iteration über Dateiverzeichnisse in einfachen Szenarien, wenn Sie Zugriff auf alle Verzeichnisse in der Struktur haben, die Dateien nicht sehr groß und die Zugriffszeiten nicht beachtlich sind. Bei diesem Ansatz tritt zu Anfang eine Wartezeit auf, während das Dateinamenarray konstruiert wird.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="enumeratefiles-example"></a>EnumerateFiles-Beispiel

 Dieses Beispiel zeigt die Iteration über Dateiverzeichnisse in einfachen Szenarien, wenn Sie Zugriff auf alle Verzeichnisse in der Struktur haben, die Dateien nicht sehr groß und die Zugriffszeiten nicht beachtlich sind. Dieser Ansatz erzeugt Ergebnisse schneller als das vorherige Beispiel.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Achten Sie bei Verwendung von <xref:System.IO.Directory.GetFiles%2A> darauf, dass Sie über ausreichende Berechtigungen für alle Verzeichnisse in der Struktur verfügen. Andernfalls wird eine Ausnahme ausgelöst, und es werden keine Ergebnisse zurückgegeben. Bei Verwendung von <xref:System.IO.Directory.EnumerateDirectories%2A> in einer PLINQ-Abfrage ist es schwierig, E/A-Ausnahmen auf eine ordnungsgemäße Weise zu behandeln, die Ihnen erlaubt, die Iteration fortzusetzen. Wenn der Code E/A- oder nicht autorisierten Zugriff betreffende Ausnahmen behandeln muss, sollten Sie den unter [Vorgehensweise: Iterieren von Dateiverzeichnissen der Parallel-Klasse](how-to-iterate-file-directories-with-the-parallel-class.md) beschriebenen Ansatz in Betracht ziehen.  
  
 Wenn E/A-Wartezeit ein Problem ist, z.B. bei Datei-E/A über ein Netzwerk, erwägen Sie die Verwendung einer der unter [TPL und herkömmliche asynchrone .NET-Programmierung](tpl-and-traditional-async-programming.md) und in diesem [Blogbeitrag](https://devblogs.microsoft.com/pfxteam/parallel-extensions-and-io/) beschriebenen asynchronen E/A-Techniken.  
  
## <a name="see-also"></a>Siehe auch

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
