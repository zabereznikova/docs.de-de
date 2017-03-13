---
title: "Distinct Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryDistinct"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Distinct clause"
  - "Distinct statement"
  - "queries [Visual Basic], Distinct"
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Distinct Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Schränkt die Werte der aktuellen Bereichsvariable ein, um doppelte Werte in nachfolgenden Abfrageklauseln auszuschließen.  
  
## Syntax  
  
```  
Distinct  
```  
  
## Hinweise  
 Die `Distinct`\-Klausel kann verwendet werden, um eine Liste eindeutiger Elemente zurückzugeben.  Die `Distinct`\-Klausel veranlasst, dass bei der Abfrage doppelte Abfrageergebnisse ignoriert werden.  Die `Distinct`\-Klausel gilt für doppelte Werte aller von der `Select`\-Klausel angegebenen Rückgabefelder.  Wenn keine `Select`\-Klausel angegeben ist, hat die `Distinct`\-Klausel für die Bereichsvariable der Abfrage Gültigkeit, die in der `From`\-Klausel angegeben ist.  Falls die Bereichsvariable ein veränderlicher Typ ist, wird die Abfrage ein Abfrageergebnis nur ignorieren, wenn alle Mitglieder des Typs dem vorhandenen Abfrageergebnis entsprechen.  
  
## Beispiel  
 Der folgende Abfrageausdruck verknüpft eine Liste von Kunden mit einer Liste von Kundenbestellungen.  Die `Distinct`\-Klausel wird angegeben, um eine Liste von eindeutigen Kundennamen und Bestelldaten zurückzugeben.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)