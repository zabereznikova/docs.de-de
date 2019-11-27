---
title: Group Join-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: 0546c86322663ce6c56a89e63311d0f02f88cfe4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346841"
---
# <a name="group-join-clause-visual-basic"></a>Group Join-Klausel (Visual Basic)
Fasst zwei Auflistungen zu einer einzelnen hierarchischen Auflistung zusammen. Der Joinvorgang basiert auf übereinstimmenden Schlüsseln.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich Die Steuerelement Variable für die Auflistung, die verknüpft wird.|  
|`type`|Optional. Der `element`-Typ. Wenn keine `type` angegeben wird, wird der Typ der `element` von `collection`abgeleitet.|  
|`collection`|Erforderlich Die Auflistung, die mit der Auflistung auf der linken Seite des `Group Join` Operators kombiniert werden soll. Eine `Group Join`-Klausel kann in einer `Join`-Klausel oder in einer anderen `Group Join`-Klausel eingefügt werden.|  
|`key1` `Equals` `key2`|Erforderlich Identifiziert Schlüssel für die Auflistungen, die verknüpft werden. Sie müssen den `Equals`-Operator verwenden, um Schlüssel aus den Auflistungen zu vergleichen, die verknüpft werden. Joinbedingungen können mithilfe des `And`-Operators kombiniert werden, um mehrere Schlüssel zu identifizieren. Der `key1`-Parameter muss von der Auflistung auf der linken Seite des `Join` Operators sein. Der `key2`-Parameter muss von der Auflistung auf der rechten Seite des `Join` Operators sein.<br /><br /> Die in der Join-Bedingung verwendeten Schlüssel können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten. Jeder Schlüssel Ausdruck kann jedoch nur Elemente aus der jeweiligen Auflistung enthalten.|  
|`expressionList`|Erforderlich Ein oder mehrere Ausdrücke, die bestimmen, wie die Gruppen von Elementen aus der Auflistung aggregiert werden. Um einen Elementnamen für die gruppierten Ergebnisse zu identifizieren, verwenden Sie das `Group`-Schlüsselwort (`<alias> = Group`). Sie können auch Aggregatfunktionen einschließen, die auf die Gruppe angewendet werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Group Join`-Klausel kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten aus den verbundenen Sammlungen. Die resultierende Auflistung kann einen Member enthalten, der auf eine Auflistung von Elementen aus der zweiten Auflistung verweist, die mit dem Schlüsselwert aus der ersten Auflistung zu vergleichen sind. Sie können auch Aggregatfunktionen angeben, die auf die gruppierten Elemente aus der zweiten Auflistung angewendet werden sollen. Weitere Informationen zu Aggregatfunktionen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Stellen Sie sich z. b. eine Sammlung von Managern und eine Sammlung von Mitarbeitern vor. Elemente aus beiden Auflistungen verfügen über eine ManagerID-Eigenschaft, die die Mitarbeiter identifiziert, die einem bestimmten Manager Berichten. Die Ergebnisse einer Join-Operation enthalten ein Ergebnis für jeden Vorgesetzten und jeden Mitarbeiter mit einem entsprechenden ManagerID-Wert. Die Ergebnisse eines `Group Join` Vorgangs enthalten die komplette Liste der Manager. Jedes Manager-Ergebnis hätte einen Member, der auf die Liste der Mitarbeiter verwiesen hat, die für den jeweiligen Vorgesetzten eine Entsprechung aufweisen.  
  
 Die aus einem `Group Join` Vorgang resultierende Auflistung kann eine beliebige Kombination von Werten aus der in der `From`-Klausel identifizierten Auflistung und die in der `Into`-Klausel der `Group Join`-Klausel identifizierten Ausdrücke enthalten. Weitere Informationen zu gültigen Ausdrücken für die `Into`-Klausel finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Ein `Group Join` Vorgang gibt alle Ergebnisse aus der Auflistung zurück, die auf der linken Seite des `Group Join` Operators identifiziert werden. Dies gilt auch, wenn in der Auflistung keine Übereinstimmungen vorhanden sind. Dies ist wie eine `LEFT OUTER JOIN` in SQL.  
  
 Sie können die `Join`-Klausel verwenden, um Auflistungen in einer einzelnen Auflistung zu kombinieren. Dies entspricht einer `INNER JOIN` in SQL.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der `Group Join`-Klausel miteinander verbunden.  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Join-Klausel](../../../visual-basic/language-reference/queries/join-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
- [Group By-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md)
