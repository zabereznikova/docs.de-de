---
title: 'Gewusst wie: Iterieren von Dateiverzeichnissen mit PLINQ'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40fd9f64b5702f5205b7817f3de1e0a8709c5a63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-plinq"></a>Gewusst wie: Iterieren von Dateiverzeichnissen mit PLINQ
Dieses Beispiel zeigt zwei einfache Möglichkeiten, um Vorgänge für Verzeichnisse zu parallelisieren. Die erste Abfrage verwendet die <xref:System.IO.Directory.GetFiles%2A> Methode, um ein Array von Dateinamen in einem Verzeichnis und alle Unterverzeichnisse aufzufüllen. Diese Methode gibt keinen zurück, bis das gesamte Array aufgefüllt wird, und daher es am Anfang des Vorgangs Latenzzeit kann. Nachdem das Array aufgefüllt wird, kann jedoch PLINQ es parallel sehr schnell verarbeitet.  
  
 Die zweite Abfrage verwendet die statische <xref:System.IO.Directory.EnumerateDirectories%2A> und <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> Methoden, die sofort Ergebnisse zurückgeben. Dieser Ansatz kann schneller sein, wenn Sie umfangreiche Verzeichnisstrukturen durchlaufen werden, obwohl die Verarbeitungszeit im Vergleich zur im ersten Beispiel wird von vielen Faktoren abhängen kann.  
  
> [!WARNING]
>  Diese Beispiele dienen zur Nutzung darstellen und möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Dateiverzeichnisse einfache Szenarien durchlaufen, wenn Sie Zugriff auf alle Verzeichnisse in der Struktur haben, die Dateigröße nicht sehr groß sind und die Zugriffszeit nicht relevant sind. Bei diesem Ansatz muss eine bestimmte Wartezeit am Anfang, während das Array von Dateinamen konstruiert wird.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Dateiverzeichnisse einfache Szenarien durchlaufen, wenn Sie Zugriff auf alle Verzeichnisse in der Struktur haben, die Dateigröße nicht sehr groß sind und die Zugriffszeit nicht relevant sind. Dieser Ansatz beginnt, erzeugt die Ergebnisse schneller als das vorherige Beispiel.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Bei Verwendung <xref:System.IO.Directory.GetFiles%2A>, achten Sie darauf, dass Sie über ausreichende Berechtigungen für alle Verzeichnisse in der Struktur verfügen. Andernfalls wird eine Ausnahme ausgelöst werden und es werden keine Ergebnisse zurückgegeben werden. Bei Verwendung der <xref:System.IO.Directory.EnumerateDirectories%2A> in einer PLINQ-Abfrage ist es schwierig, e/a-Ausnahmen auf ordnungsgemäße Weise zu behandeln, die Sie durchlaufen zu fortfahren können. Wenn der Code muss e/a- oder vor nicht autorisiertem Zugriffsausnahmen behandeln, sollten Sie in beschriebenen Ansatz [wie: Iterieren von Dateiverzeichnissen mit der Parallel-Klasse](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Wenn e/a-Latenz ein Problem ist, mit Datei-e/a über ein Netzwerk, z. B. können Sie mithilfe eines der asynchronen e/a-Techniken beschrieben, die [TPL und herkömmliche .NET Framework asynchrone Programmierung](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) und in diesem [Blogbeitrag ](http://go.microsoft.com/fwlink/?LinkID=186458).  
  
## <a name="see-also"></a>Siehe auch  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
