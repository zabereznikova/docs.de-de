---
title: 'Vorgehensweise: Angeben des Ausführungsmodus in PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: 725f232337952449cd8569b12f65da75569996df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722394"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Vorgehensweise: Angeben des Ausführungsmodus in PLINQ

Dieses Beispiel zeigt, wie erzwungen wird, dass PLINQ seine Standardheuristik umgeht und eine Abfrage unabhängig von der Form parallelisiert.  
  
> [!NOTE]
> Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  

 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ ist dazu konzipiert, Gelegenheiten zur Parallelisierung auszunutzen. Nicht alle Abfragen profitieren jedoch von der parallelen Ausführung. Wenn eine Abfrage z. B. einen einzelnen Benutzerdelegaten enthält, der wenig ausführt, ist die sequenzielle Ausführung der Abfrage in der Regel schneller. Die sequenzielle Ausführung ist schneller, da sich der Mehraufwand zum Aktivieren der parallelen Ausführung im Vergleich zur erzielten Beschleunigung nicht rentiert. Darum parallelisiert PLINQ nicht automatisch jede Abfrage. Zunächst werden die Form der Abfrage und die verschiedenen enthaltenen Operatoren untersucht. Auf Grundlage dieser Analyse kann PLINQ im Standardausführungsmodus entscheiden, die Abfrage zum Teil oder im Ganzen sequenziell auszuführen. In einigen Fällen wissen Sie jedoch vielleicht mehr über die Abfrage, als PLINQ in seiner Analyse ermitteln kann. Möglicherweise wissen Sie, dass ein Delegat aufwendig ist und die Abfrage definitiv von einer Parallelisierung profitiert. In solchen Fällen können Sie mit der <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>-Methode den <xref:System.Linq.ParallelExecutionMode.ForceParallelism>-Wert angeben und PLINQ anweisen, die Abfrage stets parallel auszuführen.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Schneiden Sie diesen Code aus, fügen Sie ihn in das [PLINQ-Datenbeispiel](plinq-data-sample.md) ein, und rufen Sie die Methode in `Main` auf.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
