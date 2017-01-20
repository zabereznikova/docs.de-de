---
title: "Gewusst wie: Speichern der Ergebnisse einer Abfrage im Speicher (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "LINQ-Abfrageergebnisspeicher [LINQ in C#]"
  - "Abfrageausdrücke [LINQ in C#], Speichern der Ergebnisse"
ms.assetid: 7271597f-3523-4f7b-b088-1eeffe913b2d
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Speichern der Ergebnisse einer Abfrage im Speicher (C#-Programmierhandbuch)
Eine Abfrage ist im Grunde ein Satz von Anweisungen, wie Daten abgerufen und organisiert werden.  Um die Abfrage auszuführen, muss die <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>\-Methode aufgerufen werden.  Dieser Aufruf wird durchgeführt, wenn Sie eine `foreach`\-Schleife zum Durchlaufen der Elemente verwenden.  Um eine Abfrage auszuwerten und ihre Ergebnisse ohne eine `foreach`\-Schleife ausführen zu speichern auf, indem Sie eine der folgenden Methoden für die Abfragevariable:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Es wird empfohlen, das zurückgegebene Auflistungsobjekt beim Speichern der Abfrageergebnisse einer neuen Variable zuzuweisen, wie es im folgenden Beispiel dargestellt wird:  
  
## Beispiel  
 [!code-cs[csProgGuideLINQ#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/csLINQProgRef/csrefLINQHowTos.cs#25)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]\-Projekt für .NET Framework, Version 3.5.  Standardmäßig weist das Projekt einen Verweis auf System.Core.dll und eine `using`\-Direktive für den System.Linq\-Namespace auf.  
  
-   Kopieren Sie den Code in Ihr Projekt.  
  
-   Drücken Sie F5, um das Programm zu kompilieren und auszuführen.  
  
-   Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)