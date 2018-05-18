---
title: Paralleles LINQ (PLINQ)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccd30ee987fbc4ad75008a28c030c4f44a2368dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="parallel-linq-plinq"></a>Paralleles LINQ (PLINQ)
Paralleles LINQ (PLINQ) ist eine parallele Implementierung für LINQ to Objects. PLINQ implementiert den kompletten Satz von LINQ-Standardabfrageoperatoren als Erweiterungsmethoden für den <xref:System.Linq>-Namespace und verfügt über zusätzliche Operatoren für parallele Vorgänge. PLINQ kombiniert die Einfachheit und Lesbarkeit der LINQ-Syntax mit der Leistungsfähigkeit der parallelen Programmierung. Ebenso wie Code für die Task Parallel Library skalieren PLINQ-Abfragen abhängig von den Funktionen (Parallelitätsgrad) des Hostcomputers.  
  
 PLINQ kann LINQ to Objects-Abfragen in vielen Fällen erheblich beschleunigen, indem alle verfügbaren Kerne auf dem Hostcomputer effizienter genutzt werden. Diese höhere Leistung stellt eine maximale Verarbeitungsleistung am Desktop bereit.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Einführung in PLINQ](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [Beibehaltung der Reihenfolge in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [Mergeoptionen in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [Gewusst wie: Erstellen und Ausführen einer einfachen PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [Gewusst wie: Kombinieren von parallelen und sequenziellen LINQ-Abfragen](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [Gewusst wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [Gewusst wie: Abbrechen einer PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [Gewusst wie: Schreiben einer benutzerdefinierten PLINQ-Aggregatfunktion](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [Gewusst wie: Angeben des Ausführungsmodus in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [Gewusst wie: Angeben von Mergeoptionen in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [Gewusst wie: Iterieren von Dateiverzeichnissen mit PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [Gewusst wie: Messen der Leistung von PLINQ-Abfragen](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)  
 [LINQ (Language Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
