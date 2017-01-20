---
title: "Gewusst wie: Ausf&#252;hren einer Unterabfrage f&#252;r eine Gruppierungsoperation (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Gruppieren von LINQ-Abfragen [C#]"
  - "Gruppen [C#], LINQ-Abfrageausdrücke"
  - "Gruppen [LINQ in C#], Unterabfragen"
  - "Abfragen [LINQ in C#], Gruppieren"
  - "Abfragen [LINQ in C#], Unterabfragen"
  - "Abfrageausdrücke [LINQ in C#], Gruppieren"
  - "Abfrageausdrücke [LINQ in C#], Unterabfragen"
  - "Unterabfragen [C#]"
ms.assetid: 7b0805cd-53b4-429d-86b6-d37fb08f2c95
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Ausf&#252;hren einer Unterabfrage f&#252;r eine Gruppierungsoperation (C#-Programmierhandbuch)
Dieses Thema zeigt zwei verschiedene Wege, wie Sie eine Abfrage erstellen können, die die Quelldaten in Gruppen sortiert und dann eine Unterabfrage für jede einzelne Gruppe durchführt.  Die zugrunde liegende Technik in jedem Beispiel besteht darin, die Quellelemente zu gruppieren, indem Sie eine *Fortsetzung* mit dem Namen `newGroup` verwenden und dann eine neue Unterabfrage für `newGroup` erstellen.  Diese Unterabfrage wird für jede neue Gruppe ausgeführt, die von der äußeren Abfrage erstellt wird.  Beachten Sie, dass in diesem speziellen Beispiel die Endausgabe keine Gruppe ist, sondern eine flache Sequenz mit anonymen Typen.  
  
 Weitere Informationen zum Gruppieren finden Sie unter [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Weitere Informationen zu Fortsetzungen finden Sie unter [into](../../../csharp/language-reference/keywords/into.md).  Im folgenden Beispiel wird eine speicherinterne Datenstruktur als Datenquelle verwendet, die gleichen Prinzipien gelten jedoch auch für andere [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Datenquellen.  
  
## Beispiel  
 [!code-cs[csProgGuideLINQ#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/csLINQProgRef/csrefLINQHowTos.cs#23)]  
  
## Kompilieren des Codes  
 Dieses Beispiel enthält Verweise auf Objekte, die in der Beispielanwendung in [Gewusst wie: Abfragen einer Auflistung von Objekten](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) definiert werden.  Um diese Methode zu kompilieren und auszuführen, fügen Sie sie in die `StudentClass`\-Klasse dieser Anwendung ein, und fügen Sie ihr von der `Main`\-Methode einen Aufruf hinzu.  
  
 Wenn Sie diese Methode an Ihre eigene Anwendung anpassen, beachten Sie, dass LINQ [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] Version 3.5 benötigt und dass das Projekt einen Verweis auf System.Core.dll enthalten und eine Direktive für System.Linq verwenden muss.  LINQ\-to\-SQL\-, LINQ\-to\-XML\- und LINQ\-to\-DataSet\-Typen erfordern zusätzliche Usings und Verweise.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)