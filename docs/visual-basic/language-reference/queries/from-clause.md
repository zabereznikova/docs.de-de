---
title: "From Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryFrom"
  - "vb.QueryFromIn"
  - "vb.QueryFromLet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], From"
  - "From clause"
  - "From statement"
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# From Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt eine oder mehrere Bereichsvariablen und eine abzufragende Auflistung an.  
  
## Syntax  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`element`|Erforderlich.  Eine *Bereichsvariable*, die zum Durchlaufen der Elemente der Auflistung verwendet wird.  Eine Bereichsvariable wird verwendet, um auf jedes Member der `collection` zu verweisen, während die Abfrage die `collection` durchläuft.  Sie muss einen Enumerable\-Typ haben.|  
|`type`|Optional.  Der Typ von `element`.  Wenn kein `type` angegeben ist, wird der Typ von `element` von `collection` abgeleitet.|  
|`collection`|Erforderlich.  Verweist auf die Auflistung, die abgefragt werden soll.  Sie muss einen Enumerable\-Typ haben.|  
  
## Hinweise  
 Die `From`\-Klausel wird verwendet, um die Quelldaten einer Abfrage und die Variablen, die auf ein Element der Quellauflistung verweisen, anzugeben.  Diese Variablen werden als *Bereichsvariablen* bezeichnet.  Die `From`\-Klausel ist für eine Abfrage notwendig. Davon ausgenommen sind Abfragen, bei denen durch Verwendung der `Aggregate`\-Klausel angezeigt wird, dass nur aggregierte Ergebnisse zurückgegeben werden.  Weitere Informationen finden Sie unter [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 In einer Abfrage können mehrere `From`\-Klauseln angegeben werden, um anzugeben, dass mehrere Auflistungen verknüpft werden sollen.  Wenn mehrere Auflistungen angegeben werden, werden sie unabhängig voneinander durchlaufen. Verwandte Auflistungen können auch verknüpft werden.  Auflistungen können mit der `Select`\-Klausel implizit und mit der `Join`\-Klausel oder der `Group Join`\-Klausel explizit verknüpft werden.  Ebenso können mehrere Bereichsvariablen und Auflistungen in einer einzigen `From`\-Klausel angegeben werden, indem jede verknüpfte Bereichsvariable und Auflistung von den anderen durch ein Komma getrennt wird.  Im folgenden Codebeispiel werden beide Syntaxoptionen für die `From`\-Klausel dargestellt.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 Die `From`\-Klausel definiert den Gültigkeitsbereich einer Abfrage. Dieser ähnelt dem Gültigkeitsbereich einer `For`\-Schleife.  Daher muss jede `element`\-Bereichsvariable im Gültigkeitsbereich einer Abfrage einen eindeutigen Namen haben.  Da mehrere `From`\-Klauseln für eine Abfrage angegeben werden können, können nachfolgende `From`\-Klauseln auf Bereichsvariablen in der `From`\-Klausel oder auf Bereichsvariablen einer vorhergehenden `From`\-Klausel verweisen.  Im folgenden Beispiel wird eine geschachtelte `From`\-Klausel gezeigt, in der die Auflistung in der zweiten Klausel auf einer Eigenschaft der Bereichsvariablen in der ersten Klausel basiert.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 Jeder `From`\-Klausel kann eine beliebige Kombination weiterer Abfrageklauseln folgen, um die Abfrage zu verfeinern.  Die Abfrage kann folgendermaßen verfeinert werden:  
  
-   Kombination mehrerer Auflistungen: implizit mit `From`\-Klauseln und `Select`\-Klauseln oder explizit mit `Join`\-Klauseln oder `Group Join`\-Klauseln.  
  
-   Verwendung der `Where`\-Klausel zum Filtern des Abfrageergebnisses.  
  
-   Sortieren des Ergebnisses mit der `Order By`\-Klausel.  
  
-   Gruppieren ähnlicher Ergebnisse mit der `Group By`\-Klausel.  
  
-   Verwendung der `Aggregate`\-Klausel, um Aggregatfunktionen festzulegen, die für das gesamte Abfrageergebnis ausgewertet werden sollen.  
  
-   Verwendung der `Let`\-Klausel zur Einführung einer Iterationsvariable, deren Wert durch einen Ausdruck statt durch eine Auflistung festgelegt wird.  
  
-   Verwendung der `Distinct`\-Klausel zum Übergehen doppelter Abfrageergebnisse.  
  
-   Verwendung der Klauseln `Skip`, `Take`, `Skip While` und `Take While` zur Festlegung von Teilen des Ergebnisses, die zurückgegeben werden sollen.  
  
## Beispiel  
 Der folgende Abfrageausdruck verwendet eine `From`\-Klausel zum Deklarieren einer Bereichsvariablen `cust` für jedes `Customer`\-Objekt in der `customers`\-Auflistung.  Die `Where`\-Klausel verwendet die Bereichsvariable, um die Ausgabe auf Kunden aus der angegebenen Region einzuschränken.  Die `For Each`\-Schleife zeigt den Namen des Unternehmens für jeden Kunden im Abfrageergebnis an.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## Siehe auch  
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [For Each...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Distinct Clause](../../../visual-basic/language-reference/queries/distinct-clause.md)   
 [Join Clause](../../../visual-basic/language-reference/queries/join-clause.md)   
 [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Let Clause](../../../visual-basic/language-reference/queries/let-clause.md)   
 [Skip Clause](../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Take Clause](../../../visual-basic/language-reference/queries/take-clause.md)   
 [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md)