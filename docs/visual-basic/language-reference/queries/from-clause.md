---
title: From-Klausel (Visual Basic)
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
ms.openlocfilehash: 1f113444efae83de7d299db330593937c7800bb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604717"
---
# <a name="from-clause-visual-basic"></a>From-Klausel (Visual Basic)
Gibt an, eine oder mehrere Bereichsvariablen und eine Auflistung Abfrage.  
  
## <a name="syntax"></a>Syntax  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich. Ein *Bereichsvariable* zum Durchlaufen der Elemente der Auflistung verwendet. Eine Bereichsvariable wird verwendet, um auf jedes Element einer finden Sie unter der `collection` wie die Abfrage durchläuft die `collection`. Ein aufzählbarer Typ muss sein.|  
|`type`|Dies ist optional. Der `element`-Typ. Wenn kein `type` angegeben wird, den Typ des `element` von hergeleitet `collection`.|  
|`collection`|Erforderlich. Bezieht sich auf die Auflistung abgefragt werden. Ein aufzählbarer Typ muss sein.|  
  
## <a name="remarks"></a>Hinweise  
 Die `From` -Klausel wird verwendet, identifizieren Sie die Quelldaten für eine Abfrage und die Variablen, die zum Verweisen auf ein Element aus der Auflistung verwendet werden. Diese Variablen heißen *Bereichsvariablen*. Die `From` -Klausel ist erforderlich für eine Abfrage, außer wenn die `Aggregate` -Klausel wird verwendet, um eine Abfrage zu identifizieren, gibt nur Ergebnisse aggregiert. Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Sie können angeben, dass mehrere `From` Klauseln in einer Abfrage zur Identifizierung von mehreren Sammlungen verknüpft werden sollen. Wenn mehrere Sammlungen angegeben werden, sie werden unabhängig voneinander durchlaufen, oder können hinzugefügt werden, wenn sie verknüpft sind. Sie können Sammlungen implizit verknüpfen, indem die `Select` -Klausel, oder explizit mit der `Join` oder `Group Join` Klauseln. Als Alternative können Sie mehrere Bereichsvariablen und Sammlungen angeben, in einer einzelnen `From` -Klausel, wobei alle verwandten Bereichsvariable und Sammlungen, die von den anderen durch Kommas getrennt. Im folgenden Codebeispiel wird gezeigt, beide Optionen zur Abfragesyntax für die `From` Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 Die `From` -Klausel definiert den Bereich einer Abfrage, der dem Bereich der ähnelt einer `For` Schleife. Aus diesem Grund jede `element` Bereichsvariable im Bereich einer Abfrage muss einen eindeutigen Namen aufweisen. Da es sich bei Angabe mehrerer `From` Klauseln für eine Abfrage, die nachfolgenden `From` Klauseln können finden Sie in der Bereichsvariablen in der `From` -Klausel, oder sie können auf Bereichsvariablen finden Sie in einem vorherigen `From` Klausel. Das folgende Beispiel zeigt beispielsweise eine geschachtelte `From` Klausel, in die Auflistung in der zweiten Klausel auf eine Eigenschaft der Bereichsvariablen in der ersten Klausel basiert.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 Jede `From` Klausel kann eine beliebige Kombination von zusätzliche Abfrageklauseln zum Verfeinern der Abfrage folgen. Sie können die Abfrage folgendermaßen optimieren:  
  
-   Kombinieren mehrerer Sammlungen implizit mithilfe der `From` und `Select` Klauseln, oder explizit mit der `Join` oder `Group Join` Klauseln.  
  
-   Verwenden der `Where` -Klausel, um das Ergebnis der Abfrage zu filtern.  
  
-   Sortieren des Ergebnisses mithilfe der `Order By` Klausel.  
  
-   Gruppieren ähnlicher Ergebnisse mithilfe der `Group By` Klausel.  
  
-   Verwenden der `Aggregate` -Klausel, um Aggregatfunktionen für das gesamte Abfrageergebnis ausgewertet werden sollen.  
  
-   Verwenden der `Let` -Klausel, um eine Iterationsvariable einführen, deren Wert durch einen Ausdruck statt einer Auflistung festgelegt ist.  
  
-   Verwenden der `Distinct` -Klausel, um doppelte Abfrageergebnisse ignoriert.  
  
-   Identifiziert DQS Teile des Ergebnisses zurückzugebenden mithilfe der `Skip`, `Take`, `Skip While`, und `Take While` Klauseln.  
  
## <a name="example"></a>Beispiel  
 Die folgende Abfrage Ausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `cust` für jede `Customer` Objekt in der `customers` Auflistung. Die `Where` -Klausel verwendet die Bereichsvariable, um die Ausgabe auf Kunden aus den angegebenen Bereich zu beschränken. Die `For Each` Schleife der Firmenname für jeden Kunden in den Abfrageergebnissen angezeigt.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Distinct-Klausel](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [Join-Klausel](../../../visual-basic/language-reference/queries/join-clause.md)  
 [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Let-Klausel](../../../visual-basic/language-reference/queries/let-clause.md)  
 [Skip-Klausel](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take-Klausel](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md)
