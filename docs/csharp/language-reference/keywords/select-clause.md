---
title: "select-Klausel (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "select_CSharpKeyword"
  - "select"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "select-Klausel [C#]"
  - "select-Schlüsselwort [C#]"
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# select-Klausel (C#-Referenz)
In einem Abfrageausdruck gibt die `select`\-Klausel den Typ der Werte an, die erstellt werden, wenn die Abfrage ausgeführt wird.  Das Ergebnis basiert auf der Auswertung aller vorherigen Klauseln und auf den Ausdrücken in der `select`\-Klausel selbst.  Ein Abfrageausdruck muss entweder mit einer `select`\-Klausel oder einer [Gruppenklausel](../../../csharp/language-reference/keywords/group-clause.md) enden.  
  
 Im folgenden Beispiel wird eine einfache `select`\-Klausel in einem Abfrageausdruck veranschaulicht.  
  
 [!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/csquerykeywords/Select.cs#8)]  
  
 Der Typ der mit der `select`\-Klausel erstellten Sequenz, bestimmt den Typ der Abfragevariablen `queryHighScores`.  Im einfachsten Fall legt die `select`\-Klausel nur die Bereichsvariable fest.  Dies bewirkt, dass die zurückgegebene Sequenz Elemente des gleichen Typs wie die Datenquelle enthält.  Weitere Informationen finden Sie unter [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  Die `select`\-Klausel bietet jedoch auch einen leistungsstarken Mechanismus zum Transformieren \(oder *Projizieren*\) von Quelldaten in neue Typen.  Weitere Informationen finden Sie unter [Datentransformationen mit LINQ \(C\#\)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).  
  
## Beispiel  
 Im folgenden Beispiel werden alle unterschiedlichen Formate, die eine `select`\-Klausel möglicherweise annehmen kann, veranschaulicht.  Beachten Sie in jeder Abfrage die Beziehung zwischen der `select`\-Klausel und dem Typ der *Abfragevariablen* \(`studentQuery1`, `studentQuery2` usw.\).  
  
 [!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/csquerykeywords/Select.cs#9)]  
  
 Wie in `studentQuery8` im vorherigen Beispiel gezeigt, ist es manchmal erwünschenswert, dass die Elemente der zurückgegebenen Sequenz nur eine Teilmenge der Eigenschaften der Quellelemente enthalten.  Indem Sie die zurückgegebene Sequenz so klein wie möglich halten, können Sie die Speicherplatzanforderung senken und die Geschwindigkeit der Abfrageausführung erhöhen.  Erstellen Sie dazu einen anonymen Typ in der `select`\-Klausel, und verwenden Sie einen Objektinitialisierer, um sie mit den entsprechenden Eigenschaften aus dem Quellelement zu initialisieren.  Ein Beispiel dazu finden Sie unter [Objekt\- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Hinweise  
 Während der Kompilierung wird die `select`\-Klausel in einen Methodenaufruf des <xref:System.Linq.Enumerable.Select%2A>\-Standardabfrageoperators übersetzt.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [Abfrageschlüsselwörter \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [from\-Klausel](../../../csharp/language-reference/keywords/from-clause.md)   
 [partial \(Methode\) \(C\#\-Referenz\)](../../../csharp/language-reference/keywords/partial-method.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)