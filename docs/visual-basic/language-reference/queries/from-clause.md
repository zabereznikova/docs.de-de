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
ms.openlocfilehash: 71573de48cc51c48291fc4b82a0628d2d0f96caa
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556808"
---
# <a name="from-clause-visual-basic"></a>From-Klausel (Visual Basic)
Gibt einen oder mehrere Bereichsvariable und eine Abfragesammlung an.  
  
## <a name="syntax"></a>Syntax  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich. Ein *Bereichsvariable* verwendet, um das Durchlaufen der Elemente der Auflistung. Eine Bereichsvariable wird verwendet, um auf jedes Element finden Sie unter den `collection` wie die Abfrage durchläuft die `collection`. Muss es sich um ein aufzählbarer Typ sein.|  
|`type`|Dies ist optional. Der `element`-Typ. Wenn kein `type` angegeben ist, den Typ des `element` von hergeleitet `collection`.|  
|`collection`|Erforderlich. Bezieht sich auf die Auflistung, die abgefragt werden. Muss es sich um ein aufzählbarer Typ sein.|  
  
## <a name="remarks"></a>Hinweise  
 Die `From` -Klausel wird verwendet, identifizieren Sie die Quelldaten für eine Abfrage und die Variablen, die zum Verweisen auf ein Element aus der Auflistung verwendet werden. Diese Variablen heißen *Bereichsvariablen*. Die `From` -Klausel ist erforderlich für eine Abfrage, außer wenn die `Aggregate` -Klausel wird verwendet, um eine Abfrage zu identifizieren, dass gibt nur die Ergebnisse aggregiert. Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Sie können angeben, dass mehrere `From` Klauseln in einer Abfrage zum Identifizieren von mehreren Sammlungen verknüpft werden sollen. Wenn mehrere Sammlungen angegeben werden, sie einzeln durchlaufen werden, oder Sie können diese verknüpfen, wenn diese verknüpft sind. Sie können Sammlungen implizit verknüpfen, indem die `Select` -Klausel, oder explizit durch Verwenden der `Join` oder `Group Join` Klauseln. Als Alternative können Sie mehrere Bereichsvariablen und Sammlungen angeben, in einem einzelnen `From` -Klausel, wobei alle entsprechenden Range-Variable und Sammlungen, die durch ein Komma voneinander getrennt. Im folgenden Codebeispiel wird veranschaulicht, beide Optionen zur Abfragesyntax für die `From` Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 Die `From` -Klausel definiert den Bereich einer Abfrage, der in den Bereich der ähnelt einem `For` Schleife. Aus diesem Grund jede `element` Bereichsvariablen im Bereich einer Abfrage muss einen eindeutigen Namen haben. Da es sich bei Angabe mehrerer `From` Klauseln für eine Abfrage, die nachfolgenden `From` Klauseln können Bereichsvariablen in finden Sie unter den `From` -Klausel, oder sie können auf Bereichsvariablen in einem vorherigen verweisen `From` Klausel. Das folgende Beispiel zeigt z. B. eine geschachtelte `From` Klausel, in die Auflistung in der zweiten Klausel auf eine Eigenschaft der Bereichsvariablen in der ersten Klausel basiert.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 Jede `From` Klausel kann eine beliebige Kombination von zusätzliche Abfrageklauseln, um die Abfrage zu verfeinern folgen. Sie können die Abfrage optimieren, es gibt folgende Möglichkeiten:  
  
-   Kombinieren Sie mehrere Sammlungen implizit mithilfe der `From` und `Select` -Klauseln, oder explizit durch Verwenden der `Join` oder `Group Join` Klauseln.  
  
-   Verwenden der `Where` -Klausel, um das Abfrageergebnis zu filtern.  
  
-   Sortieren des Ergebnisses mithilfe der `Order By` Klausel.  
  
-   Gruppieren ähnliche Ergebnisse mithilfe der `Group By` Klausel.  
  
-   Verwenden der `Aggregate` -Klausel, um Aggregatfunktionen für das Ergebnis für die gesamte Abfrage ausgewertet werden sollen.  
  
-   Verwenden der `Let` -Klausel, um eine Iterationsvariable eingeführt, deren Wert durch einen Ausdruck anstatt einer Sammlung festgelegt wird.  
  
-   Verwenden der `Distinct` -Klausel, um doppelte Abfrageergebnisse ignoriert.  
  
-   Identifizieren Sie Teile des Ergebnisses zurückgegeben mit der `Skip`, `Take`, `Skip While`, und `Take While` Klauseln.  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrageausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `cust` für jede `Customer` -Objekt in der `customers` Auflistung. Die `Where` -Klausel verwendet die Bereichsvariable, um die Ausgabe auf Kunden aus den angegebenen Bereich zu beschränken. Die `For Each` -Schleife zeigt den Firmennamen für jeden Kunden in den Abfrageergebnissen.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragen](../../../visual-basic/language-reference/queries/index.md)  
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
