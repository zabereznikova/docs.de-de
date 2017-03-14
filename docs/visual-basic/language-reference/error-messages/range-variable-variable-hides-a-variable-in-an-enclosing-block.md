---
title: "Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36633"
  - "vbc36633"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36633"
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Durch den Namen einer in den Klauseln `Select`, `From`, `Aggregate` oder `Let` angegebenen Bereichsvariablen wird der Name der zuvor bereits in der Abfrage angegebenen Bereichsvariablen oder der Name einer Variablen, die implizit durch die Abfrage deklariert wird, z. B. ein Feldname oder der Name einer Aggregatfunktion, verdoppelt.  
  
 **Fehler\-ID:** BC36633  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass alle Bereichsvariablen in einem bestimmten Abfragebereich eindeutige Namen haben.  Sie können eine Abfrage in Klammern einschließen, um sicherzustellen, dass geschachtelte Abfragen einen eindeutigen Bereich haben.  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Let Clause](../../../visual-basic/language-reference/queries/let-clause.md)   
 [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)