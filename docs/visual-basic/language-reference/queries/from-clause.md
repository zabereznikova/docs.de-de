---
title: From-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: a63fb41fc2b0ad885acf76ad5d56e446922f5b90
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343775"
---
# <a name="from-clause-visual-basic"></a>From-Klausel (Visual Basic)
Gibt eine oder mehrere Bereichs Variablen und eine abzufragende Auflistung an.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich Eine *Bereichs Variable* , die verwendet wird, um die Elemente der Auflistung zu durchlaufen. Eine Bereichs Variable wird verwendet, um auf die einzelnen Member des `collection` zu verweisen, während die Abfrage die `collection`durchläuft. Muss ein Aufzähl Bare-Typ sein.|  
|`type`|Optional. Der `element`-Typ. Wenn keine `type` angegeben wird, wird der Typ der `element` von `collection`abgeleitet.|  
|`collection`|Erforderlich Verweist auf die Auflistung, die abgefragt werden soll. Muss ein Aufzähl Bare-Typ sein.|  
  
## <a name="remarks"></a>Hinweise  
 Die `From`-Klausel wird verwendet, um die Quelldaten für eine Abfrage und die Variablen zu identifizieren, die verwendet werden, um auf ein Element aus der Quell Auflistung zu verweisen. Diese Variablen werden als *Bereichs Variablen*bezeichnet. Die `From`-Klausel ist für eine Abfrage erforderlich, außer wenn die `Aggregate`-Klausel verwendet wird, um eine Abfrage zu identifizieren, die nur aggregierte Ergebnisse zurückgibt. Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Sie können mehrere `From` Klauseln in einer Abfrage angeben, um mehrere Sammlungen zu identifizieren, die verknüpft werden sollen. Wenn mehrere Sammlungen angegeben werden, werden Sie unabhängig voneinander durchlaufen, oder Sie können Sie verknüpfen, wenn Sie verknüpft sind. Sie können Auflistungen implizit mit der `Select`-Klausel oder explizit mithilfe der Klauseln `Join` oder `Group Join` verknüpfen. Als Alternative können Sie mehrere Bereichs Variablen und Auflistungen in einer einzigen `From`-Klausel angeben, wobei jede zugehörige Bereichs Variable und Auflistung durch ein Komma von den anderen getrennt werden. Das folgende Codebeispiel zeigt beide Syntax Optionen für die `From`-Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 Die `From`-Klausel definiert den Gültigkeitsbereich einer Abfrage, die dem Bereich einer `For` Schleife ähnelt. Daher muss jede `element` Range-Variable im Gültigkeitsbereich einer Abfrage einen eindeutigen Namen aufweisen. Da Sie mehrere `From` Klauseln für eine Abfrage angeben können, können nachfolgende `From` Klauseln auf Bereichs Variablen in der `From`-Klausel verweisen, oder Sie können in einer früheren `From`-Klausel auf Bereichs Variablen verweisen. Das folgende Beispiel zeigt beispielsweise eine `From`-Klausel, bei der die Auflistung in der zweiten Klausel auf einer Eigenschaft der Bereichs Variablen in der ersten Klausel basiert.  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 Auf jede `From`-Klausel kann eine beliebige Kombination zusätzlicher Abfrage Klauseln folgen, um die Abfrage zu verfeinern. Es gibt folgende Möglichkeiten, um die Abfrage zu verfeinern:  
  
- Kombinieren Sie mehrere Auflistungen implizit mithilfe der Klauseln `From` und `Select` oder explizit mithilfe der Klauseln `Join` oder `Group Join`.  
  
- Verwenden Sie die `Where`-Klausel, um das Abfrageergebnis zu filtern.  
  
- Sortieren Sie das Ergebnis mithilfe der `Order By`-Klausel.  
  
- Gruppieren Sie ähnliche Ergebnisse mit der `Group By`-Klausel.  
  
- Verwenden Sie die `Aggregate`-Klausel, um Aggregatfunktionen zu identifizieren, die für das gesamte Abfrageergebnis ausgewertet werden sollen.  
  
- Verwenden Sie die `Let`-Klausel, um eine Iterations Variable einzuführen, deren Wert durch einen Ausdruck anstelle einer Auflistung bestimmt wird.  
  
- Verwenden Sie die `Distinct`-Klausel, um doppelte Abfrageergebnisse zu ignorieren.  
  
- Identifizieren Sie mithilfe der Klauseln `Skip`, `Take`, `Skip While`und `Take While` Teile des Ergebnisses, das zurückgegeben werden soll.  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrage Ausdruck verwendet eine `From`-Klausel, um für jedes `Customer`-Objekt in der `customers` Auflistung eine Bereichs Variable `cust` zu deklarieren. Die `Where`-Klausel verwendet die Range-Variable, um die Ausgabe auf Kunden aus dem angegebenen Bereich zu beschränken. Die `For Each`-Schleife zeigt den Firmennamen für jeden Kunden im Abfrageergebnis an.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
- [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Distinct-Klausel](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [Join-Klausel](../../../visual-basic/language-reference/queries/join-clause.md)
- [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Let-Klausel](../../../visual-basic/language-reference/queries/let-clause.md)
- [Skip-Klausel](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take-Klausel](../../../visual-basic/language-reference/queries/take-clause.md)
- [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md)
