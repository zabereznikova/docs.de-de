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
ms.openlocfilehash: 33680f49247b3b2a6082b3a6b27ca64f8401e42d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396180"
---
# <a name="from-clause-visual-basic"></a>From-Klausel (Visual Basic)
Gibt eine oder mehrere Bereichs Variablen und eine abzufragende Auflistung an.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich. Eine *Bereichs Variable* , die verwendet wird, um die Elemente der Auflistung zu durchlaufen. Eine Bereichs Variable wird verwendet, um auf die einzelnen Member von zu verweisen, `collection` während die Abfrage durchläuft `collection` . Muss ein Aufzähl Bare-Typ sein.|  
|`type`|Optional. Der `element`-Typ. Wenn kein `type` angegeben wird, wird der Typ von `element` aus abgeleitet `collection` .|  
|`collection`|Erforderlich. Verweist auf die Auflistung, die abgefragt werden soll. Muss ein Aufzähl Bare-Typ sein.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die `From` -Klausel wird verwendet, um die Quelldaten für eine Abfrage und die Variablen zu identifizieren, die verwendet werden, um auf ein Element aus der Quell Auflistung zu verweisen. Diese Variablen werden als *Bereichs Variablen*bezeichnet. Die- `From` Klausel ist für eine Abfrage erforderlich, außer wenn die- `Aggregate` Klausel verwendet wird, um eine Abfrage zu identifizieren, die nur aggregierte Ergebnisse zurückgibt. Weitere Informationen finden Sie unter [Aggregate-Klausel](aggregate-clause.md).  
  
 Sie können mehrere `From` Klauseln in einer Abfrage angeben, um mehrere Sammlungen zu identifizieren, die verknüpft werden sollen. Wenn mehrere Sammlungen angegeben werden, werden Sie unabhängig voneinander durchlaufen, oder Sie können Sie verknüpfen, wenn Sie verknüpft sind. Sie können Auflistungen implizit mithilfe der- `Select` Klausel oder explizit mithilfe der- `Join` oder- `Group Join` Klauseln verknüpfen. Als Alternative können Sie mehrere Bereichs Variablen und Auflistungen in einer einzelnen `From` Klausel angeben, wobei jede verknüpfte Bereichs Variable und Auflistung durch ein Komma von den anderen getrennt getrennt werden. Das folgende Codebeispiel zeigt beide Syntax Optionen für die- `From` Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 Die- `From` Klausel definiert den Gültigkeitsbereich einer Abfrage, die dem Gültigkeitsbereich einer- `For` Schleife ähnelt. Daher muss jede `element` Bereichs Variable im Gültigkeitsbereich einer Abfrage einen eindeutigen Namen aufweisen. Da Sie mehrere `From` Klauseln für eine Abfrage angeben können, können nachfolgende `From` Klauseln auf Bereichs Variablen in der- `From` Klausel verweisen, oder Sie können in einer vorherigen Klausel auf Bereichs Variablen verweisen `From` . Das folgende Beispiel zeigt beispielsweise eine-Klausel, in der die-Auflistung `From` in der zweiten-Klausel auf eine Eigenschaft der Bereichs Variablen in der ersten Klausel basiert.  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 `From`Auf jede Klausel kann eine beliebige Kombination zusätzlicher Abfrage Klauseln folgen, um die Abfrage zu verfeinern. Es gibt folgende Möglichkeiten, um die Abfrage zu verfeinern:  
  
- Kombinieren Sie mehrere Auflistungen implizit mithilfe der `From` -Klausel und der- `Select` Klausel oder explizit mit der- `Join` oder- `Group Join` Klausel.  
  
- Verwenden Sie die- `Where` Klausel, um das Abfrageergebnis zu filtern.  
  
- Sortieren Sie das Ergebnis mithilfe der- `Order By` Klausel.  
  
- Gruppieren Sie ähnliche Ergebnisse mit der- `Group By` Klausel.  
  
- Verwenden Sie die- `Aggregate` Klausel, um Aggregatfunktionen zu identifizieren, die für das gesamte Abfrageergebnis ausgewertet werden sollen.  
  
- Verwenden Sie die- `Let` Klausel, um eine Iterations Variable einzuführen, deren Wert durch einen Ausdruck anstelle einer Auflistung bestimmt wird.  
  
- Verwenden Sie die- `Distinct` Klausel, um doppelte Abfrageergebnisse zu ignorieren.  
  
- Identifizieren Sie mithilfe der `Skip` `Take` Klauseln,, und Teile des Ergebnisses, das zurückgegeben werden soll `Skip While` `Take While` .  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrage Ausdruck verwendet eine- `From` Klausel, um eine Bereichs Variable `cust` für jedes `Customer` Objekt in der Auflistung zu deklarieren `customers` . Die- `Where` Klausel verwendet die Range-Variable, um die Ausgabe auf Kunden aus dem angegebenen Bereich zu beschränken. In der- `For Each` Schleife wird der Firmenname für jeden Kunden im Abfrageergebnis angezeigt.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfragen](index.md)
- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [For Each...Next-Anweisung](../statements/for-each-next-statement.md)
- [For...Next-Anweisung](../statements/for-next-statement.md)
- [SELECT-Klausel](select-clause.md)
- [WHERE-Klausel](where-clause.md)
- [Aggregate Clause](aggregate-clause.md)
- [Distinct-Klausel](distinct-clause.md)
- [Join-Klausel](join-clause.md)
- [Group Join-Klausel](group-join-clause.md)
- [Order By-Klausel](order-by-clause.md)
- [Let-Klausel](let-clause.md)
- [Skip-Klausel](skip-clause.md)
- [Take-Klausel](take-clause.md)
- [SkipWhile-Klausel](skip-while-clause.md)
- [TakeWhile-Klausel](take-while-clause.md)
