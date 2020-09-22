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
ms.openlocfilehash: 8d5f3ec80cb39825a3a283907d614b9be28e6e91
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869912"
---
# <a name="group-join-clause-visual-basic"></a>Group Join-Klausel (Visual Basic)

Fasst zwei Auflistungen zu einer einzelnen hierarchischen Auflistung zusammen. Der Joinvorgang basiert auf übereinstimmenden Schlüsseln.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich. Die Steuerelement Variable für die Auflistung, die verknüpft wird.|  
|`type`|Dies ist optional. Der `element`-Typ. Wenn kein `type` angegeben wird, wird der Typ von `element` aus abgeleitet `collection` .|  
|`collection`|Erforderlich. Die Auflistung, die mit der Auflistung auf der linken Seite des Operators kombiniert werden soll `Group Join` . Eine- `Group Join` Klausel kann in einer- `Join` Klausel oder in einer anderen-Klausel eingefügt werden `Group Join` .|  
|`key1` `Equals` `key2`|Erforderlich. Identifiziert Schlüssel für die Auflistungen, die verknüpft werden. Sie müssen den- `Equals` Operator verwenden, um Schlüssel aus den verbundenen Sammlungen zu vergleichen. Joinbedingungen können mithilfe des-Operators kombiniert werden `And` , um mehrere Schlüssel zu identifizieren. Der- `key1` Parameter muss sich auf der linken Seite des Operators aus der Auflistung befinden `Join` . Der- `key2` Parameter muss sich auf der rechten Seite des-Operators aus der Auflistung befinden `Join` .<br /><br /> Die in der Join-Bedingung verwendeten Schlüssel können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten. Jeder Schlüssel Ausdruck kann jedoch nur Elemente aus der jeweiligen Auflistung enthalten.|  
|`expressionList`|Erforderlich. Ein oder mehrere Ausdrücke, die bestimmen, wie die Gruppen von Elementen aus der Auflistung aggregiert werden. Um einen Elementnamen für die gruppierten Ergebnisse zu identifizieren, verwenden Sie das- `Group` Schlüsselwort ( `<alias> = Group` ). Sie können auch Aggregatfunktionen einschließen, die auf die Gruppe angewendet werden sollen.|  
  
## <a name="remarks"></a>Bemerkungen  

 Die- `Group Join` Klausel kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten aus den verbundenen Sammlungen. Die resultierende Auflistung kann einen Member enthalten, der auf eine Auflistung von Elementen aus der zweiten Auflistung verweist, die mit dem Schlüsselwert aus der ersten Auflistung zu vergleichen sind. Sie können auch Aggregatfunktionen angeben, die auf die gruppierten Elemente aus der zweiten Auflistung angewendet werden sollen. Weitere Informationen zu Aggregatfunktionen finden Sie unter [Aggregate-Klausel](aggregate-clause.md).  
  
 Stellen Sie sich z. b. eine Sammlung von Managern und eine Sammlung von Mitarbeitern vor. Elemente aus beiden Auflistungen verfügen über eine ManagerID-Eigenschaft, die die Mitarbeiter identifiziert, die einem bestimmten Manager Berichten. Die Ergebnisse einer Join-Operation enthalten ein Ergebnis für jeden Vorgesetzten und jeden Mitarbeiter mit einem entsprechenden ManagerID-Wert. Die Ergebnisse eines- `Group Join` Vorgangs enthalten die komplette Liste der Manager. Jedes Manager-Ergebnis hätte einen Member, der auf die Liste der Mitarbeiter verwiesen hat, die für den jeweiligen Vorgesetzten eine Entsprechung aufweisen.  
  
 Die aus einem-Vorgang resultierende Auflistung `Group Join` kann eine beliebige Kombination von Werten aus der in der-Klausel identifizierten Auflistung `From` und den Ausdrücken enthalten, die in der-Klausel der-Klausel identifiziert werden `Into` `Group Join` . Weitere Informationen zu gültigen Ausdrücken für die- `Into` Klausel finden Sie unter [Aggregate-Klausel](aggregate-clause.md).  
  
 Ein- `Group Join` Vorgang gibt alle Ergebnisse aus der Auflistung zurück, die auf der linken Seite des Operators identifiziert werden `Group Join` . Dies gilt auch, wenn in der Auflistung keine Übereinstimmungen vorhanden sind. Dies ist wie ein `LEFT OUTER JOIN` in SQL.  
  
 Sie können die- `Join` Klausel verwenden, um Auflistungen in einer einzelnen Auflistung zu kombinieren. Dies entspricht einem `INNER JOIN` in SQL.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der-Klausel miteinander verbunden `Group Join` .  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [SELECT-Klausel](select-clause.md)
- [From-Klausel](from-clause.md)
- [Join-Klausel](join-clause.md)
- [WHERE-Klausel](where-clause.md)
- [Group By-Klausel](group-by-clause.md)
