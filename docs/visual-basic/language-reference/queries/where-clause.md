---
title: "Where Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryWhere"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Where statement"
  - "queries [Visual Basic], Where"
  - "Where clause"
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Where Clause (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt die Filterbedingung für eine Abfrage an.  
  
## Syntax  
  
```  
Where condition  
```  
  
## Teile  
 `condition`  
 Erforderlich.  Ein Ausdruck, mit dem ermittelt wird, ob die Werte des aktuellen Elements der Auflistung in die Ausgabeauflistung aufgenommen werden.  Der Ausdruck muss sich zu einem `Boolean`\-Wert oder dem Äquivalent eines `Boolean`\-Werts evaluieren lassen.  Wenn die Bedingung `True` ergibt, wird das Element in das Abfrageergebnis aufgenommen, andernfalls nicht.  
  
## Hinweise  
 Mit der `Where`\-Klausel können Sie Abfragedaten filtern, indem nur die Elemente ausgewählt werden, die bestimmte Kriterien erfüllen.  Elemente, durch deren Werte die `Where`\-Klausel `True` ergibt, werden in das Abfrageergebnis aufgenommen, alle andere Elemente nicht.  Der Ausdruck, der in einer `Where`\-Klausel verwendet wird, muss sich zu einem `Boolean` oder dem Äquivalent eines `Boolean` evaluieren lassen, z. B. zu einem Integer\-Wert, der `False` ergibt, wenn der Wert 0 \(null\) ist.  Sie können in einer `Where`\-Klausel mehrere Ausdrücke mithilfe von logischen Operatoren wie `And`, `Or`, `AndAlso`, `OrElse`, `Is` und `IsNot` kombinieren.  
  
 Standardmäßig werden Abfrageausdrücke nicht evaluiert, bis auf sie zugegriffen wird, beispielsweise wenn sie datengebunden sind oder in einer `For`\-Schleife durchlaufen werden.  Deshalb wird die `Where`\-Klausel erst ausgewertet, wenn auf die Abfrage zugegriffen wird.  Wenn Sie über Werte verfügen, die für die Abfrage extern sind und die in der `Where`\-Klausel verwendet werden, stellen Sie sicher, dass die entsprechenden Werte zum Zeitpunkt der Ausführung der Abfrage in der `Where`\-Klausel verwendet werden.  Weitere Informationen zur Abfrageausführung finden Sie unter [Schreiben der ersten LINQ\-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 In einer `Where`\-Klausel können Sie Funktionen aufrufen, um für einen Wert des aktuellen Elements der Auflistung eine Berechnung oder Operation durchzuführen.  Durch das Aufrufen einer Funktion in einer `Where`\-Klausel wird die Abfrage möglicherweise unmittelbar bei der Definition und nicht erst beim Zugriff ausgeführt.  Weitere Informationen zur Abfrageausführung finden Sie unter [Schreiben der ersten LINQ\-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## Beispiel  
 Der folgende Abfrageausdruck verwendet eine `From`\-Klausel zum Deklarieren einer Bereichsvariablen `cust` für jedes `Customer`\-Objekt in der `customers`\-Auflistung.  Die `Where`\-Klausel verwendet die Bereichsvariable, um die Ausgabe auf Kunden aus der angegebenen Region einzuschränken.  Die `For Each`\-Schleife zeigt den Namen des Unternehmens für jeden Kunden im Abfrageergebnis an.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird `And` und `Or` logische Operatoren in der `Where`\-Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [For Each...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)