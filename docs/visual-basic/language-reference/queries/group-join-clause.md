---
title: Group Join-Klausel (Visual Basic)
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
ms.openlocfilehash: 094281b0afb34451ae8539e4eb967043b21d379c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604756"
---
# <a name="group-join-clause-visual-basic"></a>Group Join-Klausel (Visual Basic)
Fasst zwei Auflistungen zu einer einzelnen hierarchischen Auflistung zusammen. Die Join-Vorgang basiert auf übereinstimmenden Schlüsseln.  
  
## <a name="syntax"></a>Syntax  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich. Die Steuerelementvariable für die zu verknüpfende Auflistung.|  
|`type`|Dies ist optional. Der `element`-Typ. Wenn kein `type` angegeben wird, den Typ des `element` von hergeleitet `collection`.|  
|`collection`|Erforderlich. Die Auflistung, mit der Auflistung zu kombinieren, die auf der linken Seite des ist die `Group Join` Operator. Ein `Group Join` Klausel kann geschachtelt sein, einem `Join` Klausel oder in einer anderen `Group Join` Klausel.|  
|`key1` `Equals` `key2`|Erforderlich. Identifiziert die Schlüssel für die zu verknüpfenden Auflistungen. Verwenden Sie die `Equals` Operator zum Vergleichen von Schlüsseln aus der zu verknüpfenden Auflistungen. Sie können die Join-Bedingungen kombinieren, mit der `And` Operator, um mehrere Schlüssel zu identifizieren. Die `key1` Parameter muss aus der Auflistung auf der linken Seite von der `Join` Operator. Die `key2` Parameter muss aus der Auflistung auf der rechten Seite des der `Join` Operator.<br /><br /> Die in der Joinbedingung verwendeten Schlüssel können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten. Jeder Schlüsselausdruck kann jedoch nur die Elemente aus der entsprechenden Auflistung enthalten.|  
|`expressionList`|Erforderlich. Mindestens ein Ausdruck, die angibt, wie die Gruppen von Elementen aus der Auflistung aggregiert werden. Um einen Elementnamen für die gruppierten Ergebnisse zu suchen, verwenden die `Group` Schlüsselwort (`<alias> = Group`). Sie können auch Aggregatfunktionen einschließen, die auf die Gruppe angewendet werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Group Join` Klausel Fasst zwei Auflistungen, die basierend auf übereinstimmenden Schlüsselwerten von zu verknüpfenden Auflistungen zusammen. Die resultierende Auflistung kann es sich um ein Element enthalten, die verweist auf eine Auflistung von Elementen aus der zweiten Auflistung, die den Schlüsselwert aus der ersten Auflistung entsprechen. Sie können auch Aggregatfunktionen auf die gruppierten Elemente beziehen, über die zweite Sammlung angeben. Informationen zu Aggregatfunktionen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Betrachten Sie z. B. eine Auflistung von Managern und eine Auflistung von Mitarbeitern. Elemente aus beiden Auflistungen haben eine ManagerID-Eigenschaft, die die Mitarbeiter identifiziert, die einem bestimmten Manager Berichten. Die Ergebnisse einer Join-Operation würde ein Ergebnis für jeden Manager und Mitarbeiter mit übereinstimmendem ManagerID Wert enthalten. Die Ergebnisse aus einem `Group Join` Vorgang würde eine vollständige Liste der Manager enthalten. Jedes Ergebnis Manager müsste ein Element, das die Liste der Mitarbeiter auf die verwiesen wird, die eine Übereinstimmung für den bestimmten Manager waren.  
  
 Der Auflistung, die aus einer `Group Join` Vorgang darf eine beliebige Kombination von Werten aus der Auflistung identifiziert, der `From` -Klausel und die Ausdrücke identifiziert die `Into` -Klausel der der `Group Join` Klausel. Weitere Informationen zu gültigen Ausdrücken für die `Into` -Klausel finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Ein `Group Join` Vorgang werden alle Ergebnisse zurückgegeben, aus der Auflistung, die auf der linken Seite des identifiziert die `Group Join` Operator. Dies gilt auch, wenn keine Übereinstimmungen in der zu verknüpfenden Auflistung vorhanden sind. Dies ist z. B. eine `LEFT OUTER JOIN` in SQL.  
  
 Sie können die `Join` -Klausel, um Auflistungen zu einer einzelnen Auflistung zu kombinieren. Dies ist gleichbedeutend mit einem `INNER JOIN` in SQL.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird verknüpft zwei Auflistungen mithilfe der `Group Join` Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-join-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Join-Klausel](../../../visual-basic/language-reference/queries/join-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Group By-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md)
