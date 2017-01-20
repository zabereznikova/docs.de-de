---
title: "Gewusst wie: Sortieren der Ergebnisse einer Join-Klausel (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "join-Klausel [C#]"
  - "Verknüpfungen [C#], Anordnen von Ergebnissen"
  - "Abfragen [LINQ in C#], Joins"
  - "Abfrageausdrücke [LINQ in C#], Joins"
ms.assetid: 83f36f16-2ba3-453f-8b9f-7d02b415610e
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Sortieren der Ergebnisse einer Join-Klausel (C#-Programmierhandbuch)
In diesem Beispiel wird gezeigt, wie die Ergebnisse einer Joinoperation sortiert werden.  Beachten Sie, dass die Sortierung nach dem Join ausgeführt wird.  Zwar ist es möglich, eine `orderby`\-Klausel mit einer oder mehreren Quellsequenzen vor dem Join zu verwenden, diese Vorgehensweise wird aber nicht empfohlen.  Diese Sortierung wird nach dem Join möglicherweise nicht bei allen [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Anbietern beibehalten.  
  
## Beispiel  
 Diese Abfrage erstellt einen Group Join und sortiert die Gruppen dann auf Basis des Kategorieelements, das sich noch im Gültigkeitsbereich befindet.  Im anonymen Typinitialisierer werden alle übereinstimmenden Elemente aus der Produktsequenz durch eine Unterabfrage sortiert.  
  
 [!code-cs[csProgGuideLINQ#81](../../../csharp/programming-guide/arrays/codesnippet/CSharp/csLINQProgRef/csRef30LangFeatures_2.cs#81)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]\-Projekt für .NET Framework, Version 3.5.  Standardmäßig weist das Projekt einen Verweis auf System.Core.dll und eine `using`\-Direktive für den System.Linq\-Namespace auf.  
  
-   Kopieren Sie den Code in Ihr Projekt.  
  
-   Drücken Sie F5, um das Programm zu kompilieren und auszuführen.  
  
-   Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [orderby\-Klausel](../../../csharp/language-reference/keywords/orderby-clause.md)   
 [join\-Klausel](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)