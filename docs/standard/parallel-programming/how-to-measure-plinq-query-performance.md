---
title: 'Vorgehensweise: Messen der Leistung von PLINQ-Abfragen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
ms.openlocfilehash: f240b2c275305aec5699eb42406e0689925490a8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288185"
---
# <a name="how-to-measure-plinq-query-performance"></a>Vorgehensweise: Messen der Leistung von PLINQ-Abfragen

Dieses Beispiel zeigt, wie Sie mithilfe der <xref:System.Diagnostics.Stopwatch>-Klasse messen können, wie viel Zeit für die Ausführung einer PLINQ-Abfrage benötigt wird.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine leere `foreach`-Schleife (`For Each` in Visual Basic) verwendet, um die für die Ausführung der Abfrage erforderliche Zeit zu messen. In echtem Code würde die Schleife normalerweise weitere Verarbeitungsschritte enthalten, die die Gesamtzeit der Abfrageausführung erhöhen. Beachten Sie, dass die Stoppuhr erst kurz vor der Schleife gestartet wird, wenn die Abfrageausführung beginnt. Wenn Sie eine differenziertere Messung benötigen, können Sie die `ElapsedTicks`-Eigenschaft anstelle der `ElapsedMilliseconds`-Eigenschaft verwenden.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 Die Gesamtausführungszeit ist eine wichtige Messgröße beim Testen von Abfrageimplementierungen, sie vermittelt jedoch nicht immer das Gesamtbild. Verwenden Sie die [Parallelitätsschnellansicht](/visualstudio/profiling/concurrency-visualizer), um eine genauere und umfangreichere Darstellung der Interaktion der Abfragethreads untereinander und mit anderen laufenden Prozessen zu erhalten.  
  
## <a name="see-also"></a>Siehe auch

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
