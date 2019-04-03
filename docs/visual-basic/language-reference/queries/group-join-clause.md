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
ms.openlocfilehash: 3da4ca2db299a65b2c0f1fa259bbaabe4f53aa33
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821958"
---
# <a name="group-join-clause-visual-basic"></a>Group Join-Klausel (Visual Basic)
Fasst zwei Auflistungen zu einer einzelnen hierarchischen Auflistung zusammen. Die Join-Operation wird auf Grundlage übereinstimmender Schlüssel.  
  
## <a name="syntax"></a>Syntax  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich. Die Steuerelementvariable für die Sammlung verknüpft wird.|  
|`type`|Dies ist optional. Der `element`-Typ. Wenn kein `type` angegeben ist, den Typ des `element` von hergeleitet `collection`.|  
|`collection`|Erforderlich. Die Auflistung, die mit der Auflistung, die auf der linken Seite des ist der `Group Join` Operator. Ein `Group Join` Klausel kann geschachtelt werden, einem `Join` Klausel oder in einem anderen `Group Join` Klausel.|  
|`key1` `Equals` `key2`|Erforderlich. Bezeichnet die Schlüssel für die Auflistungen verknüpft wird. Verwenden Sie die `Equals` Operator zum Vergleichen von Schlüsseln aus den zu verknüpfenden Auflistungen. Sie können den Join-Bedingungen kombinieren, mit der `And` Operator, um mehrere Schlüssel zu identifizieren. Die `key1` -Parameter muss aus der Auflistung auf der linken Seite des sein, dass die `Join` Operator. Die `key2` -Parameter muss aus der Auflistung auf der rechten Seite des sein, dass die `Join` Operator.<br /><br /> Die Schlüssel für die Join-Bedingung können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten. Jedes Schlüssel-Ausdrucks kann jedoch nur die Elemente aus der entsprechenden Auflistung enthalten.|  
|`expressionList`|Erforderlich. Eine oder mehrere Ausdrücke, die identifizieren, wie die Gruppen von Elementen aus der Auflistung aggregiert werden. Um einen Elementnamen für die gruppierten Ergebnisse zu identifizieren, verwenden Sie die `Group` Schlüsselwort (`<alias> = Group`). Sie können auch Aggregatfunktionen einschließen, die auf die Gruppe angewendet werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Group Join` Klausel Fasst zwei Auflistungen, die basierend auf übereinstimmenden Werte aus den zu verknüpfenden Auflistungen zusammen. Die resultierende Auflistung kann es sich um ein Element enthalten, die verweist auf eine Auflistung von Elementen aus der zweiten Auflistung, die den Schlüsselwert aus der ersten Auflistung entsprechen. Sie können auch Aggregatfunktionen für die die gruppierten Elemente aus der zweiten Auflistung angeben. Weitere Informationen zu Aggregatfunktionen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Betrachten Sie z. B. eine Auflistung von Managern und einer Auflistung von Mitarbeitern. Elemente aus beiden Auflistungen müssen eine ManagerID-Eigenschaft, die die Mitarbeiter identifiziert, die einen bestimmten Manager Bericht erstatten. Die Ergebnisse einer Join-Operation würde es sich um ein Ergebnis für jeden Manager und Mitarbeiter mit einem übereinstimmenden ManagerID-Wert enthalten. Die Ergebnisse aus einer `Group Join` Vorgang würde die vollständige Liste der Manager enthalten. Jedes Ergebnis Manager müsste ein Element, das die Liste der Mitarbeiter auf die verwiesen wird, die eine Übereinstimmung für den bestimmten Manager waren.  
  
 Der Auflistung, die durch eine `Group Join` Vorgang darf eine beliebige Kombination von Werten aus der Auflistung identifiziert, die der `From` -Klausel und die Ausdrücke in identifiziert die `Into` -Klausel der `Group Join` Klausel. Weitere Informationen zu gültigen Ausdrücken für die `Into` -Klausel finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Ein `Group Join` Vorgang werden alle Ergebnisse zurückgeben, aus der Auflistung, die auf der linken Seite des identifiziert die `Group Join` Operator. Dies gilt auch, wenn keine Übereinstimmungen in der Auflistung, die zu verknüpfenden vorhanden sind. Dies ist z. B. eine `LEFT OUTER JOIN` in SQL.  
  
 Sie können die `Join` -Klausel, um Auflistungen in einer einzelnen Auflistung zu kombinieren. Dies ist äquivalent zu einer `INNER JOIN` in SQL.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird joins von zwei Auflistungen mithilfe der `Group Join` Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Join-Klausel](../../../visual-basic/language-reference/queries/join-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
- [Group By-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md)
