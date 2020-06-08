---
title: Beibehaltung der Reihenfolge in PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, order preservation
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
ms.openlocfilehash: 45752f3ffa64079079505934afd76e812daad7bd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290654"
---
# <a name="order-preservation-in-plinq"></a>Beibehaltung der Reihenfolge in PLINQ
Das Ziel in PLINQ ist, die Leistung zu maximieren und gleichzeitig die korrekte Ausführung sicherzustellen. Eine Abfrage sollte so schnell wie möglich ausgeführt werden, dabei jedoch stets die korrekten Ergebnissen erzeugen. In einigen Fällen muss für eine korrekte Ausführung die Reihenfolge der Quellsequenz beibehalten werden, eine Sortierung kann jedoch sehr rechenintensiv sein. PLINQ behält die Reihenfolge der Quellsequenz daher standardmäßig nicht bei. In dieser Hinsicht ähnelt PLINQ [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)], unterscheidet sich jedoch von LINQ to Objects, wo die Reihenfolge beibehalten wird.  
  
 Um das Standardverhalten zu überschreiben, können Sie mithilfe des <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Operators in der Quellsequenz die Beibehaltung der Reihenfolge aktivieren. Sie können die Beibehaltung der Reihenfolge später in der Abfrage mit der <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>-Methode deaktivieren. Bei beiden Methoden wird die Abfrage auf Grundlage der Heuristik verarbeitet, die bestimmt, ob die Abfrage parallel oder sequenziell ausgeführt wird. Weitere Informationen finden Sie unter [Understanding Speedup in PLINQ (Grundlagen zur Beschleunigung in PLINQ)](understanding-speedup-in-plinq.md).  
  
 Im folgenden Beispiel wird eine ungeordnete parallele Abfrage gezeigt, die alle mit einer Bedingung übereinstimmenden Elemente heraus filtert, ohne die Ergebnisse auf irgendeine Weise zu sortieren.  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 Diese Abfrage gibt nicht notwendigerweise die ersten 1000 mit der Bedingung übereinstimmenden Orte in der Quellsequenz zurück, sondern einen Satz mit 1000 beliebigen Orten, die die Bedingung erfüllen. PLINQ-Abfrageoperatoren partitionieren die Quellsequenz in mehrere Untersequenzen, die als gleichzeitige Aufgaben verarbeitet werden. Wenn die Beibehaltung der Reihenfolge nicht angegeben wurde, werden die Ergebnisse jeder Partition in willkürlicher Reihenfolge an die nächste Phase der Abfrage übergeben. Darüber hinaus kann eine Partition eine Teilmenge der Ergebnisse ausgeben, bevor die Verarbeitung der restlichen Elemente fortgesetzt wird. Die resultierende Reihenfolge kann dabei jedes Mal anders sein. Die Anwendung kann die Reihenfolge nicht steuern, da diese davon abhängt, wie das Betriebssystem die Threads plant.  
  
 Im folgenden Beispiel wird das Standardverhalten mit dem <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Operator in der Quellsequenz überschrieben. Dadurch wird sichergestellt, dass die <xref:System.Linq.ParallelEnumerable.Take%2A>-Methode die ersten 1000 Orte in der Quellsequenz zurückgibt, die die Bedingung erfüllen.  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 Diese Abfrage wird wahrscheinlich nicht so schnell ausgeführt wie die unsortierte Version, da die ursprüngliche Reihenfolge in allen Partitionen nachverfolgt und beim Merge die Konsistenz der Reihenfolge sichergestellt werden muss. Daher empfiehlt es sich, <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> nur bei Bedarf und nur für die erforderlichen Teile der Abfrage zu verwenden. Wenn die Beibehaltung der Reihenfolge nicht mehr notwendig ist, deaktivieren Sie diese mit <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>. Im folgenden Beispiel wird dies erreicht, indem zwei Abfragen verfasst werden.  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 Beachten Sie, dass PLINQ die Reihenfolge einer Sequenz beibehält, die von Operatoren mit erzwungener Reihenfolge für den Rest der Abfrage erzeugt wurde. Anders ausgedrückt werden Operatoren wie <xref:System.Linq.ParallelEnumerable.OrderBy%2A> und <xref:System.Linq.ParallelEnumerable.ThenBy%2A> so behandelt, als ob ihnen ein Aufruf von <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> folgt.  
  
## <a name="query-operators-and-ordering"></a>Abfrageoperatoren und Reihenfolge  
 Die folgenden Abfrageoperatoren aktivieren die Beibehaltung der Reihenfolge für alle nachfolgenden Vorgänge in einer Abfrage bzw. solange, bis <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> aufgerufen wird:  
  
- <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
- <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
- <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
- <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 Die folgenden PLINQ-Abfrageoperatoren erfordern in bestimmten Fällen geordnete Quellsequenzen, damit die korrekten Ergebnisse erzeugt werden:  
  
- <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
- <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
- <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
- <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
- <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 Einige PLINQ-Abfrageoperatoren verhalten sich anders, je nachdem ob die Quellsequenz geordnet oder ungeordnet ist. In der folgenden Tabelle sind diese Operatoren aufgeführt.  
  
|Operator|Ergebnis bei geordneter Quellsequenz|Ergebnis bei ungeordneter Quellsequenz|  
|--------------|------------------------------------------------|--------------------------------------------------|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>|Nicht deterministische Ausgabe für nicht assoziative oder nicht kommutative Vorgänge|Nicht deterministische Ausgabe für nicht assoziative oder nicht kommutative Vorgänge|  
|<xref:System.Linq.ParallelEnumerable.All%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.Any%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.Average%2A>|Nicht deterministische Ausgabe für nicht assoziative oder nicht kommutative Vorgänge|Nicht deterministische Ausgabe für nicht assoziative oder nicht kommutative Vorgänge|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Count%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.Distinct%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.ElementAt%2A>|Rückgabe des angegebenen Elements|Willkürliches Element|  
|<xref:System.Linq.ParallelEnumerable.ElementAtOrDefault%2A>|Rückgabe des angegebenen Elements|Willkürliches Element|  
|<xref:System.Linq.ParallelEnumerable.Except%2A>|Ungeordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.First%2A>|Rückgabe des angegebenen Elements|Willkürliches Element|  
|<xref:System.Linq.ParallelEnumerable.FirstOrDefault%2A>|Rückgabe des angegebenen Elements|Willkürliches Element|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Nicht deterministische, parallele Ausführung|Nicht deterministische, parallele Ausführung|  
|<xref:System.Linq.ParallelEnumerable.GroupBy%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.GroupJoin%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Intersect%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Join%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Last%2A>|Rückgabe des angegebenen Elements|Willkürliches Element|  
|<xref:System.Linq.ParallelEnumerable.LastOrDefault%2A>|Rückgabe des angegebenen Elements|Willkürliches Element|  
|<xref:System.Linq.ParallelEnumerable.LongCount%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.Min%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.OrderBy%2A>|Neusortierung der Sequenz|Start eines neuen geordneten Abschnitts|  
|<xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>|Neusortierung der Sequenz|Start eines neuen geordneten Abschnitts|  
|<xref:System.Linq.ParallelEnumerable.Range%2A>|Nicht zutreffend (gleicher Standardwert wie <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|Nicht zutreffend (gleicher Standardwert wie <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Umkehrung|Keine Auswirkung|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Select%2A> (indiziert)|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A> (indiziert)|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|Geordneter Vergleich|Ungeordneter Vergleich|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Überspringt die ersten *n* Elemente|Überspringt *n* Elemente|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|Geordnete Ergebnisse|Nicht deterministisch Ausführung von SkipWhile für die aktuelle willkürliche Reihenfolge|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|Nicht deterministische Ausgabe für nicht assoziative oder nicht kommutative Vorgänge|Nicht deterministische Ausgabe für nicht assoziative oder nicht kommutative Vorgänge|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Verwendung der ersten `n` Elemente|Verwendung aller `n` Elemente|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|Geordnete Ergebnisse|Nicht deterministisch Ausführung von TakeWhile für die aktuelle willkürliche Reihenfolge|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|Ergänzung zu `OrderBy`|Ergänzung zu `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|Ergänzung zu `OrderBy`|Ergänzung zu `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|Nicht zutreffend|Nicht zutreffend|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Where%2A> (indiziert)|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|Geordnete Ergebnisse|Ungeordnete Ergebnisse|  
  
 Ungeordnete Ergebnisse werden nicht aktiv gemischt. Auf sie wird lediglich keine bestimmte Sortierlogik angewendet. In einigen Fällen wird in einer ungeordneten Abfrage möglicherweise die Reihenfolge der Quellsequenz beibehalten. Für Abfragen mit dem indizierten Select-Operator stellt PLINQ sicher, dass Elemente in aufsteigender Indexreihenfolge ausgegeben werden, jedoch wird nicht festgelegt, welcher Index welchem Element zugewiesen wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
- [Parallele Programmierung](index.md)
