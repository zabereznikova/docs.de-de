---
title: "Join Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryJoinIn"
  - "vb.QueryJoin"
  - "vb.QueryJoinOn"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], Join"
  - "Join statement"
  - "Join clause"
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Join Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen.  Die Joinoperation basiert auf übereinstimmenden Schlüsseln und verwendet den Operator `Equals`.  
  
## Syntax  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## Teile  
 `element`  
 Erforderlich.  Die Steuerelementvariable für die zu verknüpfende Auflistung.  
  
 `collection`  
 Erforderlich.  Die Auflistung, die mit der Auflistung auf der linken Seite des Operators `Join` verknüpft werden soll.  Eine `Join`\-Klausel kann in einer weiteren `Join`\-Klausel oder einer `Group Join`\-Klausel geschachtelt werden.  
  
 `joinClause`  
 Dies ist optional.  Eine oder mehrere zusätzliche `Join`\-Klauseln, um die Abfrage weiter zu verfeinern.  
  
 `groupJoinClause`  
 Dies ist optional.  Eine oder mehrere zusätzliche `Group Join`\-Klauseln, um die Abfrage weiter zu verfeinern.  
  
 `key1` `Equals` `key2`  
 Erforderlich.  Identifiziert Schlüssel für die zu verknüpfenden Auflistungen.  Mit dem Operator `Equals` müssen Sie Schlüssel der zu verknüpfenden Auflistungen vergleichen.  Sie können Joinbedingungen kombinieren, indem Sie mit dem Operator `And` mehrere Schlüssel identifizieren.  `key1` muss aus der Auflistung auf der linken Seite des Operators `Join` stammen.  `key2` muss aus der Auflistung auf der rechten Seite des Operators `Join` stammen.  
  
 Die in der Joinbedingung verwendeten Schlüssel können Ausdrücke sein, die mehrere Elemente der Auflistung enthalten.  Jeder Schlüsselausdruck kann jedoch nur Elemente seiner zugehörigen Auflistung enthalten.  
  
## Hinweise  
 Durch die `Join`\-Klausel werden zwei Auflistungen auf Grundlage der übereinstimmenden Schlüsselwerte der zu verknüpfenden Auflistungen kombiniert.  Die entstehende Auflistung kann jede Kombination von Werten aus der auf der linken Seite des Operators `Join` angegebenen Auflistung und der in der `Join`\-Klausel angegebenen Auflistung enthalten.  Die Abfrage gibt nur Ergebnisse zurück, die die vom Operator `Equals` angegebene Bedingung erfüllen.  Dies entspricht einem `INNER JOIN` in SQL.  
  
 In einer Abfrage können mehrere `Join`\-Klauseln verwendet werden, um zwei oder mehrere Auflistungen zu einer einzelnen Auflistung zu verknüpfen.  
  
 Sie können einen impliziten Join ausführen, um Auflistungen ohne die `Join`\-Klausel zu kombinieren.  Nehmen Sie hierfür mehrere `In`\-Klauseln in die `From`\-Klausel auf, und geben Sie eine `Where`\-Klausel an, in der die für den Join zu verwendenden Schlüssel angegeben werden.  
  
 Mit der `Group Join`\-Klausel können Sie mehrere Auflistungen in einer einzelnen hierarchischen Auflistung kombinieren.  Dies entspricht einem `LEFT OUTER JOIN` in SQL.  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein impliziter Join ausgeführt, um eine Liste von Kunden mit ihren Bestellungen zu kombinieren.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#13)]  
  
## Beispiel  
 Im folgenden Codebeispiel werden mit der `Join`\-Klausel zwei Auflistungen miteinander verknüpft.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples2.vb#12)]  
  
 Die in diesem Beispiel erzeugte Ausgabe sieht in etwa folgendermaßen aus:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## Beispiel  
 Im folgenden Codebeispiel werden durch Verwendung der `Join`\-Klausel mit zwei Schlüsselspalten zwei Auflistungen miteinander verknüpft.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples3.vb#17)]  
  
 Die im Beispiel erzeugte Ausgabe sieht in etwa folgendermaßen aus:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)