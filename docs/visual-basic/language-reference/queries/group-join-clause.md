---
title: "Group Join Clause (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.QueryGroupJoinIn"
  - "vb.QueryGroupJoinOn"
  - "vb.QueryGroupJoin"
  - "vb.QueryGroupJoinInto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Group Join clause"
  - "Group Join statement"
  - "queries [Visual Basic], Group Join"
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Group Join Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Fasst zwei Auflistungen zu einer einzelnen hierarchischen Auflistung zusammen.  Die Joinoperation beruht auf übereinstimmenden Schlüsseln.  
  
## Syntax  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`element`|Erforderlich.  Die Steuerelementvariable für die zu verknüpfende Auflistung.|  
|`type`|Optional.  Der Typ von `element`.  Wenn kein `type` angegeben ist, wird der Typ von `element` von `collection` abgeleitet.|  
|`collection`|Erforderlich.  Die Auflistung, die mit der Auflistung auf der linken Seite des Operators `Group Join` verknüpft werden soll.  Eine `Group Join`\-Klausel kann in einer `Join`\-Klausel oder einer anderen `Group Join`\-Klausel geschachtelt werden.|  
|`key1` `Equals` `key2`|Erforderlich.  Identifiziert Schlüssel für die zu verknüpfenden Auflistungen.  Mit dem Operator `Equals` müssen Sie Schlüssel der zu verknüpfenden Auflistungen vergleichen.  Sie können Joinbedingungen kombinieren, indem Sie mit dem Operator `And` mehrere Schlüssel identifizieren.  Der `key1`\-Parameter muss von der Auflistung auf der linken Seite des Operators `Join` stammen.  Der `key2`\-Parameter muss von der Auflistung auf der rechten Seite des Operators `Join` stammen.<br /><br /> Die in der Joinbedingung verwendeten Schlüssel können Ausdrücke sein, die mehrere Elemente der Auflistung enthalten.  Jeder Schlüsselausdruck kann jedoch nur Elemente seiner zugehörigen Auflistung enthalten.|  
|`expressionList`|Erforderlich.  Mindestens ein Ausdruck, der identifiziert, wie die Gruppen der Elemente aus der Auflistung aggregiert werden.  Verwenden Sie das `Group`\-Schlüsselwort \(`<alias> = Group`\), um einen Membernamen für die gruppierten Ergebnisse zu identifizieren.  Sie können auch Aggregatfunktionen auf die Gruppe anwenden.|  
  
## Hinweise  
 Durch die `Group Join`\-Klausel werden zwei Auflistungen auf Grundlage der übereinstimmenden Schlüsselwerte der zu verknüpfenden Auflistungen kombiniert.  Die entstehende Auflistung kann einen Member enthalten, der auf eine Auflistung von Elementen aus der zweiten Auflistung verweist, die mit dem Schlüsselwert aus der ersten Auflistung übereinstimmen.  Sie können auch Aggregatfunktionen angeben, die auf die gruppierten Elemente aus der zweiten Auflistung angewendet werden.  Informationen über Aggregatfunktionen finden Sie unter [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Betrachten Sie beispielsweise eine Auflistung von Managern und eine Auflistung von Mitarbeitern.  Elemente aus beiden Auflistungen verfügen über eine ManagerID\-Eigenschaft, die die Mitarbeiter identifiziert, die an einen bestimmten Manager berichten.  Die Ergebnisse einer Joinoperation würden ein Ergebnis für jeden Manager und Mitarbeiter mit übereinstimmendem ManagerID\-Wert beinhalten.  Zu den Ergebnissen einer `Group Join`\-Operation würde die vollständige Liste der Manager gehören.  Das Ergebnis für jeden Manager enthielte einen Member, der auf die Liste der Mitarbeiter verweist, die mit diesem Manager übereinstimmen.  
  
 Die Auflistung, die sich aus einem `Group Join`\-Vorgang ergibt, kann jede Kombination von Werten der in der `From`\-Klausel definierten Auflistung und den Ausdrücken, die in der `Into`\-Klausel der `Group Join`\-Klausel identifiziert werden, enthalten.  Weitere Informationen zu gültigen Ausdrücken für die `Into`\-Klausel finden Sie unter [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Ein `Group Join`\-Vorgang gibt alle Ergebnisse der identifizierten Auflistung auf der linken Seite des Operators `Group Join` zurück.  Dies gilt auch, wenn es in der zu verknüpfenden Auflistung keine Übereinstimmungen gibt.  Dies entspricht einem `LEFT OUTER JOIN` in SQL.  
  
 Mit der `Join`\-Klausel können Sie mehrere Auflistungen in einer einzelnen Auflistung kombinieren.  Dies entspricht einem `INNER JOIN` in SQL.  
  
## Beispiel  
 Im folgenden Codebeispiel werden mit der `Group Join`\-Klausel zwei Auflistungen miteinander verknüpft.  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/VbSimpleQuerySamples/QuerySamples1.vb#14)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Join Clause](../../../visual-basic/language-reference/queries/join-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Group By\-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md)